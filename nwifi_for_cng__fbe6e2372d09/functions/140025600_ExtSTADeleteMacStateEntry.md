# ExtSTADeleteMacStateEntry

- ea: `0x140025600`
- end: `0x1400256fc`
- name: `ExtSTADeleteMacStateEntry`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140025590`
- `0x140060758`
- `0x140063fa0`

## callees

- `0x140025600`
- `0x140025704`
- `0x140060814`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025695`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400256cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025695`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400256cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256e7`

## pseudocode

```c
void __fastcall ExtSTADeleteMacStateEntry(__int64 a1, struct DOT11_MAC_STATE_ENTRY *a2)
{
  _QWORD *pvAssocEntry; // rbx
  unsigned int v4; // edx
  _QWORD *v5; // rcx
  void **v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  struct DOT11_MAC_STATE_ENTRY *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = a2;
  pvAssocEntry = a2->pvAssocEntry;
  a2->pvAssocEntry = 0;
  ExtSTADeleteDataPort((struct EXTSTA_VELAN *)a1, a2);
  if ( pvAssocEntry )
  {
    pvAssocEntry[2] = 0;
    Dot11DecObjCnt(&v9, v4);
    v5 = (_QWORD *)*pvAssocEntry;
    if ( *(_QWORD **)(*pvAssocEntry + 8LL) != pvAssocEntry || (v6 = (void **)pvAssocEntry[1], *v6 != pvAssocEntry) )
      __fastfail(3u);
    *v6 = v5;
    v5[1] = v6;
    if ( *((_DWORD *)pvAssocEntry + 6) == 3 )
    {
      --*(_DWORD *)(a1 + 332);
      *(_DWORD *)(a1 + 1552) &= ~4u;
    }
    else
    {
      --*(_DWORD *)(a1 + 328);
    }
    v7 = pvAssocEntry[6];
    if ( v7 )
    {
      v8 = v7 - 16;
      if ( *(_QWORD *)v8 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
      else
        ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
      pvAssocEntry[6] = 0;
    }
    if ( *(pvAssocEntry - 2) )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(pvAssocEntry - 2), pvAssocEntry - 2);
    else
      ExFreePoolWithTag(pvAssocEntry - 2, *((_DWORD *)pvAssocEntry - 2));
  }
}

```

## disassembly

```asm
0x140025600  mov     [rsp+arg_0], rbx
0x140025605  mov     [rsp+arg_8], rdx
0x14002560a  push    rdi
0x14002560b  sub     rsp, 20h
0x14002560f  mov     rbx, [rdx+40h]
0x140025613  mov     rdi, rcx
0x140025616  mov     qword ptr [rdx+40h], 0
0x14002561e  call    ExtSTADeleteDataPort
0x140025623  test    rbx, rbx
0x140025626  jz      loc_1400256D8
0x14002562c  lea     rcx, [rsp+28h+arg_8]; struct DOT11_MAC_STATE_ENTRY **
0x140025631  mov     qword ptr [rbx+10h], 0
0x140025639  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x14002563e  mov     rcx, [rbx]
0x140025641  cmp     [rcx+8], rbx
0x140025645  jnz     loc_1400256F5
0x14002564b  mov     rax, [rbx+8]
0x14002564f  cmp     [rax], rbx
0x140025652  jnz     loc_1400256F5
0x140025658  mov     [rax], rcx
0x14002565b  mov     [rcx+8], rax
0x14002565f  cmp     dword ptr [rbx+18h], 3
0x140025663  jnz     short loc_140025674
0x140025665  dec     dword ptr [rdi+14Ch]
0x14002566b  and     dword ptr [rdi+610h], 0FFFFFFFBh
0x140025672  jmp     short loc_14002567A
0x140025674  dec     dword ptr [rdi+148h]
0x14002567a  mov     rcx, [rbx+30h]
0x14002567e  test    rcx, rcx
0x140025681  jz      short loc_1400256BA
0x140025683  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140025687  mov     rax, [rcx]
0x14002568a  test    rax, rax
0x14002568d  jz      short loc_1400256A3
0x14002568f  mov     rdx, rcx; Entry
0x140025692  mov     rcx, rax; Lookaside
0x140025695  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002569c  nop     dword ptr [rax+rax+00h]
0x1400256a1  jmp     short loc_1400256B2
0x1400256a3  mov     edx, [rcx+8]; Tag
0x1400256a6  call    cs:__imp_ExFreePoolWithTag
0x1400256ad  nop     dword ptr [rax+rax+00h]
0x1400256b2  mov     qword ptr [rbx+30h], 0
0x1400256ba  lea     rcx, [rbx-10h]; P
0x1400256be  mov     rax, [rcx]
0x1400256c1  test    rax, rax
0x1400256c4  jz      short loc_1400256E4
0x1400256c6  mov     rdx, rcx; Entry
0x1400256c9  mov     rcx, rax; Lookaside
0x1400256cc  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400256d3  nop     dword ptr [rax+rax+00h]
0x1400256d8  mov     rbx, [rsp+28h+arg_0]
0x1400256dd  add     rsp, 20h
0x1400256e1  pop     rdi
0x1400256e2  retn
0x1400256e4  mov     edx, [rcx+8]; Tag
0x1400256e7  call    cs:__imp_ExFreePoolWithTag
0x1400256ee  nop     dword ptr [rax+rax+00h]
0x1400256f3  jmp     short loc_1400256D8
0x1400256f5  mov     ecx, 3
0x1400256fa  int     29h; Win8: RtlFailFast(ecx)
```
