# NpReadAlias

- ea: `0x1400184c0`
- end: `0x140018683`
- name: `NpReadAlias`
- size: `451`
- prototype: `__int64 __fastcall(_WORD *Src, int, _WORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001f40`
- `0x1400184c0`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400185da`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140018653`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400185da`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140018653`

## pseudocode

```c
__int64 __fastcall NpReadAlias(_WORD *Src, int a2, _WORD *a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rax
  __int64 v12; // rcx
  UNICODE_STRING *v13; // r15
  __int64 v14; // rax
  __int64 v15; // r8
  UNICODE_STRING *v16; // rcx
  __int64 v17; // rax
  UNICODE_STRING *v18; // rbx
  __int64 v19; // rdi

  if ( a2 != 7 )
    return 3221225485LL;
  if ( *(_BYTE *)a5 )
  {
    ++*(_DWORD *)(a5 + 12);
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
    v8 = (unsigned __int16)(2 * (v7 + 2)) + *(_DWORD *)(a5 + 4) + 16;
    *(_DWORD *)(a5 + 4) = v8;
    v9 = v8;
    if ( *a3 )
    {
      v10 = *(_DWORD *)(a5 + 8);
      do
      {
        ++v10;
        v11 = -1;
        *(_DWORD *)(a5 + 8) = v10;
        do
          ++v11;
        while ( a3[v11] );
        v12 = (unsigned __int16)(2 * (v11 + 1));
        a3 = (_WORD *)((char *)a3 + v12);
        *(_DWORD *)(a5 + 4) = v12 + v9 + 34;
        v9 += v12 + 34;
      }
      while ( *a3 );
    }
  }
  else
  {
    v13 = *(UNICODE_STRING **)(a5 + 24);
    *(_QWORD *)(a5 + 24) = v13 + 1;
    v14 = -1;
    do
      ++v14;
    while ( Src[v14] );
    v15 = (unsigned __int16)(2 * (v14 + 2));
    v13->MaximumLength = v15;
    v13->Length = 2 * (v14 + 2) - 2;
    v13->Buffer = *(PWSTR *)(a5 + 32);
    *(_QWORD *)(a5 + 32) += v15;
    *v13->Buffer = 92;
    memmove(v13->Buffer + 1, Src, v15 - 2);
    RtlUpcaseUnicodeString(v13, v13, 0);
    while ( *a3 )
    {
      v16 = *(UNICODE_STRING **)(a5 + 16);
      *(_QWORD *)(a5 + 16) = v16 + 2;
      v17 = -1;
      v16->Buffer = &v13->Length;
      do
        ++v17;
      while ( a3[v17] );
      v18 = v16 + 1;
      v19 = (unsigned __int16)(2 * (v17 + 2));
      v16[1].MaximumLength = v19;
      v16[1].Length = 2 * (v17 + 2) - 2;
      v16[1].Buffer = *(PWSTR *)(a5 + 32);
      *(_QWORD *)(a5 + 32) += v19;
      *v16[1].Buffer = 92;
      memmove(v16[1].Buffer + 1, a3, v19 - 2);
      RtlUpcaseUnicodeString(v18, v18, 0);
      a3 = (_WORD *)((char *)a3 + v19 - 2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400184c0  push    rbx
0x1400184c2  push    rbp
0x1400184c3  push    rsi
0x1400184c4  push    rdi
0x1400184c5  push    r12
0x1400184c7  push    r14
0x1400184c9  push    r15
0x1400184cb  sub     rsp, 20h
0x1400184cf  mov     rbp, r8
0x1400184d2  mov     r9, rcx
0x1400184d5  cmp     edx, 7
0x1400184d8  jz      short loc_1400184E4
0x1400184da  mov     eax, 0C000000Dh
0x1400184df  jmp     loc_140018673
0x1400184e4  mov     rsi, [rsp+58h+arg_20]
0x1400184ec  cmp     byte ptr [rsi], 0
0x1400184ef  jz      short loc_14001856A
0x1400184f1  mov     r10d, 1
0x1400184f7  add     [rsi+0Ch], r10d
0x1400184fb  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400184ff  mov     rax, r14
0x140018502  inc     rax
0x140018505  cmp     word ptr [rcx+rax*2], 0
0x14001850a  jnz     short loc_140018502
0x14001850c  mov     edx, [rsi+4]
0x14001850f  add     ax, 2
0x140018513  add     ax, ax
0x140018516  add     edx, 10h
0x140018519  movzx   ecx, ax
0x14001851c  add     edx, ecx
0x14001851e  mov     [rsi+4], edx
0x140018521  mov     r8d, edx
0x140018524  cmp     word ptr [rbp+0], 0
0x140018529  jz      loc_140018671
0x14001852f  mov     edx, [rsi+8]
0x140018532  inc     edx
0x140018534  mov     rax, r14
0x140018537  mov     [rsi+8], edx
0x14001853a  inc     rax
0x14001853d  cmp     word ptr [rbp+rax*2+0], 0
0x140018543  jnz     short loc_14001853A
0x140018545  add     ax, r10w
0x140018549  add     ax, ax
0x14001854c  movzx   ecx, ax
0x14001854f  lea     eax, [r8+22h]
0x140018553  add     eax, ecx
0x140018555  add     rbp, rcx
0x140018558  mov     [rsi+4], eax
0x14001855b  mov     r8d, eax
0x14001855e  cmp     word ptr [rbp+0], 0
0x140018563  jnz     short loc_140018532
0x140018565  jmp     loc_140018671
0x14001856a  mov     r15, [rsi+18h]
0x14001856e  or      r14, 0FFFFFFFFFFFFFFFFh
0x140018572  lea     rax, [r15+10h]
0x140018576  mov     [rsi+18h], rax
0x14001857a  mov     rax, r14
0x14001857d  inc     rax
0x140018580  cmp     word ptr [rcx+rax*2], 0
0x140018585  jnz     short loc_14001857D
0x140018587  mov     r12d, 2
0x14001858d  mov     rdx, r9; Src
0x140018590  add     ax, r12w
0x140018594  add     ax, ax
0x140018597  movzx   r8d, ax
0x14001859b  mov     [r15+2], r8w
0x1400185a0  movzx   eax, r8w
0x1400185a4  sub     ax, r12w
0x1400185a8  mov     [r15], ax
0x1400185ac  mov     rax, [rsi+20h]
0x1400185b0  mov     [r15+8], rax
0x1400185b4  add     [rsi+20h], r8
0x1400185b8  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1400185bc  mov     rax, [r15+8]
0x1400185c0  mov     word ptr [rax], 5Ch ; '\'
0x1400185c5  mov     rcx, [r15+8]
0x1400185c9  add     rcx, r12; void *
0x1400185cc  call    memmove
0x1400185d1  xor     r8d, r8d; AllocateDestinationString
0x1400185d4  mov     rdx, r15; SourceString
0x1400185d7  mov     rcx, r15; DestinationString
0x1400185da  call    cs:__imp_RtlUpcaseUnicodeString
0x1400185e1  nop     dword ptr [rax+rax+00h]
0x1400185e6  jmp     short loc_140018666
0x1400185e8  mov     rcx, [rsi+10h]
0x1400185ec  lea     rax, [rcx+20h]
0x1400185f0  mov     [rsi+10h], rax
0x1400185f4  mov     rax, r14
0x1400185f7  mov     [rcx+8], r15
0x1400185fb  inc     rax
0x1400185fe  cmp     word ptr [rbp+rax*2+0], 0
0x140018604  jnz     short loc_1400185FB
0x140018606  add     ax, r12w
0x14001860a  lea     rbx, [rcx+10h]
0x14001860e  add     ax, ax
0x140018611  mov     rdx, rbp; Src
0x140018614  movzx   edi, ax
0x140018617  mov     [rcx+12h], di
0x14001861b  movzx   eax, di
0x14001861e  sub     ax, r12w
0x140018622  mov     [rbx], ax
0x140018625  mov     rax, [rsi+20h]
0x140018629  lea     r8, [rdi-2]; Size
0x14001862d  mov     [rcx+18h], rax
0x140018631  add     [rsi+20h], rdi
0x140018635  mov     rax, [rcx+18h]
0x140018639  mov     word ptr [rax], 5Ch ; '\'
0x14001863e  mov     rcx, [rcx+18h]
0x140018642  add     rcx, r12; void *
0x140018645  call    memmove
0x14001864a  xor     r8d, r8d; AllocateDestinationString
0x14001864d  mov     rdx, rbx; SourceString
0x140018650  mov     rcx, rbx; DestinationString
0x140018653  call    cs:__imp_RtlUpcaseUnicodeString
0x14001865a  nop     dword ptr [rax+rax+00h]
0x14001865f  add     rbp, 0FFFFFFFFFFFFFFFEh
0x140018663  add     rbp, rdi
0x140018666  cmp     word ptr [rbp+0], 0
0x14001866b  jnz     loc_1400185E8
0x140018671  xor     eax, eax
0x140018673  add     rsp, 20h
0x140018677  pop     r15
0x140018679  pop     r14
0x14001867b  pop     r12
0x14001867d  pop     rdi
0x14001867e  pop     rsi
0x14001867f  pop     rbp
0x140018680  pop     rbx
0x140018681  retn
```
