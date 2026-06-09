# CSrApiViewerAxHost::Initialize(HINSTANCE__ *,HINSTANCE__ *,SHADOW_CONTROL_REQUEST,SHADOW_PERMISSION_REQUEST,ushort const *,ushort const *,ulong,CSrApiViewerAxHost::EPromptForCredsDisposition)

- ea: `0x1400b0128`
- end: `0x1400b046f`
- name: `?Initialize@CSrApiViewerAxHost@@AEAAJPEAUHINSTANCE__@@0W4SHADOW_CONTROL_REQUEST@@W4SHADOW_PERMISSION_REQUEST@@PEBG3KW4EPromptForCredsDisposition@1@@Z`
- size: `839`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, OLECHAR *psz, OLECHAR *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400b2d10`

## callees

- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400b0128`
- `0x140113390`

## import_xrefs

- `USER32!LoadCursorW` at `0x1400b03a0`
- `USER32!LoadCursorW` at `0x1400b03a0`
- `USER32!RegisterClassExW` at `0x1400b03c9`
- `USER32!RegisterClassExW` at `0x1400b03c9`
- `KERNEL32!GetComputerNameW` at `0x1400b01da`
- `KERNEL32!GetComputerNameW` at `0x1400b01da`
- `KERNEL32!GetLastError` at `0x1400b01e4`
- `KERNEL32!GetLastError` at `0x1400b03d4`
- `KERNEL32!GetLastError` at `0x1400b01e4`
- `KERNEL32!GetLastError` at `0x1400b03d4`
- `GDI32!GetStockObject` at `0x1400b03af`
- `GDI32!GetStockObject` at `0x1400b03af`
- `OLEAUT32!__imp_SysAllocString` at `0x1400b0257`
- `OLEAUT32!__imp_SysAllocString` at `0x1400b02c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400b0257`
- `OLEAUT32!__imp_SysAllocString` at `0x1400b02c1`

## pseudocode

```c

```
