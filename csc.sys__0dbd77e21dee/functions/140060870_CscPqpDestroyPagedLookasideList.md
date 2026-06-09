# CscPqpDestroyPagedLookasideList

- ea: `0x140060870`
- end: `0x1400608a0`
- name: `CscPqpDestroyPagedLookasideList`
- size: `48`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14002cd0c`
- `0x14004635c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006088d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006088d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140060879`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140060879`

## pseudocode

```c
void __fastcall CscPqpDestroyPagedLookasideList(struct _PAGED_LOOKASIDE_LIST *P)
{
  ExDeletePagedLookasideList(P);
  ExFreePoolWithTag(P, 0x24407343u);
}

```

## disassembly

```asm
0x140060870  push    rbx
0x140060872  sub     rsp, 20h
0x140060876  mov     rbx, rcx
0x140060879  call    cs:__imp_ExDeletePagedLookasideList
0x140060880  nop     dword ptr [rax+rax+00h]
0x140060885  mov     edx, 24407343h; Tag
0x14006088a  mov     rcx, rbx; P
0x14006088d  call    cs:__imp_ExFreePoolWithTag
0x140060894  nop     dword ptr [rax+rax+00h]
0x140060899  add     rsp, 20h
0x14006089d  pop     rbx
0x14006089e  retn
```
