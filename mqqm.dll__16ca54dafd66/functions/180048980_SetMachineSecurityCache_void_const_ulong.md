# SetMachineSecurityCache(void const *,ulong)

- ea: `0x180048980`
- end: `0x180048a06`
- name: `?SetMachineSecurityCache@@YAJPEBXK@Z`
- size: `134`
- prototype: `__int64 __fastcall(const void *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800193e8`
- `0x1800386e0`
- `0x180047070`
- `0x18005e1c4`

## callees

- `0x180009924`
- `0x18002c6c8`
- `0x180048980`

## import_xrefs

- `msvcrt!free` at `0x1800489ca`
- `msvcrt!free` at `0x1800489ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800489d8`
- `KERNEL32!LeaveCriticalSection` at `0x1800489d8`
- `mqsec!SetFalconKeyValue` at `0x1800489a4`
- `mqsec!SetFalconKeyValue` at `0x1800489a4`

## string_xrefs

- `0x18004899d`: `DsSecurityCache`

## pseudocode

```c

```
