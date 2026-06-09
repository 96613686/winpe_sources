# CClientUtilsWin32::GetMonitorDimensions(HMONITOR__ *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)

- ea: `0x1801a640c`
- end: `0x1801a6a0a`
- name: `?GetMonitorDimensions@CClientUtilsWin32@@SAJPEAUHMONITOR__@@PEAK111111@Z`
- size: `1534`
- prototype: `__int64 __usercall@<rax>(HMONITOR@<rcx>, unsigned int *@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1801a6a10`
- `0x1801a6d28`
- `0x1802f9680`

## callees

- `0x18001e170`
- `0x18002a334`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1801566a0`
- `0x1801568d0`
- `0x1801a640c`
- `0x1801a7bac`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x1801a6939`
- `GDI32!GetDeviceCaps` at `0x1801a697b`
- `GDI32!GetDeviceCaps` at `0x1801a6990`
- `GDI32!GetDeviceCaps` at `0x1801a69ae`
- `GDI32!GetDeviceCaps` at `0x1801a69c3`
- `GDI32!GetDeviceCaps` at `0x1801a6939`
- `GDI32!GetDeviceCaps` at `0x1801a697b`
- `GDI32!GetDeviceCaps` at `0x1801a6990`
- `GDI32!GetDeviceCaps` at `0x1801a69ae`
- `GDI32!GetDeviceCaps` at `0x1801a69c3`
- `GDI32!DeleteDC` at `0x1801a69df`
- `GDI32!DeleteDC` at `0x1801a69df`
- `GDI32!CreateDCW` at `0x1801a66d5`
- `GDI32!CreateDCW` at `0x1801a66d5`
- `USER32!EnumDisplaySettingsW` at `0x1801a6747`
- `USER32!EnumDisplaySettingsW` at `0x1801a6747`
- `USER32!GetMonitorInfoW` at `0x1801a669a`
- `USER32!GetMonitorInfoW` at `0x1801a669a`

## pseudocode

```c

```
