# ASN1Dec_KERB_REALM_CACHE

- ea: `0x18000a1d0`
- end: `0x18000a3dc`
- name: `ASN1Dec_KERB_REALM_CACHE`
- size: `524`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a1d0`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18000a246`
- `MSASN1!ASN1BERDecPeekTag` at `0x18000a246`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18000a3a2`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18000a3a2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a2fe`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a364`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a383`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a3c4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a2fe`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a364`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a383`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000a3c4`
- `MSASN1!ASN1BERDecGeneralizedTime` at `0x18000a344`
- `MSASN1!ASN1BERDecGeneralizedTime` at `0x18000a344`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a20e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a299`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a2be`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a323`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a20e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a299`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a2be`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000a323`
- `MSASN1!ASN1BERDecZeroCharString` at `0x18000a2de`
- `MSASN1!ASN1BERDecZeroCharString` at `0x18000a2de`
- `MSASN1!ASN1DecAlloc` at `0x18000a25f`
- `MSASN1!ASN1DecAlloc` at `0x18000a25f`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_REALM_CACHE(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rsi
  __int64 v10; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h] BYREF
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  v16 = 0;
  v13 = 0;
  v15 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v16, &v13) )
    return 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v16, v13) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v16, &v15) )
      return 0;
    v7 = ASN1DecAlloc(v16, 32);
    *a3 = v7;
    if ( !v7 )
      return 0;
    v8 = v16;
    v11 = 0;
    v14 = 0;
    v10 = 0;
    v9 = v7 + 8;
    v12 = 0;
    if ( !(unsigned int)ASN1BERDecExplicitTag(v16, 16, &v11, &v14)
      || !(unsigned int)ASN1BERDecExplicitTag(v11, 0x80000000LL, &v10, &v12)
      || !(unsigned int)ASN1BERDecZeroCharString(v10, 27, v9)
      || !(unsigned int)ASN1BERDecEndOfContents(v11, v10, v12)
      || !(unsigned int)ASN1BERDecExplicitTag(v11, 2147483649LL, &v10, &v12)
      || !(unsigned int)ASN1BERDecGeneralizedTime(v10, 24, v9 + 8)
      || !(unsigned int)ASN1BERDecEndOfContents(v11, v10, v12)
      || !(unsigned int)ASN1BERDecEndOfContents(v8, v11, v14) )
    {
      return 0;
    }
    a3 = (__int64 *)*a3;
  }
  *a3 = 0;
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v16, v13) != 0;
  return v3;
}

