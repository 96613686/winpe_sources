# DhcpRegFillParams

- ea: `0x1800026fc`
- end: `0x1800032af`
- name: `DhcpRegFillParams`
- size: `2995`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003910`
- `0x1800227ac`
- `0x1800407c0`

## callees

- `0x1800026fc`
- `0x1800057f0`
- `0x180005da4`
- `0x180006440`
- `0x180007248`
- `0x180007294`
- `0x180009038`
- `0x18000a100`
- `0x180012b90`
- `0x18001a5d0`
- `0x18001cef0`
- `0x180036008`
- `0x1800366fc`
- `0x180047e24`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d310`
- `0x18004db48`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180003069`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800030be`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180003109`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000314f`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180003069`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800030be`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180003109`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000314f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d21`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d34`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d47`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d5a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d21`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d34`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d47`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002d5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002fc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002fc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002f21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003072`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800030c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003112`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003158`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002f21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003072`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800030c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003112`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003158`
- `WS2_32!__imp_htonl` at `0x180002f59`
- `WS2_32!__imp_htonl` at `0x180002f59`
- `WS2_32!__imp_inet_addr` at `0x180002a3c`
- `WS2_32!__imp_inet_addr` at `0x180002a4f`
- `WS2_32!__imp_inet_addr` at `0x180002db7`
- `WS2_32!__imp_inet_addr` at `0x180002e1f`
- `WS2_32!__imp_inet_addr` at `0x180002e32`
- `WS2_32!__imp_inet_addr` at `0x180002e7c`
- `WS2_32!__imp_inet_addr` at `0x180002e8f`
- `WS2_32!__imp_inet_addr` at `0x180002a3c`
- `WS2_32!__imp_inet_addr` at `0x180002a4f`
- `WS2_32!__imp_inet_addr` at `0x180002db7`
- `WS2_32!__imp_inet_addr` at `0x180002e1f`
- `WS2_32!__imp_inet_addr` at `0x180002e32`
- `WS2_32!__imp_inet_addr` at `0x180002e7c`
- `WS2_32!__imp_inet_addr` at `0x180002e8f`

## string_xrefs

- `0x180002818`: `IPAutoconfigurationEnabled`
- `0x180002834`: `IPAutoconfigurationSeed`
- `0x1800029b2`: `IPAutoconfigurationAddress`
- `0x1800029c8`: `IPAutoconfigurationSubnet`
- `0x1800029de`: `IPAutoconfigurationMask`

## pseudocode

```c
__int64 __fastcall DhcpRegFillParams(__int64 a1, int a2, _DWORD *a3)
{
  LSTATUS IsEnabledDHCPRegistryValue; // r15d
  HKEY v5; // r13
  unsigned int v6; // eax
  const WCHAR *v7; // r12
  __int64 v8; // r14
  const WCHAR *v9; // rbx
  DWORD v10; // ecx
  LSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  wchar_t *v14; // rcx
  DWORD v15; // r15d
  LPVOID v16; // rax
  __int64 i; // rsi
  const WCHAR *v19; // r12
  int RegistryString; // eax
  wchar_t *v21; // rbx
  unsigned __int64 v22; // rax
  const char *v23; // rax
  unsigned int v24; // eax
  char v25; // bl
  int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // edx
  unsigned int v29; // eax
  int v30; // r14d
  u_long v31; // eax
  wchar_t **v32; // rbx
  SIZE_T v33; // rcx
  wchar_t *v34; // rsi
  __int64 v35; // rcx
  int v36; // r12d
  LPVOID v37; // rax
  __int64 v38; // r14
  __int64 v39; // rsi
  __int64 v40; // rcx
  __time64_t v41; // rbx
  ULONGLONG TickCount64; // rax
  __int64 v43; // rax
  __int64 v44; // r14
  __int64 v45; // rcx
  __time64_t v46; // rbx
  ULONGLONG v47; // rax
  __int64 v48; // rax
  __int64 v49; // r14
  __time64_t v50; // rbx
  ULONGLONG v51; // rax
  __int64 v52; // rax
  __int64 v53; // r14
  __time64_t v54; // rbx
  __int64 v55; // rax
  bool v56; // zf
  int v57; // [rsp+30h] [rbp-D0h] BYREF
  int v58; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v60; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD v61; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v62; // [rsp+44h] [rbp-BCh] BYREF
  int v63; // [rsp+48h] [rbp-B8h] BYREF
  u_long v64; // [rsp+4Ch] [rbp-B4h] BYREF
  int v65; // [rsp+50h] [rbp-B0h] BYREF
  int v66; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v67; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v68; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v69; // [rsp+60h] [rbp-A0h] BYREF
  int v70; // [rsp+64h] [rbp-9Ch] BYREF
  int v71; // [rsp+68h] [rbp-98h] BYREF
  int v72; // [rsp+6Ch] [rbp-94h] BYREF
  int v73; // [rsp+70h] [rbp-90h] BYREF
  int v74; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD Type; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h] BYREF
  int v77; // [rsp+88h] [rbp-78h] BYREF
  int v78; // [rsp+8Ch] [rbp-74h] BYREF
  BOOL v79; // [rsp+90h] [rbp-70h] BYREF
  DWORD cbData; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD lpcbData; // [rsp+98h] [rbp-68h] BYREF
  int v82; // [rsp+9Ch] [rbp-64h] BYREF
  int v83; // [rsp+A0h] [rbp-60h] BYREF
  int v84; // [rsp+A4h] [rbp-5Ch] BYREF
  int v85; // [rsp+A8h] [rbp-58h]
  LPVOID v86; // [rsp+B0h] [rbp-50h]
  _DWORD *v87; // [rsp+B8h] [rbp-48h]
  int *v88; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpValueName[11]; // [rsp+C8h] [rbp-38h]
  int *v90; // [rsp+120h] [rbp+20h]
  wchar_t *String1[39]; // [rsp+128h] [rbp+28h]
  __int128 v92; // [rsp+260h] [rbp+160h] BYREF

  v87 = a3;
  v85 = a2;
  v90 = &v58;
  *(_DWORD *)Data = 0;
  String1[0] = (wchar_t *)L"EnableDhcp";
  Type = 0;
  String1[1] = (wchar_t *)&v74;
  IsEnabledDHCPRegistryValue = 0;
  cbData = 0;
  String1[2] = (wchar_t *)L"DisableDhcpOnConnect";
  String1[3] = (wchar_t *)&v77;
  String1[4] = L"DhcpUseUTF8";
  String1[5] = (wchar_t *)&v78;
  String1[6] = L"DhcpUseE1";
  String1[7] = (wchar_t *)&v66;
  String1[8] = L"Lease";
  String1[9] = (wchar_t *)&v67;
  String1[10] = (wchar_t *)L"LeaseObtainedTime";
  String1[11] = (wchar_t *)&v68;
  String1[12] = L"T1";
  String1[13] = (wchar_t *)&v69;
  String1[14] = L"T2";
  String1[15] = (wchar_t *)&v62;
  String1[16] = (wchar_t *)L"LeaseTerminatesTime";
  String1[17] = (wchar_t *)&v79;
  String1[18] = L"IPAutoconfigurationEnabled";
  String1[19] = (wchar_t *)&v92 + 6;
  String1[20] = L"IPAutoconfigurationSeed";
  String1[21] = (wchar_t *)&v84;
  String1[22] = L"AddressType";
  String1[23] = (wchar_t *)&v82;
  String1[24] = L"DontPingGateway";
  String1[25] = (wchar_t *)&v83;
  String1[26] = L"UseInform";
  String1[27] = (wchar_t *)&v70;
  String1[28] = (wchar_t *)L"DhcpInformInterval";
  String1[29] = (wchar_t *)&v71;
  v70 = 0;
  v71 = 0;
  v63 = 0;
  v60 = 0;
  v61 = 0;
  v86 = 0;
  lpcbData = 257;
  v72 = 0;
  v73 = 0;
  v92 = 0;
  v5 = *(HKEY *)(a1 + 728);
  String1[30] = L"ReleaseOnShutdown";
  String1[31] = (wchar_t *)&v60;
  String1[32] = L"DhcpDADTimeout";
  String1[33] = (wchar_t *)&v63;
  String1[34] = L"IsServerNapAware";
  String1[35] = (wchar_t *)&v72;
  String1[36] = L"SkipClientID";
  String1[37] = (wchar_t *)&v73;
  String1[38] = (wchar_t *)L"DhcpIsMeteredDetected";
  v88 = &v57;
  lpValueName[0] = L"DhcpIPAddress";
  lpValueName[1] = (LPCWSTR)&v64;
  lpValueName[2] = L"DhcpSubnetMask";
  lpValueName[3] = (LPCWSTR)&v65;
  lpValueName[4] = L"DhcpServer";
  lpValueName[5] = (LPCWSTR)&v92;
  lpValueName[6] = L"IPAutoconfigurationAddress";
  lpValueName[7] = (LPCWSTR)&v92 + 2;
  lpValueName[8] = L"IPAutoconfigurationSubnet";
  lpValueName[9] = (LPCWSTR)&v92 + 4;
  lpValueName[10] = L"IPAutoconfigurationMask";
  v58 = 1;
  v79 = DhcpGlobalAutonetEnabled != 0;
  v82 = DhcpGlobalDontPingGatewayFlag;
  v83 = DhcpGlobalUseInformFlag;
  v74 = 0;
  v77 = 0;
  v78 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v62 = 0;
  v84 = 1;
  v57 = 0;
  v64 = 0;
  v65 = 0;
  DWORD1(v92) = inet_addr("169.254.0.0");
  v6 = inet_addr("255.255.0.0");
  v7 = *(const WCHAR **)(a1 + 56);
  v8 = 0;
  *((_QWORD *)&v92 + 1) = v6;
  v72 = DhcpGlobalSkipClientID;
  v70 = 60;
  v71 = 2;
  v63 = 0;
  v60 = 4000;
  v73 = 0;
  do
  {
    cbData = 4;
    v9 = String1[2 * v8];
    if ( !wcscmp_0(v9, L"EnableDhcp") )
    {
      if ( (unsigned int)DhcpIsFSEGuestSystem() )
        *(_DWORD *)Data = 0;
      else
        IsEnabledDHCPRegistryValue = DhcpV4IsEnabledDHCPRegistryValue(v7);
      v10 = 4;
      Type = 4;
    }
    else
    {
      v11 = RegQueryValueExW(v5, v9, 0, &Type, Data, &cbData);
      v10 = Type;
      IsEnabledDHCPRegistryValue = v11;
    }
    if ( IsEnabledDHCPRegistryValue )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_SD(
          1025,
          38,
          (unsigned int)WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids,
          (_DWORD)v9,
          IsEnabledDHCPRegistryValue);
    }
    else if ( v10 == 4 )
    {
      if ( !wcscmp_0(v9, L"DhcpInformInterval") )
        *(_DWORD *)(a1 + 1976) = 1;
      v14 = String1[2 * v8 - 1];
      *(_DWORD *)v14 = *(_DWORD *)Data;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_Sl((_DWORD)v14, v12, v13, (_DWORD)v9, Data[0]);
    }
    else if ( (xmmword_1800616A0 & 2) != 0 )
    {
      WPP_SF_S(1025, 39, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v9);
    }
    ++v8;
  }
  while ( v8 != 20 );
  *(_DWORD *)(a1 + 148) = v77;
  *(_DWORD *)(a1 + 152) = v78;
  *(_DWORD *)(a1 + 840) = v63;
  if ( v74 )
    v58 = 1;
  if ( *(_DWORD *)(a1 + 820) )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_S(1028, 41, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v7);
    v58 = 0;
    v79 = 0;
  }
  if ( *(_BYTE *)(a1 + 84) == 8 )
    v58 = 0;
  DhcpGetGatewayCount(v5, &v61);
  v15 = v61;
  if ( v61 )
  {
    v16 = DhcpAlloc(4LL * v61);
    v86 = v16;
    if ( !v16 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_(1025, 42, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
      return 8;
    }
    DhcpGetGatewayInfo(v5, v16, v15);
  }
  for ( i = 0; i != 6; ++i )
  {
    v61 = 0;
    Str = 0;
    v19 = lpValueName[2 * i];
    RegistryString = GetRegistryString(v5, v19, &Str, &v61);
    if ( RegistryString )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_SD(1025, 43, (unsigned int)WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, (_DWORD)v19, RegistryString);
    }
    else
    {
      v21 = Str;
      if ( (v61 & 0xFFFFFFFE) < 0x20 )
        goto LABEL_50;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_S(1028, 44, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, Str);
      if ( wcschr(v21, 0x20u) )
        *wcschr(v21, 0x20u) = 0;
      if ( wcschr(v21, 0x2Cu) )
        *wcschr(v21, 0x2Cu) = 0;
      v22 = -1;
      do
        ++v22;
      while ( v21[v22] );
      if ( v22 < 0x10 )
      {
LABEL_50:
        v23 = (const char *)DhcpUnicodeToOem(v21);
        v24 = inet_addr(v23);
        v25 = v24;
        *(_DWORD *)lpValueName[2 * i - 1] = v24;
        DhcpPunycodeFree((LPVOID *)&Str);
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_SD(1028, 46, (unsigned int)WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, (_DWORD)v19, v25);
      }
      else
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_S(1025, 45, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v21);
        DhcpPunycodeFree((LPVOID *)&Str);
      }
    }
  }
  if ( !v57 )
    v65 = 0;
  v26 = DWORD2(v92);
  if ( DWORD2(v92) )
  {
    v28 = DWORD1(v92);
  }
  else
  {
    DWORD2(v92) = inet_addr("255.255.0.0");
    v27 = inet_addr("169.254.0.0");
    v26 = DWORD2(v92);
    v28 = v27;
    DWORD1(v92) = v27;
  }
  if ( (v28 & v26) != v28 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 47, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
    DWORD2(v92) = inet_addr("255.255.0.0");
    v29 = inet_addr("169.254.0.0");
    v26 = DWORD2(v92);
    v28 = v29;
    DWORD1(v92) = v29;
  }
  if ( (_DWORD)v92 && ((unsigned int)v92 & v26) != v28 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 48, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, (unsigned int)v92);
    LODWORD(v92) = 0;
  }
  if ( v60 < 0xFA0 )
  {
    v60 = 4000;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 49, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, 4000);
  }
  v30 = v57;
  if ( v58 && GetTickCount64() / 0x3E8 >= v62 || !v57 )
  {
    v57 = 0;
    v31 = DhcpDefaultSubnetMask(0);
    v64 = htonl(v31);
    v66 = 0;
    v62 = 0;
    v69 = 0;
    v68 = 0;
    v67 = 0;
  }
  v32 = (wchar_t **)(a1 + 1888);
  if ( *(_QWORD *)(a1 + 1888) )
    DhcpPunycodeFree((LPVOID *)(a1 + 1888));
  v33 = lpcbData;
  *v32 = 0;
  Str = (wchar_t *)DhcpAlloc(v33);
  v34 = Str;
  if ( Str )
  {
    if ( RegQueryValueExW(v5, L"DhcpNetworkHint", 0, 0, (LPBYTE)Str, &lpcbData) )
    {
      DhcpPunycodeFree((LPVOID *)&Str);
      *v32 = 0;
    }
    else
    {
      *v32 = v34;
    }
  }
  DhcpRegReadReachableGateway(a1);
  v36 = v85;
  *(_DWORD *)(a1 + 120) = v57;
  *(_DWORD *)(a1 + 124) = v64;
  *(_DWORD *)(a1 + 128) = v65;
  if ( v36 )
    *(_DWORD *)(a1 + 132) = v30;
  v37 = v86;
  *(_DWORD *)(a1 + 492) = v15;
  *(_QWORD *)(a1 + 496) = v37;
  *(_OWORD *)(a1 + 416) = v92;
  if ( v36 )
  {
    v38 = v67;
    v39 = 0xFFFFFFFFLL;
    *(_DWORD *)(a1 + 440) = v66;
    if ( (_DWORD)v38 == -1 )
    {
      v40 = 0xFFFFFFFFLL;
    }
    else
    {
      v41 = _time64(0);
      TickCount64 = GetTickCount64();
      v40 = 0;
      v43 = v38 + TickCount64 / 0x3E8 - v41;
      if ( v43 >= 0 )
        v40 = v43;
    }
    v44 = v68;
    *(_QWORD *)(a1 + 448) = v40;
    if ( (_DWORD)v44 == -1 )
    {
      v45 = 0xFFFFFFFFLL;
    }
    else
    {
      v46 = _time64(0);
      v47 = GetTickCount64();
      v45 = 0;
      v48 = v44 + v47 / 0x3E8 - v46;
      if ( v48 >= 0 )
        v45 = v48;
    }
    v49 = v69;
    *(_QWORD *)(a1 + 456) = v45;
    if ( (_DWORD)v49 == -1 )
    {
      v35 = 0xFFFFFFFFLL;
    }
    else
    {
      v50 = _time64(0);
      v51 = GetTickCount64();
      v35 = 0;
      v52 = v49 + v51 / 0x3E8 - v50;
      if ( v52 >= 0 )
        v35 = v52;
    }
    v53 = v62;
    *(_QWORD *)(a1 + 464) = v35;
    if ( (_DWORD)v53 != -1 )
    {
      v54 = _time64(0);
      v39 = 0;
      v55 = v53 + GetTickCount64() / 0x3E8 - v54;
      if ( v55 >= 0 )
        v39 = v55;
    }
    *(_QWORD *)(a1 + 472) = v39;
  }
  v56 = v83 == 0;
  *(_DWORD *)(a1 + 564) = v82 != 0;
  *(_DWORD *)(a1 + 568) = !v56;
  *(_DWORD *)(a1 + 488) = v70;
  *(_DWORD *)(a1 + 572) = v71;
  *(_DWORD *)(a1 + 1996) = v60;
  *(_DWORD *)(a1 + 2024) = v72;
  *(_DWORD *)(a1 + 580) = v73;
  if ( v36 )
  {
    *(_DWORD *)(a1 + 776) = 0;
    *(_DWORD *)(a1 + 780) = 0;
    *(_DWORD *)(a1 + 788) = 0;
    if ( v58 )
    {
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v35, DhcpEnabled, *(unsigned int *)(a1 + 48));
      *(_DWORD *)(a1 + 792) = 1;
    }
    else
    {
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v35, DhcpDisabled, *(unsigned int *)(a1 + 48));
      *(_DWORD *)(a1 + 792) = 0;
    }
    if ( v84 )
      *(_DWORD *)(a1 + 796) = (v84 == 2) + 1;
    else
      *(_DWORD *)(a1 + 796) = 0;
    *(_DWORD *)(a1 + 800) = 0;
  }
  if ( v87 )
    *v87 = v74 != 0;
  return 0;
}

