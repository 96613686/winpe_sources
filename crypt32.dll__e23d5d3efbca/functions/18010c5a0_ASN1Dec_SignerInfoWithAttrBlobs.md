# ASN1Dec_SignerInfoWithAttrBlobs

- ea: `0x18010c5a0`
- end: `0x18010c6e4`
- name: `ASN1Dec_SignerInfoWithAttrBlobs`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18008cc88`
- `0x18010a880`
- `0x18010c5a0`

## import_xrefs

- `MSASN1!ASN1BERDecEndOfContents` at `0x18010c6c1`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18010c6c1`
- `MSASN1!ASN1BERDecPeekTag` at `0x18010c63d`
- `MSASN1!ASN1BERDecPeekTag` at `0x18010c68f`
- `MSASN1!ASN1BERDecPeekTag` at `0x18010c63d`
- `MSASN1!ASN1BERDecPeekTag` at `0x18010c68f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18010c5e1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18010c5e1`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c5fb`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c611`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c627`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c67d`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c5fb`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c611`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c627`
- `MSASN1!ASN1BERDecOpenType2` at `0x18010c67d`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SignerInfoWithAttrBlobs(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+48h] [rbp+18h] BYREF
  __int64 v12; // [rsp+58h] [rbp+28h] BYREF

  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v12, &v10) )
    return 0;
  v5 = v12;
  *a3 = 0;
  if ( !(unsigned int)ASN1BERDecOpenType2(v5, a3 + 8) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOpenType2(v12, a3 + 24) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOpenType2(v12, a3 + 40) )
    return 0;
  ASN1BERDecPeekTag(v12, &v11);
  v6 = 0x80000000LL;
  if ( v11 == 0x80000000 )
  {
    v7 = v12;
    *a3 |= 0x80u;
    if ( !(unsigned int)ASN1Dec_DigestAlgorithmBlobs(v7, 0x80000000LL, a3 + 56) )
      return 0;
  }
  if ( (unsigned int)ASN1Dec_DigestEncryptionAlgIdNC(v12, v6, a3 + 72)
    && (unsigned int)ASN1BERDecOpenType2(v12, a3 + 160)
    && ((ASN1BERDecPeekTag(v12, &v11), v11 != -2147483647)
     || (v8 = v12, *a3 |= 0x40u, (unsigned int)ASN1Dec_DigestAlgorithmBlobs(v8, 2147483649LL, a3 + 176))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v12, v10) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18010c5a0  mov     [rsp-8+arg_0], rbx
0x18010c5a5  mov     [rsp-8+arg_10], rdi
0x18010c5aa  push    rbp
0x18010c5ab  mov     rbp, rsp
0x18010c5ae  sub     rsp, 30h
0x18010c5b2  test    edx, edx
0x18010c5b4  mov     [rbp+arg_18], 0
0x18010c5bc  mov     eax, 10h
0x18010c5c1  mov     [rbp+var_10], 0
0x18010c5c9  mov     rbx, r8
0x18010c5cc  mov     [rbp+arg_8], 0
0x18010c5d3  cmovz   edx, eax
0x18010c5d6  lea     r9, [rbp+var_10]
0x18010c5da  lea     r8, [rbp+arg_18]
0x18010c5de  mov     rdi, rcx
0x18010c5e1  call    cs:__imp_ASN1BERDecExplicitTag
0x18010c5e7  test    eax, eax
0x18010c5e9  jz      loc_18010C6D2
0x18010c5ef  mov     rcx, [rbp+arg_18]
0x18010c5f3  lea     rdx, [rbx+8]
0x18010c5f7  xor     eax, eax
0x18010c5f9  mov     [rbx], al
0x18010c5fb  call    cs:__imp_ASN1BERDecOpenType2
0x18010c601  test    eax, eax
0x18010c603  jz      loc_18010C6D2
0x18010c609  mov     rcx, [rbp+arg_18]
0x18010c60d  lea     rdx, [rbx+18h]
0x18010c611  call    cs:__imp_ASN1BERDecOpenType2
0x18010c617  test    eax, eax
0x18010c619  jz      loc_18010C6D2
0x18010c61f  mov     rcx, [rbp+arg_18]
0x18010c623  lea     rdx, [rbx+28h]
0x18010c627  call    cs:__imp_ASN1BERDecOpenType2
0x18010c62d  test    eax, eax
0x18010c62f  jz      loc_18010C6D2
0x18010c635  mov     rcx, [rbp+arg_18]
0x18010c639  lea     rdx, [rbp+arg_8]
0x18010c63d  call    cs:__imp_ASN1BERDecPeekTag
0x18010c643  mov     edx, 80000000h
0x18010c648  cmp     [rbp+arg_8], edx
0x18010c64b  jnz     short loc_18010C661
0x18010c64d  mov     rcx, [rbp+arg_18]
0x18010c651  lea     r8, [rbx+38h]
0x18010c655  or      byte ptr [rbx], 80h
0x18010c658  call    ASN1Dec_DigestAlgorithmBlobs
0x18010c65d  test    eax, eax
0x18010c65f  jz      short loc_18010C6D2
0x18010c661  mov     rcx, [rbp+arg_18]
0x18010c665  lea     r8, [rbx+48h]
0x18010c669  call    ASN1Dec_DigestEncryptionAlgIdNC
0x18010c66e  test    eax, eax
0x18010c670  jz      short loc_18010C6D2
0x18010c672  mov     rcx, [rbp+arg_18]
0x18010c676  lea     rdx, [rbx+0A0h]
0x18010c67d  call    cs:__imp_ASN1BERDecOpenType2
0x18010c683  test    eax, eax
0x18010c685  jz      short loc_18010C6D2
0x18010c687  mov     rcx, [rbp+arg_18]
0x18010c68b  lea     rdx, [rbp+arg_8]
0x18010c68f  call    cs:__imp_ASN1BERDecPeekTag
0x18010c695  mov     edx, 80000001h
0x18010c69a  cmp     [rbp+arg_8], edx
0x18010c69d  jnz     short loc_18010C6B6
0x18010c69f  mov     rcx, [rbp+arg_18]
0x18010c6a3  lea     r8, [rbx+0B0h]
0x18010c6aa  or      byte ptr [rbx], 40h
0x18010c6ad  call    ASN1Dec_DigestAlgorithmBlobs
0x18010c6b2  test    eax, eax
0x18010c6b4  jz      short loc_18010C6D2
0x18010c6b6  mov     r8, [rbp+var_10]
0x18010c6ba  mov     rcx, rdi
0x18010c6bd  mov     rdx, [rbp+arg_18]
0x18010c6c1  call    cs:__imp_ASN1BERDecEndOfContents
0x18010c6c7  xor     ecx, ecx
0x18010c6c9  test    eax, eax
0x18010c6cb  setnz   cl
0x18010c6ce  mov     eax, ecx
0x18010c6d0  jmp     short loc_18010C6D4
0x18010c6d2  xor     eax, eax
0x18010c6d4  mov     rbx, [rsp+30h+arg_0]
0x18010c6d9  mov     rdi, [rsp+30h+arg_10]
0x18010c6de  add     rsp, 30h
0x18010c6e2  pop     rbp
0x18010c6e3  retn
```
