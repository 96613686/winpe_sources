# CAutoReconnectDlg::UpdateConnectionAttempts(ulong,ulong,int)

- ea: `0x180510da8`
- end: `0x180510f26`
- name: `?UpdateConnectionAttempts@CAutoReconnectDlg@@AEAAXKKH@Z`
- size: `382`
- prototype: `void __fastcall(CAutoReconnectDlg *__hidden this, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18050fb08`
- `0x18050fed0`

## callees

- `0x180039ce4`
- `0x1800e9b1c`
- `0x1801aa66c`
- `0x18050f28c`
- `0x180510da8`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180510e44`
- `KERNEL32!GetLastError` at `0x180510e44`
- `KERNEL32!LocalFree` at `0x180510e1c`
- `KERNEL32!LocalFree` at `0x180510e1c`
- `USER32!GetWindowRect` at `0x180510ec8`
- `USER32!GetWindowRect` at `0x180510ec8`
- `USER32!MapWindowPoints` at `0x180510ee3`
- `USER32!MapWindowPoints` at `0x180510ee3`
- `USER32!UpdateWindow` at `0x180510f02`
- `USER32!UpdateWindow` at `0x180510f02`
- `USER32!InvalidateRect` at `0x180510ef8`
- `USER32!InvalidateRect` at `0x180510ef8`
- `USER32!SetDlgItemTextW` at `0x180510e13`
- `USER32!SetDlgItemTextW` at `0x180510ead`
- `USER32!SetDlgItemTextW` at `0x180510e13`
- `USER32!SetDlgItemTextW` at `0x180510ead`
- `USER32!GetDlgItem` at `0x180510ddc`
- `USER32!GetDlgItem` at `0x180510ddc`

## pseudocode

```c

```
