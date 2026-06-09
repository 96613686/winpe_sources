# ExtSTADeleteMacStateEntry

- ea: `0x14002537c`
- end: `0x140025478`
- name: `ExtSTADeleteMacStateEntry`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002530c`
- `0x14005ef28`
- `0x140062770`

## callees

- `0x14002537c`
- `0x140025480`
- `0x14005efe4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025411`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025448`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025411`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025448`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025422`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025463`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025422`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025463`

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
0x14002537c  mov     [rsp+arg_0], rbx
0x140025381  mov     [rsp+arg_8], rdx
0x140025386  push    rdi
0x140025387  sub     rsp, 20h
0x14002538b  mov     rbx, [rdx+40h]
0x14002538f  mov     rdi, rcx
0x140025392  mov     qword ptr [rdx+40h], 0
0x14002539a  call    ExtSTADeleteDataPort
0x14002539f  test    rbx, rbx
0x1400253a2  jz      loc_140025454
0x1400253a8  lea     rcx, [rsp+28h+arg_8]; struct DOT11_MAC_STATE_ENTRY **
0x1400253ad  mov     qword ptr [rbx+10h], 0
0x1400253b5  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x1400253ba  mov     rcx, [rbx]
0x1400253bd  cmp     [rcx+8], rbx
0x1400253c1  jnz     loc_140025471
0x1400253c7  mov     rax, [rbx+8]
0x1400253cb  cmp     [rax], rbx
0x1400253ce  jnz     loc_140025471
0x1400253d4  mov     [rax], rcx
0x1400253d7  mov     [rcx+8], rax
0x1400253db  cmp     dword ptr [rbx+18h], 3
0x1400253df  jnz     short loc_1400253F0
0x1400253e1  dec     dword ptr [rdi+14Ch]
0x1400253e7  and     dword ptr [rdi+610h], 0FFFFFFFBh
0x1400253ee  jmp     short loc_1400253F6
0x1400253f0  dec     dword ptr [rdi+148h]
0x1400253f6  mov     rcx, [rbx+30h]
0x1400253fa  test    rcx, rcx
0x1400253fd  jz      short loc_140025436
0x1400253ff  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140025403  mov     rax, [rcx]
0x140025406  test    rax, rax
0x140025409  jz      short loc_14002541F
0x14002540b  mov     rdx, rcx; Entry
0x14002540e  mov     rcx, rax; Lookaside
0x140025411  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025418  nop     dword ptr [rax+rax+00h]
0x14002541d  jmp     short loc_14002542E
0x14002541f  mov     edx, [rcx+8]; Tag
0x140025422  call    cs:__imp_ExFreePoolWithTag
0x140025429  nop     dword ptr [rax+rax+00h]
0x14002542e  mov     qword ptr [rbx+30h], 0
0x140025436  lea     rcx, [rbx-10h]; P
0x14002543a  mov     rax, [rcx]
0x14002543d  test    rax, rax
0x140025440  jz      short loc_140025460
0x140025442  mov     rdx, rcx; Entry
0x140025445  mov     rcx, rax; Lookaside
0x140025448  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002544f  nop     dword ptr [rax+rax+00h]
0x140025454  mov     rbx, [rsp+28h+arg_0]
0x140025459  add     rsp, 20h
0x14002545d  pop     rdi
0x14002545e  retn
0x140025460  mov     edx, [rcx+8]; Tag
0x140025463  call    cs:__imp_ExFreePoolWithTag
0x14002546a  nop     dword ptr [rax+rax+00h]
0x14002546f  jmp     short loc_140025454
0x140025471  mov     ecx, 3
0x140025476  int     29h; Win8: RtlFailFast(ecx)
```
