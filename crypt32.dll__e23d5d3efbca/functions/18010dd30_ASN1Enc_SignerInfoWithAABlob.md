# ASN1Enc_SignerInfoWithAABlob

- ea: `0x18010dd30`
- end: `0x18010de0e`
- name: `ASN1Enc_SignerInfoWithAABlob`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18010de20`

## callees

- `0x1800fe470`
- `0x18010dd30`

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x18010dd6c`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dd81`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dd92`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dda3`
- `MSASN1!ASN1BEREncOpenType` at `0x18010ddb4`
- `MSASN1!ASN1BEREncOpenType` at `0x18010ddc5`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dd6c`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dd81`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dd92`
- `MSASN1!ASN1BEREncOpenType` at `0x18010dda3`
- `MSASN1!ASN1BEREncOpenType` at `0x18010ddb4`
- `MSASN1!ASN1BEREncOpenType` at `0x18010ddc5`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18010ddf0`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18010ddf0`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18010dd57`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18010dd57`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_SignerInfoWithAABlob(__int64 a1, __int64 a2, char *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v6)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 8)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 24)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 40)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 56)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 72)
      && (unsigned int)ASN1BEREncOpenType(a1, a3 + 88)
      && (*a3 >= 0 || (unsigned int)ASN1Enc_SetOfAny(a1, 2147483649LL, a3 + 104))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6) != 0;
}

```

## disassembly

```asm
0x18010dd30  mov     [rsp+arg_0], rbx
0x18010dd35  push    rdi
0x18010dd36  sub     rsp, 20h
0x18010dd3a  test    edx, edx
0x18010dd3c  mov     [rsp+28h+arg_8], 0
0x18010dd44  mov     eax, 10h
0x18010dd49  mov     rbx, r8
0x18010dd4c  cmovz   edx, eax
0x18010dd4f  lea     r8, [rsp+28h+arg_8]
0x18010dd54  mov     rdi, rcx
0x18010dd57  call    cs:__imp_ASN1BEREncExplicitTag
0x18010dd5d  test    eax, eax
0x18010dd5f  jz      loc_18010DE01
0x18010dd65  lea     rdx, [rbx+8]
0x18010dd69  mov     rcx, rdi
0x18010dd6c  call    cs:__imp_ASN1BEREncOpenType
0x18010dd72  test    eax, eax
0x18010dd74  jz      loc_18010DE01
0x18010dd7a  lea     rdx, [rbx+18h]
0x18010dd7e  mov     rcx, rdi
0x18010dd81  call    cs:__imp_ASN1BEREncOpenType
0x18010dd87  test    eax, eax
0x18010dd89  jz      short loc_18010DE01
0x18010dd8b  lea     rdx, [rbx+28h]
0x18010dd8f  mov     rcx, rdi
0x18010dd92  call    cs:__imp_ASN1BEREncOpenType
0x18010dd98  test    eax, eax
0x18010dd9a  jz      short loc_18010DE01
0x18010dd9c  lea     rdx, [rbx+38h]
0x18010dda0  mov     rcx, rdi
0x18010dda3  call    cs:__imp_ASN1BEREncOpenType
0x18010dda9  test    eax, eax
0x18010ddab  jz      short loc_18010DE01
0x18010ddad  lea     rdx, [rbx+48h]
0x18010ddb1  mov     rcx, rdi
0x18010ddb4  call    cs:__imp_ASN1BEREncOpenType
0x18010ddba  test    eax, eax
0x18010ddbc  jz      short loc_18010DE01
0x18010ddbe  lea     rdx, [rbx+58h]
0x18010ddc2  mov     rcx, rdi
0x18010ddc5  call    cs:__imp_ASN1BEREncOpenType
0x18010ddcb  test    eax, eax
0x18010ddcd  jz      short loc_18010DE01
0x18010ddcf  cmp     byte ptr [rbx], 0
0x18010ddd2  jge     short loc_18010DDE9
0x18010ddd4  lea     r8, [rbx+68h]
0x18010ddd8  mov     edx, 80000001h
0x18010dddd  mov     rcx, rdi
0x18010dde0  call    ASN1Enc_SetOfAny
0x18010dde5  test    eax, eax
0x18010dde7  jz      short loc_18010DE01
0x18010dde9  mov     edx, [rsp+28h+arg_8]
0x18010dded  mov     rcx, rdi
0x18010ddf0  call    cs:__imp_ASN1BEREncEndOfContents
0x18010ddf6  xor     ecx, ecx
0x18010ddf8  test    eax, eax
0x18010ddfa  setnz   cl
0x18010ddfd  mov     eax, ecx
0x18010ddff  jmp     short loc_18010DE03
0x18010de01  xor     eax, eax
0x18010de03  mov     rbx, [rsp+28h+arg_0]
0x18010de08  add     rsp, 20h
0x18010de0c  pop     rdi
0x18010de0d  retn
```
