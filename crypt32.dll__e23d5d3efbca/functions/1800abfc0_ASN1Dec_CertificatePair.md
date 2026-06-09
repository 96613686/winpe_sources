# ASN1Dec_CertificatePair

- ea: `0x1800abfc0`
- end: `0x1800ac031`
- name: `ASN1Dec_CertificatePair`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800abfc0`

## import_xrefs

- `MSASN1!ASN1BERDecEndOfContents` at `0x18011dedd`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18011df46`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18011df5f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18011dedd`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18011df46`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18011df5f`
- `MSASN1!ASN1BERDecPeekTag` at `0x18011de8a`
- `MSASN1!ASN1BERDecPeekTag` at `0x18011def3`
- `MSASN1!ASN1BERDecPeekTag` at `0x18011de8a`
- `MSASN1!ASN1BERDecPeekTag` at `0x18011def3`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800ac011`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18011dead`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18011df16`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800ac011`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18011dead`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18011df16`
- `MSASN1!ASN1BERDecOpenType2` at `0x18011dec3`
- `MSASN1!ASN1BERDecOpenType2` at `0x18011df2c`
- `MSASN1!ASN1BERDecOpenType2` at `0x18011dec3`
- `MSASN1!ASN1BERDecOpenType2` at `0x18011df2c`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_CertificatePair(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+58h] [rbp+18h] BYREF
  __int64 v13; // [rsp+68h] [rbp+28h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v9 = 0;
  v10 = 0;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v13, &v11)
    && ((v6 = v13, *a3 = 0, !(unsigned int)ASN1BERDecPeekTag(v6, &v12))
     || v12 != 0x80000000
     || (v7 = v13, *a3 |= 0x80u, (unsigned int)ASN1BERDecExplicitTag(v7, 0x80000000LL, &v9, &v10))
     && (unsigned int)ASN1BERDecOpenType2(v9, a3 + 8)
     && (unsigned int)ASN1BERDecEndOfContents(v13, v9, v10))
    && (!(unsigned int)ASN1BERDecPeekTag(v13, &v12)
     || v12 != -2147483647
     || (v8 = v13, *a3 |= 0x40u, (unsigned int)ASN1BERDecExplicitTag(v8, 2147483649LL, &v9, &v10))
     && (unsigned int)ASN1BERDecOpenType2(v9, a3 + 24)
     && (unsigned int)ASN1BERDecEndOfContents(v13, v9, v10)) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v13, v11) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800abfc0  mov     [rsp-8+arg_0], rbx
0x1800abfc5  mov     [rsp-8+arg_10], rdi
0x1800abfca  push    rbp
0x1800abfcb  mov     rbp, rsp
0x1800abfce  sub     rsp, 40h
0x1800abfd2  test    edx, edx
0x1800abfd4  mov     [rbp+arg_18], 0
0x1800abfdc  mov     eax, 10h
0x1800abfe1  mov     [rbp+var_10], 0
0x1800abfe9  mov     rbx, r8
0x1800abfec  mov     [rbp+arg_8], 0
0x1800abff3  cmovz   edx, eax
0x1800abff6  mov     [rbp+var_20], 0
0x1800abffe  lea     r9, [rbp+var_10]
0x1800ac002  mov     [rbp+var_18], 0
0x1800ac00a  lea     r8, [rbp+arg_18]
0x1800ac00e  mov     rdi, rcx
0x1800ac011  call    cs:__imp_ASN1BERDecExplicitTag
0x1800ac017  test    eax, eax
0x1800ac019  jnz     loc_18011DE7E
0x1800ac01f  xor     eax, eax
0x1800ac021  mov     rbx, [rsp+40h+arg_0]
0x1800ac026  mov     rdi, [rsp+40h+arg_10]
0x1800ac02b  add     rsp, 40h
0x1800ac02f  pop     rbp
0x1800ac030  retn
0x18011de7e  mov     rcx, [rbp+arg_18]
0x18011de82  lea     rdx, [rbp+arg_8]
0x18011de86  xor     eax, eax
0x18011de88  mov     [rbx], al
0x18011de8a  call    cs:__imp_ASN1BERDecPeekTag
0x18011de90  test    eax, eax
0x18011de92  jz      short loc_18011DEEB
0x18011de94  mov     edx, 80000000h
0x18011de99  cmp     [rbp+arg_8], edx
0x18011de9c  jnz     short loc_18011DEEB
0x18011de9e  mov     rcx, [rbp+arg_18]
0x18011dea2  lea     r9, [rbp+var_18]
0x18011dea6  or      byte ptr [rbx], 80h
0x18011dea9  lea     r8, [rbp+var_20]
0x18011dead  call    cs:__imp_ASN1BERDecExplicitTag
0x18011deb3  test    eax, eax
0x18011deb5  jz      loc_1800AC01F
0x18011debb  mov     rcx, [rbp+var_20]
0x18011debf  lea     rdx, [rbx+8]
0x18011dec3  call    cs:__imp_ASN1BERDecOpenType2
0x18011dec9  test    eax, eax
0x18011decb  jz      loc_1800AC01F
0x18011ded1  mov     r8, [rbp+var_18]
0x18011ded5  mov     rdx, [rbp+var_20]
0x18011ded9  mov     rcx, [rbp+arg_18]
0x18011dedd  call    cs:__imp_ASN1BERDecEndOfContents
0x18011dee3  test    eax, eax
0x18011dee5  jz      loc_1800AC01F
0x18011deeb  mov     rcx, [rbp+arg_18]
0x18011deef  lea     rdx, [rbp+arg_8]
0x18011def3  call    cs:__imp_ASN1BERDecPeekTag
0x18011def9  test    eax, eax
0x18011defb  jz      short loc_18011DF54
0x18011defd  mov     edx, 80000001h
0x18011df02  cmp     [rbp+arg_8], edx
0x18011df05  jnz     short loc_18011DF54
0x18011df07  mov     rcx, [rbp+arg_18]
0x18011df0b  lea     r9, [rbp+var_18]
0x18011df0f  or      byte ptr [rbx], 40h
0x18011df12  lea     r8, [rbp+var_20]
0x18011df16  call    cs:__imp_ASN1BERDecExplicitTag
0x18011df1c  test    eax, eax
0x18011df1e  jz      loc_1800AC01F
0x18011df24  mov     rcx, [rbp+var_20]
0x18011df28  lea     rdx, [rbx+18h]
0x18011df2c  call    cs:__imp_ASN1BERDecOpenType2
0x18011df32  test    eax, eax
0x18011df34  jz      loc_1800AC01F
0x18011df3a  mov     r8, [rbp+var_18]
0x18011df3e  mov     rdx, [rbp+var_20]
0x18011df42  mov     rcx, [rbp+arg_18]
0x18011df46  call    cs:__imp_ASN1BERDecEndOfContents
0x18011df4c  test    eax, eax
0x18011df4e  jz      loc_1800AC01F
0x18011df54  mov     r8, [rbp+var_10]
0x18011df58  mov     rcx, rdi
0x18011df5b  mov     rdx, [rbp+arg_18]
0x18011df5f  call    cs:__imp_ASN1BERDecEndOfContents
0x18011df65  xor     ecx, ecx
0x18011df67  test    eax, eax
0x18011df69  setnz   cl
0x18011df6c  mov     eax, ecx
0x18011df6e  jmp     loc_1800AC021
```
