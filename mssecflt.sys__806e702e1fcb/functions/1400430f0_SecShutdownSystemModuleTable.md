# SecShutdownSystemModuleTable

- ea: `0x1400430f0`
- end: `0x14004314f`
- name: `SecShutdownSystemModuleTable`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140042918`

## callees

- `0x140009b80`
- `0x140042e88`
- `0x1400430f0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140043121`
- `ntoskrnl!ExDeleteResourceLite` at `0x140043121`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14004310e`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14004310e`

## pseudocode

```c
void SecShutdownSystemModuleTable()
{
  if ( SecSystemModuleTable )
  {
    SecCleanupSystemModuleContexts();
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)&SecSystemModuleTable[1].ActiveCount);
    ExDeleteResourceLite(SecSystemModuleTable);
    SecFreePool(SecSystemModuleTable, 0x546D6353u);
    SecSystemModuleTable = 0;
  }
}

```

## disassembly

```asm
0x1400430f0  sub     rsp, 28h
0x1400430f4  cmp     cs:SecSystemModuleTable, 0
0x1400430fc  jz      short loc_140043149
0x1400430fe  call    SecCleanupSystemModuleContexts
0x140043103  mov     rcx, cs:SecSystemModuleTable
0x14004310a  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14004310e  call    cs:__imp_ExDeletePagedLookasideList
0x140043115  nop     dword ptr [rax+rax+00h]
0x14004311a  mov     rcx, cs:SecSystemModuleTable; Resource
0x140043121  call    cs:__imp_ExDeleteResourceLite
0x140043128  nop     dword ptr [rax+rax+00h]
0x14004312d  mov     rcx, cs:SecSystemModuleTable; P
0x140043134  mov     edx, 546D6353h; Tag
0x140043139  call    SecFreePool
0x14004313e  mov     cs:SecSystemModuleTable, 0
0x140043149  add     rsp, 28h
0x14004314d  retn
```
