# WfpSysTimerModuleShutdown

- ea: `0x14006c480`
- end: `0x14006c4e1`
- name: `WfpSysTimerModuleShutdown`
- size: `97`
- prototype: `__int64 __fastcall(PNPAGED_LOOKASIDE_LIST Lookaside)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140065f80`

## callees

- `0x14006c480`
- `0x14006c5f0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14006c49f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c49f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006c4ce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006c4ce`

## pseudocode

```c
void __fastcall WfpSysTimerModuleShutdown(PNPAGED_LOOKASIDE_LIST Lookaside)
{
  void *v2; // rcx

  *((_DWORD *)&Lookaside[1].L.SingleListHead + 2) = 1;
  v2 = *(void **)&Lookaside[1].L.Depth;
  if ( v2 )
    ObfDereferenceObject(v2);
  while ( HIDWORD(Lookaside[1].L.SingleListHead.Next) )
    WfpTimerDelayExecution();
  while ( LODWORD(Lookaside[1].L.ListHead.Alignment) )
    WfpTimerDelayExecution();
  ExDeleteNPagedLookasideList(Lookaside);
}

```

## disassembly

```asm
0x14006c480  push    rbx
0x14006c482  sub     rsp, 20h
0x14006c486  mov     rbx, rcx
0x14006c489  mov     dword ptr [rcx+88h], 1
0x14006c493  mov     rcx, [rcx+90h]; Object
0x14006c49a  test    rcx, rcx
0x14006c49d  jz      short loc_14006C4B2
0x14006c49f  call    cs:__imp_ObfDereferenceObject
0x14006c4a6  nop     dword ptr [rax+rax+00h]
0x14006c4ab  jmp     short loc_14006C4B2
0x14006c4ad  call    WfpTimerDelayExecution
0x14006c4b2  cmp     dword ptr [rbx+84h], 0
0x14006c4b9  ja      short loc_14006C4AD
0x14006c4bb  jmp     short loc_14006C4C2
0x14006c4bd  call    WfpTimerDelayExecution
0x14006c4c2  cmp     dword ptr [rbx+80h], 0
0x14006c4c9  ja      short loc_14006C4BD
0x14006c4cb  mov     rcx, rbx; Lookaside
0x14006c4ce  call    cs:__imp_ExDeleteNPagedLookasideList
0x14006c4d5  nop     dword ptr [rax+rax+00h]
0x14006c4da  add     rsp, 20h
0x14006c4de  pop     rbx
0x14006c4df  retn
```