```

## disassembly

```asm
0x1800026fc  mov     [rsp-8+arg_8], rbx
0x180002701  push    rbp
0x180002702  push    rsi
0x180002703  push    rdi
0x180002704  push    r12
0x180002706  push    r13
0x180002708  push    r14
0x18000270a  push    r15
0x18000270c  lea     rbp, [rsp-190h]
0x180002714  sub     rsp, 290h
0x18000271b  mov     rax, cs:__security_cookie
0x180002722  xor     rax, rsp
0x180002725  mov     [rbp+1C0h+var_40], rax
0x18000272c  xor     ebx, ebx
0x18000272e  mov     [rbp+1C0h+var_208], r8
0x180002732  lea     rax, [rsp+2C0h+var_28C]
0x180002737  mov     [rbp+1C0h+var_218], edx
0x18000273a  mov     [rbp+1C0h+var_1A0], rax
0x18000273e  xorps   xmm0, xmm0
0x180002741  lea     rax, aEnabledhcp; "EnableDhcp"
0x180002748  mov     dword ptr [rsp+2C0h+Data], ebx
0x18000274c  mov     [rbp+1C0h+String1], rax
0x180002750  mov     rdi, rcx
0x180002753  lea     rax, [rsp+2C0h+var_24C]
0x180002758  mov     [rsp+2C0h+Type], ebx
0x18000275c  mov     [rbp+1C0h+var_190], rax
0x180002760  mov     r15d, ebx
0x180002763  lea     rax, aDisabledhcponc; "DisableDhcpOnConnect"
0x18000276a  mov     [rbp+1C0h+cbData], ebx
0x18000276d  mov     [rbp+1C0h+var_188], rax
0x180002771  lea     rax, [rbp+1C0h+var_238]
0x180002775  mov     [rbp+1C0h+var_180], rax
0x180002779  lea     rax, aDhcpuseutf8; "DhcpUseUTF8"
0x180002780  mov     [rbp+1C0h+var_178], rax
0x180002784  lea     rax, [rbp+1C0h+var_234]
0x180002788  mov     [rbp+1C0h+var_170], rax
0x18000278c  lea     rax, aDhcpusee1; "DhcpUseE1"
0x180002793  mov     [rbp+1C0h+var_168], rax
0x180002797  lea     rax, [rsp+2C0h+var_26C]
0x18000279c  mov     [rbp+1C0h+var_160], rax
0x1800027a0  lea     rax, aLease; "Lease"
0x1800027a7  mov     [rbp+1C0h+var_158], rax
0x1800027ab  lea     rax, [rsp+2C0h+var_268]
0x1800027b0  mov     [rbp+1C0h+var_150], rax
0x1800027b4  lea     rax, aLeaseobtainedt; "LeaseObtainedTime"
0x1800027bb  mov     [rbp+1C0h+var_148], rax
0x1800027bf  lea     rax, [rsp+2C0h+var_264]
0x1800027c4  mov     [rbp+1C0h+var_140], rax
0x1800027cb  lea     rax, aT1; "T1"
0x1800027d2  mov     [rbp+1C0h+var_138], rax
0x1800027d9  lea     rax, [rsp+2C0h+var_260]
0x1800027de  mov     [rbp+1C0h+var_130], rax
0x1800027e5  lea     rax, aT2; "T2"
0x1800027ec  mov     [rbp+1C0h+var_128], rax
0x1800027f3  lea     rax, [rsp+2C0h+var_27C]
0x1800027f8  mov     [rbp+1C0h+var_120], rax
0x1800027ff  lea     rax, aLeaseterminate; "LeaseTerminatesTime"
0x180002806  mov     [rbp+1C0h+var_118], rax
0x18000280d  lea     rax, [rbp+1C0h+var_230]
0x180002811  mov     [rbp+1C0h+var_110], rax
0x180002818  lea     rax, aIpautoconfigur_1; "IPAutoconfigurationEnabled"
0x18000281f  mov     [rbp+1C0h+var_108], rax
0x180002826  lea     rax, [rbp+1C0h+var_60+0Ch]
0x18000282d  mov     [rbp+1C0h+var_100], rax
0x180002834  lea     rax, aIpautoconfigur_2; "IPAutoconfigurationSeed"
0x18000283b  mov     [rbp+1C0h+var_F8], rax
0x180002842  lea     rax, [rbp+1C0h+var_21C]
0x180002846  mov     [rbp+1C0h+var_F0], rax
0x18000284d  lea     rax, aAddresstype; "AddressType"
0x180002854  mov     [rbp+1C0h+var_E8], rax
0x18000285b  lea     rax, [rbp+1C0h+var_224]
0x18000285f  mov     [rbp+1C0h+var_E0], rax
0x180002866  lea     rax, aDontpinggatewa; "DontPingGateway"
0x18000286d  mov     [rbp+1C0h+var_D8], rax
0x180002874  lea     rax, [rbp+1C0h+var_220]
0x180002878  mov     [rbp+1C0h+var_D0], rax
0x18000287f  lea     rax, aUseinform; "UseInform"
0x180002886  mov     [rbp+1C0h+var_C8], rax
0x18000288d  lea     rax, [rsp+2C0h+var_25C]
0x180002892  mov     [rbp+1C0h+var_C0], rax
0x180002899  lea     rax, aDhcpinforminte; "DhcpInformInterval"
0x1800028a0  mov     [rbp+1C0h+var_B8], rax
0x1800028a7  lea     rax, [rsp+2C0h+var_258]
0x1800028ac  mov     [rbp+1C0h+var_B0], rax
0x1800028b3  mov     [rsp+2C0h+var_25C], ebx
0x1800028b7  mov     [rsp+2C0h+var_258], ebx
0x1800028bb  mov     [rsp+2C0h+var_278], ebx
0x1800028bf  mov     [rsp+2C0h+var_284], ebx
0x1800028c3  mov     [rsp+2C0h+var_280], ebx
0x1800028c7  mov     [rbp+1C0h+var_210], rbx
0x1800028cb  mov     [rbp+1C0h+var_228], 101h
0x1800028d2  mov     [rsp+2C0h+var_254], ebx
0x1800028d6  mov     [rsp+2C0h+var_250], ebx
0x1800028da  movups  xmmword ptr [rbp+160h], xmm0
0x1800028e1  cmp     cs:DhcpGlobalAutonetEnabled, ebx
0x1800028e7  lea     rax, aReleaseonshutd; "ReleaseOnShutdown"
0x1800028ee  mov     r13, [rcx+2D8h]
0x1800028f5  lea     rcx, cp; "169.254.0.0"
0x1800028fc  mov     [rbp+1C0h+var_A8], rax
0x180002903  lea     rax, [rsp+2C0h+var_284]
0x180002908  mov     [rbp+1C0h+var_A0], rax
0x18000290f  lea     rax, aDhcpdadtimeout; "DhcpDADTimeout"
0x180002916  mov     [rbp+1C0h+var_98], rax
0x18000291d  lea     rax, [rsp+2C0h+var_278]
0x180002922  mov     [rbp+1C0h+var_90], rax
0x180002929  lea     rax, aIsservernapawa; "IsServerNapAware"
0x180002930  mov     [rbp+1C0h+var_88], rax
0x180002937  lea     rax, [rsp+2C0h+var_254]
0x18000293c  mov     [rbp+1C0h+var_80], rax
0x180002943  lea     rax, aSkipclientid; "SkipClientID"
0x18000294a  mov     [rbp+1C0h+var_78], rax
0x180002951  lea     rax, [rsp+2C0h+var_250]
0x180002956  mov     [rbp+1C0h+var_70], rax
0x18000295d  lea     rax, aDhcpismeteredd; "DhcpIsMeteredDetected"
0x180002964  mov     [rbp+1C0h+var_68], rax
0x18000296b  lea     rax, [rsp+2C0h+var_290]
0x180002970  mov     [rbp+1C0h+var_200], rax
0x180002974  lea     rax, aDhcpipaddress; "DhcpIPAddress"
0x18000297b  mov     [rbp+1C0h+lpValueName], rax
0x18000297f  lea     rax, [rsp+2C0h+var_274]
0x180002984  mov     [rbp+1C0h+var_1F0], rax
0x180002988  lea     rax, aDhcpsubnetmask_0; "DhcpSubnetMask"
0x18000298f  mov     [rbp+1C0h+var_1E8], rax
0x180002993  lea     rax, [rsp+2C0h+var_270]
0x180002998  mov     [rbp+1C0h+var_1E0], rax
0x18000299c  lea     rax, aDhcpserver; "DhcpServer"
0x1800029a3  mov     [rbp+1C0h+var_1D8], rax
0x1800029a7  lea     rax, [rbp+1C0h+var_60]
0x1800029ae  mov     [rbp+1C0h+var_1D0], rax
0x1800029b2  lea     rax, aIpautoconfigur_3; "IPAutoconfigurationAddress"
0x1800029b9  mov     [rbp+1C0h+var_1C8], rax
0x1800029bd  lea     rax, [rbp+1C0h+var_60+4]
0x1800029c4  mov     [rbp+1C0h+var_1C0], rax
0x1800029c8  lea     rax, aIpautoconfigur_0; "IPAutoconfigurationSubnet"
0x1800029cf  mov     [rbp+1C0h+var_1B8], rax
0x1800029d3  lea     rax, [rbp+1C0h+var_60+8]
0x1800029da  mov     [rbp+1C0h+var_1B0], rax
0x1800029de  lea     rax, aIpautoconfigur; "IPAutoconfigurationMask"
0x1800029e5  mov     [rbp+1C0h+var_1A8], rax
0x1800029e9  mov     eax, ebx
0x1800029eb  setnz   al
0x1800029ee  mov     [rsp+2C0h+var_28C], 1
0x1800029f6  mov     [rbp+1C0h+var_230], eax
0x1800029f9  mov     eax, cs:DhcpGlobalDontPingGatewayFlag
0x1800029ff  mov     [rbp+1C0h+var_224], eax
0x180002a02  mov     eax, cs:DhcpGlobalUseInformFlag
0x180002a08  mov     [rbp+1C0h+var_220], eax
0x180002a0b  mov     [rsp+2C0h+var_24C], ebx
0x180002a0f  mov     [rbp+1C0h+var_238], ebx
0x180002a12  mov     [rbp+1C0h+var_234], ebx
0x180002a15  mov     [rsp+2C0h+var_26C], ebx
0x180002a19  mov     [rsp+2C0h+var_268], ebx
0x180002a1d  mov     [rsp+2C0h+var_264], ebx
0x180002a21  mov     [rsp+2C0h+var_260], ebx
0x180002a25  mov     [rsp+2C0h+var_27C], ebx
0x180002a29  mov     [rbp+1C0h+var_21C], 1
0x180002a30  mov     [rsp+2C0h+var_290], ebx
0x180002a34  mov     [rsp+2C0h+var_274], ebx
0x180002a38  mov     [rsp+2C0h+var_270], ebx
0x180002a3c  call    cs:__imp_inet_addr
0x180002a42  lea     rcx, a25525500; "255.255.0.0"
0x180002a49  mov     dword ptr [rbp+1C0h+var_60+4], eax
0x180002a4f  call    cs:__imp_inet_addr
0x180002a55  mov     r12, [rdi+38h]
0x180002a59  mov     r14d, ebx
0x180002a5c  mov     dword ptr [rbp+1C0h+var_60+8], eax
0x180002a62  mov     eax, cs:DhcpGlobalSkipClientID
0x180002a68  mov     [rsp+2C0h+var_254], eax
0x180002a6c  mov     dword ptr [rbp+1C0h+var_60+0Ch], ebx
0x180002a72  mov     [rsp+2C0h+var_25C], 3Ch ; '<'
0x180002a7a  mov     [rsp+2C0h+var_258], 2
0x180002a82  mov     [rsp+2C0h+var_278], ebx
0x180002a86  mov     [rsp+2C0h+var_284], 0FA0h
0x180002a8e  mov     [rsp+2C0h+var_250], ebx
0x180002a92  mov     rsi, r14
0x180002a95  mov     [rbp+1C0h+cbData], 4
0x180002a9c  add     rsi, rsi
0x180002a9f  lea     rdx, aEnabledhcp; "EnableDhcp"
0x180002aa6  mov     rbx, [rbp+rsi*8+1C0h+String1]
0x180002aab  mov     rcx, rbx; String1
0x180002aae  call    wcscmp_0
0x180002ab3  test    eax, eax
0x180002ab5  jnz     short loc_180002AE5
0x180002ab7  call    DhcpIsFSEGuestSystem
0x180002abc  test    eax, eax
0x180002abe  jz      short loc_180002ACA
0x180002ac0  mov     dword ptr [rsp+2C0h+Data], 0
0x180002ac8  jmp     short loc_180002ADA
0x180002aca  lea     rdx, [rsp+2C0h+Data]
0x180002acf  mov     rcx, r12; LPCWSTR
0x180002ad2  call    DhcpV4IsEnabledDHCPRegistryValue
0x180002ad7  mov     r15d, eax
0x180002ada  mov     ecx, 4
0x180002adf  mov     [rsp+2C0h+Type], ecx
0x180002ae3  jmp     short loc_180002B13
0x180002ae5  lea     rax, [rbp+1C0h+cbData]
0x180002ae9  xor     r8d, r8d; lpReserved
0x180002aec  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180002af1  lea     r9, [rsp+2C0h+Type]; lpType
0x180002af6  lea     rax, [rsp+2C0h+Data]
0x180002afb  mov     rdx, rbx; lpValueName
0x180002afe  mov     rcx, r13; hKey
0x180002b01  mov     [rsp+2C0h+lpData], rax; lpData
0x180002b06  call    cs:__imp_RegQueryValueExW
0x180002b0c  mov     ecx, [rsp+2C0h+Type]
0x180002b10  mov     r15d, eax
0x180002b13  test    r15d, r15d
0x180002b16  jz      short loc_180002B45
0x180002b18  test    byte ptr cs:xmmword_1800616A0, 2
0x180002b1f  jz      loc_180002BAF
0x180002b25  mov     edx, 26h ; '&'
0x180002b2a  mov     dword ptr [rsp+2C0h+lpData], r15d
0x180002b2f  mov     ecx, 401h
0x180002b34  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180002b3b  mov     r9, rbx
0x180002b3e  call    WPP_SF_SD
0x180002b43  jmp     short loc_180002BAF
0x180002b45  cmp     ecx, 4
0x180002b48  jz      short loc_180002B6E
0x180002b4a  test    byte ptr cs:xmmword_1800616A0, 2
0x180002b51  jz      short loc_180002BAF
0x180002b53  mov     edx, 27h ; '''
0x180002b58  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180002b5f  mov     ecx, 401h
0x180002b64  mov     r9, rbx
0x180002b67  call    WPP_SF_S
0x180002b6c  jmp     short loc_180002BAF
0x180002b6e  lea     rdx, aDhcpinforminte; "DhcpInformInterval"
0x180002b75  mov     rcx, rbx; String1
0x180002b78  call    wcscmp_0
0x180002b7d  test    eax, eax
0x180002b7f  jnz     short loc_180002B8B
0x180002b81  mov     dword ptr [rdi+7B8h], 1
0x180002b8b  mov     rcx, [rbp+rsi*8+1C0h+var_1A0]
0x180002b90  mov     eax, dword ptr [rsp+2C0h+Data]
0x180002b94  mov     [rcx], eax
0x180002b96  test    byte ptr cs:xmmword_1800616A0, 10h
0x180002b9d  jz      short loc_180002BAF
0x180002b9f  mov     eax, dword ptr [rsp+2C0h+Data]
0x180002ba3  mov     r9, rbx
0x180002ba6  mov     dword ptr [rsp+2C0h+lpData], eax
0x180002baa  call    WPP_SF_Sl
0x180002baf  inc     r14
0x180002bb2  cmp     r14, 14h
0x180002bb6  jnz     loc_180002A92
0x180002bbc  mov     eax, [rbp+1C0h+var_238]
0x180002bbf  xor     ebx, ebx
0x180002bc1  mov     [rdi+94h], eax
0x180002bc7  mov     eax, [rbp+1C0h+var_234]
0x180002bca  mov     [rdi+98h], eax
0x180002bd0  mov     eax, [rsp+2C0h+var_278]
0x180002bd4  mov     [rdi+348h], eax
0x180002bda  cmp     [rsp+2C0h+var_24C], ebx
0x180002bde  jz      short loc_180002BE8
0x180002be0  mov     [rsp+2C0h+var_28C], 1
0x180002be8  mov     eax, [rdi+334h]
0x180002bee  test    eax, eax
0x180002bf0  jz      short loc_180002C1B
0x180002bf2  test    byte ptr cs:xmmword_1800616A0, 10h
0x180002bf9  jz      short loc_180002C14
0x180002bfb  mov     edx, 29h ; ')'
0x180002c00  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180002c07  mov     ecx, 404h
0x180002c0c  mov     r9, r12
0x180002c0f  call    WPP_SF_S
0x180002c14  mov     [rsp+2C0h+var_28C], ebx
0x180002c18  mov     [rbp+1C0h+var_230], ebx
0x180002c1b  cmp     byte ptr [rdi+54h], 8
0x180002c1f  jnz     short loc_180002C25
0x180002c21  mov     [rsp+2C0h+var_28C], ebx
0x180002c25  lea     rdx, [rsp+2C0h+var_280]
0x180002c2a  mov     rcx, r13
0x180002c2d  call    DhcpGetGatewayCount
0x180002c32  mov     r15d, [rsp+2C0h+var_280]
0x180002c37  test    r15d, r15d
0x180002c3a  jz      short loc_180002C86
0x180002c3c  mov     ecx, r15d
0x180002c3f  shl     rcx, 2
0x180002c43  call    DhcpAlloc
0x180002c48  mov     [rbp+1C0h+var_210], rax
0x180002c4c  test    rax, rax
0x180002c4f  jnz     short loc_180002C78
0x180002c51  test    byte ptr cs:xmmword_1800616A0, 2
0x180002c58  jz      short loc_180002C6E
0x180002c5a  lea     edx, [rax+2Ah]
0x180002c5d  mov     ecx, 401h
0x180002c62  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180002c69  call    WPP_SF_
0x180002c6e  mov     eax, 8
0x180002c73  jmp     loc_180003285
0x180002c78  mov     r8d, r15d
0x180002c7b  mov     rdx, rax
0x180002c7e  mov     rcx, r13
0x180002c81  call    DhcpGetGatewayInfo
0x180002c86  mov     rsi, rbx
0x180002c89  mov     r14, rsi
0x180002c8c  mov     [rsp+2C0h+var_280], ebx
0x180002c90  add     r14, r14
0x180002c93  mov     [rbp+1C0h+Str], rbx
0x180002c97  lea     r9, [rsp+2C0h+var_280]
  ... truncated ...
```
