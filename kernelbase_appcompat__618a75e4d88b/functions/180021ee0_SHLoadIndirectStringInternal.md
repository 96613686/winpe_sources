# SHLoadIndirectStringInternal

- ea: `0x180021ee0`
- end: `0x1800225c6`
- name: `SHLoadIndirectStringInternal`
- size: `1766`
- prototype: `__int64 __fastcall(LPCWSTR lpString, PWSTR Buffer, ULONG cchBuffer)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting`

## callers

- `0x1800df110`

## callees

- `0x18001bba0`
- `0x18001c500`
- `0x18001cd34`
- `0x180020e60`
- `0x180020f20`
- `0x180021d10`
- `0x180021e08`
- `0x180021ee0`
- `0x180023c10`
- `0x180024ed0`
- `0x1800285f0`
- `0x1800378f0`
- `0x180037920`
- `0x1800391f0`
- `0x18004081c`
- `0x1800461b0`
- `0x180046520`
- `0x180046ac0`
- `0x180048f20`
- `0x1801379c4`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022203`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002226f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022203`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002226f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180022230`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800222cb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180022230`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800222cb`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueIsResourceReference` at `0x180022358`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueIsResourceReference` at `0x180022358`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x180022389`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x180022389`

## string_xrefs

- `0x1800220c9`: `shell32.dll`
- `0x1800224a2`: `shell32.dll`
- `0x1800224de`: `shell32.dll`
- `0x180199e1d`: `shell32.dll`

## pseudocode

```c

```
