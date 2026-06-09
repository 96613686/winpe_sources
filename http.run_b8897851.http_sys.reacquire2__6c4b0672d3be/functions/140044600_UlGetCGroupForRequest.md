# UlGetCGroupForRequest

- ea: `0x140044600`
- end: `0x1400459bc`
- name: `UlGetCGroupForRequest`
- size: `5052`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14002cfc0`

## callees

- `0x140030e8c`
- `0x140041fc8`
- `0x140043608`
- `0x140043710`
- `0x1400437e0`
- `0x140043af0`
- `0x140043f98`
- `0x140044600`
- `0x1400459d0`
- `0x1400a22b0`
- `0x1401c3008`
- `0x1401c45cc`
- `0x1401c5128`
- `0x1401c62f8`
- `0x1401c8a48`
- `0x1401c8b04`
- `0x1401c9050`
- `0x1401d9c5c`
- `0x1401d9dd8`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da2b4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400456aa`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400458f1`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400456aa`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400458f1`
- `ntoskrnl!wcschr` at `0x1400447f6`
- `ntoskrnl!wcschr` at `0x140044d15`
- `ntoskrnl!wcschr` at `0x1400447f6`
- `ntoskrnl!wcschr` at `0x140044d15`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400446a3`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400446a3`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140044efa`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140044efa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140044fc9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400450e1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140044fc9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400450e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044f06`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044f06`
- `ntoskrnl!ExAllocatePool3` at `0x14004531a`
- `ntoskrnl!ExAllocatePool3` at `0x14004531a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b7a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004468e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004468e`

## pseudocode

