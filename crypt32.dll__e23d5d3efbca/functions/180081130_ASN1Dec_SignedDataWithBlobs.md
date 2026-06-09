# ASN1Dec_SignedDataWithBlobs

- ea: `0x180081130`
- end: `0x180081624`
- name: `ASN1Dec_SignedDataWithBlobs`
- size: `1268`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180081130`
- `0x18010a880`

## import_xrefs

- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18008124a`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18008124a`
- `MSASN1!ASN1DecRealloc` at `0x1800813d6`
- `MSASN1!ASN1DecRealloc` at `0x180081514`
- `MSASN1!ASN1DecRealloc` at `0x1800815c5`
- `MSASN1!ASN1DecRealloc` at `0x1800813d6`
- `MSASN1!ASN1DecRealloc` at `0x180081514`
- `MSASN1!ASN1DecRealloc` at `0x1800815c5`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800811f8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800812b9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800812d2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180081568`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180081581`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800815a1`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800811f8`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800812b9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800812d2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180081568`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180081581`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800815a1`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x1800811df`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x180081340`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x1800814b5`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x1800811df`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x180081340`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x1800814b5`
- `MSASN1!ASN1BERDecPeekTag` at `0x180081260`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800812e8`
- `MSASN1!ASN1BERDecPeekTag` at `0x180081356`
- `MSASN1!ASN1BERDecPeekTag` at `0x18008139b`
- `MSASN1!ASN1BERDecPeekTag` at `0x18008145e`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800814cb`
- `MSASN1!ASN1BERDecPeekTag` at `0x180081260`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800812e8`
- `MSASN1!ASN1BERDecPeekTag` at `0x180081356`
- `MSASN1!ASN1BERDecPeekTag` at `0x18008139b`
- `MSASN1!ASN1BERDecPeekTag` at `0x18008145e`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800814cb`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18008116e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800811b8`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18008122c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180081289`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180081319`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180081492`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18008116e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800811b8`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18008122c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180081289`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180081319`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180081492`
- `MSASN1!ASN1DecSetError` at `0x180081430`
- `MSASN1!ASN1DecSetError` at `0x180081430`
- `MSASN1!ASN1BERDecS32Val` at `0x18008118b`
- `MSASN1!ASN1BERDecS32Val` at `0x18008118b`
- `MSASN1!ASN1BERDecOpenType2` at `0x18008129f`
- `MSASN1!ASN1BERDecOpenType2` at `0x180081384`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800813fc`
- `MSASN1!ASN1BERDecOpenType2` at `0x18008154a`
- `MSASN1!ASN1BERDecOpenType2` at `0x18008129f`
- `MSASN1!ASN1BERDecOpenType2` at `0x180081384`
- `MSASN1!ASN1BERDecOpenType2` at `0x1800813fc`
- `MSASN1!ASN1BERDecOpenType2` at `0x18008154a`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SignedDataWithBlobs(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rsi
  unsigned int v7; // edi
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // r8
  __int64 v22; // rsi
  unsigned int v23; // edi
  unsigned __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // [rsp+20h] [rbp-30h] BYREF
  __int64 v31; // [rsp+28h] [rbp-28h] BYREF
  __int64 v32; // [rsp+30h] [rbp-20h] BYREF
  __int64 v33; // [rsp+38h] [rbp-18h] BYREF
  __int64 v34; // [rsp+40h] [rbp-10h] BYREF
  __int64 v35; // [rsp+48h] [rbp-8h] BYREF
  int v36; // [rsp+98h] [rbp+48h] BYREF
  int v37; // [rsp+A8h] [rbp+58h] BYREF

  v30 = 0;
  v35 = 0;
  v36 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v30, &v35, v30) )
    return 0;
  v5 = v30;
  *(_BYTE *)a3 = 0;
  if ( !(unsigned int)ASN1BERDecS32Val(v5, 2, a3 + 4) )
    return 0;
  v6 = v30;
  v31 = 0;
  v32 = 0;
  v37 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v30, 17, &v31, &v32, v30) )
    return 0;
  v7 = 0;
  *(_DWORD *)(a3 + 8) = 0;
  *(_QWORD *)(a3 + 16) = 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v31, v32) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v31, &v37) )
      return 0;
    if ( *(_DWORD *)(a3 + 8) >= v7 )
    {
      v15 = v31;
      if ( v7 )
      {
        v7 *= 2;
        if ( !v7 )
          goto LABEL_38;
      }
      else
      {
        v7 = 16;
      }
      v16 = 16LL * v7;
      if ( v16 > 0xFFFFFFFF || (unsigned int)v16 >= 0x6000000 )
      {
LABEL_38:
        ASN1DecSetError(v15, 4294966290LL);
        return 0;
      }
      v17 = ASN1DecRealloc(v31, *(_QWORD *)(a3 + 16));
      if ( !v17 )
        return 0;
      *(_QWORD *)(a3 + 16) = v17;
    }
    v18 = *(_QWORD *)(a3 + 16) + 16LL * *(unsigned int *)(a3 + 8);
    v19 = v31;
    ++*(_DWORD *)(a3 + 8);
    if ( !(unsigned int)ASN1BERDecOpenType2(v19, v18) )
      return 0;
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v6, v31, v32) )
    return 0;
  v8 = v30;
  v31 = 0;
  v34 = 0;
  v37 = 0;
  v32 = 0;
  v33 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v30, 16, &v31, &v34, v30) )
    return 0;
  v9 = v31;
  *(_BYTE *)(a3 + 24) = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier2(v9, 6, a3 + 28) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v31, &v37) )
  {
    if ( v37 == 0x80000000 )
    {
      v10 = v31;
      *(_BYTE *)(a3 + 24) |= 0x80u;
      if ( !(unsigned int)ASN1BERDecExplicitTag(v10, 0x80000000LL, &v32, &v33, v30)
        || !(unsigned int)ASN1BERDecOpenType2(v32, a3 + 96)
        || !(unsigned int)ASN1BERDecEndOfContents(v31, v32, v33) )
      {
        return 0;
      }
    }
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v8, v31, v34) )
    return 0;
  ASN1BERDecPeekTag(v30, &v36);
  if ( v36 == 0x80000000 )
  {
    v11 = v30;
    *(_BYTE *)a3 |= 0x80u;
    v31 = 0;
    v32 = 0;
    v37 = 0;
    if ( !(unsigned int)ASN1BERDecExplicitTag(v11, 0x80000000LL, &v31, &v32, v30) )
      return 0;
    v12 = 0;
    *(_DWORD *)(a3 + 112) = 0;
    *(_QWORD *)(a3 + 120) = 0;
    while ( (unsigned int)ASN1BERDecNotEndOfContents(v31, v32) )
    {
      if ( !(unsigned int)ASN1BERDecPeekTag(v31, &v37) )
        return 0;
      if ( *(_DWORD *)(a3 + 112) >= v12 )
      {
        v15 = v31;
        if ( v12 )
        {
          v12 *= 2;
          if ( !v12 )
            goto LABEL_38;
        }
        else
        {
          v12 = 16;
        }
        v20 = 16LL * v12;
        if ( v20 > 0xFFFFFFFF || (unsigned int)v20 >= 0x6000000 )
          goto LABEL_38;
        v28 = ASN1DecRealloc(v31, *(_QWORD *)(a3 + 120));
        if ( !v28 )
          return 0;
        *(_QWORD *)(a3 + 120) = v28;
      }
      v13 = *(_QWORD *)(a3 + 120) + 16LL * *(unsigned int *)(a3 + 112);
      v14 = v31;
      ++*(_DWORD *)(a3 + 112);
      if ( !(unsigned int)ASN1BERDecOpenType2(v14, v13) )
        return 0;
    }
    if ( !(unsigned int)ASN1BERDecEndOfContents(v11, v31, v32) )
      return 0;
  }
  ASN1BERDecPeekTag(v30, &v36);
  if ( v36 == -2147483647 )
  {
    v29 = v30;
    *(_BYTE *)a3 |= 0x40u;
    if ( !(unsigned int)ASN1Dec_DigestAlgorithmBlobs(v29, 2147483649LL, a3 + 128) )
      return 0;
  }
  v22 = v30;
  v31 = 0;
  v32 = 0;
  v37 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v30, 17, &v31, &v32, v30) )
    return 0;
  v23 = 0;
  *(_DWORD *)(a3 + 144) = 0;
  *(_QWORD *)(a3 + 152) = 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v31, v32) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v31, &v37) )
      return 0;
    if ( *(_DWORD *)(a3 + 144) >= v23 )
    {
      v15 = v31;
      if ( v23 )
      {
        v23 *= 2;
        if ( !v23 )
          goto LABEL_38;
      }
      else
      {
        v23 = 16;
      }
      v24 = 16LL * v23;
      if ( v24 > 0xFFFFFFFF || (unsigned int)v24 >= 0x6000000 )
        goto LABEL_38;
      v25 = ASN1DecRealloc(v31, *(_QWORD *)(a3 + 152));
      if ( !v25 )
        return 0;
      *(_QWORD *)(a3 + 152) = v25;
    }
    v26 = *(_QWORD *)(a3 + 152) + 16LL * *(unsigned int *)(a3 + 144);
    v27 = v31;
    ++*(_DWORD *)(a3 + 144);
    if ( !(unsigned int)ASN1BERDecOpenType2(v27, v26) )
      return 0;
  }
  return (unsigned int)ASN1BERDecEndOfContents(v22, v31, v32)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v30, v35) != 0;
}

```

