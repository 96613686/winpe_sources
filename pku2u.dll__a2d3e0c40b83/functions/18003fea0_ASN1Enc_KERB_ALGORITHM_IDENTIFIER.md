# ASN1Enc_KERB_ALGORITHM_IDENTIFIER

- ea: `0x18003fea0`
- end: `0x18003ff22`
- name: `ASN1Enc_KERB_ALGORITHM_IDENTIFIER`
- size: `130`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180040380`
- `0x180040520`
- `0x18004223c`
- `0x180042ab0`

## callees

- `0x18003fea0`

## import_xrefs

- `MSASN1!ASN1BEREncEndOfContents` at `0x18003ff04`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18003ff04`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x18003fedd`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x18003fedd`
- `MSASN1!ASN1BEREncOpenType` at `0x18003fef3`
- `MSASN1!ASN1BEREncOpenType` at `0x18003fef3`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18003fec7`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18003fec7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, char *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  return (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v6)
      && (unsigned int)ASN1BEREncObjectIdentifier(a1, 6, a3 + 8)
      && (*a3 >= 0 || (unsigned int)ASN1BEREncOpenType(a1, a3 + 16))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6) != 0;
}

```

## disassembly

```asm
0x18003fea0  mov     [rsp+arg_0], rbx
0x18003fea5  push    rdi
0x18003fea6  sub     rsp, 20h
0x18003feaa  test    edx, edx
0x18003feac  mov     [rsp+28h+arg_8], 0
0x18003feb4  mov     eax, 10h
0x18003feb9  mov     rbx, r8
0x18003febc  cmovz   edx, eax
0x18003febf  lea     r8, [rsp+28h+arg_8]
0x18003fec4  mov     rdi, rcx
0x18003fec7  call    cs:__imp_ASN1BEREncExplicitTag
0x18003fecd  test    eax, eax
0x18003fecf  jz      short loc_18003FF15
0x18003fed1  lea     r8, [rbx+8]
0x18003fed5  mov     edx, 6
0x18003feda  mov     rcx, rdi
0x18003fedd  call    cs:__imp_ASN1BEREncObjectIdentifier
0x18003fee3  test    eax, eax
0x18003fee5  jz      short loc_18003FF15
0x18003fee7  cmp     byte ptr [rbx], 0
0x18003feea  jge     short loc_18003FEFD
0x18003feec  lea     rdx, [rbx+10h]
0x18003fef0  mov     rcx, rdi
0x18003fef3  call    cs:__imp_ASN1BEREncOpenType
0x18003fef9  test    eax, eax
0x18003fefb  jz      short loc_18003FF15
0x18003fefd  mov     edx, [rsp+28h+arg_8]
0x18003ff01  mov     rcx, rdi
0x18003ff04  call    cs:__imp_ASN1BEREncEndOfContents
0x18003ff0a  xor     ecx, ecx
0x18003ff0c  test    eax, eax
0x18003ff0e  setnz   cl
0x18003ff11  mov     eax, ecx
0x18003ff13  jmp     short loc_18003FF17
0x18003ff15  xor     eax, eax
0x18003ff17  mov     rbx, [rsp+28h+arg_0]
0x18003ff1c  add     rsp, 20h
0x18003ff20  pop     rdi
0x18003ff21  retn
```
