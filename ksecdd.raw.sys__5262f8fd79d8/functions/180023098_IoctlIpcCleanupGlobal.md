# IoctlIpcCleanupGlobal

- ea: `0x180023098`
- end: `0x1800230c8`
- name: `IoctlIpcCleanupGlobal`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18002b078`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1800230a3`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1800230b6`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1800230a3`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1800230b6`

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
0x180023098  sub     rsp, 28h
0x18002309c  lea     rcx, stru_180019720; Lookaside
0x1800230a3  call    cs:__imp_ExDeleteLookasideListEx
0x1800230aa  nop     dword ptr [rax+rax+00h]
0x1800230af  lea     rcx, Lookaside; Lookaside
0x1800230b6  call    cs:__imp_ExDeleteLookasideListEx
0x1800230bd  nop     dword ptr [rax+rax+00h]
0x1800230c2  add     rsp, 28h
0x1800230c6  retn
```
