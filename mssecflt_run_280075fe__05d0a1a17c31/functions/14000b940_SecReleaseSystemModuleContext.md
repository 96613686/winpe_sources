# SecReleaseSystemModuleContext

- ea: `0x14000b940`
- end: `0x14000ba24`
- name: `SecReleaseSystemModuleContext`
- size: `228`
- prototype: `__int64 __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b598`
- `0x14000bb5c`
- `0x14000bbbc`
- `0x140040f3c`
- `0x1400412c4`
- `0x14004184c`
- `0x140041cec`
- `0x140042f84`

## callees

- `0x1400061dc`
- `0x140009b80`
- `0x14000b940`
- `0x140011610`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000b959`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000b959`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000ba18`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000b9f6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000b9f6`
- `ntoskrnl!ExQueryDepthSList` at `0x14000b9ca`
- `ntoskrnl!ExQueryDepthSList` at `0x14000b9ca`

## pseudocode

```c

```
