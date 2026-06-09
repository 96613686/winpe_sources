# Int_FWVerifyFirewallRule

- ea: `0x18000d490`
- end: `0x18000f50c`
- name: `Int_FWVerifyFirewallRule`
- size: `8316`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c720`

## callees

- `0x1800072d0`
- `0x18000c880`
- `0x18000cb50`
- `0x18000cbd0`
- `0x18000ccd4`
- `0x18000cdf0`
- `0x18000d2cc`
- `0x18000d364`
- `0x18000d3fc`
- `0x18000d490`
- `0x18000f520`
- `0x18000fbc0`
- `0x18000fdc0`
- `0x1800116f0`
- `0x1800118e0`
- `0x180014200`
- `0x180017be0`
- `0x180017d1c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000dfeb`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000e163`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000dfeb`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000e163`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d554`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d598`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d60b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d655`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d6a8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d6f1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000da50`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dab0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000db2b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dbbb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dc0b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dcd5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dd8b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000ddf6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000de59`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d554`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d598`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d60b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d655`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d6a8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d6f1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000da50`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dab0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000db2b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dbbb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dc0b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dcd5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dd8b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000ddf6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000de59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d5ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d5ce`

## pseudocode

```c
__int64 __fastcall Int_FWVerifyFirewallRule(__int64 a1, __int64 a2, int *a3)
{
  unsigned __int16 v5; // ax
  unsigned int v6; // eax
  unsigned int v7; // r12d
  const wchar_t *v8; // rcx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rax
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  const WCHAR *v13; // r8
  const wchar_t *v14; // rcx
  unsigned __int64 v15; // rax
  const wchar_t *v16; // rcx
  unsigned __int64 v17; // rax
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rcx
  unsigned __int64 v20; // rax
  const wchar_t *v21; // rcx
  const wchar_t *v22; // rcx
  unsigned __int64 v23; // rax
  unsigned __int16 v24; // ax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned __int16 v27; // di
  unsigned __int16 v28; // dx
  int v29; // edx
  unsigned int v30; // eax
  unsigned __int16 v31; // cx
  __int16 v32; // ax
  __int16 v33; // cx
  __int16 v34; // ax
  __int16 v35; // ax
  const wchar_t *v36; // rcx
  unsigned __int64 v37; // rax
  const WCHAR *v38; // rdi
  _BYTE *v39; // r10
  const wchar_t *v40; // rcx
  unsigned __int64 v41; // rax
  const WCHAR *v42; // rdi
  const wchar_t *v43; // rcx
  unsigned __int64 v44; // rax
  const WCHAR **v45; // rdi
  const WCHAR *v46; // rsi
  int v47; // ebp
  const wchar_t *v48; // rcx
  unsigned __int64 v49; // rax
  const wchar_t *v50; // rcx
  unsigned __int64 v51; // rax
  unsigned int v52; // edi
  __int64 i; // rdi
  const wchar_t *v54; // rcx
  unsigned __int64 v55; // rax
  _BYTE *v56; // r10
  __int64 j; // r8
  const wchar_t *v58; // rcx
  unsigned __int64 v59; // rax
  __int64 k; // rdi
  unsigned int v61; // eax
  const wchar_t *v62; // rcx
  unsigned __int64 v63; // rax
  __int16 v64; // cx
  const wchar_t *v65; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  __int16 v69; // ax
  unsigned __int16 v70; // dx
  __int64 v71; // rax
  _QWORD *v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r9
  _QWORD *v75; // rcx
  __int64 v76; // rdx
  _QWORD *v77; // rcx
  __int64 v78; // rdx
  _QWORD *v79; // rcx
  __int64 v80; // rdx
  _QWORD *v81; // rcx
  __int64 v82; // rdx
  _QWORD *v83; // rcx
  __int64 v84; // rdx
  _QWORD *v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rdx
  int v88; // eax
  _QWORD *v89; // rcx
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // rdx
  _QWORD *v94; // rcx
  __int64 v95; // rdx
  _QWORD *v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rdx
  _QWORD *v100; // rcx
  __int64 v101; // rdx
  _QWORD *v102; // rcx
  __int64 v103; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  *a3 = 0x10000;
  v5 = *(_WORD *)(a2 + 8);
  if ( v5 < 0x100u )
  {
    *a3 = 1069136;
    v7 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    return v7;
  }
  if ( v5 < 0x200u )
  {
    if ( (unsigned int)IsRuleOldv1Compliant(a2)
      && ((unsigned int)IsRuleOldGlobalOpenPort(a2) || (unsigned int)IsRuleOldAuthApp(a2)) )
    {
      *a3 = 1069136;
      v7 = 87;
      v72 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v73 = 13;
      v74 = 87;
    }
    else
    {
      *a3 = 1069136;
      v7 = 87;
      v72 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v73 = 12;
      v74 = 87;
    }
LABEL_300:
    WPP_SF_d(v72[2], v73, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v74);
    return v7;
  }
  if ( v5 >= 0x300u )
    *a3 = 0x40000;
  v6 = Int_FwValidateComplianceAndReduceFirewallRuleToVersion(a2, a3, *(unsigned __int16 *)(a2 + 8));
  v7 = v6;
  if ( v6 )
  {
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v73 = 14;
    v74 = v6;
    goto LABEL_300;
  }
  v8 = *(const wchar_t **)(a2 + 16);
  if ( !v8 )
  {
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_352;
    v76 = 228;
    goto LABEL_379;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  if ( v10 >= 0x200 )
  {
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_352;
    v76 = 229;
    goto LABEL_379;
  }
  if ( !v10 )
  {
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_352;
    v76 = 230;
    goto LABEL_379;
  }
  if ( wcschr(v8, 0x7Cu) )
  {
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_352;
    v76 = 231;
LABEL_379:
    WPP_SF_d(v75[2], v76, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
LABEL_352:
    *a3 = 524296;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 15;
    goto LABEL_248;
  }
  v11 = *(const wchar_t **)(a2 + 24);
  if ( !v11 )
  {
    v77 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_355;
    v78 = 228;
    goto LABEL_392;
  }
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  if ( v12 >= 0x2710 )
  {
    v77 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_355;
    v78 = 229;
    goto LABEL_392;
  }
  if ( !v12 )
  {
    v77 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_355;
    v78 = 230;
    goto LABEL_392;
  }
  if ( wcschr(v11, 0x7Cu) )
  {
    v77 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_355;
    v78 = 231;
LABEL_392:
    WPP_SF_d(v77[2], v78, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
LABEL_355:
    *a3 = 524289;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 16;
    goto LABEL_248;
  }
  v13 = *(const WCHAR **)(a2 + 24);
  if ( v13 && CompareStringW(0x7Fu, 1u, v13, -1, L"ALL", -1) == 2 )
  {
    *a3 = 524289;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 17;
    goto LABEL_248;
  }
  v14 = *(const wchar_t **)(a2 + 32);
  if ( v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    if ( v15 >= 0x2710 )
    {
      v79 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_358;
      v80 = 229;
    }
    else
    {
      if ( !wcschr(v14, 0x7Cu) )
        goto LABEL_26;
      v79 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_358:
        *a3 = 524290;
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 18;
        goto LABEL_248;
      }
      v80 = 231;
    }
    WPP_SF_d(v79[2], v80, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_358;
  }
LABEL_26:
  v16 = *(const wchar_t **)(a2 + 272);
  if ( v16 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    if ( v17 >= 0x104 )
    {
      v81 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_361;
      v82 = 229;
    }
    else if ( v17 )
    {
      if ( !wcschr(v16, 0x7Cu) )
        goto LABEL_32;
      v81 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_361:
        *a3 = 524291;
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 19;
        goto LABEL_248;
      }
      v82 = 231;
    }
    else
    {
      v81 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_361;
      v82 = 230;
    }
    WPP_SF_d(v81[2], v82, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_361;
  }
LABEL_32:
  v18 = *(const wchar_t **)(a2 + 272);
  if ( v18 && wcspbrk(v18, L"/*?\"<>|") )
  {
    *a3 = 524291;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 20;
    goto LABEL_248;
  }
  v19 = *(const wchar_t **)(a2 + 280);
  if ( v19 )
  {
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    if ( v20 >= 0x104 )
    {
      v83 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_364;
      v84 = 229;
    }
    else if ( v20 )
    {
      if ( !wcschr(v19, 0x7Cu) )
        goto LABEL_39;
      v83 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_364:
        *a3 = 524292;
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 21;
        goto LABEL_248;
      }
      v84 = 231;
    }
    else
    {
      v83 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_364;
      v84 = 230;
    }
    WPP_SF_d(v83[2], v84, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_364;
  }
LABEL_39:
  v21 = *(const wchar_t **)(a2 + 280);
  if ( v21 && wcspbrk(v21, L"/\\") )
  {
    *a3 = 524292;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 22;
    goto LABEL_248;
  }
  v22 = *(const wchar_t **)(a2 + 312);
  if ( v22 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    if ( v23 >= 0x2710 )
    {
      v85 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_346;
      v86 = 229;
    }
    else
    {
      if ( !wcschr(v22, 0x7Cu) )
        goto LABEL_45;
      v85 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_346:
        *a3 = 524295;
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 23;
        goto LABEL_248;
      }
      v86 = 231;
    }
    WPP_SF_d(v85[2], v86, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_346;
  }
LABEL_45:
  if ( (unsigned int)(*(_DWORD *)(a2 + 44) - 1) > 1 )
  {
    *a3 = 1048720;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 24;
    goto LABEL_248;
  }
  if ( (unsigned int)Int_FwValidateProfiles(*(_DWORD *)(a2 + 40)) )
  {
    *a3 = 1048656;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 25;
    goto LABEL_248;
  }
  v24 = *(_WORD *)(a2 + 48);
  if ( v24 > 0x100u )
  {
    *a3 = 1048736;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 26;
    goto LABEL_248;
  }
  switch ( v24 )
  {
    case 6u:
      v27 = 272;
      if ( *(_DWORD *)(a2 + 44) != 2 )
        v27 = 0;
      v28 = 0;
      if ( *(_DWORD *)(a2 + 44) != 2 )
        v28 = 523;
      if ( (unsigned int)Int_FwValidatePorts((unsigned __int16 *)(a2 + 56), v28, 1, a3) )
      {
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 27;
        goto LABEL_248;
      }
      if ( (unsigned int)Int_FwValidatePorts((unsigned __int16 *)(a2 + 80), v27, 1, a3) )
      {
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 28;
        goto LABEL_248;
      }
      break;
    case 0x11u:
      v69 = 196;
      if ( *(_DWORD *)(a2 + 44) != 1 )
        v69 = 4;
      v70 = 0;
      if ( *(_DWORD *)(a2 + 44) != 2 )
        v70 = v69;
      if ( (unsigned int)Int_FwValidatePorts((unsigned __int16 *)(a2 + 56), v70, 1, a3) )
      {
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 29;
        goto LABEL_248;
      }
      if ( (unsigned int)Int_FwValidatePorts((unsigned __int16 *)(a2 + 80), 0, 1, a3) )
      {
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 30;
        goto LABEL_248;
      }
      break;
    case 1u:
      if ( (unsigned int)Int_FwValidateIcmpList(a2 + 56, a3) )
      {
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 31;
        goto LABEL_248;
      }
      break;
    case 0x3Au:
      if ( (unsigned int)Int_FwValidateIcmpList(a2 + 56, a3) )
      {
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 32;
        goto LABEL_248;
      }
      break;
    default:
      if ( *(_DWORD *)(a2 + 64) || *(_DWORD *)(a2 + 88) || *(_DWORD *)(a2 + 56) || *(_WORD *)(a2 + 80) )
      {
        *a3 = 1048737;
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v26 = 33;
        goto LABEL_248;
      }
      break;
  }
  if ( (unsigned int)Int_FwValidateAddresses(a2 + 104, 0, 1, a3) )
  {
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 34;
    goto LABEL_248;
  }
  if ( (unsigned int)Int_FwValidateAddresses(a2 + 176, 0, 0, a3) )
  {
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 35;
    goto LABEL_248;
  }
  v29 = *(_DWORD *)(a2 + 248);
  if ( v29 )
  {
    if ( !*(_QWORD *)(a2 + 256) )
    {
LABEL_69:
      *a3 = 1048688;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 36;
      goto LABEL_248;
    }
  }
  else if ( *(_QWORD *)(a2 + 256) )
  {
    goto LABEL_69;
  }
  v30 = *(_DWORD *)(a2 + 264);
  if ( v30 >= 0x10 )
  {
    *a3 = 1048689;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 37;
    goto LABEL_248;
  }
  v31 = *(_WORD *)(a2 + 292);
  if ( (v31 & 0x2000) != 0 && (v29 != 1 || v30) )
  {
    *a3 = 1048688;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 38;
    goto LABEL_248;
  }
  if ( (unsigned int)(*(_DWORD *)(a2 + 288) - 1) > 2 )
  {
    *a3 = 1048704;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 39;
    goto LABEL_248;
  }
  if ( v31 >= 0x4000u )
  {
    *a3 = 1048752;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 40;
    goto LABEL_248;
  }
  if ( (v31 & 8) != 0 && *(_DWORD *)(a2 + 44) == 2 )
  {
    *a3 = 1048752;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 41;
    goto LABEL_248;
  }
  if ( (v31 & 0x80u) != 0 && *(_DWORD *)(a2 + 44) == 2 )
  {
    *a3 = 1048752;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 42;
    goto LABEL_248;
  }
  if ( (v31 & 0x100) != 0 && *(_DWORD *)(a2 + 44) == 2 )
  {
    *a3 = 1048752;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 43;
    goto LABEL_248;
  }
  if ( (v31 & 0x88) == 0x80 )
  {
    *a3 = 1048738;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 44;
    goto LABEL_248;
  }
  if ( (v31 & 0x108) == 0x108 )
  {
    *a3 = 1048738;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 45;
    goto LABEL_248;
  }
  if ( (v31 & 0x100) != 0 && (unsigned int)Int_FwValidateDeferUserRule(a2) )
  {
    *a3 = 1048740;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 46;
    goto LABEL_248;
  }
  v32 = *(_WORD *)(a2 + 292);
  if ( (v32 & 0x10) != 0 )
  {
    if ( *(_DWORD *)(a2 + 44) == 1 || *(_WORD *)(a2 + 48) == 6 || (v33 = *(_WORD *)(a2 + 292) & 6, (v32 & 6) != 0) )
    {
      *a3 = 1048752;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 47;
      goto LABEL_248;
    }
  }
  else
  {
    v33 = *(_WORD *)(a2 + 292) & 6;
  }
  if ( (v32 & 0x800) != 0 )
  {
    if ( *(_WORD *)(a2 + 48) == 6 || v33 )
    {
      *a3 = 1048752;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 48;
      goto LABEL_248;
    }
  }
  else if ( v33 == 6 )
  {
    *a3 = 1048756;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 49;
    goto LABEL_248;
  }
  if ( (v32 & 0x22) == 0x20 )
  {
    *a3 = 1048760;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 50;
    goto LABEL_248;
  }
  if ( v33 && *(_DWORD *)(a2 + 288) == 2 )
  {
    *a3 = 1048707;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 51;
    goto LABEL_248;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 449, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  *a3 = 0x10000;
  if ( !(unsigned int)FwLicensingIsNetIsolationOnly() )
  {
    if ( *(_DWORD *)(a2 + 288) == 1
      && (*(_DWORD *)(a2 + 44) != 1 || (*(_BYTE *)(a2 + 292) & 6) == 0 || !*(_QWORD *)(a2 + 296)) )
    {
      *a3 = 1048705;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_451;
      v87 = 450;
      goto LABEL_450;
    }
    v34 = *(_WORD *)(a2 + 292);
    if ( (v34 & 0x200) != 0 && *(_DWORD *)(a2 + 44) == 2 && (v34 & 6) == 0 )
    {
      *a3 = 1048739;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_451;
      v87 = 451;
LABEL_450:
      WPP_SF_d(v25[2], v87, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      v25 = WPP_GLOBAL_Control;
LABEL_451:
      v7 = 87;
      if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 1) == 0 )
        return v7;
      v26 = 52;
      goto LABEL_248;
    }
  }
  v35 = *(_WORD *)(a2 + 292);
  if ( (v35 & 0x40) != 0 && ((v35 & 4) == 0 || *(_DWORD *)(a2 + 44) == 2) )
  {
    v88 = 1048766;
    v7 = 87;
    if ( *(_DWORD *)(a2 + 44) != 2 )
      v88 = 1048758;
    *a3 = v88;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 53;
    goto LABEL_248;
  }
  v36 = *(const wchar_t **)(a2 + 296);
  if ( v36 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
    if ( v37 >= 0x2710 )
    {
      v89 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_472;
      v90 = 229;
    }
    else
    {
      if ( !wcschr(v36, 0x7Cu) )
        goto LABEL_112;
      v89 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_472;
      v90 = 231;
    }
    v91 = v89[2];
    goto LABEL_466;
  }
LABEL_112:
  v38 = *(const WCHAR **)(a2 + 296);
  v39 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v39 = WPP_GLOBAL_Control;
  }
  if ( v38 )
  {
    v67 = -1;
    do
      ++v67;
    while ( v38[v67] );
    if ( v67 )
    {
      if ( !(unsigned int)Int_FwValidateAndMigrateSecurityDescriptor(v38, 0, 0) )
      {
        v39 = WPP_GLOBAL_Control;
        goto LABEL_116;
      }
LABEL_472:
      *a3 = 524293;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 57;
      goto LABEL_248;
    }
    if ( v39 == (_BYTE *)&WPP_GLOBAL_Control || (v39[28] & 1) == 0 )
      goto LABEL_472;
    v91 = *((_QWORD *)v39 + 2);
    v90 = 295;
LABEL_466:
    WPP_SF_d(v91, v90, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_472;
  }
LABEL_116:
  v40 = *(const wchar_t **)(a2 + 304);
  if ( v40 )
  {
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    if ( v41 >= 0x2710 )
    {
      if ( v39 == (_BYTE *)&WPP_GLOBAL_Control || (v39[28] & 1) == 0 )
        goto LABEL_485;
      v92 = 229;
LABEL_479:
      WPP_SF_d(*((_QWORD *)v39 + 2), v92, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
LABEL_485:
      *a3 = 524294;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 58;
      goto LABEL_248;
    }
    if ( wcschr(v40, 0x7Cu) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      goto LABEL_485;
    }
    v39 = WPP_GLOBAL_Control;
  }
  v42 = *(const WCHAR **)(a2 + 304);
  if ( v39 != (_BYTE *)&WPP_GLOBAL_Control && (v39[28] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)v39 + 2), 294, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v39 = WPP_GLOBAL_Control;
  }
  if ( !v42 )
    goto LABEL_126;
  v68 = -1;
  do
    ++v68;
  while ( v42[v68] );
  if ( !v68 )
  {
    if ( v39 == (_BYTE *)&WPP_GLOBAL_Control || (v39[28] & 1) == 0 )
      goto LABEL_485;
    v92 = 295;
    goto LABEL_479;
  }
  if ( (unsigned int)Int_FwValidateAndMigrateSecurityDescriptor(v42, 0, 0) )
    goto LABEL_485;
  v39 = WPP_GLOBAL_Control;
LABEL_126:
  if ( (*(_WORD *)(a2 + 292) & 0x1000) != 0 )
    goto LABEL_495;
  v43 = *(const wchar_t **)(a2 + 368);
  if ( v43 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    if ( v44 >= 0x2710 )
    {
      if ( v39 == (_BYTE *)&WPP_GLOBAL_Control || (v39[28] & 1) == 0 )
        goto LABEL_500;
      v93 = 229;
LABEL_491:
      WPP_SF_d(*((_QWORD *)v39 + 2), v93, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      goto LABEL_500;
    }
    if ( wcschr(v43, 0x7Cu) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      goto LABEL_500;
    }
    v39 = WPP_GLOBAL_Control;
  }
  if ( (*(_WORD *)(a2 + 292) & 0x1000) != 0 )
  {
LABEL_495:
    v45 = (const WCHAR **)(a2 + 368);
    if ( (unsigned int)Int_FwValidateSerializedString(*(_QWORD *)(a2 + 368)) )
    {
LABEL_500:
      *a3 = 524306;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 59;
      goto LABEL_248;
    }
    v39 = WPP_GLOBAL_Control;
  }
  else
  {
    v45 = (const WCHAR **)(a2 + 368);
  }
  v46 = *v45;
  v47 = (*(unsigned __int16 *)(a2 + 292) >> 12) & 1;
  if ( v39 != (_BYTE *)&WPP_GLOBAL_Control && (v39[28] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)v39 + 2), 294, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v39 = WPP_GLOBAL_Control;
    v45 = (const WCHAR **)(a2 + 368);
  }
  if ( !v46 )
    goto LABEL_139;
  v71 = -1;
  do
    ++v71;
  while ( v46[v71] );
  if ( !v71 )
  {
    if ( v39 == (_BYTE *)&WPP_GLOBAL_Control || (v39[28] & 1) == 0 )
      goto LABEL_500;
    v93 = 295;
    goto LABEL_491;
  }
  if ( (unsigned int)Int_FwValidateAndMigrateSecurityDescriptor(v46, v47, 0) )
    goto LABEL_500;
  v39 = WPP_GLOBAL_Control;
LABEL_139:
  if ( *v45 && *(_QWORD *)(a2 + 280) )
  {
    *a3 = 1048770;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 60;
    goto LABEL_248;
  }
  v48 = *(const wchar_t **)(a2 + 376);
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( v48[v49] );
    if ( v49 >= 0x2710 )
    {
      if ( v39 != (_BYTE *)&WPP_GLOBAL_Control && (v39[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v39 + 2), 229, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      goto LABEL_509;
    }
    if ( wcschr(v48, 0x7Cu) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      goto LABEL_509;
    }
  }
  if ( (unsigned int)Int_FwValidatePackageId(*(_QWORD *)(a2 + 376)) )
  {
LABEL_509:
    *a3 = 1048832;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 61;
    goto LABEL_248;
  }
  v50 = *(const wchar_t **)(a2 + 384);
  if ( !v50 )
    goto LABEL_151;
  v51 = -1;
  do
    ++v51;
  while ( v50[v51] );
  if ( v51 >= 0x2710 )
  {
    v94 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_349;
    v95 = 229;
LABEL_515:
    WPP_SF_d(v94[2], v95, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_349;
  }
  if ( wcschr(v50, 0x7Cu) )
  {
    v94 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_349;
    v95 = 231;
    goto LABEL_515;
  }
LABEL_151:
  if ( (unsigned int)Int_FwValidateUser(*(_QWORD *)(a2 + 384)) )
  {
LABEL_349:
    *a3 = 1048772;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 62;
    goto LABEL_248;
  }
  v52 = *(_DWORD *)(a2 + 392);
  if ( v52 )
  {
    if ( *(_DWORD *)(a2 + 64)
      || *(_WORD *)(a2 + 56)
      || *(_DWORD *)(a2 + 88)
      || *(_WORD *)(a2 + 80)
      || !(unsigned int)IsAddressesEmpty(a2 + 104)
      || !(unsigned int)IsAddressesEmpty(a2 + 176) )
    {
      *a3 = 1049088;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 63;
      goto LABEL_248;
    }
    if ( v52 >= 0x100 )
    {
      *a3 = 1049089;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v26 = 64;
      goto LABEL_248;
    }
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 400); i = (unsigned int)(i + 1) )
  {
    v54 = *(const wchar_t **)(*(_QWORD *)(a2 + 408) + 8 * i);
    if ( !v54 )
    {
      v96 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v97 = 228;
LABEL_538:
        WPP_SF_d(v96[2], v97, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      }
LABEL_539:
      *(_DWORD *)(a2 + 336) = 524310;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
        v25 = WPP_GLOBAL_Control;
      }
      v7 = 87;
      if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 1) == 0 )
        return v7;
      v26 = 65;
LABEL_248:
      WPP_SF_d(v25[2], v26, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      return v7;
    }
    v55 = -1;
    do
      ++v55;
    while ( v54[v55] );
    if ( v55 >= 0x104 )
    {
      v96 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v97 = 229;
        goto LABEL_538;
      }
      goto LABEL_539;
    }
    if ( !v55 )
    {
      v96 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v97 = 230;
        goto LABEL_538;
      }
      goto LABEL_539;
    }
    if ( wcschr(v54, 0x7Cu) )
    {
      v96 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v97 = 231;
        goto LABEL_538;
      }
      goto LABEL_539;
    }
  }
  if ( (*(_QWORD *)(a2 + 296) || *(_QWORD *)(a2 + 304))
    && (*(_BYTE *)(a2 + 292) & 6) == 0
    && (*(_WORD *)(a2 + 424) & 0x100) == 0 )
  {
    *a3 = 1048768;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 66;
    goto LABEL_248;
  }
  if ( *(_DWORD *)(a2 + 44) == 2 && *(_QWORD *)(a2 + 304) )
  {
    *a3 = 1048769;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 67;
    goto LABEL_248;
  }
  if ( !*(_QWORD *)(a2 + 328) )
  {
    if ( !*(_DWORD *)(a2 + 320) )
      goto LABEL_174;
LABEL_206:
    *a3 = 1048800;
    v7 = 87;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v26 = 68;
    goto LABEL_248;
  }
  if ( !*(_DWORD *)(a2 + 320) )
    goto LABEL_206;
LABEL_174:
  v56 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v56 = WPP_GLOBAL_Control;
  }
  for ( j = 0; (unsigned int)j < *(_DWORD *)(a2 + 320); j = (unsigned int)(j + 1) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(a2 + 328) + 4 * j) & 0xF8u) >= 0x10 )
    {
      *a3 = 1048802;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
        v25 = WPP_GLOBAL_Control;
      }
      v7 = 87;
      if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
      {
        v26 = 69;
        goto LABEL_248;
      }
      return v7;
    }
  }
  v58 = *(const wchar_t **)(a2 + 416);
  if ( !v58 )
    goto LABEL_185;
  v59 = -1;
  do
    ++v59;
  while ( v58[v59] );
  if ( v59 >= 0x104 )
  {
    if ( v56 == (_BYTE *)&WPP_GLOBAL_Control || (v56[28] & 1) == 0 )
      goto LABEL_561;
    v98 = *((_QWORD *)v56 + 2);
    v99 = 229;
LABEL_560:
    WPP_SF_d(v98, v99, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_561;
  }
  if ( !v59 )
  {
    if ( v56 == (_BYTE *)&WPP_GLOBAL_Control || (v56[28] & 1) == 0 )
      goto LABEL_561;
    v98 = *((_QWORD *)v56 + 2);
    v99 = 230;
    goto LABEL_560;
  }
  if ( wcschr(v58, 0x7Cu) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v98 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v99 = 231;
      goto LABEL_560;
    }
LABEL_561:
    *(_DWORD *)(a2 + 336) = 524311;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 297, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
      v25 = WPP_GLOBAL_Control;
    }
    v7 = 87;
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
    {
      v26 = 70;
      goto LABEL_248;
    }
    return v7;
  }
LABEL_185:
  if ( (*(_BYTE *)(a2 + 424) & 3) != 3 )
  {
    for ( k = 0; ; k = (unsigned int)(k + 1) )
    {
      v61 = *(_DWORD *)(a2 + 432);
      if ( (unsigned int)k >= v61 )
        break;
      v62 = *(const wchar_t **)(*(_QWORD *)(a2 + 440) + 8 * k);
      if ( !v62 )
      {
        v100 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v101 = 228;
LABEL_582:
          WPP_SF_d(v100[2], v101, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
        }
LABEL_583:
        *(_DWORD *)(a2 + 336) = 524310;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
          v25 = WPP_GLOBAL_Control;
        }
        v7 = 87;
        if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
        {
          v26 = 72;
          goto LABEL_248;
        }
        return v7;
      }
      v63 = -1;
      do
        ++v63;
      while ( v62[v63] );
      if ( v63 >= 0x104 )
      {
        v100 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v101 = 229;
          goto LABEL_582;
        }
        goto LABEL_583;
      }
      if ( !v63 )
      {
        v100 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v101 = 230;
          goto LABEL_582;
        }
        goto LABEL_583;
      }
      if ( wcschr(v62, 0x7Cu) )
      {
        v100 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v101 = 231;
          goto LABEL_582;
        }
        goto LABEL_583;
      }
    }
    v64 = *(_WORD *)(a2 + 424);
    if ( (v64 & 0x10) != 0 && v61 || (v64 & 0x20) != 0 && !v61 && (v64 & 0x10) == 0 )
    {
      *a3 = 1048777;
      v7 = 87;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v26 = 73;
        goto LABEL_248;
      }
      return v7;
    }
    v65 = *(const wchar_t **)(a2 + 448);
    if ( !v65 )
      return v7;
    do
      ++v9;
    while ( v65[v9] );
    if ( v9 >= 0x104 )
    {
      v102 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_599;
      v103 = 229;
    }
    else
    {
      if ( v9 )
      {
        if ( !wcschr(v65, 0x7Cu) )
          return v7;
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v103 = 231;
          goto LABEL_598;
        }
LABEL_599:
        *a3 = 524312;
        v7 = 87;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v26 = 74;
          goto LABEL_248;
        }
        return v7;
      }
      v102 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_599;
      v103 = 230;
    }
LABEL_598:
    WPP_SF_d(v102[2], v103, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    goto LABEL_599;
  }
  *a3 = 1048775;
  v7 = 87;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v26 = 71;
    goto LABEL_248;
  }
  return v7;
}

```

