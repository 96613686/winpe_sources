# FreeFTContext(NWF_FT_CONTEXT * *)

- ea: `0x140047998`
- end: `0x140047a37`
- name: `?FreeFTContext@@YAXPEAPEAUNWF_FT_CONTEXT@@@Z`
- size: `159`
- prototype: `void __fastcall(struct NWF_FT_CONTEXT **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400416c0`
- `0x140041f8c`
- `0x140045a90`
- `0x1400463a8`
- `0x140046910`

## callees

- `0x140047998`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400479c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047a07`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400479c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047a07`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400479d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400479d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a18`

## pseudocode

```c
void __fastcall FreeFTContext(struct NWF_FT_CONTEXT **a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  ULONG *p_pReassembledFTEIE; // rcx

  v1 = (__int64)*a1;
  if ( *a1 )
  {
    v3 = *(_QWORD *)(v1 + 88);
    if ( v3 )
    {
      v4 = v3 - 16;
      if ( *(_QWORD *)v4 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v4, (PVOID)v4);
      else
        ExFreePoolWithTag((PVOID)v4, *(_DWORD *)(v4 + 8));
      *(_QWORD *)(v1 + 88) = 0;
    }
    if ( *a1 )
    {
      p_pReassembledFTEIE = (ULONG *)&(*a1)[-1].pReassembledFTEIE;
      if ( *(_QWORD *)p_pReassembledFTEIE )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_pReassembledFTEIE, &(*a1)[-1].pReassembledFTEIE);
      else
        ExFreePoolWithTag(p_pReassembledFTEIE, p_pReassembledFTEIE[2]);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x140047998  mov     [rsp+arg_0], rbx
0x14004799d  push    rdi
0x14004799e  sub     rsp, 20h
0x1400479a2  mov     rdi, [rcx]
0x1400479a5  mov     rbx, rcx
0x1400479a8  test    rdi, rdi
0x1400479ab  jz      short loc_140047A2B
0x1400479ad  mov     rcx, [rdi+58h]
0x1400479b1  test    rcx, rcx
0x1400479b4  jz      short loc_1400479ED
0x1400479b6  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400479ba  mov     rax, [rcx]
0x1400479bd  test    rax, rax
0x1400479c0  jz      short loc_1400479D6
0x1400479c2  mov     rdx, rcx; Entry
0x1400479c5  mov     rcx, rax; Lookaside
0x1400479c8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400479cf  nop     dword ptr [rax+rax+00h]
0x1400479d4  jmp     short loc_1400479E5
0x1400479d6  mov     edx, [rcx+8]; Tag
0x1400479d9  call    cs:__imp_ExFreePoolWithTag
0x1400479e0  nop     dword ptr [rax+rax+00h]
0x1400479e5  mov     qword ptr [rdi+58h], 0
0x1400479ed  mov     rcx, [rbx]
0x1400479f0  test    rcx, rcx
0x1400479f3  jz      short loc_140047A2B
0x1400479f5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400479f9  mov     rax, [rcx]
0x1400479fc  test    rax, rax
0x1400479ff  jz      short loc_140047A15
0x140047a01  mov     rdx, rcx; Entry
0x140047a04  mov     rcx, rax; Lookaside
0x140047a07  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047a0e  nop     dword ptr [rax+rax+00h]
0x140047a13  jmp     short loc_140047A24
0x140047a15  mov     edx, [rcx+8]; Tag
0x140047a18  call    cs:__imp_ExFreePoolWithTag
0x140047a1f  nop     dword ptr [rax+rax+00h]
0x140047a24  mov     qword ptr [rbx], 0
0x140047a2b  mov     rbx, [rsp+28h+arg_0]
0x140047a30  add     rsp, 20h
0x140047a34  pop     rdi
0x140047a35  retn
```
