# ASN1Enc_KERB_ALGORITHM_IDENTIFIER

- ea: `0x180073b20`
- end: `0x180073ba2`
- name: `ASN1Enc_KERB_ALGORITHM_IDENTIFIER`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180074568`
- `0x1800791cc`
- `0x18007953c`
- `0x18007a4c0`
- `0x18007aee0`

## callees

- `0x180073b20`

## import_xrefs

- `MSASN1!ASN1BEREncObjectIdentifier` at `0x180073b5d`
- `MSASN1!ASN1BEREncObjectIdentifier` at `0x180073b5d`
- `MSASN1!ASN1BEREncOpenType` at `0x180073b73`
- `MSASN1!ASN1BEREncOpenType` at `0x180073b73`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180073b84`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180073b84`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180073b47`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180073b47`

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
0x180073b20  mov     [rsp+arg_0], rbx
0x180073b25  push    rdi
0x180073b26  sub     rsp, 20h
0x180073b2a  test    edx, edx
0x180073b2c  mov     [rsp+28h+arg_8], 0
0x180073b34  mov     eax, 10h
0x180073b39  mov     rbx, r8
0x180073b3c  cmovz   edx, eax
0x180073b3f  lea     r8, [rsp+28h+arg_8]
0x180073b44  mov     rdi, rcx
0x180073b47  call    cs:__imp_ASN1BEREncExplicitTag
0x180073b4d  test    eax, eax
0x180073b4f  jz      short loc_180073B95
0x180073b51  lea     r8, [rbx+8]
0x180073b55  mov     edx, 6
0x180073b5a  mov     rcx, rdi
0x180073b5d  call    cs:__imp_ASN1BEREncObjectIdentifier
0x180073b63  test    eax, eax
0x180073b65  jz      short loc_180073B95
0x180073b67  cmp     byte ptr [rbx], 0
0x180073b6a  jge     short loc_180073B7D
0x180073b6c  lea     rdx, [rbx+10h]
0x180073b70  mov     rcx, rdi
0x180073b73  call    cs:__imp_ASN1BEREncOpenType
0x180073b79  test    eax, eax
0x180073b7b  jz      short loc_180073B95
0x180073b7d  mov     edx, [rsp+28h+arg_8]
0x180073b81  mov     rcx, rdi
0x180073b84  call    cs:__imp_ASN1BEREncEndOfContents
0x180073b8a  xor     ecx, ecx
0x180073b8c  test    eax, eax
0x180073b8e  setnz   cl
0x180073b91  mov     eax, ecx
0x180073b93  jmp     short loc_180073B97
0x180073b95  xor     eax, eax
0x180073b97  mov     rbx, [rsp+28h+arg_0]
0x180073b9c  add     rsp, 20h
0x180073ba0  pop     rdi
0x180073ba1  retn
```
