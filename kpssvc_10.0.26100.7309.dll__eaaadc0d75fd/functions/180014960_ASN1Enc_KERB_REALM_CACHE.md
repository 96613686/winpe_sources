# ASN1Enc_KERB_REALM_CACHE

- ea: `0x180014960`
- end: `0x180014ad7`
- name: `ASN1Enc_KERB_REALM_CACHE`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014960`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x18001498c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800149ad`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800149e0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180014a3f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001498c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800149ad`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800149e0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180014a3f`
- `MSASN1!ASN1DEREncGeneralizedTime` at `0x180014a5b`
- `MSASN1!ASN1DEREncGeneralizedTime` at `0x180014a5b`
- `MSASN1!ASN1DEREncCharString` at `0x180014a03`
- `MSASN1!ASN1DEREncCharString` at `0x180014a03`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014a1e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014a72`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014a89`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014aac`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014a1e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014a72`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014a89`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180014aac`
- `KERNEL32!lstrlenA` at `0x1800149c5`
- `KERNEL32!lstrlenA` at `0x1800149c5`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_REALM_CACHE(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v3; // ebx
  int i; // eax
  unsigned int v7; // ebp
  _DWORD v9[10]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v9[0] = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  for ( i = ASN1BEREncExplicitTag(a1, a2, v9); i; i = ASN1BEREncEndOfContents(a1, v11) )
  {
    a3 = (__int64 *)*a3;
    if ( !a3 )
    {
      LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v9[0]) != 0;
      return v3;
    }
    v11 = 0;
    v10 = 0;
    if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v11) )
      break;
    v7 = lstrlenA((LPCSTR)a3[1]);
    if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v10)
      || !(unsigned int)ASN1DEREncCharString(a1, 27, v7, a3[1])
      || !(unsigned int)ASN1BEREncEndOfContents(a1, v10)
      || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v10)
      || !(unsigned int)ASN1DEREncGeneralizedTime(a1, 24, a3 + 2)
      || !(unsigned int)ASN1BEREncEndOfContents(a1, v10) )
    {
      break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014960  mov     rax, rsp
0x180014963  mov     [rax+8], rbx
0x180014967  mov     [rax+18h], rbp
0x18001496b  push    rsi
0x18001496c  push    rdi
0x18001496d  push    r14
0x18001496f  sub     rsp, 30h
0x180014973  xor     ebx, ebx
0x180014975  mov     rsi, r8
0x180014978  test    edx, edx
0x18001497a  mov     [rax-28h], ebx
0x18001497d  lea     r8, [rax-28h]
0x180014981  mov     rdi, rcx
0x180014984  lea     r14d, [rbx+10h]
0x180014988  cmovz   edx, r14d
0x18001498c  call    cs:__imp_ASN1BEREncExplicitTag
0x180014993  nop     dword ptr [rax+rax+00h]
0x180014998  jmp     loc_180014A95
0x18001499d  lea     r8, [rsp+48h+arg_18]
0x1800149a2  mov     [rsp+48h+arg_18], ebx
0x1800149a6  mov     edx, r14d
0x1800149a9  mov     [rsp+48h+arg_8], ebx
0x1800149ad  call    cs:__imp_ASN1BEREncExplicitTag
0x1800149b4  nop     dword ptr [rax+rax+00h]
0x1800149b9  test    eax, eax
0x1800149bb  jz      loc_180014AC1
0x1800149c1  mov     rcx, [rsi+8]; lpString
0x1800149c5  call    cs:__imp_lstrlenA
0x1800149cc  nop     dword ptr [rax+rax+00h]
0x1800149d1  lea     r8, [rsp+48h+arg_8]
0x1800149d6  mov     edx, 80000000h
0x1800149db  mov     rcx, rdi
0x1800149de  mov     ebp, eax
0x1800149e0  call    cs:__imp_ASN1BEREncExplicitTag
0x1800149e7  nop     dword ptr [rax+rax+00h]
0x1800149ec  test    eax, eax
0x1800149ee  jz      loc_180014AC1
0x1800149f4  mov     r9, [rsi+8]
0x1800149f8  mov     r8d, ebp
0x1800149fb  mov     edx, 1Bh
0x180014a00  mov     rcx, rdi
0x180014a03  call    cs:__imp_ASN1DEREncCharString
0x180014a0a  nop     dword ptr [rax+rax+00h]
0x180014a0f  test    eax, eax
0x180014a11  jz      loc_180014AC1
0x180014a17  mov     edx, [rsp+48h+arg_8]
0x180014a1b  mov     rcx, rdi
0x180014a1e  call    cs:__imp_ASN1BEREncEndOfContents
0x180014a25  nop     dword ptr [rax+rax+00h]
0x180014a2a  test    eax, eax
0x180014a2c  jz      loc_180014AC1
0x180014a32  lea     r8, [rsp+48h+arg_8]
0x180014a37  mov     edx, 80000001h
0x180014a3c  mov     rcx, rdi
0x180014a3f  call    cs:__imp_ASN1BEREncExplicitTag
0x180014a46  nop     dword ptr [rax+rax+00h]
0x180014a4b  test    eax, eax
0x180014a4d  jz      short loc_180014AC1
0x180014a4f  lea     r8, [rsi+10h]
0x180014a53  mov     edx, 18h
0x180014a58  mov     rcx, rdi
0x180014a5b  call    cs:__imp_ASN1DEREncGeneralizedTime
0x180014a62  nop     dword ptr [rax+rax+00h]
0x180014a67  test    eax, eax
0x180014a69  jz      short loc_180014AC1
0x180014a6b  mov     edx, [rsp+48h+arg_8]
0x180014a6f  mov     rcx, rdi
0x180014a72  call    cs:__imp_ASN1BEREncEndOfContents
0x180014a79  nop     dword ptr [rax+rax+00h]
0x180014a7e  test    eax, eax
0x180014a80  jz      short loc_180014AC1
0x180014a82  mov     edx, [rsp+48h+arg_18]
0x180014a86  mov     rcx, rdi
0x180014a89  call    cs:__imp_ASN1BEREncEndOfContents
0x180014a90  nop     dword ptr [rax+rax+00h]
0x180014a95  test    eax, eax
0x180014a97  jz      short loc_180014AC1
0x180014a99  mov     rsi, [rsi]
0x180014a9c  mov     rcx, rdi
0x180014a9f  test    rsi, rsi
0x180014aa2  jnz     loc_18001499D
0x180014aa8  mov     edx, [rsp+48h+var_28]
0x180014aac  call    cs:__imp_ASN1BEREncEndOfContents
0x180014ab3  nop     dword ptr [rax+rax+00h]
0x180014ab8  test    eax, eax
0x180014aba  setnz   bl
0x180014abd  mov     eax, ebx
0x180014abf  jmp     short loc_180014AC3
0x180014ac1  xor     eax, eax
0x180014ac3  mov     rbx, [rsp+48h+arg_0]
0x180014ac8  mov     rbp, [rsp+48h+arg_10]
0x180014acd  add     rsp, 30h
0x180014ad1  pop     r14
0x180014ad3  pop     rdi
0x180014ad4  pop     rsi
0x180014ad5  retn
```
