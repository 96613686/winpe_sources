# ExtSTAAbortOpenAssociation

- ea: `0x140025480`
- end: `0x14002558a`
- name: `ExtSTAAbortOpenAssociation`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140060044`
- `0x1400641b4`

## callees

- `0x140025480`
- `0x140025704`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400254f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002552e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400254f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002552e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025508`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002553f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025508`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002553f`

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
0x140025480  mov     [rsp+arg_8], rbx
0x140025485  mov     [rsp+arg_10], rbp
0x14002548a  push    rsi
0x14002548b  push    rdi
0x14002548c  push    r14
0x14002548e  sub     rsp, 20h
0x140025492  lea     rdi, [rcx+1A0h]
0x140025499  mov     rbp, rcx
0x14002549c  mov     rbx, [rdi]
0x14002549f  cmp     rbx, rdi
0x1400254a2  jz      loc_14002556F
0x1400254a8  cmp     dword ptr [rbx+18h], 1
0x1400254ac  mov     rsi, [rbx]
0x1400254af  jnz     loc_140025563
0x1400254b5  mov     r14, [rbx+10h]
0x1400254b9  mov     [rsp+38h+arg_0], r14
0x1400254be  cmp     [rsi+8], rbx
0x1400254c2  jnz     loc_140025583
0x1400254c8  mov     rax, [rbx+8]
0x1400254cc  cmp     [rax], rbx
0x1400254cf  jnz     loc_140025583
0x1400254d5  mov     [rax], rsi
0x1400254d8  mov     [rsi+8], rax
0x1400254dc  mov     rcx, [rbx+30h]
0x1400254e0  test    rcx, rcx
0x1400254e3  jz      short loc_14002551C
0x1400254e5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400254e9  mov     rax, [rcx]
0x1400254ec  test    rax, rax
0x1400254ef  jz      short loc_140025505
0x1400254f1  mov     rdx, rcx; Entry
0x1400254f4  mov     rcx, rax; Lookaside
0x1400254f7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400254fe  nop     dword ptr [rax+rax+00h]
0x140025503  jmp     short loc_140025514
0x140025505  mov     edx, [rcx+8]; Tag
0x140025508  call    cs:__imp_ExFreePoolWithTag
0x14002550f  nop     dword ptr [rax+rax+00h]
0x140025514  mov     qword ptr [rbx+30h], 0
0x14002551c  lea     rcx, [rbx-10h]; P
0x140025520  mov     rax, [rcx]
0x140025523  test    rax, rax
0x140025526  jz      short loc_14002553C
0x140025528  mov     rdx, rcx; Entry
0x14002552b  mov     rcx, rax; Lookaside
0x14002552e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025535  nop     dword ptr [rax+rax+00h]
0x14002553a  jmp     short loc_14002554B
0x14002553c  mov     edx, [rcx+8]; Tag
0x14002553f  call    cs:__imp_ExFreePoolWithTag
0x140025546  nop     dword ptr [rax+rax+00h]
0x14002554b  dec     dword ptr [rbp+148h]
0x140025551  lea     rcx, [rsp+38h+arg_0]; struct DOT11_MAC_STATE_ENTRY **
0x140025556  mov     qword ptr [r14+40h], 0
0x14002555e  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x140025563  mov     rbx, rsi
0x140025566  cmp     rsi, rdi
0x140025569  jnz     loc_1400254A8
0x14002556f  mov     rbx, [rsp+38h+arg_8]
0x140025574  mov     rbp, [rsp+38h+arg_10]
0x140025579  add     rsp, 20h
0x14002557d  pop     r14
0x14002557f  pop     rdi
0x140025580  pop     rsi
0x140025581  retn
0x140025583  mov     ecx, 3
0x140025588  int     29h; Win8: RtlFailFast(ecx)
```
