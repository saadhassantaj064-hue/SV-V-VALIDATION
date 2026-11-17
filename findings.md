# Findings

Students: A = Saad Hassan Taj (131, Section A), B = Ahmed Ali (Section A)

## Where our answers differed

| Item | A | B | Agreed answer | Reason |
|------|---|---|---------------|--------|
| C-13 | No | No ? | No | R-01 is online only, no option for elderly patients |
| C-14 | No | No ? | No | "user-friendly" has no measurable target |
| C-15 | Yes | No ? | Yes | R-11 states the limit of 3, but "active" is a separate problem (F-09) |
| C-16 | No | Yes ? | No | R-07 does not say the slot can be booked again |
| C-12 | No ? | No | No | R-10 has no emergency walk-in rule |

## Real problems in the SRS

| ID | Requirement | Problem | Why it matters | Fix |
|----|-------------|---------|----------------|-----|
| F-01 | R-02 | "quickly" has no number or unit | Cannot be tested, Monday mornings are busy | e.g. "Booking confirmation within 2 seconds for 95% of requests" |
| F-02 | R-04, R-05 | R-04 says fixed 15 minutes, R-05 says 10 to 30 minutes | Contradiction | Make 15 minutes the default, doctors may change it to 10 to 30 |
| F-03 | R-06 | No time and no channel for reminders | Patients forget appointments, costs money | e.g. "SMS 24 hours and 2 hours before" |
| F-04 | R-07 | Three actions in one requirement, "at any time" is unclear, patient not notified, slot release not stated | Not testable, slot may stay empty | Split into separate requirements, state cancellation limit and slot release |
| F-05 | R-08 | "user-friendly for all age groups" is not measurable | Elderly patients may be left out | e.g. "90% of patients over 65 book in under 5 minutes in a test" |
| F-06 | R-09 | "securely" has no roles, no encryption, no access log, no retention | Medical data is private | List roles per record, require access log and retention period |
| F-07 | R-10 | No rule for emergency walk-ins | Emergencies must not be left out | Add emergency priority booking |
| F-08 | R-12 | "normal working hours" is not defined | Cannot test availability | State days, hours and allowed downtime |
| F-09 | R-11 | "active appointment" is not defined | Same limit can be read in two ways | Define active as booked and not yet completed or cancelled |
| F-10 | R-13 | Payments and "clinic policy" are never described | Requirement cannot be built or tested | Define the payment rules or remove it |
| F-11 | R-03 | Does not say how double bookings are stopped, nothing about simultaneous bookings | Double booking is the manager's top worry | Add rule: one slot is given to only one patient, even with simultaneous requests |
| F-12 | Missing | No performance target for Monday mornings | Busiest time | State number of simultaneous users and response time |
| F-13 | Missing | Elderly patients without internet have no way to book | They are left out | Allow booking by phone through the receptionist |
| F-14 | Missing | No requirements for the clinic administrator | One user role has no needs covered | Add user and doctor management, reports |
| F-15 | Missing | Doctors cannot mark leave or breaks | Patients could book when the doctor is absent | Add doctor unavailability |
| F-16 | Missing | No requirement for the data protection officer | Privacy duties not covered | Add access log, data retention and export |

## Checklist improvements for v0.2

- C-15 should be split: one item for the limit and one for the meaning of "active".
- Add an item about rescheduling and about notifying the patient on cancellation.
- Too many items had the answer No because the SRS is short, so add a few more items that can be answered Yes or N/A.
