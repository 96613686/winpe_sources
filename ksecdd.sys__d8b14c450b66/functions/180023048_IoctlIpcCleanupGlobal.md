# IoctlIpcCleanupGlobal

- ea: `0x180023048`
- end: `0x180023078`
- name: `IoctlIpcCleanupGlobal`
- size: `48`
- prototype: `void()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18002b078`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x180023053`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x180023066`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x180023053`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x180023066`

## pseudocode

```c
void IoctlIpcCleanupGlobal()
{
  ExDeleteLookasideListEx(&stru_180019720);
  ExDeleteLookasideListEx(&Lookaside);
}

```

## disassembly

```asm
0x180023048  sub     rsp, 28h
0x18002304c  lea     rcx, stru_180019720; Lookaside
0x180023053  call    cs:__imp_ExDeleteLookasideListEx
0x18002305a  nop     dword ptr [rax+rax+00h]
0x18002305f  lea     rcx, Lookaside; Lookaside
0x180023066  call    cs:__imp_ExDeleteLookasideListEx
0x18002306d  nop     dword ptr [rax+rax+00h]
0x180023072  add     rsp, 28h
0x180023076  retn
```