```c
__int64 __fastcall UlGetCGroupForRequest(__int64 a1)
{
  __int64 v1; // rsi
  _WORD *v2; // rcx
  wchar_t *v3; // r14
  __int64 v4; // rbx
  unsigned __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  int WildcardSite; // ebx
  wchar_t *v9; // r12
  __int64 v10; // r15
  __int64 i; // rbx
  const wchar_t *v12; // r14
  int v13; // edi
  unsigned __int8 v14; // si
  unsigned __int64 v15; // rcx
  bool v16; // zf
  char v17; // al
  WCHAR *v18; // rdi
  wchar_t *v19; // rax
  __int64 v20; // rax
  int v21; // r12d
  __int64 v22; // rsi
  wchar_t *v23; // r8
  __int64 v24; // r13
  WCHAR v25; // ax
  WCHAR v26; // ax
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // rcx
  _WORD *Pool3; // rdi
  __int64 v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rcx
  wchar_t *v34; // rsi
  __int64 v35; // r14
  __int64 j; // rbx
  const wchar_t *v37; // r15
  int v38; // edi
  unsigned __int8 v39; // r9
  unsigned int v40; // edx
  unsigned __int64 v41; // rcx
  WCHAR *v42; // rdi
  wchar_t *v43; // rax
  __int64 v44; // rax
  int v45; // r12d
  __int64 v46; // rsi
  wchar_t *v47; // r8
  __int64 v48; // r13
  WCHAR v49; // ax
  WCHAR v50; // ax
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rdi
  _WORD *v54; // rax
  __int64 v56; // rax
  __int64 v57; // rdi
  __int64 v58; // rax
  __int64 v59; // rax
  _WORD *v60; // rax
  int v61; // ecx
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // rdx
  __int128 v65; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v66; // [rsp+60h] [rbp-A0h]
  __int64 v67; // [rsp+70h] [rbp-90h] BYREF
  __int64 v68; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h]
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+98h] [rbp-68h]
  unsigned int v73; // [rsp+A0h] [rbp-60h]
  wchar_t *v74; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v75; // [rsp+B0h] [rbp-50h]
  UNICODE_STRING String2; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v78; // [rsp+D8h] [rbp-28h]
  wchar_t *v79; // [rsp+E0h] [rbp-20h]
  __int64 v80; // [rsp+E8h] [rbp-18h]
  __int64 v81; // [rsp+F0h] [rbp-10h]
  __int64 v83; // [rsp+158h] [rbp+58h] BYREF
  int v84; // [rsp+160h] [rbp+60h]
  char v85; // [rsp+168h] [rbp+68h]

  v1 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v59 = *(_QWORD *)(a1 + 64);
    else
      v59 = 0;
    WPP_SF_qq(1032, 127, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1, v59);
  }
  v2 = *(_WORD **)(v1 + 2056);
  if ( v2 )
    *v2 = 0;
  if ( *(_DWORD *)(v1 + 1984) == 3 && (v60 = *(_WORD **)(v1 + 2048), *v60 == 42) && !v60[1] )
  {
    *v60 = 47;
    v85 = 1;
  }
  else
  {
    v85 = 0;
  }
  v3 = *(wchar_t **)(v1 + 2032);
  v79 = v3;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqqi(1028, 142, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v3, v1, *(_QWORD *)(v1 + 64), v1 + 1296);
  if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_Sq(1284, 143, (unsigned int)WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (_DWORD)v3, v1);
  v4 = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 1096LL);
  KeEnterCriticalRegion();
  v81 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v4 + 1368), 0);
  v65 = 0;
  v66 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqqi(1028, 56, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v3, v1, *(_QWORD *)(v1 + 64), v1 + 1296);
  v7 = *(_QWORD *)(v1 + 24);
  *(_QWORD *)&v66 = v1 + 1296;
  BYTE1(v65) = 1;
  Str = 0;
  *((_QWORD *)&v66 + 1) = *(_QWORD *)(v7 + 1096);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 38, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v3, &v65);
  if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 20LL) )
  {
    WildcardSite = -1073741772;
    goto LABEL_65;
  }
  LOBYTE(v6) = 1;
  WildcardSite = UlpTreeFindWildcardSite(DWORD2(v66), (_DWORD)v3, v6, (unsigned int)&Str, (__int64)&v65 + 8);
  if ( WildcardSite >= 0 )
  {
    v9 = Str;
    v10 = *((_QWORD *)&v65 + 1);
    v72 = v66;
    v78 = Str;
    v80 = *((_QWORD *)&v65 + 1);
    LOBYTE(v65) = 1;
    v68 = 0;
    v71 = 0;
    LOBYTE(v83) = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      WPP_SF_qqqi(
        1028,
        31,
        WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids,
        *((_QWORD *)&v65 + 1),
        Str,
        v66,
        (char *)&v65 + 1);
    i = v10;
    BYTE1(v65) = 1;
    v67 = v10;
    v12 = v9;
    v68 = 0;
    v13 = 0;
    LOBYTE(v83) = 0;
    v6 = 0;
    v75 = 0;
    v14 = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    {
      WPP_SF_qqLqqqq(1028, 29, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v10, v9, 3, &v83, &v71, &v68, 0);
      i = v67;
      v6 = 0;
    }
    v71 = 0;
    v68 = 0;
    LOBYTE(v83) = 0;
    while ( 1 )
    {
      LODWORD(v5) = *(unsigned __int8 *)(i + 37);
      LODWORD(v15) = 0;
      if ( (_BYTE)v5 )
        v6 = i;
      else
        LODWORD(v15) = v14;
      v16 = *(_BYTE *)(i + 36) == 0;
      v17 = v15;
      v70 = v6;
      LOBYTE(v84) = v15;
      if ( !v16 )
      {
        v17 = 1;
        v75 = i;
        LOBYTE(v84) = 1;
      }
      if ( !v12 || !*v12 )
        goto LABEL_51;
      v18 = (WCHAR *)v12;
      v19 = wcschr(v12, 0x2Fu);
      v12 = v19;
      if ( v19 )
      {
        *v19 = 0;
        v20 = v19 - v18;
        ++v12;
      }
      else
      {
        v20 = -1;
        do
          ++v20;
        while ( v18[v20] );
      }
      v21 = 2 * v20;
      String1 = 0;
      v22 = *(_QWORD *)(v67 + 136);
      v23 = *(wchar_t **)(v67 + 16);
      v74 = v23;
      v24 = *(_QWORD *)(v22 + 1360);
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qqqdq(1028, 12, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, v22, v23, v18, v21, &v67);
        v23 = v74;
      }
      i = 0;
      v67 = 0;
      if ( v21 )
        break;
      v13 = -1073741811;
LABEL_43:
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qD(1028, 13, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, i, v13);
        i = v67;
      }
      if ( v12 )
      {
        *((_WORD *)v12 - 1) = 47;
        i = v67;
      }
      v6 = v70;
      if ( v13 == -1073741772 )
      {
        v17 = v84;
LABEL_51:
        v71 = v75;
        v68 = v6;
        if ( v75 != v6 )
          LOBYTE(v83) = v17;
LABEL_53:
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
          WPP_SF_d(1028, 30, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)v13);
        if ( v71 && (_BYTE)v83 )
        {
          BYTE1(v65) = 0;
LABEL_179:
          LOBYTE(v27) = v72;
          WildcardSite = -1073741772;
        }
        else
        {
          if ( !v68 )
            goto LABEL_179;
          v10 = v68;
          v27 = v72;
          if ( *(_QWORD *)(v68 + 8) )
          {
            while ( v10 )
            {
              if ( *(_BYTE *)(v10 + 37) )
              {
                WildcardSite = UlpSetUrlInfo(v27, v10, 0);
                if ( WildcardSite < 0 )
                  goto LABEL_63;
              }
              v10 = *(_QWORD *)(v10 + 8);
            }
          }
          else
          {
            LOBYTE(v6) = 1;
            WildcardSite = UlpSetUrlInfo(v72, v68, v6);
            if ( WildcardSite < 0 )
              goto LABEL_63;
          }
          WildcardSite = 0;
        }
LABEL_63:
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
        {
          WPP_SF_qSqqcd(v15, v5, v6, v10, (__int64)v78, v27, v68, SBYTE1(v65), WildcardSite);
          if ( (xmmword_1401A2CA0 & 0x10) != 0 )
            WPP_SF_Dd(1028, 33, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, BYTE1(v65), WildcardSite);
        }
        v1 = a1;
        v3 = v79;
        goto LABEL_65;
      }
      v14 = v84;
      if ( v13 < 0 )
        goto LABEL_53;
    }
    if ( !v23 )
    {
LABEL_42:
      v13 = -1073741772;
      goto LABEL_43;
    }
    v25 = *v18;
    String1.Buffer = v18;
    String1.Length = v21;
    String1.MaximumLength = v21;
    LODWORD(v5) = *(_DWORD *)(v24 + 24);
    v73 = v5;
    if ( v25 )
    {
      do
      {
        if ( v25 >= 0x100u )
          v26 = RtlUpcaseUnicodeChar(v25);
        else
          v26 = *(_WORD *)(v22 + 2LL * (unsigned __int8)v25 + 6080);
        ++v18;
        LODWORD(i) = v26 + 101 * i;
        v25 = *v18;
      }
      while ( *v18 );
      LODWORD(v10) = v80;
      LODWORD(v5) = v73;
      v23 = v74;
    }
    v15 = ((unsigned int)v5
         & ((69069 * (_DWORD)i + 1) & 0xFFFF0000 | ((unsigned __int64)(unsigned int)(1103515245 * i + 12345) >> 16))) << 6;
    for ( i = *(_QWORD *)(v15 + *(_QWORD *)(v24 + 8)); ; i = *(_QWORD *)(i + 24) )
    {
      while ( 1 )
      {
        if ( !i )
        {
          i = v67;
          goto LABEL_42;
        }
        v56 = *(_QWORD *)(i + 8);
        if ( v56 )
          break;
        if ( *(_QWORD *)(*((_QWORD *)v23 + 4) + 8LL) )
        {
          i = *(_QWORD *)(i + 24);
        }
        else
        {
LABEL_181:
          LODWORD(v15) = *(_DWORD *)(i + 32);
          if ( v21 == (_DWORD)v15 )
          {
            *(_DWORD *)(&String2.MaximumLength + 1) = 0;
            String2.Length = v15;
            String2.MaximumLength = v15;
            String2.Buffer = (PWSTR)(i + 144);
            if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
            {
              v67 = i;
              v13 = 0;
              goto LABEL_43;
            }
            v23 = v74;
          }
          i = *(_QWORD *)(i + 24);
        }
      }
      if ( v23 == *(wchar_t **)(v56 + 16) )
        goto LABEL_181;
    }
  }
LABEL_65:
  v28 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v28 + 20) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v28, 39, v6, (_DWORD)v3, (__int64)Str, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 40, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qilq(1028, 41, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v1, *(_QWORD *)(v1 + 64), 0, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 28LL) )
  {
    WildcardSite = UlGenerateRoutingToken(v1, 2);
    if ( WildcardSite >= 0 )
    {
      WildcardSite = UlpTreeFindSiteIpMatch(v1, (char *)&v65 + 8);
      if ( WildcardSite >= 0 )
      {
        v62 = *(_QWORD *)(v1 + 2048) + 2LL;
        LOBYTE(v65) = 1;
        WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v62, v66, (char *)&v65 + 1);
      }
      if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_SSld(v61, 42, v6, *(_QWORD *)(v1 + 2080), *(_QWORD *)(v1 + 2048), WildcardSite >= 0, WildcardSite);
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 43, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qilq(1028, 41, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v1, *(_QWORD *)(v1 + 64), 1, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 28LL) )
  {
    WildcardSite = UlGenerateRoutingToken(v1, 3);
    if ( WildcardSite >= 0 )
    {
      WildcardSite = UlpTreeFindSiteIpMatch(v1, (char *)&v65 + 8);
      if ( WildcardSite >= 0 )
      {
        v64 = *(_QWORD *)(v1 + 2048) + 2LL;
        LOBYTE(v65) = 1;
        WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v64, v66, (char *)&v65 + 1);
      }
      if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_SSld(v63, 42, v6, *(_QWORD *)(v1 + 2080), *(_QWORD *)(v1 + 2048), WildcardSite >= 0, WildcardSite);
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 43, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  v83 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 44, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v3, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 12LL) )
  {
    WildcardSite = UlpTreeFindSite(*((_QWORD *)&v66 + 1), v3, &v83, (char *)&v65 + 8);
    if ( WildcardSite >= 0 )
    {
      LOBYTE(v65) = 1;
      WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v83, v66, (char *)&v65 + 1);
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  v29 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v29 + 12) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v29, 45, v6, (_DWORD)v3, v83, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 46, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  Str = 0;
  Pool3 = 0;
  v84 = 0;
  LODWORD(v83) = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 47, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v3, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 12LL) )
  {
    WildcardSite = UlpExtractSchemeHostPortIp(v3);
    if ( WildcardSite >= 0 )
    {
      v5 = 2LL * (unsigned int)(v84 + 2);
      if ( v5 <= 0xFFFFFFFF )
        Pool3 = (_WORD *)ExAllocatePool3(66, v5, 1280666709, UxLowPriorityPool, 1);
      if ( Pool3 )
      {
        WildcardSite = UlGenerateSubdomainWildcardUrl(v3, (__int64)&v83);
        if ( WildcardSite >= 0 )
        {
          Pool3[(unsigned int)v83] = 47;
          Pool3[(unsigned int)(v83 + 1)] = 0;
          LODWORD(v83) = v83 + 2;
          WildcardSite = UlpTreeFindSite(*((_QWORD *)&v66 + 1), Pool3, &Str, (char *)&v65 + 8);
          if ( WildcardSite >= 0 )
          {
            LOBYTE(v65) = 1;
            Str = &v3[v84 + 1];
            WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), Str, v66, (char *)&v65 + 1);
          }
        }
      }
      else
      {
        WildcardSite = -1073741670;
      }
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  v31 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v31 + 12) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSl(v31, v5, v6, (_DWORD)v3, (__int64)Str, WildcardSite >= 0);
  if ( Pool3 )
    ExFreePoolWithTag(Pool3, 0);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 49, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  v32 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqP(1028, 50, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v1, *(_QWORD *)(v1 + 64), &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 16LL) )
  {
    WildcardSite = UlGenerateRoutingToken(v1, 1);
    if ( WildcardSite >= 0 )
    {
      WildcardSite = UlpTreeFindSiteIpMatch(v1, (char *)&v65 + 8);
      if ( WildcardSite >= 0 )
      {
        v32 = *(_QWORD *)(v1 + 2048) + 2LL;
        LOBYTE(v65) = 1;
        WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v32, v66, (char *)&v65 + 1);
      }
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  v33 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v33 + 16) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v33, 51, v6, *(_QWORD *)(v1 + 2080), v32, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 52, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
  {
LABEL_163:
    if ( WildcardSite >= 0 )
    {
      v52 = *((_QWORD *)&v65 + 1);
      v53 = a1;
      *(_DWORD *)(a1 + 1448) = *(_DWORD *)(*((_QWORD *)&v65 + 1) + 72LL);
      if ( *(_BYTE *)(v52 + 38) && *(_DWORD *)(v52 + 72) == 1 && !(unsigned __int8)UlpIsLocalRequest(a1) )
        WildcardSite = -1073741790;
      goto LABEL_165;
    }
LABEL_200:
    v53 = a1;
    goto LABEL_165;
  }
  if ( !BYTE1(v65) )
    goto LABEL_199;
  v74 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 53, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v3, &v65);
  if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 24LL) )
  {
    WildcardSite = -1073741772;
    goto LABEL_157;
  }
  WildcardSite = UlpTreeFindWildcardSite(DWORD2(v66), (_DWORD)v3, 0, (unsigned int)&v74, (__int64)&v65 + 8);
  if ( WildcardSite >= 0 )
  {
    v34 = v74;
    v35 = *((_QWORD *)&v65 + 1);
    v70 = v66;
    v78 = v74;
    LOBYTE(v65) = 1;
    v68 = 0;
    v71 = 0;
    LOBYTE(v83) = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      WPP_SF_qqqi(
        1028,
        31,
        WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids,
        *((_QWORD *)&v65 + 1),
        v74,
        v66,
        (char *)&v65 + 1);
    j = v35;
    BYTE1(v65) = 1;
    v67 = v35;
    v37 = v34;
    v68 = 0;
    v38 = 0;
    LOBYTE(v83) = 0;
    v6 = 0;
    v75 = 0;
    v39 = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    {
      WPP_SF_qqLqqqq(1028, 29, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v35, v34, 3, &v83, &v71, &v68, 0);
      j = v67;
      v6 = 0;
      v39 = 0;
    }
    v71 = 0;
    v68 = 0;
    LOBYTE(v83) = 0;
    while ( 1 )
    {
      v40 = *(unsigned __int8 *)(j + 37);
      LODWORD(v41) = 0;
      if ( (_BYTE)v40 )
        v6 = j;
      else
        LODWORD(v41) = v39;
      v16 = *(_BYTE *)(j + 36) == 0;
      v72 = v6;
      LOBYTE(v84) = v41;
      if ( !v16 )
      {
        v75 = j;
        LOBYTE(v84) = 1;
      }
      if ( !v37 || !*v37 )
        break;
      v42 = (WCHAR *)v37;
      v43 = wcschr(v37, 0x2Fu);
      v37 = v43;
      if ( v43 )
      {
        *v43 = 0;
        v44 = v43 - v42;
        ++v37;
      }
      else
      {
        v44 = -1;
        do
          ++v44;
        while ( v42[v44] );
      }
      v45 = 2 * v44;
      String2 = 0;
      v46 = *(_QWORD *)(v67 + 136);
      v47 = *(wchar_t **)(v67 + 16);
      Str = v47;
      v48 = *(_QWORD *)(v46 + 1360);
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qqqdq(1028, 12, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, v46, v47, v42, v45, &v67);
        v47 = Str;
      }
      j = 0;
      v67 = 0;
      if ( v45 )
      {
        if ( !v47 )
        {
LABEL_147:
          v38 = -1073741772;
          goto LABEL_148;
        }
        v49 = *v42;
        String2.Buffer = v42;
        String2.Length = v45;
        String2.MaximumLength = v45;
        v40 = *(_DWORD *)(v48 + 24);
        v73 = v40;
        if ( v49 )
        {
          do
          {
            if ( v49 >= 0x100u )
              v50 = RtlUpcaseUnicodeChar(v49);
            else
              v50 = *(_WORD *)(v46 + 2LL * (unsigned __int8)v49 + 6080);
            ++v42;
            LODWORD(j) = v50 + 101 * j;
            v49 = *v42;
          }
          while ( *v42 );
          v40 = v73;
          v47 = Str;
        }
        v41 = (v40
             & ((69069 * (_DWORD)j + 1) & 0xFFFF0000 | ((unsigned __int64)(unsigned int)(1103515245 * j + 12345) >> 16))) << 6;
        for ( j = *(_QWORD *)(v41 + *(_QWORD *)(v48 + 8)); ; j = *(_QWORD *)(j + 24) )
        {
          while ( 2 )
          {
            if ( !j )
            {
              j = v67;
              goto LABEL_147;
            }
            v58 = *(_QWORD *)(j + 8);
            if ( v58 )
            {
              if ( v47 != *(wchar_t **)(v58 + 16) )
              {
                j = *(_QWORD *)(j + 24);
                continue;
              }
            }
            else if ( *(_QWORD *)(*((_QWORD *)v47 + 4) + 8LL) )
            {
              j = *(_QWORD *)(j + 24);
              continue;
            }
            break;
          }
          LODWORD(v41) = *(_DWORD *)(j + 32);
          if ( v45 == (_DWORD)v41 )
          {
            *(_DWORD *)(&String1.MaximumLength + 1) = 0;
            String1.Length = v41;
            String1.MaximumLength = v41;
            String1.Buffer = (PWSTR)(j + 144);
            if ( !RtlCompareUnicodeString(&String2, &String1, 1u) )
            {
              v67 = j;
              v38 = 0;
              goto LABEL_148;
            }
            v47 = Str;
          }
        }
      }
      v38 = -1073741811;
LABEL_148:
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qD(1028, 13, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, j, v38);
        j = v67;
      }
      if ( v37 )
      {
        *((_WORD *)v37 - 1) = 47;
        j = v67;
      }
      v6 = v72;
      if ( v38 == -1073741772 )
        break;
      v39 = v84;
      if ( v38 < 0 )
        goto LABEL_186;
    }
    v71 = v75;
    v68 = v6;
    if ( v75 != v6 )
      LOBYTE(v83) = v84;
LABEL_186:
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      WPP_SF_d(1028, 30, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)v38);
    if ( v71 && (_BYTE)v83 )
    {
      BYTE1(v65) = 0;
    }
    else if ( v68 )
    {
      v35 = v68;
      v57 = v70;
      if ( *(_QWORD *)(v68 + 8) )
      {
        while ( v35 )
        {
          if ( *(_BYTE *)(v35 + 37) )
          {
            WildcardSite = UlpSetUrlInfo(v57, v35, 0);
            if ( WildcardSite < 0 )
              goto LABEL_156;
          }
          v35 = *(_QWORD *)(v35 + 8);
        }
      }
      else
      {
        LOBYTE(v6) = 1;
        WildcardSite = UlpSetUrlInfo(v70, v68, v6);
        if ( WildcardSite < 0 )
          goto LABEL_156;
      }
      WildcardSite = 0;
LABEL_156:
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qSqqcd(v41, v40, v6, v35, (__int64)v78, v57, v68, SBYTE1(v65), WildcardSite);
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
          WPP_SF_Dd(1028, 33, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, BYTE1(v65), WildcardSite);
      }
      goto LABEL_157;
    }
    LOBYTE(v57) = v70;
    WildcardSite = -1073741772;
    goto LABEL_156;
  }
LABEL_157:
  v51 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v51 + 24) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v51, 54, v6, (_DWORD)v79, (__int64)v74, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 55, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
  {
LABEL_199:
    WildcardSite = -1073741769;
    goto LABEL_200;
  }
  v53 = a1;
  if ( (_BYTE)v65 )
    WildcardSite = -1073741766;
LABEL_165:
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qD(1028, 57, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v53 + 1296, WildcardSite);
  ExReleaseCacheAwarePushLockSharedEx(v81, 0);
  KeLeaveCriticalRegion();
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qD(1028, 144, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v53 + 1296, WildcardSite);
  v54 = *(_WORD **)(v53 + 2056);
  if ( v54 )
    *v54 = 63;
  if ( v85 )
    **(_WORD **)(v53 + 2048) = 42;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 128, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, (unsigned int)WildcardSite);
  return (unsigned int)WildcardSite;
}

```

