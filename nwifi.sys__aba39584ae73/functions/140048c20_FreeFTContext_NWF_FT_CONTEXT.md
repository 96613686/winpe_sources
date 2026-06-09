# FreeFTContext(NWF_FT_CONTEXT * *)

- ea: `0x140048c20`
- end: `0x140048cbf`
- name: `?FreeFTContext@@YAXPEAPEAUNWF_FT_CONTEXT@@@Z`
- size: `159`
- prototype: `void __fastcall(struct NWF_FT_CONTEXT **)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004215c`
- `0x140042a1c`
- `0x140046610`
- `0x140046f4c`
- `0x1400474b4`
- `0x140047794`

## callees

- `0x140048c20`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048c50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048c8f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048c50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048c8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ca0`

## pseudocode

```c
void __fastcall FreeFTContext(struct NWF_FT_CONTEXT **a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  unsigned int *p_uResponseIEsLength; // rcx

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
      p_uResponseIEsLength = &(*a1)[-1].uResponseIEsLength;
      if ( *(_QWORD *)p_uResponseIEsLength )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_uResponseIEsLength, &(*a1)[-1].uResponseIEsLength);
      else
        ExFreePoolWithTag(p_uResponseIEsLength, p_uResponseIEsLength[2]);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x140048c20  mov     [rsp+arg_0], rbx
0x140048c25  push    rdi
0x140048c26  sub     rsp, 20h
0x140048c2a  mov     rdi, [rcx]
0x140048c2d  mov     rbx, rcx
0x140048c30  test    rdi, rdi
0x140048c33  jz      short loc_140048CB3
0x140048c35  mov     rcx, [rdi+58h]
0x140048c39  test    rcx, rcx
0x140048c3c  jz      short loc_140048C75
0x140048c3e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048c42  mov     rax, [rcx]
0x140048c45  test    rax, rax
0x140048c48  jz      short loc_140048C5E
0x140048c4a  mov     rdx, rcx; Entry
0x140048c4d  mov     rcx, rax; Lookaside
0x140048c50  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048c57  nop     dword ptr [rax+rax+00h]
0x140048c5c  jmp     short loc_140048C6D
0x140048c5e  mov     edx, [rcx+8]; Tag
0x140048c61  call    cs:__imp_ExFreePoolWithTag
0x140048c68  nop     dword ptr [rax+rax+00h]
0x140048c6d  mov     qword ptr [rdi+58h], 0
0x140048c75  mov     rcx, [rbx]
0x140048c78  test    rcx, rcx
0x140048c7b  jz      short loc_140048CB3
0x140048c7d  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048c81  mov     rax, [rcx]
0x140048c84  test    rax, rax
0x140048c87  jz      short loc_140048C9D
0x140048c89  mov     rdx, rcx; Entry
0x140048c8c  mov     rcx, rax; Lookaside
0x140048c8f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048c96  nop     dword ptr [rax+rax+00h]
0x140048c9b  jmp     short loc_140048CAC
0x140048c9d  mov     edx, [rcx+8]; Tag
0x140048ca0  call    cs:__imp_ExFreePoolWithTag
0x140048ca7  nop     dword ptr [rax+rax+00h]
0x140048cac  mov     qword ptr [rbx], 0
0x140048cb3  mov     rbx, [rsp+28h+arg_0]
0x140048cb8  add     rsp, 20h
0x140048cbc  pop     rdi
0x140048cbd  retn
```
