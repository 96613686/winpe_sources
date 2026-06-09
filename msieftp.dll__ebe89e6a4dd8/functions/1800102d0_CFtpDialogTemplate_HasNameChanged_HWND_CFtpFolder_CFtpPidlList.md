# CFtpDialogTemplate::HasNameChanged(HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x1800102d0`
- end: `0x180010388`
- name: `?HasNameChanged@CFtpDialogTemplate@@QEAAHPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `184`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e510`

## callees

- `0x180002240`
- `0x18001027c`
- `0x1800102d0`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x180010355`
- `SHLWAPI!StrCmpW` at `0x180010355`
- `USER32!GetDlgItem` at `0x180010302`
- `USER32!GetDlgItem` at `0x18001032e`
- `USER32!GetDlgItem` at `0x180010302`
- `USER32!GetDlgItem` at `0x18001032e`
- `USER32!GetWindowTextW` at `0x180010342`
- `USER32!GetWindowTextW` at `0x180010342`
- `USER32!IsWindowVisible` at `0x18001030b`
- `USER32!IsWindowVisible` at `0x18001030b`

## pseudocode

```c

```
