# ASN1Dec_SignerInfoWithBlobs

- ea: `0x18007aa40`
- end: `0x18007ae70`
- name: `ASN1Dec_SignerInfoWithBlobs`
- size: `1072`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18007aa40`
- `0x18007ae80`

## import_xrefs

- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007abb1`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007acbe`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007abb1`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18007acbe`
- `MSASN1!ASN1BERDecOctetString2` at `0x18007ad20`
- `MSASN1!ASN1BERDecOctetString2` at `0x18007ad20`
- `MSASN1!ASN1DecRealloc` at `0x18007adee`
- `MSASN1!ASN1DecRealloc` at `0x18007ae17`
- `MSASN1!ASN1DecRealloc` at `0x18007adee`
- `MSASN1!ASN1DecRealloc` at `0x18007ae17`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ac78`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ad02`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ad6c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ad8c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ada8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ac78`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ad02`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ad6c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ad8c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18007ada8`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18007ab3a`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18007abf8`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18007ab3a`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18007abf8`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007aae2`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007ab50`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007ac0e`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007acd0`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007ad36`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007aae2`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007ab50`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007ac0e`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007acd0`
- `MSASN1!ASN1BERDecPeekTag` at `0x18007ad36`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007aa83`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007ab14`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007ab90`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007abde`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007aca4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007aa83`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007ab14`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007ab90`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007abde`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18007aca4`
- `MSASN1!ASN1DecSetError` at `0x18007ac4d`
- `MSASN1!ASN1DecSetError` at `0x18007ac4d`
- `MSASN1!ASN1BERDecS32Val` at `0x18007aaa0`
- `MSASN1!ASN1BERDecS32Val` at `0x18007aaa0`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007aab6`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007aacc`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007ace9`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007ae43`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007aab6`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007aacc`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007ace9`
- `MSASN1!ASN1BERDecOpenType2` at `0x18007ae43`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SignerInfoWithBlobs(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // r13
  unsigned int v7; // esi
  __int64 v8; // rdi
  __int64 v9; // r12
  __int64 v10; // r14
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // r15
  unsigned int v14; // edi
  __int64 v15; // rcx
  unsigned __int64 v16; // r8
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-50h] BYREF
  __int64 v28; // [rsp+28h] [rbp-48h] BYREF
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  __int64 v30; // [rsp+38h] [rbp-38h] BYREF
  __int64 v31; // [rsp+40h] [rbp-30h] BYREF
  int v32; // [rsp+48h] [rbp-28h] BYREF
  __int64 v33; // [rsp+50h] [rbp-20h] BYREF
  __int64 v34; // [rsp+58h] [rbp-18h] BYREF
  __int64 v35; // [rsp+60h] [rbp-10h] BYREF
  int v37; // [rsp+B8h] [rbp+48h] BYREF
  int v38; // [rsp+C8h] [rbp+58h] BYREF

  v28 = 0;
  v35 = 0;
  v37 = 0;
  v4 = a1;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v28, &v35, v27) )
    return 0;
  v5 = v28;
  *(_BYTE *)a3 = 0;
  if ( !(unsigned int)ASN1BERDecS32Val(v5, 2, a3 + 4)
    || !(unsigned int)ASN1BERDecOpenType2(v28, a3 + 8)
    || !(unsigned int)ASN1BERDecOpenType2(v28, a3 + 24) )
  {
    return 0;
  }
  ASN1BERDecPeekTag(v28, &v37);
  if ( v37 == 0x80000000 )
  {
    v6 = v28;
    *(_BYTE *)a3 |= 0x80u;
    v27 = 0;
    v34 = 0;
    v38 = 0;
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))ASN1BERDecExplicitTag)(
                          v6,
                          0x80000000LL,
                          &v27,
                          &v34) )
      return 0;
    v7 = 0;
    *(_DWORD *)(a3 + 40) = 0;
    *(_QWORD *)(a3 + 48) = 0;
    while ( (unsigned int)ASN1BERDecNotEndOfContents(v27, v34) )
    {
      if ( !(unsigned int)ASN1BERDecPeekTag(v27, &v38) )
        return 0;
      if ( *(_DWORD *)(a3 + 40) >= v7 )
      {
        v15 = v27;
        if ( v7 )
        {
          v7 *= 2;
          if ( !v7 )
            goto LABEL_23;
        }
        else
        {
          v7 = 16;
        }
        v22 = 88LL * v7;
        if ( v22 > 0xFFFFFFFF || (unsigned int)v22 >= 0x6000000 )
        {
LABEL_23:
          ASN1DecSetError(v15, 4294966290LL);
          return 0;
        }
        v23 = ASN1DecRealloc(v27, *(_QWORD *)(a3 + 48));
        if ( !v23 )
          return 0;
        *(_QWORD *)(a3 + 48) = v23;
      }
      v8 = *(unsigned int *)(a3 + 40);
      v9 = v27;
      v10 = *(_QWORD *)(a3 + 48);
      v11 = v27;
      v31 = 0;
      v30 = 0;
      *(_DWORD *)(a3 + 40) = v8 + 1;
      if ( (unsigned int)ASN1BERDecExplicitTag(v11, 16, &v31, &v30, v27) )
      {
        v12 = 88 * v8 + v10;
        if ( (unsigned int)ASN1BERDecObjectIdentifier2(v31, 6, v12) )
        {
          v13 = v31;
          v14 = 0;
          v29 = 0;
          v33 = 0;
          v32 = 0;
          if ( (unsigned int)ASN1BERDecExplicitTag(v31, 17, &v29, &v33, v27) )
          {
            *(_DWORD *)(v12 + 72) = 0;
            *(_QWORD *)(v12 + 80) = 0;
            while ( (unsigned int)ASN1BERDecNotEndOfContents(v29, v33) )
            {
              if ( !(unsigned int)ASN1BERDecPeekTag(v29, &v32) )
                return 0;
              if ( *(_DWORD *)(v12 + 72) >= v14 )
              {
                v15 = v29;
                if ( v14 )
                {
                  v14 *= 2;
                  if ( !v14 )
                    goto LABEL_23;
                }
                else
                {
                  v14 = 16;
                }
                v16 = 16LL * v14;
                if ( v16 > 0xFFFFFFFF || (unsigned int)v16 >= 0x6000000 )
                  goto LABEL_23;
                v24 = ASN1DecRealloc(v29, *(_QWORD *)(v12 + 80));
                if ( !v24 )
                  return 0;
                *(_QWORD *)(v12 + 80) = v24;
              }
              v25 = *(_QWORD *)(v12 + 80) + 16LL * *(unsigned int *)(v12 + 72);
              v26 = v29;
              ++*(_DWORD *)(v12 + 72);
              if ( !(unsigned int)ASN1BERDecOpenType2(v26, v25) )
                return 0;
            }
            if ( (unsigned int)ASN1BERDecEndOfContents(v13, v29, v33)
              && (unsigned int)ASN1BERDecEndOfContents(v9, v31, v30) )
            {
              continue;
            }
          }
        }
      }
      return 0;
    }
    if ( !(unsigned int)ASN1BERDecEndOfContents(v6, v27, v34) )
      return 0;
    v4 = a1;
  }
  v18 = v28;
  v27 = 0;
  v30 = 0;
  v38 = 0;
  if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))ASN1BERDecExplicitTag)(
                        v28,
                        16,
                        &v27,
                        &v30) )
    return 0;
  v19 = v27;
  *(_BYTE *)(a3 + 56) = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier2(v19, 6, a3 + 60) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v27, &v38) )
  {
    v20 = v27;
    *(_BYTE *)(a3 + 56) |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType2(v20, a3 + 128) )
      return 0;
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v18, v27, v30) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOctetString2(v28, 4, a3 + 144) )
    return 0;
  ASN1BERDecPeekTag(v28, &v37);
  if ( v37 == -2147483647 )
  {
    v21 = v28;
    *(_BYTE *)a3 |= 0x40u;
    if ( !(unsigned int)ASN1Dec_AttributesNC2(v21, 2147483649LL, a3 + 160) )
      return 0;
  }
  return (unsigned int)ASN1BERDecEndOfContents(v4, v28, v35) != 0;
}

```