## disassembly

```asm
0x140044600  mov     [rsp-8+arg_0], rcx
0x140044605  push    rbp
0x140044606  push    rbx
0x140044607  push    rsi
0x140044608  push    rdi
0x140044609  push    r12
0x14004460b  push    r13
0x14004460d  push    r14
0x14004460f  push    r15
0x140044611  lea     rbp, [rsp-8]
0x140044616  sub     rsp, 108h
0x14004461d  mov     rsi, rcx
0x140044620  xor     r13d, r13d
0x140044623  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14004462a  jnz     loc_140045550
0x140044630  mov     rcx, [rsi+808h]
0x140044637  test    rcx, rcx
0x14004463a  jz      short loc_140044640
0x14004463c  mov     [rcx], r13w
0x140044640  cmp     dword ptr [rsi+7C0h], 3
0x140044647  mov     r12d, 2Fh ; '/'
0x14004464d  jz      loc_140045581
0x140044653  mov     [rbp+40h+arg_18], r13b
0x140044657  mov     r14, [rsi+7F0h]
0x14004465e  lea     rdi, [rsi+510h]
0x140044665  mov     [rbp+40h+var_60], r14
0x140044669  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044670  jnz     loc_1400455AA
0x140044676  test    byte ptr cs:xmmword_1401A2CA0+8, 10h
0x14004467d  jnz     loc_1400455DB
0x140044683  mov     rax, [rsi+18h]
0x140044687  mov     rbx, [rax+448h]
0x14004468e  call    cs:__imp_KeEnterCriticalRegion
0x140044695  nop     dword ptr [rax+rax+00h]
0x14004469a  mov     rcx, [rbx+558h]
0x1400446a1  xor     edx, edx
0x1400446a3  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400446aa  nop     dword ptr [rax+rax+00h]
0x1400446af  xorps   xmm0, xmm0
0x1400446b2  mov     [rbp+40h+var_50], rax
0x1400446b6  movups  [rsp+140h+var_F0], xmm0
0x1400446bb  movups  [rsp+140h+var_E0], xmm0
0x1400446c0  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400446c7  jnz     loc_1400453F3
0x1400446cd  mov     rax, [rsi+18h]
0x1400446d1  mov     qword ptr [rsp+140h+var_E0], rdi
0x1400446d6  mov     byte ptr [rsp+140h+var_F0+1], 1
0x1400446db  mov     [rbp+40h+Str], r13
0x1400446df  mov     rcx, [rax+448h]
0x1400446e6  mov     qword ptr [rsp+140h+var_E0+8], rcx
0x1400446eb  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400446f2  jnz     loc_1400455FE
0x1400446f8  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x1400446fd  mov     rcx, [rax+528h]
0x140044704  cmp     [rcx+14h], r13d
0x140044708  jz      loc_140045626
0x14004470e  mov     rcx, qword ptr [rsp+140h+var_E0+8]
0x140044713  lea     rax, [rsp+140h+var_F0+8]
0x140044718  lea     r9, [rbp+40h+Str]
0x14004471c  mov     [rsp+140h+var_120], rax
0x140044721  mov     r8b, 1
0x140044724  mov     rdx, r14
0x140044727  call    UlpTreeFindWildcardSite
0x14004472c  mov     ebx, eax
0x14004472e  test    eax, eax
0x140044730  js      loc_1400449DC
0x140044736  mov     r8, qword ptr [rsp+140h+var_E0]
0x14004473b  mov     r12, [rbp+40h+Str]
0x14004473f  mov     r15, qword ptr [rsp+140h+var_F0+8]
0x140044744  mov     [rbp+40h+var_A8], r8
0x140044748  mov     [rbp+40h+var_68], r12
0x14004474c  mov     [rbp+40h+var_58], r15
0x140044750  mov     byte ptr [rsp+140h+var_F0], 1
0x140044755  mov     [rsp+140h+var_C8], r13
0x14004475a  mov     [rbp+40h+var_B0], r13
0x14004475e  mov     byte ptr [rbp+40h+arg_8], r13b
0x140044762  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044769  jnz     loc_140045630
0x14004476f  mov     rbx, r15
0x140044772  mov     byte ptr [rsp+140h+var_F0+1], 1
0x140044777  mov     [rsp+140h+var_D0], rbx
0x14004477c  mov     r14, r12
0x14004477f  mov     [rsp+140h+var_C8], r13
0x140044784  mov     edi, r13d
0x140044787  mov     byte ptr [rbp+40h+arg_8], r13b
0x14004478b  mov     r8, r13
0x14004478e  mov     [rbp+40h+var_90], r13
0x140044792  xor     sil, sil
0x140044795  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14004479c  jnz     loc_140175F5E
0x1400447a2  mov     [rbp+40h+var_B0], r13
0x1400447a6  mov     [rsp+140h+var_C8], r13
0x1400447ab  mov     byte ptr [rbp+40h+arg_8], sil
0x1400447af  movzx   edx, byte ptr [rbx+25h]
0x1400447b3  mov     ecx, r13d
0x1400447b6  test    dl, dl
0x1400447b8  movzx   eax, sil
0x1400447bc  cmovz   ecx, eax
0x1400447bf  cmovnz  r8, rbx
0x1400447c3  cmp     byte ptr [rbx+24h], 0
0x1400447c7  movzx   eax, cl
0x1400447ca  mov     [rbp+40h+var_B8], r8
0x1400447ce  mov     byte ptr [rbp+40h+arg_10], cl
0x1400447d1  jnz     loc_1400451EC
0x1400447d7  test    r14, r14
0x1400447da  jz      loc_14004494B
0x1400447e0  cmp     word ptr [r14], 0
0x1400447e5  jz      loc_14004494B
0x1400447eb  mov     edx, 2Fh ; '/'; Ch
0x1400447f0  mov     rcx, r14; Str
0x1400447f3  mov     rdi, r14
0x1400447f6  call    cs:__imp_wcschr
0x1400447fd  nop     dword ptr [rax+rax+00h]
0x140044802  mov     r14, rax
0x140044805  test    rax, rax
0x140044808  jz      loc_140045105
0x14004480e  mov     [rax], r13w
0x140044812  sub     rax, rdi
0x140044815  sar     rax, 1
0x140044818  add     r14, 2
0x14004481c  lea     r12d, [rax+rax]
0x140044820  xorps   xmm0, xmm0
0x140044823  mov     rax, [rsp+140h+var_D0]
0x140044828  movups  xmmword ptr [rbp+40h+String1.Length], xmm0
0x14004482c  mov     rsi, [rax+88h]
0x140044833  mov     r8, [rax+10h]
0x140044837  mov     [rbp+40h+var_98], r8
0x14004483b  mov     r13, [rsi+550h]
0x140044842  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044849  jnz     loc_140045662
0x14004484f  xor     ebx, ebx
0x140044851  mov     [rsp+140h+var_D0], rbx
0x140044856  test    r12d, r12d
0x140044859  jz      loc_14004569D
0x14004485f  test    r8, r8
0x140044862  jz      loc_140044907
0x140044868  movzx   eax, word ptr [rdi]
0x14004486b  mov     [rbp+40h+String1.Buffer], rdi
0x14004486f  mov     [rbp+40h+String1.Length], r12w
0x140044874  mov     [rbp+40h+String1.MaximumLength], r12w
0x140044879  mov     edx, [r13+18h]
0x14004487d  mov     [rbp+40h+var_A0], edx
0x140044880  test    ax, ax
0x140044883  jz      short loc_1400448C4
0x140044885  mov     r15d, 100h
0x14004488b  nop     dword ptr [rax+rax+00h]
0x140044890  cmp     ax, r15w
0x140044894  jnb     loc_1400456A7
0x14004489a  movzx   ecx, al
0x14004489d  movzx   eax, word ptr [rsi+rcx*2+17C0h]
0x1400448a5  imul    ebx, 65h ; 'e'
0x1400448a8  add     rdi, 2
0x1400448ac  movzx   eax, ax
0x1400448af  add     ebx, eax
0x1400448b1  movzx   eax, word ptr [rdi]
0x1400448b4  test    ax, ax
0x1400448b7  jnz     short loc_140044890
0x1400448b9  mov     r15, [rbp+40h+var_58]
0x1400448bd  mov     edx, [rbp+40h+var_A0]
0x1400448c0  mov     r8, [rbp+40h+var_98]
0x1400448c4  imul    ecx, ebx, 41C64E6Dh
0x1400448ca  mov     r9d, 0FFFF0000h
0x1400448d0  imul    eax, ebx, 10DCDh
0x1400448d6  add     ecx, 3039h
0x1400448dc  inc     eax
0x1400448de  shr     rcx, 10h
0x1400448e2  and     rax, r9
0x1400448e5  or      rcx, rax
0x1400448e8  mov     eax, edx
0x1400448ea  and     rcx, rax
0x1400448ed  mov     rax, [r13+8]
0x1400448f1  shl     rcx, 6
0x1400448f5  mov     rbx, [rcx+rax]
0x1400448f9  test    rbx, rbx
0x1400448fc  jnz     loc_140044F5E
0x140044902  mov     rbx, [rsp+140h+var_D0]
0x140044907  mov     edi, 0C0000034h
0x14004490c  xor     r13d, r13d
0x14004490f  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044916  jnz     loc_14004548A
0x14004491c  test    r14, r14
0x14004491f  jz      short loc_14004492D
0x140044921  mov     word ptr [r14-2], 2Fh ; '/'
0x140044928  mov     rbx, [rsp+140h+var_D0]
0x14004492d  mov     r8, [rbp+40h+var_B8]
0x140044931  cmp     edi, 0C0000034h
0x140044937  jz      short loc_140044947
0x140044939  movzx   esi, byte ptr [rbp+40h+arg_10]
0x14004493d  test    edi, edi
0x14004493f  jns     loc_1400447AF
0x140044945  jmp     short loc_140044960
0x140044947  movzx   eax, byte ptr [rbp+40h+arg_10]
0x14004494b  mov     r9, [rbp+40h+var_90]
0x14004494f  mov     [rbp+40h+var_B0], r9
0x140044953  mov     [rsp+140h+var_C8], r8
0x140044958  cmp     r9, r8
0x14004495b  jz      short loc_140044960
0x14004495d  mov     byte ptr [rbp+40h+arg_8], al
0x140044960  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044967  jnz     loc_1400456D1
0x14004496d  cmp     [rbp+40h+var_B0], 0
0x140044972  jnz     loc_1400451FA
0x140044978  mov     rax, [rsp+140h+var_C8]
0x14004497d  test    rax, rax
0x140044980  jz      loc_140044F7B
0x140044986  cmp     qword ptr [rax+8], 0
0x14004498b  mov     r15, rax
0x14004498e  mov     rdi, [rbp+40h+var_A8]
0x140044992  jz      loc_1400451CF
0x140044998  test    r15, r15
0x14004499b  jz      short loc_1400449BE
0x14004499d  cmp     byte ptr [r15+25h], 0
0x1400449a2  jz      short loc_1400449B8
0x1400449a4  xor     r8d, r8d
0x1400449a7  mov     rdx, r15
0x1400449aa  mov     rcx, rdi
0x1400449ad  call    UlpSetUrlInfo
0x1400449b2  mov     ebx, eax
0x1400449b4  test    eax, eax
0x1400449b6  js      short loc_1400449C1
0x1400449b8  mov     r15, [r15+8]
0x1400449bc  jmp     short loc_140044998
0x1400449be  mov     ebx, r13d
0x1400449c1  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400449c8  jnz     loc_140175FB2
0x1400449ce  mov     rsi, [rbp+40h+arg_0]
0x1400449d2  mov     r12d, 2Fh ; '/'
0x1400449d8  mov     r14, [rbp+40h+var_60]
0x1400449dc  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x1400449e1  mov     rcx, [rax+528h]
0x1400449e8  cmp     dword ptr [rcx+14h], 0
0x1400449ec  jz      short loc_1400449FB
0x1400449ee  test    byte ptr cs:xmmword_1401A2CA0+8, 10h
0x1400449f5  jnz     loc_1400456EF
0x1400449fb  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a02  jnz     loc_140045719
0x140044a08  mov     r15d, 2Ah ; '*'
0x140044a0e  cmp     ebx, 0C0000034h
0x140044a14  jnz     loc_140044EBC
0x140044a1a  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044a1f  jz      loc_140045093
0x140044a25  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a2c  jnz     loc_140045737
0x140044a32  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044a37  mov     rcx, [rax+528h]
0x140044a3e  cmp     dword ptr [rcx+1Ch], 0
0x140044a42  jnz     loc_140176012
0x140044a48  mov     ebx, 0C0000034h
0x140044a4d  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a54  jnz     loc_1400454B1
0x140044a5a  cmp     ebx, 0C0000034h
0x140044a60  jnz     loc_140044EBC
0x140044a66  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044a6b  jz      loc_140045093
0x140044a71  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a78  jnz     loc_14004576D
0x140044a7e  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044a83  mov     rcx, [rax+528h]
0x140044a8a  cmp     dword ptr [rcx+1Ch], 0
0x140044a8e  jnz     loc_14017609F
0x140044a94  mov     ebx, 0C0000034h
0x140044a99  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044aa0  jnz     loc_1400454CF
0x140044aa6  cmp     ebx, 0C0000034h
0x140044aac  jnz     loc_140044EBC
0x140044ab2  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044ab7  jz      loc_140045093
0x140044abd  mov     [rbp+40h+arg_8], r13
0x140044ac1  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044ac8  jnz     loc_1400457A6
0x140044ace  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044ad3  mov     rcx, [rax+528h]
0x140044ada  cmp     dword ptr [rcx+0Ch], 0
0x140044ade  jnz     loc_140045226
0x140044ae4  mov     ebx, 0C0000034h
0x140044ae9  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044aee  mov     rcx, [rax+528h]
0x140044af5  cmp     dword ptr [rcx+0Ch], 0
0x140044af9  jnz     loc_1400453BC
0x140044aff  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044b06  jnz     loc_1400457CE
0x140044b0c  cmp     ebx, 0C0000034h
0x140044b12  jnz     loc_140044EBC
0x140044b18  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044b1d  jz      loc_140045093
0x140044b23  mov     [rbp+40h+Str], r13
0x140044b27  mov     rdi, r13
0x140044b2a  mov     [rbp+40h+arg_10], r13d
0x140044b2e  mov     dword ptr [rbp+40h+arg_8], r13d
0x140044b32  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044b39  jnz     loc_140045464
0x140044b3f  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044b44  mov     rcx, [rax+528h]
0x140044b4b  cmp     dword ptr [rcx+0Ch], 0
0x140044b4f  jnz     loc_1400452D5
0x140044b55  mov     ebx, 0C0000034h
0x140044b5a  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044b5f  mov     rcx, [rax+528h]
0x140044b66  cmp     dword ptr [rcx+0Ch], 0
0x140044b6a  jnz     loc_14004528B
  ... truncated ...
```
