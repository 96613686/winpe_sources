# addCommas

- ea: `0x14000d528`
- end: `0x14000d692`
- name: `addCommas`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cec0`

## callees

- `0x14000d528`
- `0x14000e406`
- `0x14000e450`

## import_xrefs

- `msvcrt!strspn` at `0x14000d558`
- `msvcrt!strspn` at `0x14000d582`
- `msvcrt!strspn` at `0x14000d558`
- `msvcrt!strspn` at `0x14000d582`
- `msvcrt!strpbrk` at `0x14000d56e`
- `msvcrt!strpbrk` at `0x14000d56e`

## pseudocode

```c
__int64 __fastcall addCommas(const char *a1, int a2)
{
  int v4; // eax
  __int64 v5; // r14
  int v6; // ebp
  const char *v7; // rdi
  char *v8; // rax
  int v9; // esi
  int v10; // r12d
  __int64 v11; // rsi
  int v12; // r15d
  char *v13; // r14
  int v14; // edi
  char *v15; // r14
  _BYTE *v16; // rcx
  int v17; // esi
  _BYTE Src[24]; // [rsp+20h] [rbp-68h] BYREF

  v4 = strspn(a1, " ");
  v5 = v4;
  v6 = v4;
  v7 = &a1[v4];
  v8 = strpbrk(v7, " ");
  v9 = (int)v8;
  if ( v8 )
  {
    v10 = strspn(v8, " ");
    LODWORD(v11) = v9 - (_DWORD)a1 - v6;
  }
  else
  {
    v10 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
  }
  if ( (int)v11 <= 3 )
    return 0;
  v12 = ((int)v11 - 1) / 3;
  if ( v12 + (int)v11 > a2 || (unsigned int)(v11 + v6) >= 0x14 )
    return 0;
  memcpy_0(Src, v7, (int)v11);
  if ( v6 <= 0 || v6 < v12 )
    v13 = (char *)a1;
  else
    v13 = (char *)&a1[v5 - v12];
  v14 = (int)v11 % 3;
  if ( !((int)v11 % 3) )
    v14 = 3;
  memcpy_0(v13, Src, v14);
  v15 = &v13[v14];
  v16 = &Src[v14];
  v17 = v11 - v14;
  while ( v17 > 0 )
  {
    *v15 = 44;
    v17 -= 3;
    *(_WORD *)(v15 + 1) = *(_WORD *)v16;
    v15[3] = v16[2];
    v15 += 4;
    v16 += 3;
  }
  if ( v10 + v6 <= v12 )
    *v15 = 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000d528  push    rbx
0x14000d52a  push    rbp
0x14000d52b  push    rsi
0x14000d52c  push    rdi
0x14000d52d  push    r12
0x14000d52f  push    r13
0x14000d531  push    r14
0x14000d533  push    r15
0x14000d535  sub     rsp, 48h
0x14000d539  mov     rax, cs:__security_cookie
0x14000d540  xor     rax, rsp
0x14000d543  mov     [rsp+88h+var_50], rax
0x14000d548  mov     r13d, edx
0x14000d54b  lea     r15, asc_14001413C; " "
0x14000d552  mov     rdx, r15; Control
0x14000d555  mov     rbx, rcx
0x14000d558  call    cs:__imp_strspn
0x14000d55e  movsxd  r14, eax
0x14000d561  mov     rdx, r15; Control
0x14000d564  mov     rbp, rax
0x14000d567  lea     rdi, [r14+rbx]
0x14000d56b  mov     rcx, rdi; Str
0x14000d56e  call    cs:__imp_strpbrk
0x14000d574  mov     rsi, rax
0x14000d577  test    rax, rax
0x14000d57a  jz      short loc_14000D591
0x14000d57c  mov     rdx, r15; Control
0x14000d57f  mov     rcx, rax; Str
0x14000d582  call    cs:__imp_strspn
0x14000d588  sub     esi, ebx
0x14000d58a  mov     r12, rax
0x14000d58d  sub     esi, ebp
0x14000d58f  jmp     short loc_14000D5A1
0x14000d591  xor     r12d, r12d
0x14000d594  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d598  inc     rsi
0x14000d59b  cmp     [rdi+rsi], r12b
0x14000d59f  jnz     short loc_14000D598
0x14000d5a1  cmp     esi, 3
0x14000d5a4  jle     loc_14000D672
0x14000d5aa  lea     ecx, [rsi-1]
0x14000d5ad  mov     eax, 55555556h
0x14000d5b2  imul    ecx
0x14000d5b4  mov     r15d, edx
0x14000d5b7  shr     r15d, 1Fh
0x14000d5bb  add     r15d, edx
0x14000d5be  lea     eax, [r15+rsi]
0x14000d5c2  cmp     eax, r13d
0x14000d5c5  jg      loc_14000D672
0x14000d5cb  lea     eax, [rsi+rbp]
0x14000d5ce  cmp     eax, 14h
0x14000d5d1  jnb     loc_14000D672
0x14000d5d7  movsxd  r8, esi; Size
0x14000d5da  lea     rcx, [rsp+88h+Src]; void *
0x14000d5df  mov     rdx, rdi; Src
0x14000d5e2  call    memcpy_0
0x14000d5e7  test    ebp, ebp
0x14000d5e9  jle     short loc_14000D5FB
0x14000d5eb  cmp     ebp, r15d
0x14000d5ee  jl      short loc_14000D5FB
0x14000d5f0  movsxd  rax, r15d
0x14000d5f3  sub     r14, rax
0x14000d5f6  add     r14, rbx
0x14000d5f9  jmp     short loc_14000D5FE
0x14000d5fb  mov     r14, rbx
0x14000d5fe  mov     eax, 55555556h
0x14000d603  mov     edi, esi
0x14000d605  imul    esi
0x14000d607  mov     r13d, 3
0x14000d60d  mov     rcx, r14; void *
0x14000d610  mov     eax, edx
0x14000d612  shr     eax, 1Fh
0x14000d615  add     edx, eax
0x14000d617  lea     eax, [rdx+rdx*2]
0x14000d61a  sub     edi, eax
0x14000d61c  lea     rdx, [rsp+88h+Src]; Src
0x14000d621  cmovz   edi, r13d
0x14000d625  movsxd  rbx, edi
0x14000d628  mov     r8, rbx; Size
0x14000d62b  call    memcpy_0
0x14000d630  lea     rcx, [rsp+88h+Src]
0x14000d635  add     r14, rbx
0x14000d638  add     rcx, rbx
0x14000d63b  sub     esi, edi
0x14000d63d  jmp     short loc_14000D65C
0x14000d63f  mov     byte ptr [r14], 2Ch ; ','
0x14000d643  sub     esi, r13d
0x14000d646  movzx   eax, word ptr [rcx]
0x14000d649  mov     [r14+1], ax
0x14000d64e  mov     al, [rcx+2]
0x14000d651  mov     [r14+3], al
0x14000d655  add     r14, 4
0x14000d659  add     rcx, r13
0x14000d65c  test    esi, esi
0x14000d65e  jg      short loc_14000D63F
0x14000d660  lea     ecx, [r12+rbp]
0x14000d664  cmp     ecx, r15d
0x14000d667  jg      short loc_14000D66D
0x14000d669  mov     byte ptr [r14], 0
0x14000d66d  mov     eax, r15d
0x14000d670  jmp     short loc_14000D674
0x14000d672  xor     eax, eax
0x14000d674  mov     rcx, [rsp+88h+var_50]
0x14000d679  xor     rcx, rsp; StackCookie
0x14000d67c  call    __security_check_cookie
0x14000d681  add     rsp, 48h
0x14000d685  pop     r15
0x14000d687  pop     r14
0x14000d689  pop     r13
0x14000d68b  pop     r12
0x14000d68d  pop     rdi
0x14000d68e  pop     rsi
0x14000d68f  pop     rbp
0x14000d690  pop     rbx
0x14000d691  retn
```