## disassembly

```asm
0x18007aa40  mov     [rsp-38h+arg_10], rbx
0x18007aa45  mov     [rsp-38h+arg_0], rcx
0x18007aa4a  push    rbp
0x18007aa4b  push    rsi
0x18007aa4c  push    rdi
0x18007aa4d  push    r12
0x18007aa4f  push    r13
0x18007aa51  push    r14
0x18007aa53  push    r15
0x18007aa55  mov     rbp, rsp
0x18007aa58  sub     rsp, 70h
0x18007aa5c  xor     r15d, r15d
0x18007aa5f  lea     r9, [rbp+var_10]
0x18007aa63  test    edx, edx
0x18007aa65  mov     [rbp+var_48], r15
0x18007aa69  mov     rbx, r8
0x18007aa6c  mov     [rbp+var_10], r15
0x18007aa70  lea     r8, [rbp+var_48]
0x18007aa74  mov     [rbp+arg_8], r15d
0x18007aa78  lea     r14d, [r15+10h]
0x18007aa7c  mov     rsi, rcx
0x18007aa7f  cmovz   edx, r14d
0x18007aa83  call    cs:__imp_ASN1BERDecExplicitTag
0x18007aa89  test    eax, eax
0x18007aa8b  jz      loc_18007AC53
0x18007aa91  mov     rcx, [rbp+var_48]
0x18007aa95  lea     r8, [rbx+4]
0x18007aa99  xor     eax, eax
0x18007aa9b  mov     [rbx], al
0x18007aa9d  lea     edx, [rax+2]
0x18007aaa0  call    cs:__imp_ASN1BERDecS32Val
0x18007aaa6  test    eax, eax
0x18007aaa8  jz      loc_18007AC53
0x18007aaae  mov     rcx, [rbp+var_48]
0x18007aab2  lea     rdx, [rbx+8]
0x18007aab6  call    cs:__imp_ASN1BERDecOpenType2
0x18007aabc  test    eax, eax
0x18007aabe  jz      loc_18007AC53
0x18007aac4  mov     rcx, [rbp+var_48]
0x18007aac8  lea     rdx, [rbx+18h]
0x18007aacc  call    cs:__imp_ASN1BERDecOpenType2
0x18007aad2  test    eax, eax
0x18007aad4  jz      loc_18007AC53
0x18007aada  mov     rcx, [rbp+var_48]
0x18007aade  lea     rdx, [rbp+arg_8]
0x18007aae2  call    cs:__imp_ASN1BERDecPeekTag
0x18007aae8  mov     edx, 80000000h
0x18007aaed  cmp     [rbp+arg_8], edx
0x18007aaf0  jnz     loc_18007AC86
0x18007aaf6  mov     r13, [rbp+var_48]
0x18007aafa  lea     r9, [rbp+var_18]
0x18007aafe  or      byte ptr [rbx], 80h
0x18007ab01  lea     r8, [rbp+var_50]
0x18007ab05  mov     rcx, r13
0x18007ab08  mov     [rbp+var_50], r15
0x18007ab0c  mov     [rbp+var_18], r15
0x18007ab10  mov     [rbp+arg_18], r15d
0x18007ab14  call    cs:__imp_ASN1BERDecExplicitTag
0x18007ab1a  test    eax, eax
0x18007ab1c  jz      loc_18007AC53
0x18007ab22  mov     esi, r15d
0x18007ab25  mov     [rbx+28h], r15d
0x18007ab29  mov     [rbx+30h], r15
0x18007ab2d  mov     rdx, [rbp+var_18]
0x18007ab31  mov     edi, 0FFFFFFFFh
0x18007ab36  mov     rcx, [rbp+var_50]
0x18007ab3a  call    cs:__imp_ASN1BERDecNotEndOfContents
0x18007ab40  test    eax, eax
0x18007ab42  jz      loc_18007AC6D
0x18007ab48  mov     rcx, [rbp+var_50]
0x18007ab4c  lea     rdx, [rbp+arg_18]
0x18007ab50  call    cs:__imp_ASN1BERDecPeekTag
0x18007ab56  test    eax, eax
0x18007ab58  jz      loc_18007AC53
0x18007ab5e  cmp     [rbx+28h], esi
0x18007ab61  jnb     loc_18007ADBF
0x18007ab67  mov     edi, [rbx+28h]
0x18007ab6a  lea     r9, [rbp+var_38]
0x18007ab6e  mov     r12, [rbp+var_50]
0x18007ab72  lea     r8, [rbp+var_30]
0x18007ab76  mov     r14, [rbx+30h]
0x18007ab7a  mov     edx, 10h
0x18007ab7f  mov     rcx, r12
0x18007ab82  mov     [rbp+var_30], r15
0x18007ab86  lea     eax, [rdi+1]
0x18007ab89  mov     [rbp+var_38], r15
0x18007ab8d  mov     [rbx+28h], eax
0x18007ab90  call    cs:__imp_ASN1BERDecExplicitTag
0x18007ab96  test    eax, eax
0x18007ab98  jz      loc_18007AC53
0x18007ab9e  imul    rcx, rdi, 58h ; 'X'
0x18007aba2  mov     edx, 6
0x18007aba7  add     r14, rcx
0x18007abaa  mov     rcx, [rbp+var_30]
0x18007abae  mov     r8, r14
0x18007abb1  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18007abb7  test    eax, eax
0x18007abb9  jz      loc_18007AC53
0x18007abbf  mov     r15, [rbp+var_30]
0x18007abc3  lea     r9, [rbp+var_20]
0x18007abc7  xor     edi, edi
0x18007abc9  lea     r8, [rbp+var_40]
0x18007abcd  mov     rcx, r15
0x18007abd0  mov     [rbp+var_40], rdi
0x18007abd4  mov     [rbp+var_20], rdi
0x18007abd8  mov     [rbp+var_28], edi
0x18007abdb  lea     edx, [rdi+11h]
0x18007abde  call    cs:__imp_ASN1BERDecExplicitTag
0x18007abe4  test    eax, eax
0x18007abe6  jz      short loc_18007AC53
0x18007abe8  mov     [r14+48h], edi
0x18007abec  mov     [r14+50h], rdi
0x18007abf0  mov     rdx, [rbp+var_20]
0x18007abf4  mov     rcx, [rbp+var_40]
0x18007abf8  call    cs:__imp_ASN1BERDecNotEndOfContents
0x18007abfe  test    eax, eax
0x18007ac00  jz      loc_18007AD81
0x18007ac06  mov     rcx, [rbp+var_40]
0x18007ac0a  lea     rdx, [rbp+var_28]
0x18007ac0e  call    cs:__imp_ASN1BERDecPeekTag
0x18007ac14  test    eax, eax
0x18007ac16  jz      short loc_18007AC53
0x18007ac18  cmp     [r14+48h], edi
0x18007ac1c  jb      loc_18007AE2A
0x18007ac22  mov     rcx, [rbp+var_40]
0x18007ac26  test    edi, edi
0x18007ac28  jnz     loc_18007AE56
0x18007ac2e  mov     edi, 10h
0x18007ac33  mov     r8d, edi
0x18007ac36  mov     eax, 0FFFFFFFFh
0x18007ac3b  shl     r8, 4
0x18007ac3f  cmp     r8, rax
0x18007ac42  jbe     loc_18007AE06
0x18007ac48  mov     edx, 0FFFFFC12h
0x18007ac4d  call    cs:__imp_ASN1DecSetError
0x18007ac53  xor     eax, eax
0x18007ac55  mov     rbx, [rsp+70h+arg_10]
0x18007ac5d  add     rsp, 70h
0x18007ac61  pop     r15
0x18007ac63  pop     r14
0x18007ac65  pop     r13
0x18007ac67  pop     r12
0x18007ac69  pop     rdi
0x18007ac6a  pop     rsi
0x18007ac6b  pop     rbp
0x18007ac6c  retn
0x18007ac6d  mov     r8, [rbp+var_18]
0x18007ac71  mov     rcx, r13
0x18007ac74  mov     rdx, [rbp+var_50]
0x18007ac78  call    cs:__imp_ASN1BERDecEndOfContents
0x18007ac7e  test    eax, eax
0x18007ac80  jz      short loc_18007AC53
0x18007ac82  mov     rsi, [rbp+arg_0]
0x18007ac86  mov     rdi, [rbp+var_48]
0x18007ac8a  lea     r9, [rbp+var_38]
0x18007ac8e  mov     rcx, rdi
0x18007ac91  mov     [rbp+var_50], r15
0x18007ac95  lea     r8, [rbp+var_50]
0x18007ac99  mov     [rbp+var_38], r15
0x18007ac9d  mov     edx, r14d
0x18007aca0  mov     [rbp+arg_18], r15d
0x18007aca4  call    cs:__imp_ASN1BERDecExplicitTag
0x18007acaa  test    eax, eax
0x18007acac  jz      short loc_18007AC53
0x18007acae  mov     rcx, [rbp+var_50]
0x18007acb2  lea     r8, [rbx+3Ch]
0x18007acb6  xor     eax, eax
0x18007acb8  mov     [rbx+38h], al
0x18007acbb  lea     edx, [rax+6]
0x18007acbe  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18007acc4  test    eax, eax
0x18007acc6  jz      short loc_18007AC53
0x18007acc8  mov     rcx, [rbp+var_50]
0x18007accc  lea     rdx, [rbp+arg_18]
0x18007acd0  call    cs:__imp_ASN1BERDecPeekTag
0x18007acd6  test    eax, eax
0x18007acd8  jz      short loc_18007ACF7
0x18007acda  mov     rcx, [rbp+var_50]
0x18007acde  lea     rdx, [rbx+80h]
0x18007ace5  or      byte ptr [rbx+38h], 80h
0x18007ace9  call    cs:__imp_ASN1BERDecOpenType2
0x18007acef  test    eax, eax
0x18007acf1  jz      loc_18007AC53
0x18007acf7  mov     r8, [rbp+var_38]
0x18007acfb  mov     rcx, rdi
0x18007acfe  mov     rdx, [rbp+var_50]
0x18007ad02  call    cs:__imp_ASN1BERDecEndOfContents
0x18007ad08  test    eax, eax
0x18007ad0a  jz      loc_18007AC53
0x18007ad10  mov     rcx, [rbp+var_48]
0x18007ad14  lea     r8, [rbx+90h]
0x18007ad1b  mov     edx, 4
0x18007ad20  call    cs:__imp_ASN1BERDecOctetString2
0x18007ad26  test    eax, eax
0x18007ad28  jz      loc_18007AC53
0x18007ad2e  mov     rcx, [rbp+var_48]
0x18007ad32  lea     rdx, [rbp+arg_8]
0x18007ad36  call    cs:__imp_ASN1BERDecPeekTag
0x18007ad3c  mov     edx, 80000001h
0x18007ad41  cmp     [rbp+arg_8], edx
0x18007ad44  jnz     short loc_18007AD61
0x18007ad46  mov     rcx, [rbp+var_48]
0x18007ad4a  lea     r8, [rbx+0A0h]
0x18007ad51  or      byte ptr [rbx], 40h
0x18007ad54  call    ASN1Dec_AttributesNC2
0x18007ad59  test    eax, eax
0x18007ad5b  jz      loc_18007AC53
0x18007ad61  mov     r8, [rbp+var_10]
0x18007ad65  mov     rcx, rsi
0x18007ad68  mov     rdx, [rbp+var_48]
0x18007ad6c  call    cs:__imp_ASN1BERDecEndOfContents
0x18007ad72  test    eax, eax
0x18007ad74  mov     ecx, r15d
0x18007ad77  setnz   cl
0x18007ad7a  mov     eax, ecx
0x18007ad7c  jmp     loc_18007AC55
0x18007ad81  mov     r8, [rbp+var_20]
0x18007ad85  mov     rcx, r15
0x18007ad88  mov     rdx, [rbp+var_40]
0x18007ad8c  call    cs:__imp_ASN1BERDecEndOfContents
0x18007ad92  xor     r15d, r15d
0x18007ad95  test    eax, eax
0x18007ad97  jz      loc_18007AC53
0x18007ad9d  mov     r8, [rbp+var_38]
0x18007ada1  mov     rcx, r12
0x18007ada4  mov     rdx, [rbp+var_30]
0x18007ada8  call    cs:__imp_ASN1BERDecEndOfContents
0x18007adae  test    eax, eax
0x18007adb0  jz      loc_18007AC53
0x18007adb6  lea     r14d, [r15+10h]
0x18007adba  jmp     loc_18007AB2D
0x18007adbf  mov     rcx, [rbp+var_50]
0x18007adc3  test    esi, esi
0x18007adc5  jnz     loc_18007AE63
0x18007adcb  mov     esi, r14d
0x18007adce  mov     eax, esi
0x18007add0  imul    r8, rax, 58h ; 'X'
0x18007add4  cmp     r8, rdi
0x18007add7  ja      loc_18007AC48
0x18007addd  cmp     r8d, 6000000h
0x18007ade4  jnb     loc_18007AC48
0x18007adea  mov     rdx, [rbx+30h]
0x18007adee  call    cs:__imp_ASN1DecRealloc
0x18007adf4  test    rax, rax
0x18007adf7  jz      loc_18007AC53
0x18007adfd  mov     [rbx+30h], rax
0x18007ae01  jmp     loc_18007AB67
0x18007ae06  cmp     r8d, 6000000h
0x18007ae0d  jnb     loc_18007AC48
0x18007ae13  mov     rdx, [r14+50h]
0x18007ae17  call    cs:__imp_ASN1DecRealloc
0x18007ae1d  test    rax, rax
0x18007ae20  jz      loc_18007AC53
0x18007ae26  mov     [r14+50h], rax
0x18007ae2a  mov     ecx, [r14+48h]
0x18007ae2e  mov     edx, ecx
0x18007ae30  shl     rdx, 4
0x18007ae34  add     rdx, [r14+50h]
0x18007ae38  lea     eax, [rcx+1]
0x18007ae3b  mov     rcx, [rbp+var_40]
0x18007ae3f  mov     [r14+48h], eax
0x18007ae43  call    cs:__imp_ASN1BERDecOpenType2
0x18007ae49  test    eax, eax
0x18007ae4b  jnz     loc_18007ABF0
0x18007ae51  jmp     loc_18007AC53
0x18007ae56  add     edi, edi
0x18007ae58  jz      loc_18007AC48
0x18007ae5e  jmp     loc_18007AC33
0x18007ae63  add     esi, esi
0x18007ae65  jz      loc_18007AC48
0x18007ae6b  jmp     loc_18007ADCE
```