## disassembly

```asm
0x18000d490  push    rbx
0x18000d492  push    rbp
0x18000d493  push    r12
0x18000d495  push    r13
0x18000d497  push    r15
0x18000d499  sub     rsp, 30h
0x18000d49d  mov     r15, r8
0x18000d4a0  mov     rbx, rdx
0x18000d4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4aa  lea     rbp, WPP_GLOBAL_Control
0x18000d4b1  cmp     rcx, rbp
0x18000d4b4  jnz     loc_18000DE87
0x18000d4ba  mov     dword ptr [r15], 10000h
0x18000d4c1  mov     r13d, 100h
0x18000d4c7  movzx   eax, word ptr [rbx+8]
0x18000d4cb  mov     [rsp+58h+arg_8], rdi
0x18000d4d0  cmp     ax, r13w
0x18000d4d4  jb      loc_18000E442
0x18000d4da  mov     [rsp+58h+arg_0], rsi
0x18000d4df  mov     esi, 200h
0x18000d4e4  cmp     ax, si
0x18000d4e7  jb      loc_18000E3EE
0x18000d4ed  mov     ecx, 300h
0x18000d4f2  cmp     ax, cx
0x18000d4f5  jnb     loc_18000E220
0x18000d4fb  movzx   r8d, word ptr [rbx+8]
0x18000d500  mov     rdx, r15
0x18000d503  mov     rcx, rbx
0x18000d506  call    Int_FwValidateComplianceAndReduceFirewallRuleToVersion
0x18000d50b  mov     r12d, eax
0x18000d50e  test    eax, eax
0x18000d510  jnz     loc_18000E57D
0x18000d516  mov     rcx, [rbx+10h]; Str
0x18000d51a  mov     [rsp+58h+arg_10], r14
0x18000d51f  test    rcx, rcx
0x18000d522  jz      loc_18000E858
0x18000d528  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000d52f  mov     rax, r14
0x18000d532  inc     rax
0x18000d535  cmp     word ptr [rcx+rax*2], 0
0x18000d53a  jnz     short loc_18000D532
0x18000d53c  cmp     rax, rsi
0x18000d53f  jnb     loc_18000E879
0x18000d545  cmp     rax, 1
0x18000d549  jb      loc_18000E89A
0x18000d54f  mov     edx, 7Ch ; '|'; Ch
0x18000d554  call    cs:__imp_wcschr
0x18000d55a  test    rax, rax
0x18000d55d  jnz     loc_18000E8BB
0x18000d563  mov     rcx, [rbx+18h]; Str
0x18000d567  test    rcx, rcx
0x18000d56a  jz      loc_18000E8F5
0x18000d570  mov     rax, r14
0x18000d573  inc     rax
0x18000d576  cmp     word ptr [rcx+rax*2], 0
0x18000d57b  jnz     short loc_18000D573
0x18000d57d  cmp     rax, 2710h
0x18000d583  jnb     loc_18000E916
0x18000d589  cmp     rax, 1
0x18000d58d  jb      loc_18000E937
0x18000d593  mov     edx, 7Ch ; '|'; Ch
0x18000d598  call    cs:__imp_wcschr
0x18000d59e  test    rax, rax
0x18000d5a1  jnz     loc_18000E958
0x18000d5a7  mov     r8, [rbx+18h]; lpString1
0x18000d5ab  test    r8, r8
0x18000d5ae  jz      short loc_18000D5DD
0x18000d5b0  lea     rax, String2; "ALL"
0x18000d5b7  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x18000d5bc  mov     r9d, r14d; cchCount1
0x18000d5bf  mov     [rsp+58h+lpString2], rax; lpString2
0x18000d5c4  mov     edx, 1; dwCmpFlags
0x18000d5c9  mov     ecx, 7Fh; Locale
0x18000d5ce  call    cs:__imp_CompareStringW
0x18000d5d4  cmp     eax, 2
0x18000d5d7  jz      loc_18000E5A4
0x18000d5dd  mov     rcx, [rbx+20h]; Str
0x18000d5e1  test    rcx, rcx
0x18000d5e4  jz      short loc_18000D61A
0x18000d5e6  mov     rax, r14
0x18000d5e9  nop     dword ptr [rax+00000000h]
0x18000d5f0  inc     rax
0x18000d5f3  cmp     word ptr [rcx+rax*2], 0
0x18000d5f8  jnz     short loc_18000D5F0
0x18000d5fa  cmp     rax, 2710h
0x18000d600  jnb     loc_18000E992
0x18000d606  mov     edx, 7Ch ; '|'; Ch
0x18000d60b  call    cs:__imp_wcschr
0x18000d611  test    rax, rax
0x18000d614  jnz     loc_18000E9B3
0x18000d61a  mov     rcx, [rbx+110h]; Str
0x18000d621  test    rcx, rcx
0x18000d624  jz      short loc_18000D664
0x18000d626  mov     rax, r14
0x18000d629  nop     dword ptr [rax+00000000h]
0x18000d630  inc     rax
0x18000d633  cmp     word ptr [rcx+rax*2], 0
0x18000d638  jnz     short loc_18000D630
0x18000d63a  cmp     rax, 104h
0x18000d640  jnb     loc_18000E9ED
0x18000d646  cmp     rax, 1
0x18000d64a  jb      loc_18000EA0E
0x18000d650  mov     edx, 7Ch ; '|'; Ch
0x18000d655  call    cs:__imp_wcschr
0x18000d65b  test    rax, rax
0x18000d65e  jnz     loc_18000EA2F
0x18000d664  mov     rcx, [rbx+110h]; String
0x18000d66b  test    rcx, rcx
0x18000d66e  jnz     loc_18000DFE4
0x18000d674  mov     rcx, [rbx+118h]; Str
0x18000d67b  test    rcx, rcx
0x18000d67e  jz      short loc_18000D6B7
0x18000d680  mov     rax, r14
0x18000d683  inc     rax
0x18000d686  cmp     word ptr [rcx+rax*2], 0
0x18000d68b  jnz     short loc_18000D683
0x18000d68d  cmp     rax, 104h
0x18000d693  jnb     loc_18000EA69
0x18000d699  cmp     rax, 1
0x18000d69d  jb      loc_18000EA8A
0x18000d6a3  mov     edx, 7Ch ; '|'; Ch
0x18000d6a8  call    cs:__imp_wcschr
0x18000d6ae  test    rax, rax
0x18000d6b1  jnz     loc_18000EAAB
0x18000d6b7  mov     rcx, [rbx+118h]; String
0x18000d6be  test    rcx, rcx
0x18000d6c1  jnz     loc_18000E15C
0x18000d6c7  mov     rcx, [rbx+138h]; Str
0x18000d6ce  test    rcx, rcx
0x18000d6d1  jz      short loc_18000D700
0x18000d6d3  mov     rax, r14
0x18000d6d6  inc     rax
0x18000d6d9  cmp     word ptr [rcx+rax*2], 0
0x18000d6de  jnz     short loc_18000D6D6
0x18000d6e0  cmp     rax, 2710h
0x18000d6e6  jnb     loc_18000EAE5
0x18000d6ec  mov     edx, 7Ch ; '|'; Ch
0x18000d6f1  call    cs:__imp_wcschr
0x18000d6f7  test    rax, rax
0x18000d6fa  jnz     loc_18000EB06
0x18000d700  mov     eax, [rbx+2Ch]
0x18000d703  dec     eax
0x18000d705  cmp     eax, 1
0x18000d708  ja      loc_18000E0DA
0x18000d70e  mov     ecx, [rbx+28h]
0x18000d711  call    Int_FwValidateProfiles
0x18000d716  test    eax, eax
0x18000d718  jnz     loc_18000E5D5
0x18000d71e  movzx   eax, word ptr [rbx+30h]
0x18000d722  cmp     ax, r13w
0x18000d726  ja      loc_18000E606
0x18000d72c  cmp     ax, 6
0x18000d730  jz      short loc_18000D79E
0x18000d732  cmp     ax, 11h
0x18000d736  jz      loc_18000E02B
0x18000d73c  cmp     ax, 1
0x18000d740  jz      loc_18000E1A3
0x18000d746  cmp     ax, 3Ah ; ':'
0x18000d74a  jz      loc_18000E22C
0x18000d750  cmp     dword ptr [rbx+40h], 0
0x18000d754  jnz     short loc_18000D76D
0x18000d756  cmp     dword ptr [rbx+58h], 0
0x18000d75a  jnz     short loc_18000D76D
0x18000d75c  cmp     dword ptr [rbx+38h], 0
0x18000d760  jnz     short loc_18000D76D
0x18000d762  cmp     word ptr [rbx+50h], 0
0x18000d767  jz      loc_18000D7F3
0x18000d76d  mov     dword ptr [r15], 1000A1h
0x18000d774  mov     r12d, 57h ; 'W'
0x18000d77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d781  cmp     rcx, rbp
0x18000d784  jz      loc_18000DE68
0x18000d78a  test    byte ptr [rcx+1Ch], 1
0x18000d78e  jz      loc_18000DE68
0x18000d794  mov     edx, 21h ; '!'
0x18000d799  jmp     loc_18000E106
0x18000d79e  xor     eax, eax
0x18000d7a0  lea     rcx, [rbx+38h]
0x18000d7a4  cmp     dword ptr [rbx+2Ch], 2
0x18000d7a8  mov     edi, 110h
0x18000d7ad  mov     r9, r15
0x18000d7b0  mov     r8d, 1
0x18000d7b6  cmovnz  di, ax
0x18000d7ba  xor     edx, edx
0x18000d7bc  cmp     dword ptr [rbx+2Ch], 2
0x18000d7c0  mov     eax, 20Bh
0x18000d7c5  cmovnz  dx, ax
0x18000d7c9  call    Int_FwValidatePorts
0x18000d7ce  test    eax, eax
0x18000d7d0  jnz     loc_18000E637
0x18000d7d6  lea     rcx, [rbx+50h]
0x18000d7da  mov     r9, r15
0x18000d7dd  mov     r8d, 1
0x18000d7e3  movzx   edx, di
0x18000d7e6  call    Int_FwValidatePorts
0x18000d7eb  test    eax, eax
0x18000d7ed  jnz     loc_18000E486
0x18000d7f3  lea     rcx, [rbx+68h]
0x18000d7f7  mov     r9, r15
0x18000d7fa  xor     edx, edx
0x18000d7fc  mov     r8d, 1
0x18000d802  call    Int_FwValidateAddresses
0x18000d807  test    eax, eax
0x18000d809  jnz     loc_18000E3C4
0x18000d80f  lea     rcx, [rbx+0B0h]
0x18000d816  mov     r9, r15
0x18000d819  xor     r8d, r8d
0x18000d81c  xor     edx, edx
0x18000d81e  call    Int_FwValidateAddresses
0x18000d823  test    eax, eax
0x18000d825  jnz     loc_18000E35F
0x18000d82b  mov     edx, [rbx+0F8h]
0x18000d831  test    edx, edx
0x18000d833  jnz     short loc_18000D870
0x18000d835  cmp     qword ptr [rbx+100h], 0
0x18000d83d  jz      short loc_18000D87A
0x18000d83f  mov     dword ptr [r15], 100070h
0x18000d846  mov     r12d, 57h ; 'W'
0x18000d84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d853  cmp     rcx, rbp
0x18000d856  jz      loc_18000DE68
0x18000d85c  test    byte ptr [rcx+1Ch], 1
0x18000d860  jz      loc_18000DE68
0x18000d866  mov     edx, 24h ; '$'
0x18000d86b  jmp     loc_18000E106
0x18000d870  cmp     qword ptr [rbx+100h], 0
0x18000d878  jz      short loc_18000D83F
0x18000d87a  mov     eax, [rbx+108h]
0x18000d880  cmp     eax, 10h
0x18000d883  jnb     loc_18000E661
0x18000d889  movzx   ecx, word ptr [rbx+124h]
0x18000d890  bt      cx, 0Dh
0x18000d895  jb      loc_18000E692
0x18000d89b  mov     eax, [rbx+120h]
0x18000d8a1  dec     eax
0x18000d8a3  cmp     eax, 2
0x18000d8a6  ja      loc_18000F4DB
0x18000d8ac  mov     eax, 4000h
0x18000d8b1  cmp     cx, ax
0x18000d8b4  jnb     loc_18000E6D0
0x18000d8ba  test    cl, 8
0x18000d8bd  jnz     loc_18000E2E3
0x18000d8c3  test    cl, cl
0x18000d8c5  js      loc_18000E389
0x18000d8cb  movzx   edx, cx
0x18000d8ce  and     dx, r13w
0x18000d8d2  jnz     loc_18000E26A
0x18000d8d8  movzx   eax, cl
0x18000d8db  and     al, 88h
0x18000d8dd  cmp     al, 80h
0x18000d8df  jnz     short loc_18000D912
0x18000d8e1  mov     dword ptr [r15], 1000A2h
0x18000d8e8  mov     r12d, 57h ; 'W'
0x18000d8ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8f5  cmp     rcx, rbp
0x18000d8f8  jz      loc_18000DE68
0x18000d8fe  test    byte ptr [rcx+1Ch], 1
0x18000d902  jz      loc_18000DE68
0x18000d908  mov     edx, 2Ch ; ','
0x18000d90d  jmp     loc_18000E106
0x18000d912  mov     eax, 108h
0x18000d917  and     cx, ax
0x18000d91a  cmp     cx, ax
0x18000d91d  jnz     short loc_18000D950
0x18000d91f  mov     dword ptr [r15], 1000A2h
0x18000d926  mov     r12d, 57h ; 'W'
0x18000d92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d933  cmp     rcx, rbp
0x18000d936  jz      loc_18000DE68
0x18000d93c  test    byte ptr [rcx+1Ch], 1
0x18000d940  jz      loc_18000DE68
0x18000d946  mov     edx, 2Dh ; '-'
0x18000d94b  jmp     loc_18000E106
0x18000d950  test    dx, dx
0x18000d953  jnz     loc_18000E31E
0x18000d959  movzx   eax, word ptr [rbx+124h]
0x18000d960  test    al, 10h
0x18000d962  jnz     loc_18000EB40
0x18000d968  movzx   ecx, ax
0x18000d96b  and     cx, 6
0x18000d96f  bt      ax, 0Bh
0x18000d974  jb      short loc_18000D9AD
0x18000d976  cmp     cx, 6
0x18000d97a  jnz     short loc_18000D9C1
0x18000d97c  mov     dword ptr [r15], 1000B4h
0x18000d983  mov     r12d, 57h ; 'W'
0x18000d989  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d990  cmp     rcx, rbp
0x18000d993  jz      loc_18000DE68
0x18000d999  test    byte ptr [rcx+1Ch], 1
0x18000d99d  jz      loc_18000DE68
0x18000d9a3  mov     edx, 31h ; '1'
0x18000d9a8  jmp     loc_18000E106
0x18000d9ad  cmp     word ptr [rbx+30h], 6
0x18000d9b2  jz      loc_18000EB8B
0x18000d9b8  test    cx, cx
0x18000d9bb  jnz     loc_18000EB8B
0x18000d9c1  and     al, 22h
0x18000d9c3  cmp     al, 20h ; ' '
0x18000d9c5  jz      loc_18000EBBC
  ... truncated ...
```
