# RealtimeProtection::DlpInjection::InjectEnforcementDll(PPID const &,wchar_t const * const)

- ea: `0x1800af07c`
- end: `0x1800af508`
- name: `?InjectEnforcementDll@DlpInjection@RealtimeProtection@@YAJAEBUPPID@@QEB_W@Z`
- size: `1164`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpInjection *__hidden this, const struct PPID *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800af030`

## callees

- `0x18001b7bc`
- `0x18001db28`
- `0x180046d10`
- `0x18007eab0`
- `0x1800809d0`
- `0x1800a1b90`
- `0x1800a99d4`
- `0x1800af07c`
- `0x1800b51d0`
- `0x1800bc158`
- `0x1800c8d30`
- `0x1801018c4`
- `0x18010cb40`
- `0x18020bfd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800af20e`
- `KERNEL32!CloseHandle` at `0x1800af28a`
- `KERNEL32!CloseHandle` at `0x1800af2b9`
- `KERNEL32!CloseHandle` at `0x1800af34d`
- `KERNEL32!CloseHandle` at `0x1800af45c`
- `KERNEL32!CloseHandle` at `0x1800af491`
- `KERNEL32!CloseHandle` at `0x1800af20e`
- `KERNEL32!CloseHandle` at `0x1800af28a`
- `KERNEL32!CloseHandle` at `0x1800af2b9`
- `KERNEL32!CloseHandle` at `0x1800af34d`
- `KERNEL32!CloseHandle` at `0x1800af45c`
- `KERNEL32!CloseHandle` at `0x1800af491`

## string_xrefs

- `0x1800af3b1`: `MpDetours.dll`

## pseudocode

```c

```