```

## disassembly

```asm
0x18000a1d0  mov     [rsp-28h+arg_0], rbx
0x18000a1d5  mov     [rsp-28h+arg_10], rsi
0x18000a1da  push    rbp
0x18000a1db  push    rdi
0x18000a1dc  push    r12
0x18000a1de  push    r14
0x18000a1e0  push    r15
0x18000a1e2  mov     rbp, rsp
0x18000a1e5  sub     rsp, 50h
0x18000a1e9  xor     ebx, ebx
0x18000a1eb  lea     r9, [rbp+var_18]
0x18000a1ef  test    edx, edx
0x18000a1f1  mov     [rbp+arg_18], rbx
0x18000a1f5  mov     rdi, r8
0x18000a1f8  mov     [rbp+var_18], rbx
0x18000a1fc  lea     r8, [rbp+arg_18]
0x18000a200  mov     [rbp+arg_8], ebx
0x18000a203  lea     r12d, [rbx+10h]
0x18000a207  mov     r15, rcx
0x18000a20a  cmovz   edx, r12d
0x18000a20e  call    cs:__imp_ASN1BERDecExplicitTag
0x18000a215  nop     dword ptr [rax+rax+00h]
0x18000a21a  test    eax, eax
0x18000a21c  jnz     loc_18000A39A
0x18000a222  xor     eax, eax
0x18000a224  lea     r11, [rsp+50h+var_s0]
0x18000a229  mov     rbx, [r11+30h]
0x18000a22d  mov     rsi, [r11+40h]
0x18000a231  mov     rsp, r11
0x18000a234  pop     r15
0x18000a236  pop     r14
0x18000a238  pop     r12
0x18000a23a  pop     rdi
0x18000a23b  pop     rbp
0x18000a23c  retn
0x18000a23e  mov     rcx, [rbp+arg_18]
0x18000a242  lea     rdx, [rbp+arg_8]
0x18000a246  call    cs:__imp_ASN1BERDecPeekTag
0x18000a24d  nop     dword ptr [rax+rax+00h]
0x18000a252  test    eax, eax
0x18000a254  jz      short loc_18000A222
0x18000a256  mov     rcx, [rbp+arg_18]
0x18000a25a  mov     edx, 20h ; ' '
0x18000a25f  call    cs:__imp_ASN1DecAlloc
0x18000a266  nop     dword ptr [rax+rax+00h]
0x18000a26b  mov     [rdi], rax
0x18000a26e  test    rax, rax
0x18000a271  jz      short loc_18000A222
0x18000a273  mov     r14, [rbp+arg_18]
0x18000a277  lea     r9, [rbp+var_10]
0x18000a27b  mov     rcx, r14
0x18000a27e  mov     [rbp+var_28], rbx
0x18000a282  lea     r8, [rbp+var_28]
0x18000a286  mov     [rbp+var_10], rbx
0x18000a28a  mov     edx, r12d
0x18000a28d  mov     [rbp+var_30], rbx
0x18000a291  lea     rsi, [rax+8]
0x18000a295  mov     [rbp+var_20], rbx
0x18000a299  call    cs:__imp_ASN1BERDecExplicitTag
0x18000a2a0  nop     dword ptr [rax+rax+00h]
0x18000a2a5  test    eax, eax
0x18000a2a7  jz      loc_18000A222
0x18000a2ad  mov     rcx, [rbp+var_28]
0x18000a2b1  lea     r9, [rbp+var_20]
0x18000a2b5  lea     r8, [rbp+var_30]
0x18000a2b9  mov     edx, 80000000h
0x18000a2be  call    cs:__imp_ASN1BERDecExplicitTag
0x18000a2c5  nop     dword ptr [rax+rax+00h]
0x18000a2ca  test    eax, eax
0x18000a2cc  jz      loc_18000A222
0x18000a2d2  mov     rcx, [rbp+var_30]
0x18000a2d6  mov     r8, rsi
0x18000a2d9  mov     edx, 1Bh
0x18000a2de  call    cs:__imp_ASN1BERDecZeroCharString
0x18000a2e5  nop     dword ptr [rax+rax+00h]
0x18000a2ea  test    eax, eax
0x18000a2ec  jz      loc_18000A222
0x18000a2f2  mov     r8, [rbp+var_20]
0x18000a2f6  mov     rdx, [rbp+var_30]
0x18000a2fa  mov     rcx, [rbp+var_28]
0x18000a2fe  call    cs:__imp_ASN1BERDecEndOfContents
0x18000a305  nop     dword ptr [rax+rax+00h]
0x18000a30a  test    eax, eax
0x18000a30c  jz      loc_18000A222
0x18000a312  mov     rcx, [rbp+var_28]
0x18000a316  lea     r9, [rbp+var_20]
0x18000a31a  lea     r8, [rbp+var_30]
0x18000a31e  mov     edx, 80000001h
0x18000a323  call    cs:__imp_ASN1BERDecExplicitTag
0x18000a32a  nop     dword ptr [rax+rax+00h]
0x18000a32f  test    eax, eax
0x18000a331  jz      loc_18000A222
0x18000a337  mov     rcx, [rbp+var_30]
0x18000a33b  lea     r8, [rsi+8]
0x18000a33f  mov     edx, 18h
0x18000a344  call    cs:__imp_ASN1BERDecGeneralizedTime
0x18000a34b  nop     dword ptr [rax+rax+00h]
0x18000a350  test    eax, eax
0x18000a352  jz      loc_18000A222
0x18000a358  mov     r8, [rbp+var_20]
0x18000a35c  mov     rdx, [rbp+var_30]
0x18000a360  mov     rcx, [rbp+var_28]
0x18000a364  call    cs:__imp_ASN1BERDecEndOfContents
0x18000a36b  nop     dword ptr [rax+rax+00h]
0x18000a370  test    eax, eax
0x18000a372  jz      loc_18000A222
0x18000a378  mov     r8, [rbp+var_10]
0x18000a37c  mov     rcx, r14
0x18000a37f  mov     rdx, [rbp+var_28]
0x18000a383  call    cs:__imp_ASN1BERDecEndOfContents
0x18000a38a  nop     dword ptr [rax+rax+00h]
0x18000a38f  test    eax, eax
0x18000a391  jz      loc_18000A222
0x18000a397  mov     rdi, [rdi]
0x18000a39a  mov     rdx, [rbp+var_18]
0x18000a39e  mov     rcx, [rbp+arg_18]
0x18000a3a2  call    cs:__imp_ASN1BERDecNotEndOfContents
0x18000a3a9  nop     dword ptr [rax+rax+00h]
0x18000a3ae  test    eax, eax
0x18000a3b0  jnz     loc_18000A23E
0x18000a3b6  mov     [rdi], rbx
0x18000a3b9  mov     rcx, r15
0x18000a3bc  mov     r8, [rbp+var_18]
0x18000a3c0  mov     rdx, [rbp+arg_18]
0x18000a3c4  call    cs:__imp_ASN1BERDecEndOfContents
0x18000a3cb  nop     dword ptr [rax+rax+00h]
0x18000a3d0  test    eax, eax
0x18000a3d2  setnz   bl
0x18000a3d5  mov     eax, ebx
0x18000a3d7  jmp     loc_18000A224
```
