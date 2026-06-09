# ASN1Dec_SignedContent

- ea: `0x180083440`
- end: `0x18008357c`
- name: `ASN1Dec_SignedContent`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180083440`

## import_xrefs

- `MSASN1!ASN1BERDecEoid` at `0x1800834e9`
- `MSASN1!ASN1BERDecEoid` at `0x1800834e9`
- `MSASN1!ASN1BERDecBitString2` at `0x180083541`
- `MSASN1!ASN1BERDecBitString2` at `0x180083541`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18008352a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180083556`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18008352a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180083556`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800834ff`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800834ff`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18008347f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800834cb`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18008347f`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800834cb`
- `MSASN1!ASN1BERDecOpenType2` at `0x180083494`
- `MSASN1!ASN1BERDecOpenType2` at `0x180083515`
- `MSASN1!ASN1BERDecOpenType2` at `0x180083494`
- `MSASN1!ASN1BERDecOpenType2` at `0x180083515`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SignedContent(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+68h] [rbp+28h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  v9 = 0;
  v11 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v9, &v11) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOpenType2(v9, a3) )
    return 0;
  v5 = v9;
  v13 = 0;
  v10 = 0;
  v12 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v9, 16, &v13, &v10) )
    return 0;
  v6 = v13;
  *(_BYTE *)(a3 + 16) = 0;
  if ( !(unsigned int)ASN1BERDecEoid(v6, 6, a3 + 24) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v13, &v12) )
  {
    v7 = v13;
    *(_BYTE *)(a3 + 16) |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType2(v7, a3 + 40) )
      return 0;
  }
  return (unsigned int)ASN1BERDecEndOfContents(v5, v13, v10)
      && (unsigned int)ASN1BERDecBitString2(v9, 3, a3 + 56)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v9, v11) != 0;
}

```

## disassembly

```asm
0x180083440  mov     [rsp-18h+arg_0], rbx
0x180083445  mov     [rsp-18h+arg_10], rsi
0x18008344a  push    rbp
0x18008344b  push    rdi
0x18008344c  push    r15
0x18008344e  mov     rbp, rsp
0x180083451  sub     rsp, 40h
0x180083455  test    edx, edx
0x180083457  mov     [rbp+var_20], 0
0x18008345f  mov     rbx, r8
0x180083462  mov     [rbp+var_10], 0
0x18008346a  mov     r15d, 10h
0x180083470  lea     r9, [rbp+var_10]
0x180083474  cmovz   edx, r15d
0x180083478  lea     r8, [rbp+var_20]
0x18008347c  mov     rsi, rcx
0x18008347f  call    cs:__imp_ASN1BERDecExplicitTag
0x180083485  test    eax, eax
0x180083487  jz      loc_180083578
0x18008348d  mov     rcx, [rbp+var_20]
0x180083491  mov     rdx, rbx
0x180083494  call    cs:__imp_ASN1BERDecOpenType2
0x18008349a  test    eax, eax
0x18008349c  jz      loc_180083578
0x1800834a2  mov     rdi, [rbp+var_20]
0x1800834a6  lea     r9, [rbp+var_18]
0x1800834aa  mov     rcx, rdi
0x1800834ad  mov     [rbp+arg_18], 0
0x1800834b5  lea     r8, [rbp+arg_18]
0x1800834b9  mov     [rbp+var_18], 0
0x1800834c1  mov     edx, r15d
0x1800834c4  mov     [rbp+arg_8], 0
0x1800834cb  call    cs:__imp_ASN1BERDecExplicitTag
0x1800834d1  test    eax, eax
0x1800834d3  jz      loc_180083578
0x1800834d9  mov     rcx, [rbp+arg_18]
0x1800834dd  lea     r8, [rbx+18h]
0x1800834e1  xor     eax, eax
0x1800834e3  mov     [rbx+10h], al
0x1800834e6  lea     edx, [rax+6]
0x1800834e9  call    cs:__imp_ASN1BERDecEoid
0x1800834ef  test    eax, eax
0x1800834f1  jz      loc_180083578
0x1800834f7  mov     rcx, [rbp+arg_18]
0x1800834fb  lea     rdx, [rbp+arg_8]
0x1800834ff  call    cs:__imp_ASN1BERDecPeekTag
0x180083505  test    eax, eax
0x180083507  jz      short loc_18008351F
0x180083509  mov     rcx, [rbp+arg_18]
0x18008350d  lea     rdx, [rbx+28h]
0x180083511  or      byte ptr [rbx+10h], 80h
0x180083515  call    cs:__imp_ASN1BERDecOpenType2
0x18008351b  test    eax, eax
0x18008351d  jz      short loc_180083578
0x18008351f  mov     r8, [rbp+var_18]
0x180083523  mov     rcx, rdi
0x180083526  mov     rdx, [rbp+arg_18]
0x18008352a  call    cs:__imp_ASN1BERDecEndOfContents
0x180083530  test    eax, eax
0x180083532  jz      short loc_180083578
0x180083534  mov     rcx, [rbp+var_20]
0x180083538  lea     r8, [rbx+38h]
0x18008353c  mov     edx, 3
0x180083541  call    cs:__imp_ASN1BERDecBitString2
0x180083547  test    eax, eax
0x180083549  jz      short loc_180083578
0x18008354b  mov     r8, [rbp+var_10]
0x18008354f  mov     rcx, rsi
0x180083552  mov     rdx, [rbp+var_20]
0x180083556  call    cs:__imp_ASN1BERDecEndOfContents
0x18008355c  xor     ecx, ecx
0x18008355e  test    eax, eax
0x180083560  setnz   cl
0x180083563  mov     eax, ecx
0x180083565  mov     rbx, [rsp+40h+arg_0]
0x18008356a  mov     rsi, [rsp+40h+arg_10]
0x18008356f  add     rsp, 40h
0x180083573  pop     r15
0x180083575  pop     rdi
0x180083576  pop     rbp
0x180083577  retn
0x180083578  xor     eax, eax
0x18008357a  jmp     short loc_180083565
```
