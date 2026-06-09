# ASN1Enc_CertificatePair

- ea: `0x1800ebe20`
- end: `0x1800ebefe`
- name: `ASN1Enc_CertificatePair`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800ebe20`

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x1800ebe80`
- `MSASN1!ASN1BEREncOpenType` at `0x1800ebebe`
- `MSASN1!ASN1BEREncOpenType` at `0x1800ebe80`
- `MSASN1!ASN1BEREncOpenType` at `0x1800ebebe`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ebe91`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ebecf`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ebee0`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ebe91`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ebecf`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ebee0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ebe4f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ebe6f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ebead`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ebe4f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ebe6f`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ebead`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_CertificatePair(__int64 a1, __int64 a2, char *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v7)
      && (*a3 >= 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v6)
       && (unsigned int)ASN1BEREncOpenType(a1, a3 + 8)
       && (unsigned int)ASN1BEREncEndOfContents(a1, v6))
      && ((*a3 & 0x40) == 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v6)
       && (unsigned int)ASN1BEREncOpenType(a1, a3 + 24)
       && (unsigned int)ASN1BEREncEndOfContents(a1, v6))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
}

```

## disassembly

```asm
0x1800ebe20  mov     [rsp+arg_0], rbx
0x1800ebe25  push    rdi
0x1800ebe26  sub     rsp, 20h
0x1800ebe2a  test    edx, edx
0x1800ebe2c  mov     [rsp+28h+arg_18], 0
0x1800ebe34  mov     eax, 10h
0x1800ebe39  mov     [rsp+28h+arg_8], 0
0x1800ebe41  mov     rdi, r8
0x1800ebe44  cmovz   edx, eax
0x1800ebe47  lea     r8, [rsp+28h+arg_18]
0x1800ebe4c  mov     rbx, rcx
0x1800ebe4f  call    cs:__imp_ASN1BEREncExplicitTag
0x1800ebe55  test    eax, eax
0x1800ebe57  jz      loc_1800EBEF1
0x1800ebe5d  cmp     byte ptr [rdi], 0
0x1800ebe60  jge     short loc_1800EBE9B
0x1800ebe62  lea     r8, [rsp+28h+arg_8]
0x1800ebe67  mov     edx, 80000000h
0x1800ebe6c  mov     rcx, rbx
0x1800ebe6f  call    cs:__imp_ASN1BEREncExplicitTag
0x1800ebe75  test    eax, eax
0x1800ebe77  jz      short loc_1800EBEF1
0x1800ebe79  lea     rdx, [rdi+8]
0x1800ebe7d  mov     rcx, rbx
0x1800ebe80  call    cs:__imp_ASN1BEREncOpenType
0x1800ebe86  test    eax, eax
0x1800ebe88  jz      short loc_1800EBEF1
0x1800ebe8a  mov     edx, [rsp+28h+arg_8]
0x1800ebe8e  mov     rcx, rbx
0x1800ebe91  call    cs:__imp_ASN1BEREncEndOfContents
0x1800ebe97  test    eax, eax
0x1800ebe99  jz      short loc_1800EBEF1
0x1800ebe9b  test    byte ptr [rdi], 40h
0x1800ebe9e  jz      short loc_1800EBED9
0x1800ebea0  lea     r8, [rsp+28h+arg_8]
0x1800ebea5  mov     edx, 80000001h
0x1800ebeaa  mov     rcx, rbx
0x1800ebead  call    cs:__imp_ASN1BEREncExplicitTag
0x1800ebeb3  test    eax, eax
0x1800ebeb5  jz      short loc_1800EBEF1
0x1800ebeb7  lea     rdx, [rdi+18h]
0x1800ebebb  mov     rcx, rbx
0x1800ebebe  call    cs:__imp_ASN1BEREncOpenType
0x1800ebec4  test    eax, eax
0x1800ebec6  jz      short loc_1800EBEF1
0x1800ebec8  mov     edx, [rsp+28h+arg_8]
0x1800ebecc  mov     rcx, rbx
0x1800ebecf  call    cs:__imp_ASN1BEREncEndOfContents
0x1800ebed5  test    eax, eax
0x1800ebed7  jz      short loc_1800EBEF1
0x1800ebed9  mov     edx, [rsp+28h+arg_18]
0x1800ebedd  mov     rcx, rbx
0x1800ebee0  call    cs:__imp_ASN1BEREncEndOfContents
0x1800ebee6  xor     ecx, ecx
0x1800ebee8  test    eax, eax
0x1800ebeea  setnz   cl
0x1800ebeed  mov     eax, ecx
0x1800ebeef  jmp     short loc_1800EBEF3
0x1800ebef1  xor     eax, eax
0x1800ebef3  mov     rbx, [rsp+28h+arg_0]
0x1800ebef8  add     rsp, 20h
0x1800ebefc  pop     rdi
0x1800ebefd  retn
```
