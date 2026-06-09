# ExtSTAAbortOpenAssociation

- ea: `0x1400251fc`
- end: `0x140025306`
- name: `ExtSTAAbortOpenAssociation`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14005e814`
- `0x140062984`

## callees

- `0x1400251fc`
- `0x140025480`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025273`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400252aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025273`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400252aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025284`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400252bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025284`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400252bb`

## pseudocode

```c
void __fastcall ExtSTAAbortOpenAssociation(__int64 a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // rbx
  __int64 *v4; // rsi
  struct DOT11_MAC_STATE_ENTRY *v5; // r14
  __int64 **v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // edx
  struct DOT11_MAC_STATE_ENTRY *v10; // [rsp+40h] [rbp+8h] BYREF

  v1 = (__int64 *)(a1 + 416);
  v3 = *(__int64 **)(a1 + 416);
  if ( v3 != (__int64 *)(a1 + 416) )
  {
    do
    {
      v4 = (__int64 *)*v3;
      if ( *((_DWORD *)v3 + 6) == 1 )
      {
        v5 = (struct DOT11_MAC_STATE_ENTRY *)v3[2];
        v10 = v5;
        if ( (__int64 *)v4[1] != v3 || (v6 = (__int64 **)v3[1], *v6 != v3) )
          __fastfail(3u);
        *v6 = v4;
        v4[1] = (__int64)v6;
        v7 = v3[6];
        if ( v7 )
        {
          v8 = v7 - 16;
          if ( *(_QWORD *)v8 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
          else
            ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
          v3[6] = 0;
        }
        if ( *(v3 - 2) )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(v3 - 2), v3 - 2);
        else
          ExFreePoolWithTag(v3 - 2, *((_DWORD *)v3 - 2));
        --*(_DWORD *)(a1 + 328);
        v5->pvAssocEntry = 0;
        Dot11DecObjCnt(&v10, v9);
      }
      v3 = v4;
    }
    while ( v4 != v1 );
  }
}

```

## disassembly

```asm
0x1400251fc  mov     [rsp+arg_8], rbx
0x140025201  mov     [rsp+arg_10], rbp
0x140025206  push    rsi
0x140025207  push    rdi
0x140025208  push    r14
0x14002520a  sub     rsp, 20h
0x14002520e  lea     rdi, [rcx+1A0h]
0x140025215  mov     rbp, rcx
0x140025218  mov     rbx, [rdi]
0x14002521b  cmp     rbx, rdi
0x14002521e  jz      loc_1400252EB
0x140025224  cmp     dword ptr [rbx+18h], 1
0x140025228  mov     rsi, [rbx]
0x14002522b  jnz     loc_1400252DF
0x140025231  mov     r14, [rbx+10h]
0x140025235  mov     [rsp+38h+arg_0], r14
0x14002523a  cmp     [rsi+8], rbx
0x14002523e  jnz     loc_1400252FF
0x140025244  mov     rax, [rbx+8]
0x140025248  cmp     [rax], rbx
0x14002524b  jnz     loc_1400252FF
0x140025251  mov     [rax], rsi
0x140025254  mov     [rsi+8], rax
0x140025258  mov     rcx, [rbx+30h]
0x14002525c  test    rcx, rcx
0x14002525f  jz      short loc_140025298
0x140025261  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140025265  mov     rax, [rcx]
0x140025268  test    rax, rax
0x14002526b  jz      short loc_140025281
0x14002526d  mov     rdx, rcx; Entry
0x140025270  mov     rcx, rax; Lookaside
0x140025273  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002527a  nop     dword ptr [rax+rax+00h]
0x14002527f  jmp     short loc_140025290
0x140025281  mov     edx, [rcx+8]; Tag
0x140025284  call    cs:__imp_ExFreePoolWithTag
0x14002528b  nop     dword ptr [rax+rax+00h]
0x140025290  mov     qword ptr [rbx+30h], 0
0x140025298  lea     rcx, [rbx-10h]; P
0x14002529c  mov     rax, [rcx]
0x14002529f  test    rax, rax
0x1400252a2  jz      short loc_1400252B8
0x1400252a4  mov     rdx, rcx; Entry
0x1400252a7  mov     rcx, rax; Lookaside
0x1400252aa  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400252b1  nop     dword ptr [rax+rax+00h]
0x1400252b6  jmp     short loc_1400252C7
0x1400252b8  mov     edx, [rcx+8]; Tag
0x1400252bb  call    cs:__imp_ExFreePoolWithTag
0x1400252c2  nop     dword ptr [rax+rax+00h]
0x1400252c7  dec     dword ptr [rbp+148h]
0x1400252cd  lea     rcx, [rsp+38h+arg_0]; struct DOT11_MAC_STATE_ENTRY **
0x1400252d2  mov     qword ptr [r14+40h], 0
0x1400252da  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x1400252df  mov     rbx, rsi
0x1400252e2  cmp     rsi, rdi
0x1400252e5  jnz     loc_140025224
0x1400252eb  mov     rbx, [rsp+38h+arg_8]
0x1400252f0  mov     rbp, [rsp+38h+arg_10]
0x1400252f5  add     rsp, 20h
0x1400252f9  pop     r14
0x1400252fb  pop     rdi
0x1400252fc  pop     rsi
0x1400252fd  retn
0x1400252ff  mov     ecx, 3
0x140025304  int     29h; Win8: RtlFailFast(ecx)
```
