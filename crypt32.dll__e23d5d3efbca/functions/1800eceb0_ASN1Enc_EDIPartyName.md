# ASN1Enc_EDIPartyName

- ea: `0x1800eceb0`
- end: `0x1800ecf89`
- name: `ASN1Enc_EDIPartyName`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800eceb0`

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x1800ecf10`
- `MSASN1!ASN1BEREncOpenType` at `0x1800ecf49`
- `MSASN1!ASN1BEREncOpenType` at `0x1800ecf10`
- `MSASN1!ASN1BEREncOpenType` at `0x1800ecf49`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ecf21`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ecf5a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ecf6b`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ecf21`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ecf5a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800ecf6b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ecedf`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800eceff`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ecf38`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ecedf`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800eceff`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800ecf38`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_EDIPartyName(__int64 a1, __int64 a2, char *a3)
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
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v6)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 24)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6)
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7) != 0;
}

```

## disassembly

```asm
0x1800eceb0  mov     [rsp+arg_0], rbx
0x1800eceb5  push    rdi
0x1800eceb6  sub     rsp, 20h
0x1800eceba  test    edx, edx
0x1800ecebc  mov     [rsp+28h+arg_18], 0
0x1800ecec4  mov     eax, 10h
0x1800ecec9  mov     [rsp+28h+arg_8], 0
0x1800eced1  mov     rdi, r8
0x1800eced4  cmovz   edx, eax
0x1800eced7  lea     r8, [rsp+28h+arg_18]
0x1800ecedc  mov     rbx, rcx
0x1800ecedf  call    cs:__imp_ASN1BEREncExplicitTag
0x1800ecee5  test    eax, eax
0x1800ecee7  jz      loc_1800ECF7C
0x1800eceed  cmp     byte ptr [rdi], 0
0x1800ecef0  jge     short loc_1800ECF2B
0x1800ecef2  lea     r8, [rsp+28h+arg_8]
0x1800ecef7  mov     edx, 80000000h
0x1800ecefc  mov     rcx, rbx
0x1800eceff  call    cs:__imp_ASN1BEREncExplicitTag
0x1800ecf05  test    eax, eax
0x1800ecf07  jz      short loc_1800ECF7C
0x1800ecf09  lea     rdx, [rdi+8]
0x1800ecf0d  mov     rcx, rbx
0x1800ecf10  call    cs:__imp_ASN1BEREncOpenType
0x1800ecf16  test    eax, eax
0x1800ecf18  jz      short loc_1800ECF7C
0x1800ecf1a  mov     edx, [rsp+28h+arg_8]
0x1800ecf1e  mov     rcx, rbx
0x1800ecf21  call    cs:__imp_ASN1BEREncEndOfContents
0x1800ecf27  test    eax, eax
0x1800ecf29  jz      short loc_1800ECF7C
0x1800ecf2b  lea     r8, [rsp+28h+arg_8]
0x1800ecf30  mov     edx, 80000001h
0x1800ecf35  mov     rcx, rbx
0x1800ecf38  call    cs:__imp_ASN1BEREncExplicitTag
0x1800ecf3e  test    eax, eax
0x1800ecf40  jz      short loc_1800ECF7C
0x1800ecf42  lea     rdx, [rdi+18h]
0x1800ecf46  mov     rcx, rbx
0x1800ecf49  call    cs:__imp_ASN1BEREncOpenType
0x1800ecf4f  test    eax, eax
0x1800ecf51  jz      short loc_1800ECF7C
0x1800ecf53  mov     edx, [rsp+28h+arg_8]
0x1800ecf57  mov     rcx, rbx
0x1800ecf5a  call    cs:__imp_ASN1BEREncEndOfContents
0x1800ecf60  test    eax, eax
0x1800ecf62  jz      short loc_1800ECF7C
0x1800ecf64  mov     edx, [rsp+28h+arg_18]
0x1800ecf68  mov     rcx, rbx
0x1800ecf6b  call    cs:__imp_ASN1BEREncEndOfContents
0x1800ecf71  xor     ecx, ecx
0x1800ecf73  test    eax, eax
0x1800ecf75  setnz   cl
0x1800ecf78  mov     eax, ecx
0x1800ecf7a  jmp     short loc_1800ECF7E
0x1800ecf7c  xor     eax, eax
0x1800ecf7e  mov     rbx, [rsp+28h+arg_0]
0x1800ecf83  add     rsp, 20h
0x1800ecf87  pop     rdi
0x1800ecf88  retn
```
