# Criminal Risk Assessment Request - XLSForm

## Overview

This is an ODK/KoboToolbox XLSForm for the **Criminal Risk Assessment Request** used by Manitoba Families - Criminal Risk Assessment Unit, Child Protection Branch.

The form captures personal identification, consent, and agency submission details required to conduct a criminal risk assessment through the Winnipeg Police Service (WPS) and RCMP.

---

## Form Structure

### Sheet: survey

The survey sheet contains all form questions, organized into two pages:

#### Page 1 - Subject Information
- **Consent section** - Date, signature, and unconsented option with witness name
- **Personal details** - First name, second name, last name, date of birth, sex
- **Additional identifiers** - Other names used, current address, phone, place of birth
- **Identification** - Two pieces of ID required (MB Driver's Licence preferred)
- **Calculations** - Full name concatenation and age calculation

#### Page 2 - Agency Submission
- **Agency details** - Submitting agency name, reason for assessment, assigned worker
- **Designate information** - Name, phone, email, fax
- **Request date** - Defaults to today's date

### Sheet: choices

Contains option lists used in the survey:

| List Name | Options |
|-----------|---------|
| `yes_no` | Yes, No |
| `sex_list` | Male, Female |
| `id_type_list` | Birth Certificate, Social Insurance Card, Manitoba Health Card, Treaty Card, MB Driver's Licence with Photo, Other |
| `reason_list` | With or Without Consent: Child Protection Concerns, Must have consent: Place of Safety, Must have consent: Kinship or Customary Care Agreement |

### Sheet: settings

| Field | Value |
|-------|-------|
| form_title | Criminal Risk Assessment Request |
| form_id | criminal_risk_assessment_request |
| version | 2025010902 |
| default_language | English (en) |
| style | pages |

---

## Column Reference (survey sheet)

| Column | Description |
|--------|-------------|
| type | Question type (text, date, image, note, calculate, select_one, etc.) |
| name | Unique variable name |
| label | Display label shown to user |
| required | Whether the field is mandatory (yes/no) |
| required_message | Custom message shown when required field is empty |
| appearance | Visual presentation (field-list, signature, numbers, minimal) |
| hint | Helper text displayed below the field |
| relevant | Conditional logic - show field only when expression is true |
| default | Default value for the field |
| constraint | Validation rule (e.g., date must not be in future) |
| constraint_message | Custom message shown when constraint fails |
| calculation | Expression to compute a value |
| repeat_count | Number of repeats (unused in this form) |
| read_only | Whether the field is read-only (yes/no) |

---

## Key Features

- **Two-page layout** using ODK `field-list` appearance and `pages` style
- **Conditional visibility** - Fields appear/disappear based on answers (e.g., witness name shows only when unconsented is "no")
- **Read-only computed fields** - Full name and age are auto-calculated
- **Email validation** - Regex constraint on designate email field
- **Date validation** - Date of birth cannot be in the future
- **Signature capture** - Uses `signature` appearance for patient signature


