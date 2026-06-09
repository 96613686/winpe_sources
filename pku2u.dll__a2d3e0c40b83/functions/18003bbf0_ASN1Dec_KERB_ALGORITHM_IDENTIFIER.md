# ASN1Dec_KERB_ALGORITHM_IDENTIFIER

- ea: `0x18003bbf0`
- end: `0x18003bca5`
- name: `ASN1Dec_KERB_ALGORITHM_IDENTIFIER`
- size: `181`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bfa0`
- `0x18003eaa8`
- `0x18003ebc0`
- `0x18003f800`

## callees

- `0x18003bbf0`

## import_xrefs

- `MSASN1!ASN1BERDecObjectIdentifier` at `0x18003bc46`
- `MSASN1!ASN1BERDecObjectIdentifier` at `0x18003bc46`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18003bc87`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18003bc87`
- `MSASN1!ASN1BERDecPeekTag` at `0x18003bc5a`
- `MSASN1!ASN1BERDecPeekTag` at `0x18003bc5a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18003bc2c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18003bc2c`
- `MSASN1!ASN1BERDecOpenType2` at `0x18003bc70`
- `MSASN1!ASN1BERDecOpenType2` at `0x18003bc70`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_KERB_ALGORITHM_IDENTIFIER(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v10, v8)
    && (v5 = v10, *a3 = 0, (unsigned int)ASN1BERDecObjectIdentifier(v5, 6, a3 + 8))
    && (!(unsigned int)ASN1BERDecPeekTag(v10, &v9)
     || (v6 = v10, *a3 |= 0x80u, (unsigned int)ASN1BERDecOpenType2(v6, a3 + 16))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8[0]) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18003bbf0  mov     r11, rsp
0x18003bbf3  mov     [r11+8], rbx
0x18003bbf7  push    rdi
0x18003bbf8  sub     rsp, 30h
0x18003bbfc  test    edx, edx
0x18003bbfe  mov     qword ptr [r11+20h], 0
0x18003bc06  mov     eax, 10h
0x18003bc0b  mov     qword ptr [r11-18h], 0
0x18003bc13  mov     rbx, r8
0x18003bc16  mov     [rsp+38h+arg_8], 0
0x18003bc1e  cmovz   edx, eax
0x18003bc21  lea     r9, [r11-18h]
0x18003bc25  lea     r8, [r11+20h]
0x18003bc29  mov     rdi, rcx
0x18003bc2c  call    cs:__imp_ASN1BERDecExplicitTag
0x18003bc32  test    eax, eax
0x18003bc34  jz      short loc_18003BC98
0x18003bc36  mov     rcx, [rsp+38h+arg_18]
0x18003bc3b  lea     r8, [rbx+8]
0x18003bc3f  xor     eax, eax
0x18003bc41  mov     [rbx], al
0x18003bc43  lea     edx, [rax+6]
0x18003bc46  call    cs:__imp_ASN1BERDecObjectIdentifier
0x18003bc4c  test    eax, eax
0x18003bc4e  jz      short loc_18003BC98
0x18003bc50  mov     rcx, [rsp+38h+arg_18]
0x18003bc55  lea     rdx, [rsp+38h+arg_8]
0x18003bc5a  call    cs:__imp_ASN1BERDecPeekTag
0x18003bc60  test    eax, eax
0x18003bc62  jz      short loc_18003BC7A
0x18003bc64  mov     rcx, [rsp+38h+arg_18]
0x18003bc69  lea     rdx, [rbx+10h]
0x18003bc6d  or      byte ptr [rbx], 80h
0x18003bc70  call    cs:__imp_ASN1BERDecOpenType2
0x18003bc76  test    eax, eax
0x18003bc78  jz      short loc_18003BC98
0x18003bc7a  mov     r8, [rsp+38h+var_18]
0x18003bc7f  mov     rcx, rdi
0x18003bc82  mov     rdx, [rsp+38h+arg_18]
0x18003bc87  call    cs:__imp_ASN1BERDecEndOfContents
0x18003bc8d  xor     ecx, ecx
0x18003bc8f  test    eax, eax
0x18003bc91  setnz   cl
0x18003bc94  mov     eax, ecx
0x18003bc96  jmp     short loc_18003BC9A
0x18003bc98  xor     eax, eax
0x18003bc9a  mov     rbx, [rsp+38h+arg_0]
0x18003bc9f  add     rsp, 30h
0x18003bca3  pop     rdi
0x18003bca4  retn
```
