# ASN1Enc_KrbFastArmor

- ea: `0x18000fc38`
- end: `0x18000fd4a`
- name: `ASN1Enc_KrbFastArmor`
- size: `274`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180010c90`
- `0x1800116a0`
- `0x1800119d0`
- `0x180013dc8`
- `0x180014154`
- `0x180014e74`
- `0x18001638c`

## callees

- `0x18000fc38`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x18000fc60`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000fc81`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000fcd6`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000fc60`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000fc81`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18000fcd6`
- `MSASN1!ASN1BEREncS32` at `0x18000fc9e`
- `MSASN1!ASN1BEREncS32` at `0x18000fc9e`
- `MSASN1!ASN1DEREncOctetString` at `0x18000fcf4`
- `MSASN1!ASN1DEREncOctetString` at `0x18000fcf4`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000fcb9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000fd0b`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000fd22`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000fcb9`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000fd0b`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18000fd22`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KrbFastArmor(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  v8 = 0;
  v7 = 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v8)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v7)
    || !(unsigned int)ASN1BEREncS32(a1, 2, *a3)
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v7)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v7)
    || !(unsigned int)ASN1DEREncOctetString(a1, 4, a3[2], *((_QWORD *)a3 + 2))
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v7) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  return v3;
}

```

## disassembly

```asm
0x18000fc38  mov     rax, rsp
0x18000fc3b  mov     [rax+8], rbx
0x18000fc3f  mov     [rax+18h], rsi
0x18000fc43  mov     [rax+10h], edx
0x18000fc46  push    rdi
0x18000fc47  sub     rsp, 20h
0x18000fc4b  xor     ebx, ebx
0x18000fc4d  mov     rsi, r8
0x18000fc50  lea     r8, [rax+20h]
0x18000fc54  mov     [rax+20h], ebx
0x18000fc57  mov     rdi, rcx
0x18000fc5a  mov     [rax+10h], ebx
0x18000fc5d  lea     edx, [rbx+10h]
0x18000fc60  call    cs:__imp_ASN1BEREncExplicitTag
0x18000fc67  nop     dword ptr [rax+rax+00h]
0x18000fc6c  test    eax, eax
0x18000fc6e  jz      loc_18000FD37
0x18000fc74  lea     r8, [rsp+28h+arg_8]
0x18000fc79  mov     edx, 80000000h
0x18000fc7e  mov     rcx, rdi
0x18000fc81  call    cs:__imp_ASN1BEREncExplicitTag
0x18000fc88  nop     dword ptr [rax+rax+00h]
0x18000fc8d  test    eax, eax
0x18000fc8f  jz      loc_18000FD37
0x18000fc95  mov     r8d, [rsi]
0x18000fc98  lea     edx, [rbx+2]
0x18000fc9b  mov     rcx, rdi
0x18000fc9e  call    cs:__imp_ASN1BEREncS32
0x18000fca5  nop     dword ptr [rax+rax+00h]
0x18000fcaa  test    eax, eax
0x18000fcac  jz      loc_18000FD37
0x18000fcb2  mov     edx, [rsp+28h+arg_8]
0x18000fcb6  mov     rcx, rdi
0x18000fcb9  call    cs:__imp_ASN1BEREncEndOfContents
0x18000fcc0  nop     dword ptr [rax+rax+00h]
0x18000fcc5  test    eax, eax
0x18000fcc7  jz      short loc_18000FD37
0x18000fcc9  lea     r8, [rsp+28h+arg_8]
0x18000fcce  mov     edx, 80000001h
0x18000fcd3  mov     rcx, rdi
0x18000fcd6  call    cs:__imp_ASN1BEREncExplicitTag
0x18000fcdd  nop     dword ptr [rax+rax+00h]
0x18000fce2  test    eax, eax
0x18000fce4  jz      short loc_18000FD37
0x18000fce6  mov     r9, [rsi+10h]
0x18000fcea  lea     edx, [rbx+4]
0x18000fced  mov     r8d, [rsi+8]
0x18000fcf1  mov     rcx, rdi
0x18000fcf4  call    cs:__imp_ASN1DEREncOctetString
0x18000fcfb  nop     dword ptr [rax+rax+00h]
0x18000fd00  test    eax, eax
0x18000fd02  jz      short loc_18000FD37
0x18000fd04  mov     edx, [rsp+28h+arg_8]
0x18000fd08  mov     rcx, rdi
0x18000fd0b  call    cs:__imp_ASN1BEREncEndOfContents
0x18000fd12  nop     dword ptr [rax+rax+00h]
0x18000fd17  test    eax, eax
0x18000fd19  jz      short loc_18000FD37
0x18000fd1b  mov     edx, [rsp+28h+arg_18]
0x18000fd1f  mov     rcx, rdi
0x18000fd22  call    cs:__imp_ASN1BEREncEndOfContents
0x18000fd29  nop     dword ptr [rax+rax+00h]
0x18000fd2e  test    eax, eax
0x18000fd30  setnz   bl
0x18000fd33  mov     eax, ebx
0x18000fd35  jmp     short loc_18000FD39
0x18000fd37  xor     eax, eax
0x18000fd39  mov     rbx, [rsp+28h+arg_0]
0x18000fd3e  mov     rsi, [rsp+28h+arg_10]
0x18000fd43  add     rsp, 20h
0x18000fd47  pop     rdi
0x18000fd48  retn
```
