# DestroyTimerQ

- ea: `0x140044864`
- end: `0x140044883`
- name: `DestroyTimerQ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14002cbc4`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004486f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004486f`

## pseudocode

```c
__int64 DestroyTimerQ()
{
  ExDeleteNPagedLookasideList(&Lookaside);
  return 0;
}

```

## disassembly

```asm
0x140044864  sub     rsp, 28h
0x140044868  lea     rcx, Lookaside; Lookaside
0x14004486f  call    cs:__imp_ExDeleteNPagedLookasideList
0x140044876  nop     dword ptr [rax+rax+00h]
0x14004487b  xor     eax, eax
0x14004487d  add     rsp, 28h
0x140044881  retn
```
