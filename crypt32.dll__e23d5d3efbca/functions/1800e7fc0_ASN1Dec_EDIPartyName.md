# ASN1Dec_EDIPartyName

- ea: `0x1800e7fc0`
- end: `0x1800e80f5`
- name: `ASN1Dec_EDIPartyName`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800e7fc0`

## import_xrefs

- `MSASN1!ASN1BERDecEndOfContents` at `0x1800e807a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800e80bd`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800e80d2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800e807a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800e80bd`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800e80d2`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800e802b`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800e802b`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800e8011`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800e804e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800e8095`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800e8011`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800e804e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800e8095`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800e8064`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800e80a7`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800e8064`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800e80a7`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_EDIPartyName(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+58h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+28h] BYREF

  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v8 = 0;
  v9 = 0;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, a2, &v12, &v10)
    && ((v5 = v12, *a3 = 0, !(unsigned int)ASN1BERDecPeekTag(v5, &v11))
     || v11 != 0x80000000
     || (v6 = v12, *a3 |= 0x80u, (unsigned int)ASN1BERDecExplicitTag(v6, 0x80000000LL, &v8, &v9))
     && (unsigned int)ASN1BERDecOpenType2(v8, a3 + 8)
     && (unsigned int)ASN1BERDecEndOfContents(v12, v8, v9))
    && (unsigned int)ASN1BERDecExplicitTag(v12, 2147483649LL, &v8, &v9)
    && (unsigned int)ASN1BERDecOpenType2(v8, a3 + 24)
    && (unsigned int)ASN1BERDecEndOfContents(v12, v8, v9) )
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
0x1800e7fc0  mov     [rsp-8+arg_0], rbx
0x1800e7fc5  mov     [rsp-8+arg_10], rdi
0x1800e7fca  push    rbp
0x1800e7fcb  mov     rbp, rsp
0x1800e7fce  sub     rsp, 40h
0x1800e7fd2  test    edx, edx
0x1800e7fd4  mov     [rbp+arg_18], 0
0x1800e7fdc  mov     eax, 10h
0x1800e7fe1  mov     [rbp+var_10], 0
0x1800e7fe9  mov     rbx, r8
0x1800e7fec  mov     [rbp+arg_8], 0
0x1800e7ff3  cmovz   edx, eax
0x1800e7ff6  mov     [rbp+var_20], 0
0x1800e7ffe  lea     r9, [rbp+var_10]
0x1800e8002  mov     [rbp+var_18], 0
0x1800e800a  lea     r8, [rbp+arg_18]
0x1800e800e  mov     rdi, rcx
0x1800e8011  call    cs:__imp_ASN1BERDecExplicitTag
0x1800e8017  test    eax, eax
0x1800e8019  jz      loc_1800E80E3
0x1800e801f  mov     rcx, [rbp+arg_18]
0x1800e8023  lea     rdx, [rbp+arg_8]
0x1800e8027  xor     eax, eax
0x1800e8029  mov     [rbx], al
0x1800e802b  call    cs:__imp_ASN1BERDecPeekTag
0x1800e8031  test    eax, eax
0x1800e8033  jz      short loc_1800E8084
0x1800e8035  mov     edx, 80000000h
0x1800e803a  cmp     [rbp+arg_8], edx
0x1800e803d  jnz     short loc_1800E8084
0x1800e803f  mov     rcx, [rbp+arg_18]
0x1800e8043  lea     r9, [rbp+var_18]
0x1800e8047  or      byte ptr [rbx], 80h
0x1800e804a  lea     r8, [rbp+var_20]
0x1800e804e  call    cs:__imp_ASN1BERDecExplicitTag
0x1800e8054  test    eax, eax
0x1800e8056  jz      loc_1800E80E3
0x1800e805c  mov     rcx, [rbp+var_20]
0x1800e8060  lea     rdx, [rbx+8]
0x1800e8064  call    cs:__imp_ASN1BERDecOpenType2
0x1800e806a  test    eax, eax
0x1800e806c  jz      short loc_1800E80E3
0x1800e806e  mov     r8, [rbp+var_18]
0x1800e8072  mov     rdx, [rbp+var_20]
0x1800e8076  mov     rcx, [rbp+arg_18]
0x1800e807a  call    cs:__imp_ASN1BERDecEndOfContents
0x1800e8080  test    eax, eax
0x1800e8082  jz      short loc_1800E80E3
0x1800e8084  mov     rcx, [rbp+arg_18]
0x1800e8088  lea     r9, [rbp+var_18]
0x1800e808c  lea     r8, [rbp+var_20]
0x1800e8090  mov     edx, 80000001h
0x1800e8095  call    cs:__imp_ASN1BERDecExplicitTag
0x1800e809b  test    eax, eax
0x1800e809d  jz      short loc_1800E80E3
0x1800e809f  mov     rcx, [rbp+var_20]
0x1800e80a3  lea     rdx, [rbx+18h]
0x1800e80a7  call    cs:__imp_ASN1BERDecOpenType2
0x1800e80ad  test    eax, eax
0x1800e80af  jz      short loc_1800E80E3
0x1800e80b1  mov     r8, [rbp+var_18]
0x1800e80b5  mov     rdx, [rbp+var_20]
0x1800e80b9  mov     rcx, [rbp+arg_18]
0x1800e80bd  call    cs:__imp_ASN1BERDecEndOfContents
0x1800e80c3  test    eax, eax
0x1800e80c5  jz      short loc_1800E80E3
0x1800e80c7  mov     r8, [rbp+var_10]
0x1800e80cb  mov     rcx, rdi
0x1800e80ce  mov     rdx, [rbp+arg_18]
0x1800e80d2  call    cs:__imp_ASN1BERDecEndOfContents
0x1800e80d8  xor     ecx, ecx
0x1800e80da  test    eax, eax
0x1800e80dc  setnz   cl
0x1800e80df  mov     eax, ecx
0x1800e80e1  jmp     short loc_1800E80E5
0x1800e80e3  xor     eax, eax
0x1800e80e5  mov     rbx, [rsp+40h+arg_0]
0x1800e80ea  mov     rdi, [rsp+40h+arg_10]
0x1800e80ef  add     rsp, 40h
0x1800e80f3  pop     rbp
0x1800e80f4  retn
```