## disassembly

```asm
0x180081130  mov     [rsp-38h+arg_0], rbx
0x180081135  push    rbp
0x180081136  push    rsi
0x180081137  push    rdi
0x180081138  push    r12
0x18008113a  push    r13
0x18008113c  push    r14
0x18008113e  push    r15
0x180081140  mov     rbp, rsp
0x180081143  sub     rsp, 50h
0x180081147  xor     r15d, r15d
0x18008114a  lea     r9, [rbp+var_8]
0x18008114e  test    edx, edx
0x180081150  mov     [rbp+var_30], r15
0x180081154  mov     rbx, r8
0x180081157  mov     [rbp+var_8], r15
0x18008115b  lea     r8, [rbp+var_30]
0x18008115f  mov     [rbp+arg_8], r15d
0x180081163  lea     r13d, [r15+10h]
0x180081167  mov     r14, rcx
0x18008116a  cmovz   edx, r13d
0x18008116e  call    cs:__imp_ASN1BERDecExplicitTag
0x180081174  test    eax, eax
0x180081176  jz      loc_180081436
0x18008117c  mov     rcx, [rbp+var_30]
0x180081180  lea     r8, [rbx+4]
0x180081184  xor     eax, eax
0x180081186  mov     [rbx], al
0x180081188  lea     edx, [rax+2]
0x18008118b  call    cs:__imp_ASN1BERDecS32Val
0x180081191  test    eax, eax
0x180081193  jz      loc_180081436
0x180081199  mov     rsi, [rbp+var_30]
0x18008119d  lea     r9, [rbp+var_20]
0x1800811a1  mov     rcx, rsi
0x1800811a4  mov     [rbp+var_28], r15
0x1800811a8  lea     r8, [rbp+var_28]
0x1800811ac  mov     [rbp+var_20], r15
0x1800811b0  lea     edx, [r15+11h]
0x1800811b4  mov     [rbp+arg_18], r15d
0x1800811b8  call    cs:__imp_ASN1BERDecExplicitTag
0x1800811be  test    eax, eax
0x1800811c0  jz      loc_180081436
0x1800811c6  mov     edi, r15d
0x1800811c9  mov     [rbx+8], r15d
0x1800811cd  mov     [rbx+10h], r15
0x1800811d1  mov     r12d, 0FFFFFFFFh
0x1800811d7  mov     rdx, [rbp+var_20]
0x1800811db  mov     rcx, [rbp+var_28]
0x1800811df  call    cs:__imp_ASN1BERDecNotEndOfContents
0x1800811e5  test    eax, eax
0x1800811e7  jnz     loc_180081393
0x1800811ed  mov     r8, [rbp+var_20]
0x1800811f1  mov     rcx, rsi
0x1800811f4  mov     rdx, [rbp+var_28]
0x1800811f8  call    cs:__imp_ASN1BERDecEndOfContents
0x1800811fe  test    eax, eax
0x180081200  jz      loc_180081436
0x180081206  mov     rdi, [rbp+var_30]
0x18008120a  lea     r9, [rbp+var_10]
0x18008120e  mov     rcx, rdi
0x180081211  mov     [rbp+var_28], r15
0x180081215  lea     r8, [rbp+var_28]
0x180081219  mov     [rbp+var_10], r15
0x18008121d  mov     edx, r13d
0x180081220  mov     [rbp+arg_18], r15d
0x180081224  mov     [rbp+var_20], r15
0x180081228  mov     [rbp+var_18], r15
0x18008122c  call    cs:__imp_ASN1BERDecExplicitTag
0x180081232  test    eax, eax
0x180081234  jz      loc_180081436
0x18008123a  mov     rcx, [rbp+var_28]
0x18008123e  lea     r8, [rbx+1Ch]
0x180081242  xor     eax, eax
0x180081244  mov     [rbx+18h], al
0x180081247  lea     edx, [rax+6]
0x18008124a  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x180081250  test    eax, eax
0x180081252  jz      loc_180081436
0x180081258  mov     rcx, [rbp+var_28]
0x18008125c  lea     rdx, [rbp+arg_18]
0x180081260  call    cs:__imp_ASN1BERDecPeekTag
0x180081266  mov     r12d, 80000000h
0x18008126c  test    eax, eax
0x18008126e  jz      short loc_1800812C7
0x180081270  cmp     [rbp+arg_18], r12d
0x180081274  jnz     short loc_1800812C7
0x180081276  mov     rcx, [rbp+var_28]
0x18008127a  lea     r9, [rbp+var_18]
0x18008127e  or      byte ptr [rbx+18h], 80h
0x180081282  lea     r8, [rbp+var_20]
0x180081286  mov     edx, r12d
0x180081289  call    cs:__imp_ASN1BERDecExplicitTag
0x18008128f  test    eax, eax
0x180081291  jz      loc_180081436
0x180081297  mov     rcx, [rbp+var_20]
0x18008129b  lea     rdx, [rbx+60h]
0x18008129f  call    cs:__imp_ASN1BERDecOpenType2
0x1800812a5  test    eax, eax
0x1800812a7  jz      loc_180081436
0x1800812ad  mov     r8, [rbp+var_18]
0x1800812b1  mov     rdx, [rbp+var_20]
0x1800812b5  mov     rcx, [rbp+var_28]
0x1800812b9  call    cs:__imp_ASN1BERDecEndOfContents
0x1800812bf  test    eax, eax
0x1800812c1  jz      loc_180081436
0x1800812c7  mov     r8, [rbp+var_10]
0x1800812cb  mov     rcx, rdi
0x1800812ce  mov     rdx, [rbp+var_28]
0x1800812d2  call    cs:__imp_ASN1BERDecEndOfContents
0x1800812d8  test    eax, eax
0x1800812da  jz      loc_180081436
0x1800812e0  mov     rcx, [rbp+var_30]
0x1800812e4  lea     rdx, [rbp+arg_8]
0x1800812e8  call    cs:__imp_ASN1BERDecPeekTag
0x1800812ee  cmp     [rbp+arg_8], r12d
0x1800812f2  jnz     loc_180081450
0x1800812f8  mov     rsi, [rbp+var_30]
0x1800812fc  lea     r9, [rbp+var_20]
0x180081300  or      byte ptr [rbx], 80h
0x180081303  lea     r8, [rbp+var_28]
0x180081307  mov     rcx, rsi
0x18008130a  mov     [rbp+var_28], r15
0x18008130e  mov     edx, r12d
0x180081311  mov     [rbp+var_20], r15
0x180081315  mov     [rbp+arg_18], r15d
0x180081319  call    cs:__imp_ASN1BERDecExplicitTag
0x18008131f  test    eax, eax
0x180081321  jz      loc_180081436
0x180081327  mov     edi, r15d
0x18008132a  mov     [rbx+70h], r15d
0x18008132e  mov     [rbx+78h], r15
0x180081332  mov     r12d, 0FFFFFFFFh
0x180081338  mov     rdx, [rbp+var_20]
0x18008133c  mov     rcx, [rbp+var_28]
0x180081340  call    cs:__imp_ASN1BERDecNotEndOfContents
0x180081346  test    eax, eax
0x180081348  jz      loc_180081596
0x18008134e  mov     rcx, [rbp+var_28]
0x180081352  lea     rdx, [rbp+arg_18]
0x180081356  call    cs:__imp_ASN1BERDecPeekTag
0x18008135c  test    eax, eax
0x18008135e  jz      loc_180081436
0x180081364  cmp     [rbx+70h], edi
0x180081367  jnb     loc_18008140C
0x18008136d  mov     ecx, [rbx+70h]
0x180081370  mov     edx, ecx
0x180081372  shl     rdx, 4
0x180081376  add     rdx, [rbx+78h]
0x18008137a  lea     eax, [rcx+1]
0x18008137d  mov     rcx, [rbp+var_28]
0x180081381  mov     [rbx+70h], eax
0x180081384  call    cs:__imp_ASN1BERDecOpenType2
0x18008138a  test    eax, eax
0x18008138c  jnz     short loc_180081338
0x18008138e  jmp     loc_180081436
0x180081393  mov     rcx, [rbp+var_28]
0x180081397  lea     rdx, [rbp+arg_18]
0x18008139b  call    cs:__imp_ASN1BERDecPeekTag
0x1800813a1  test    eax, eax
0x1800813a3  jz      loc_180081436
0x1800813a9  cmp     [rbx+8], edi
0x1800813ac  jb      short loc_1800813E5
0x1800813ae  mov     rcx, [rbp+var_28]
0x1800813b2  test    edi, edi
0x1800813b4  jnz     loc_1800815DD
0x1800813ba  mov     edi, r13d
0x1800813bd  mov     r8d, edi
0x1800813c0  shl     r8, 4
0x1800813c4  cmp     r8, r12
0x1800813c7  ja      short loc_18008142B
0x1800813c9  cmp     r8d, 6000000h
0x1800813d0  jnb     short loc_18008142B
0x1800813d2  mov     rdx, [rbx+10h]
0x1800813d6  call    cs:__imp_ASN1DecRealloc
0x1800813dc  test    rax, rax
0x1800813df  jz      short loc_180081436
0x1800813e1  mov     [rbx+10h], rax
0x1800813e5  mov     ecx, [rbx+8]
0x1800813e8  mov     edx, ecx
0x1800813ea  shl     rdx, 4
0x1800813ee  add     rdx, [rbx+10h]
0x1800813f2  lea     eax, [rcx+1]
0x1800813f5  mov     rcx, [rbp+var_28]
0x1800813f9  mov     [rbx+8], eax
0x1800813fc  call    cs:__imp_ASN1BERDecOpenType2
0x180081402  test    eax, eax
0x180081404  jnz     loc_1800811D7
0x18008140a  jmp     short loc_180081436
0x18008140c  mov     rcx, [rbp+var_28]
0x180081410  test    edi, edi
0x180081412  jnz     loc_1800815F7
0x180081418  mov     edi, r13d
0x18008141b  mov     r8d, edi
0x18008141e  shl     r8, 4
0x180081422  cmp     r8, r12
0x180081425  jbe     loc_1800815B4
0x18008142b  mov     edx, 0FFFFFC12h
0x180081430  call    cs:__imp_ASN1DecSetError
0x180081436  xor     eax, eax
0x180081438  mov     rbx, [rsp+50h+arg_0]
0x180081440  add     rsp, 50h
0x180081444  pop     r15
0x180081446  pop     r14
0x180081448  pop     r13
0x18008144a  pop     r12
0x18008144c  pop     rdi
0x18008144d  pop     rsi
0x18008144e  pop     rbp
0x18008144f  retn
0x180081450  mov     r12d, 0FFFFFFFFh
0x180081456  mov     rcx, [rbp+var_30]
0x18008145a  lea     rdx, [rbp+arg_8]
0x18008145e  call    cs:__imp_ASN1BERDecPeekTag
0x180081464  mov     edx, 80000001h
0x180081469  cmp     [rbp+arg_8], edx
0x18008146c  jz      loc_180081604
0x180081472  mov     rsi, [rbp+var_30]
0x180081476  lea     r9, [rbp+var_20]
0x18008147a  mov     rcx, rsi
0x18008147d  mov     [rbp+var_28], r15
0x180081481  lea     r8, [rbp+var_28]
0x180081485  mov     [rbp+var_20], r15
0x180081489  mov     edx, 11h
0x18008148e  mov     [rbp+arg_18], r15d
0x180081492  call    cs:__imp_ASN1BERDecExplicitTag
0x180081498  test    eax, eax
0x18008149a  jz      short loc_180081436
0x18008149c  mov     edi, r15d
0x18008149f  mov     [rbx+90h], r15d
0x1800814a6  mov     [rbx+98h], r15
0x1800814ad  mov     rdx, [rbp+var_20]
0x1800814b1  mov     rcx, [rbp+var_28]
0x1800814b5  call    cs:__imp_ASN1BERDecNotEndOfContents
0x1800814bb  test    eax, eax
0x1800814bd  jz      loc_18008155D
0x1800814c3  mov     rcx, [rbp+var_28]
0x1800814c7  lea     rdx, [rbp+arg_18]
0x1800814cb  call    cs:__imp_ASN1BERDecPeekTag
0x1800814d1  test    eax, eax
0x1800814d3  jz      loc_180081436
0x1800814d9  cmp     [rbx+90h], edi
0x1800814df  jb      short loc_18008152A
0x1800814e1  mov     rcx, [rbp+var_28]
0x1800814e5  test    edi, edi
0x1800814e7  jnz     loc_1800815EA
0x1800814ed  mov     edi, r13d
0x1800814f0  mov     r8d, edi
0x1800814f3  shl     r8, 4
0x1800814f7  cmp     r8, r12
0x1800814fa  ja      loc_18008142B
0x180081500  cmp     r8d, 6000000h
0x180081507  jnb     loc_18008142B
0x18008150d  mov     rdx, [rbx+98h]
0x180081514  call    cs:__imp_ASN1DecRealloc
0x18008151a  test    rax, rax
0x18008151d  jz      loc_180081436
0x180081523  mov     [rbx+98h], rax
0x18008152a  mov     ecx, [rbx+90h]
0x180081530  mov     edx, ecx
0x180081532  shl     rdx, 4
0x180081536  add     rdx, [rbx+98h]
0x18008153d  lea     eax, [rcx+1]
0x180081540  mov     rcx, [rbp+var_28]
0x180081544  mov     [rbx+90h], eax
0x18008154a  call    cs:__imp_ASN1BERDecOpenType2
0x180081550  test    eax, eax
0x180081552  jnz     loc_1800814AD
0x180081558  jmp     loc_180081436
0x18008155d  mov     r8, [rbp+var_20]
0x180081561  mov     rcx, rsi
0x180081564  mov     rdx, [rbp+var_28]
0x180081568  call    cs:__imp_ASN1BERDecEndOfContents
0x18008156e  test    eax, eax
0x180081570  jz      loc_180081436
0x180081576  mov     r8, [rbp+var_8]
0x18008157a  mov     rcx, r14
0x18008157d  mov     rdx, [rbp+var_30]
0x180081581  call    cs:__imp_ASN1BERDecEndOfContents
0x180081587  test    eax, eax
0x180081589  mov     ecx, r15d
0x18008158c  setnz   cl
0x18008158f  mov     eax, ecx
0x180081591  jmp     loc_180081438
0x180081596  mov     r8, [rbp+var_20]
0x18008159a  mov     rcx, rsi
0x18008159d  mov     rdx, [rbp+var_28]
0x1800815a1  call    cs:__imp_ASN1BERDecEndOfContents
0x1800815a7  test    eax, eax
0x1800815a9  jnz     loc_180081456
0x1800815af  jmp     loc_180081436
0x1800815b4  cmp     r8d, 6000000h
0x1800815bb  jnb     loc_18008142B
0x1800815c1  mov     rdx, [rbx+78h]
0x1800815c5  call    cs:__imp_ASN1DecRealloc
0x1800815cb  test    rax, rax
0x1800815ce  jz      loc_180081436
0x1800815d4  mov     [rbx+78h], rax
0x1800815d8  jmp     loc_18008136D
0x1800815dd  add     edi, edi
  ... truncated ...
```
