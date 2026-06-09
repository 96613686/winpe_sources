# IpcpProjectionNotification

- ea: `0x18001ea80`
- end: `0x18001f754`
- name: `IpcpProjectionNotification`
- size: `3284`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800185d8`
- `0x180018674`
- `0x18001bab4`
- `0x18001ea80`
- `0x180020b1c`
- `0x18002b0dc`
- `0x18002dc44`
- `0x180031cd0`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001eeeb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001eeeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f350`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f350`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f144`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f1f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f144`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f1f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f21a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ed6c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ed6c`
- `DNSAPI!DnsSetConfigDword` at `0x18001f066`
- `DNSAPI!DnsSetConfigDword` at `0x18001f08a`
- `DNSAPI!DnsSetConfigDword` at `0x18001f0d1`
- `DNSAPI!DnsSetConfigDword` at `0x18001f0f5`
- `DNSAPI!DnsSetConfigDword` at `0x18001f066`
- `DNSAPI!DnsSetConfigDword` at `0x18001f08a`
- `DNSAPI!DnsSetConfigDword` at `0x18001f0d1`
- `DNSAPI!DnsSetConfigDword` at `0x18001f0f5`
- `rtutils!LogEventW` at `0x18001f626`
- `rtutils!LogEventW` at `0x18001f662`
- `rtutils!LogEventW` at `0x18001f626`
- `rtutils!LogEventW` at `0x18001f662`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18001f71c`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18001f71c`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18001ecd8`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18001ecd8`

## string_xrefs

- `0x18001edde`: `IPCP: NsiGetCompartmentIdForRoutingDomain: failed Err: %d`
- `0x18001ef94`: `IPCP: LocalAlloc for pLinkup Info =%d`
- `0x18001f3ae`: `IPCP:RasPortSetProtocolCompression(s=%d,%d r=%d,%d)`
- `0x18001f43a`: `IPCP: RasPortSetProtocolCompression done(%d)`

## pseudocode

```c
__int64 __fastcall IpcpProjectionNotification(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // r14d
  __int64 v4; // rdx
  __int64 v5; // r8
  bool v6; // zf
  int v7; // ecx
  unsigned int v8; // eax
  unsigned int *v9; // r12
  __int64 v10; // r9
  int v11; // eax
  __int128 v12; // xmm1
  unsigned int CompartmentIdForRoutingDomain; // eax
  const wchar_t *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r15
  DWORD LastError; // eax
  GUID v19; // xmm0
  unsigned int v20; // eax
  wchar_t *v21; // rax
  _OWORD *v22; // rax
  DWORD v23; // eax
  __int64 v24; // rdx
  _OWORD *v25; // rcx
  __int128 v26; // xmm1
  __int64 v27; // rdx
  __int64 v28; // rdx
  const wchar_t *v29; // r8
  __int64 v30; // rdx
  const wchar_t *v31; // r8
  wchar_t **v32; // rax
  wchar_t **v33; // rsi
  DWORD v34; // eax
  __int64 v35; // rdx
  wchar_t *v36; // rax
  DWORD v37; // eax
  const wchar_t *v38; // r8
  unsigned int v39; // eax
  int v40; // eax
  __int64 v41; // r9
  __int64 v42; // r8
  unsigned int v43; // eax
  unsigned int v44; // ecx
  __int64 v45; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  __int64 cchWideChar; // [rsp+28h] [rbp-D8h]
  __int64 v49; // [rsp+30h] [rbp-D0h] BYREF
  int v50; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR plpwsSubStrings[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v52; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v53[3]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v54; // [rsp+60h] [rbp-A0h]
  int v55; // [rsp+64h] [rbp-9Ch]
  int v56; // [rsp+84h] [rbp-7Ch]
  unsigned int v57; // [rsp+29Ch] [rbp+19Ch]
  int v58; // [rsp+2A0h] [rbp+1A0h]
  int v59; // [rsp+2A4h] [rbp+1A4h]
  _BYTE v60[28]; // [rsp+2B4h] [rbp+1B4h]
  wchar_t pszDest[274]; // [rsp+2D0h] [rbp+1D0h] BYREF
  GUID v62; // [rsp+4F4h] [rbp+3F4h]
  int v63; // [rsp+510h] [rbp+410h] BYREF
  char v64[2044]; // [rsp+514h] [rbp+414h] BYREF

  v50 = 0;
  v63 = 0;
  v2 = 0;
  memset_0(v64, 0, sizeof(v64));
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpProjectionNotification");
  if ( *(_DWORD *)(a1 + 28) )
  {
    v3 = 0;
    memset_0(&v52, 0, 0x4B8u);
    v6 = *(_DWORD *)(a1 + 2088) == 2;
    v52 = 1200;
    if ( v6 )
      v7 = 2;
    else
      v7 = *(_DWORD *)a1 == 0;
    v8 = *(_DWORD *)(a1 + 2080);
    v9 = (unsigned int *)(a1 + 2104);
    v10 = *(unsigned int *)(a1 + 144);
    *(_DWORD *)(a1 + 2104) = 0;
    v54 = v8;
    v11 = *(_DWORD *)(a1 + 148);
    v53[0] = v7;
    v58 = -1;
    v57 = v10;
    v59 = v11;
    v56 = 1;
    v12 = *(_OWORD *)(a1 + 2148);
    v62 = GUID_NULL;
    *(_OWORD *)v60 = *(_OWORD *)(a1 + 2136);
    *(_OWORD *)&v60[12] = v12;
    if ( v7 )
    {
      v55 = 0;
    }
    else
    {
      CompartmentIdForRoutingDomain = RasPPPGetNewSubInterfaceIndex();
      v2 = CompartmentIdForRoutingDomain;
      if ( CompartmentIdForRoutingDomain )
      {
        if ( !*((_QWORD *)&xmmword_18004D860 + 1) )
          goto LABEL_122;
        v14 = L"IPCP: RasPPPGetNewSubInterfaceIndex: failed Err: %d";
        goto LABEL_11;
      }
      v10 = v57;
      v55 = *v9;
    }
    v53[2] = *(_DWORD *)(a1 + 16);
    v53[1] = 0;
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      LOWORD(v63) = 0;
      FormatRRASErrorString((wchar_t *)&v63, L"IPCP: RasActivateRoute(u=%x,a=%x,nf=%d)...", v53[0], v10, 0);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v63);
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      {
        LOWORD(v63) = 0;
        FormatRRASErrorString((wchar_t *)&v63, L"IPCP: RasActivateRoute ICB# == %d", v54);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          &v63);
      }
    }
    if ( v53[0] == 1 )
    {
      v15 = RasAllocInterfaceLuidIndex(*(_QWORD *)(a1 + 8), a1 + 704, v5, v10);
      v2 = v15;
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      {
        v16 = *(unsigned int *)(a1 + 704);
        LOWORD(v63) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v63,
          L"IPCP: RasAllocateInterfaceLuidIndex returns %I64X as the LuidIndex %x as the return value",
          v16,
          v15);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          &v63);
      }
    }
    v17 = -1;
    if ( v53[0] == 1 )
    {
      if ( *(_BYTE *)(a1 + 1812) && !MultiByteToWideChar(0, 0, (LPCCH)(a1 + 1812), -1, (LPWSTR)(a1 + 708), 256) )
      {
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          LOWORD(v63) = 0;
          LastError = GetLastError();
          FormatRRASErrorString((wchar_t *)&v63, L"IPCP:MultiByteToWideChar failed. Error %d", LastError);
          goto LABEL_12;
        }
        goto LABEL_122;
      }
    }
    else if ( !v53[0] )
    {
      LODWORD(v49) = 1;
      CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain((_QWORD *)(a1 + 2120), &v49);
      v2 = CompartmentIdForRoutingDomain;
      if ( CompartmentIdForRoutingDomain )
      {
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          v14 = L"IPCP: NsiGetCompartmentIdForRoutingDomain: failed Err: %d";
LABEL_11:
          LOWORD(v63) = 0;
          FormatRRASErrorString((wchar_t *)&v63, v14, CompartmentIdForRoutingDomain);
LABEL_12:
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004D860 + 1),
            &v63);
        }
LABEL_122:
        *(_DWORD *)(a1 + 28) = 0;
        if ( v2 )
        {
          if ( v50 && *(_DWORD *)(a1 + 16) )
          {
            LOBYTE(v10) = 1;
            LOBYTE(v4) = 1;
            ((void (__fastcall *)(_QWORD, __int64, __int64, __int64))xmmword_18004D450)(
              0,
              v4,
              (*(_DWORD *)(a1 + 1256) & 0xFFFFFF | 0x17000000LL) << 24,
              v10);
          }
          if ( *(_DWORD *)(a1 + 76) || *(_DWORD *)(a1 + 80) )
          {
            if ( *((_QWORD *)&xmmword_18004D860 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                *((_QWORD *)&xmmword_18004D860 + 1),
                L"IPCP: RasDeAllocateRoute...");
            ((void (__fastcall *)(_QWORD, __int64))xmmword_18004D440)(*(_QWORD *)(a1 + 2072), 2048);
            *(_QWORD *)(a1 + 76) = 0;
          }
          *(_DWORD *)(a1 + 2104) = 0;
          if ( v3 )
          {
            RasFreeInterfaceLuidIndex(*(_QWORD *)(a1 + 8), *(unsigned int *)(a1 + 1256));
            *(_DWORD *)(a1 + 1256) = 0;
          }
        }
        return v2;
      }
      v19 = *(GUID *)(a1 + 2120);
      v56 = v49;
      v62 = v19;
LABEL_32:
      if ( v53[0] == 1 )
        v3 = 1;
      *(_DWORD *)(a1 + 1256) = *(_DWORD *)(a1 + 704);
      *(_DWORD *)(a1 + 1236) = 0;
      LODWORD(v49) = v3;
      if ( *(_WORD *)(a1 + 1264) )
        StringCchCopyW(pszDest, 0x111u, (STRSAFE_LPCWSTR)(a1 + 1264));
      else
        pszDest[0] = 0;
      v20 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, int *))&xmmword_18004D440 + 1))(
              *(_QWORD *)(a1 + 8),
              2048,
              a1 + 184,
              &v52);
      v2 = v20;
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      {
        LOWORD(v63) = 0;
        FormatRRASErrorString((wchar_t *)&v63, L"IPCP: RasActivateRoute done(%d)", v20);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          &v63);
      }
      if ( v2 )
        goto LABEL_122;
      v6 = v53[0] == 2;
      *(_DWORD *)(a1 + 76) = 1;
      if ( v6 )
        *(_DWORD *)(a1 + 1256) = *(_DWORD *)(a1 + 704);
      v21 = wcschr((const wchar_t *)(a1 + 448), 0x5Cu);
      *(_QWORD *)(a1 + 1248) = v21;
      if ( !v21 )
      {
        v4 = *((_QWORD *)&xmmword_18004D860 + 1);
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004D860 + 1),
            L"IPCP: No device?");
        v2 = 87;
        goto LABEL_122;
      }
      *(_QWORD *)(a1 + 1248) = v21 + 1;
      if ( *(_DWORD *)a1 && *(_DWORD *)(a1 + 2088) != 2 )
        goto LABEL_89;
      v22 = LocalAlloc(0x40u, 0x4B0u);
      *(_QWORD *)(a1 + 2112) = v22;
      if ( !v22 )
      {
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          LOWORD(v63) = 0;
          v23 = GetLastError();
          FormatRRASErrorString((wchar_t *)&v63, L"IPCP: LocalAlloc for pLinkup Info =%d", v23);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004D860 + 1),
            &v63);
        }
        goto LABEL_89;
      }
      v24 = 9;
      v25 = v53;
      do
      {
        *v22 = *v25;
        v22[1] = v25[1];
        v22[2] = v25[2];
        v22[3] = v25[3];
        v22[4] = v25[4];
        v22[5] = v25[5];
        v22[6] = v25[6];
        v26 = v25[7];
        v25 += 8;
        v22[7] = v26;
        v22 += 8;
        --v24;
      }
      while ( v24 );
      *v22 = *v25;
      v22[1] = v25[1];
      v22[2] = v25[2];
      v2 = ApplyIpcpSettings(a1, v53, &v50);
      v27 = *(_QWORD *)(a1 + 1248);
      if ( *(_DWORD *)(a1 + 68) )
      {
        DnsSetConfigDword(65552, v27, 1);
        v28 = *((_QWORD *)&xmmword_18004D860 + 1);
        if ( !*((_QWORD *)&xmmword_18004D860 + 1) )
          goto LABEL_59;
        v29 = L"DnsEnableDynamicRegistration";
      }
      else
      {
        DnsSetConfigDword(65552, v27, 0);
        v28 = *((_QWORD *)&xmmword_18004D860 + 1);
        if ( !*((_QWORD *)&xmmword_18004D860 + 1) )
          goto LABEL_59;
        v29 = L"DnsDisableDynamicRegistration";
      }
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v28, v29);
LABEL_59:
      v30 = *(_QWORD *)(a1 + 1248);
      if ( *(_DWORD *)(a1 + 72) )
      {
        DnsSetConfigDword(10, v30, 1);
        v4 = *((_QWORD *)&xmmword_18004D860 + 1);
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          v31 = L"DnsEnableAdapterDomainNameRegistration";
LABEL_64:
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v4, v31);
        }
      }
      else
      {
        DnsSetConfigDword(10, v30, 0);
        v4 = *((_QWORD *)&xmmword_18004D860 + 1);
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          v31 = L"DnsDisableAdapterDomainNameRegistration";
          goto LABEL_64;
        }
      }
      if ( *(_DWORD *)a1 || *(_DWORD *)(a1 + 2088) == 2 )
      {
LABEL_88:
        if ( v2 )
          goto LABEL_122;
        goto LABEL_89;
      }
      v32 = (wchar_t **)LocalAlloc(0x40u, 0x28u);
      v33 = v32;
      if ( !v32 )
      {
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          LOWORD(v63) = 0;
          v34 = GetLastError();
          FormatRRASErrorString((wchar_t *)&v63, L"IPCP: LocalAlloc 1 =%d", v34);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004D860 + 1),
            &v63);
        }
        goto LABEL_87;
      }
      v32[2] = *(wchar_t **)(a1 + 8);
      v35 = -1;
      *((_DWORD *)v32 + 6) = *(_BYTE *)(a1 + 1812) == 0;
      do
        ++v35;
      while ( *(_WORD *)(*(_QWORD *)(a1 + 1248) + 2 * v35) );
      v36 = (wchar_t *)LocalAlloc(0x40u, 2 * v35 + 2);
      *v33 = v36;
      if ( !v36 )
      {
        if ( !*((_QWORD *)&xmmword_18004D860 + 1) )
        {
LABEL_86:
          LocalFree(*v33);
          v3 = v49;
LABEL_87:
          LocalFree(v33);
          goto LABEL_88;
        }
        LOWORD(v63) = 0;
        v37 = GetLastError();
        FormatRRASErrorString((wchar_t *)&v63, L"IPCP: LocalAlloc 2 =%d", v37);
LABEL_85:
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          &v63);
        goto LABEL_86;
      }
      v38 = *(const wchar_t **)(a1 + 1248);
      do
        ++v17;
      while ( v38[v17] );
      StringCchCopyW(v36, v17 + 1, v38);
      v33[1] = *(wchar_t **)(a1 + 2072);
      if ( *(_BYTE *)(a1 + 1812) )
      {
        if ( !*((_QWORD *)&xmmword_18004D860 + 1) )
        {
LABEL_82:
          *((_DWORD *)v33 + 7) = 0;
          v33[4] = (wchar_t *)SendMessageToProtocolEngine;
          v39 = DhcpInformRequestAsync(v33);
          v2 = v39;
          if ( !v39 )
          {
            v3 = v49;
LABEL_89:
            *(_DWORD *)(a1 + 24) = 1;
            if ( *(_DWORD *)(a1 + 32) )
            {
              *(_WORD *)(a1 + 176) = 0;
              *(_WORD *)(a1 + 178) = 0;
            }
            if ( !*(_DWORD *)(a1 + 180) )
            {
              *(_WORD *)(a1 + 172) = 0;
              *(_WORD *)(a1 + 174) = 0;
            }
            if ( *((_QWORD *)&xmmword_18004D860 + 1) )
            {
              v40 = *(unsigned __int8 *)(a1 + 179);
              v41 = *(unsigned __int8 *)(a1 + 175);
              v42 = *(unsigned __int8 *)(a1 + 174);
              LOWORD(v63) = 0;
              LODWORD(cchWideChar) = v40;
              LODWORD(lpWideCharStr) = *(unsigned __int8 *)(a1 + 178);
              FormatRRASErrorString(
                (wchar_t *)&v63,
                L"IPCP:RasPortSetProtocolCompression(s=%d,%d r=%d,%d)",
                v42,
                v41,
                lpWideCharStr,
                cchWideChar);
              ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                *((_QWORD *)&xmmword_18004D860 + 1),
                &v63);
            }
            v43 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))&xmmword_18004D4B0 + 1))(
                    *(_QWORD *)(a1 + 8),
                    2048,
                    a1 + 172,
                    a1 + 176);
            v2 = v43;
            if ( *((_QWORD *)&xmmword_18004D860 + 1) )
            {
              LOWORD(v63) = 0;
              FormatRRASErrorString((wchar_t *)&v63, L"IPCP: RasPortSetProtocolCompression done(%d)", v43);
              ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                *((_QWORD *)&xmmword_18004D860 + 1),
                &v63);
            }
            if ( !*(_DWORD *)a1 && *(_DWORD *)(a1 + 2088) != 2 )
              goto LABEL_122;
            v44 = *(_DWORD *)(a1 + 148);
            if ( v44 )
            {
              v4 = *((_QWORD *)&xmmword_18004D860 + 1);
              v49 = 0;
              if ( *((_QWORD *)&xmmword_18004D860 + 1) )
              {
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004D860 + 1),
                  L"IPCP: RasPPPActivateIpv4Address...");
                v44 = *(_DWORD *)(a1 + 148);
              }
              if ( *(_DWORD *)(a1 + 2088) == 2 && v44 )
                v45 = (*(_DWORD *)(a1 + 1256) & 0xFFFFFF | 0x17000000LL) << 24;
              else
                v45 = *v9;
              v49 = v45;
              if ( xmmword_18004D510 )
              {
                *(_OWORD *)plpwsSubStrings = *(_OWORD *)(a1 + 2120);
                v2 = xmmword_18004D510(plpwsSubStrings, v44, v53[0], &v49);
              }
              else
              {
                v2 = 4317;
              }
              if ( *((_QWORD *)&xmmword_18004D860 + 1) )
              {
                LOWORD(v63) = 0;
                FormatRRASErrorString((wchar_t *)&v63, L"IPCP: RasPPPActivateIpv4Address done(%d)", v2);
                ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004D860 + 1),
                  &v63);
              }
              if ( *(_DWORD *)(a1 + 2088) != 2 )
                goto LABEL_122;
              if ( *((_QWORD *)&xmmword_18004D860 + 1) )
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004D860 + 1),
                  L"IPCP: RasPPPActivateDoDSpecificRoute...");
              RasPPPActivateDoDSpecificRoute(*(unsigned int *)(a1 + 148));
              v4 = *((_QWORD *)&xmmword_18004D860 + 1);
              if ( *((_QWORD *)&xmmword_18004D860 + 1) )
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004D860 + 1),
                  L"IPCP: RasPPPActivateDoDSpecificRoute done");
            }
            if ( *(_DWORD *)(a1 + 2088) == 2 )
            {
              *(_OWORD *)plpwsSubStrings = 0;
              if ( !*(_DWORD *)(a1 + 148) )
              {
                plpwsSubStrings[1] = (LPWSTR)(a1 + 1264);
                plpwsSubStrings[0] = (LPWSTR)(a1 + 1778);
                LogEventW(2u, 0x4EC6u, 2u, plpwsSubStrings);
              }
              if ( !*(_DWORD *)(a1 + 144) )
              {
                plpwsSubStrings[0] = (LPWSTR)(a1 + 1778);
                plpwsSubStrings[1] = (LPWSTR)(a1 + 1264);
                LogEventW(2u, 0x4EC5u, 2u, plpwsSubStrings);
              }
            }
            goto LABEL_122;
          }
          if ( !*((_QWORD *)&xmmword_18004D860 + 1) )
            goto LABEL_86;
          LOWORD(v63) = 0;
          FormatRRASErrorString((wchar_t *)&v63, L"IPCP: RtlQueueWorkItem=%d", v39);
          goto LABEL_85;
        }
        LOWORD(v63) = 0;
        FormatRRASErrorString((wchar_t *)&v63, L"IPCP: DhcpInform: DNS Suffix %hs", a1 + 1812);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          &v63);
      }
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          L"DHCP inform is happening asynchronously");
      goto LABEL_82;
    }
    if ( v2 )
      goto LABEL_122;
    goto LABEL_32;
  }
  return v2;
}

```

## disassembly

```asm
0x18001ea80  push    rbp
0x18001ea82  push    rbx
0x18001ea83  push    rsi
0x18001ea84  push    rdi
0x18001ea85  push    r12
0x18001ea87  push    r13
0x18001ea89  push    r14
0x18001ea8b  push    r15
0x18001ea8d  lea     rbp, [rsp-0C28h]
0x18001ea95  sub     rsp, 0D28h
0x18001ea9c  mov     rax, cs:__security_cookie
0x18001eaa3  xor     rax, rsp
0x18001eaa6  mov     [rbp+0C60h+var_50], rax
0x18001eaad  xor     esi, esi
0x18001eaaf  mov     rbx, rcx
0x18001eab2  lea     rcx, [rbp+0C60h+var_84C]; void *
0x18001eab9  mov     [rsp+0D60h+var_D28], esi
0x18001eabd  xor     edx, edx; Val
0x18001eabf  mov     [rbp+0C60h+var_850], esi
0x18001eac5  mov     r8d, 7FCh; Size
0x18001eacb  mov     edi, esi
0x18001eacd  call    memset_0
0x18001ead2  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001ead9  test    rdx, rdx
0x18001eadc  jz      short loc_18001EAF8
0x18001eade  mov     rcx, cs:gRasIpcpEtwContext
0x18001eae5  lea     r8, aIpcpIpcpprojec; "IPCP: IpcpProjectionNotification"
0x18001eaec  mov     rax, cs:gRasIpcpTemplateFunc
0x18001eaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaf8  cmp     [rbx+1Ch], esi
0x18001eafb  jz      loc_18001F72E
0x18001eb01  xor     edx, edx; Val
0x18001eb03  lea     rcx, [rsp+0D60h+var_D10]; void *
0x18001eb08  mov     r8d, 4B8h; Size
0x18001eb0e  mov     r14d, esi
0x18001eb11  call    memset_0
0x18001eb16  cmp     dword ptr [rbx+828h], 2
0x18001eb1d  mov     [rsp+0D60h+var_D10], 4B0h
0x18001eb25  jnz     short loc_18001EB2E
0x18001eb27  mov     ecx, 2
0x18001eb2c  jmp     short loc_18001EB35
0x18001eb2e  cmp     [rbx], esi
0x18001eb30  mov     ecx, esi
0x18001eb32  setz    cl
0x18001eb35  mov     eax, [rbx+820h]
0x18001eb3b  lea     r12, [rbx+838h]
0x18001eb42  mov     r9d, [rbx+90h]
0x18001eb49  mov     r13d, 1
0x18001eb4f  mov     [r12], esi
0x18001eb53  mov     [rsp+0D60h+var_D00], eax
0x18001eb57  mov     eax, [rbx+94h]
0x18001eb5d  mov     [rsp+0D60h+var_D0C], ecx
0x18001eb61  mov     [rbp+0C60h+var_AC0], 0FFFFFFFFh
0x18001eb6b  mov     [rbp+0C60h+var_AC4], r9d
0x18001eb72  mov     [rbp+0C60h+var_ABC], eax
0x18001eb78  mov     [rbp+0C60h+var_CDC], r13d
0x18001eb7c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001eb83  movups  xmm1, xmmword ptr [rbx+864h]
0x18001eb8a  movdqu  [rbp+0C60h+var_86C], xmm0
0x18001eb92  movups  xmm0, xmmword ptr [rbx+858h]
0x18001eb99  movups  xmmword ptr [rbp+0C60h+var_AAC], xmm0
0x18001eba0  movups  xmmword ptr [rbp+0C60h+var_AAC+0Ch], xmm1
0x18001eba7  test    ecx, ecx
0x18001eba9  jnz     short loc_18001EC1A
0x18001ebab  mov     rcx, r12
0x18001ebae  call    RasPPPGetNewSubInterfaceIndex
0x18001ebb3  mov     edi, eax
0x18001ebb5  test    eax, eax
0x18001ebb7  jz      short loc_18001EC09
0x18001ebb9  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001ebc0  jz      loc_18001F674
0x18001ebc6  lea     rdx, aIpcpRaspppgetn; "IPCP: RasPPPGetNewSubInterfaceIndex: fa"...
0x18001ebcd  mov     word ptr [rbp+0C60h+var_850], si
0x18001ebd4  mov     r8d, eax
0x18001ebd7  lea     rcx, [rbp+0C60h+var_850]
0x18001ebde  call    FormatRRASErrorString
0x18001ebe3  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001ebea  lea     r8, [rbp+0C60h+var_850]
0x18001ebf1  mov     rcx, cs:gRasIpcpEtwContext
0x18001ebf8  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec04  jmp     loc_18001F674
0x18001ec09  mov     eax, [r12]
0x18001ec0d  mov     r9d, [rbp+0C60h+var_AC4]
0x18001ec14  mov     [rsp+0D60h+var_CFC], eax
0x18001ec18  jmp     short loc_18001EC1E
0x18001ec1a  mov     [rsp+0D60h+var_CFC], esi
0x18001ec1e  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001ec25  mov     eax, [rbx+10h]
0x18001ec28  mov     [rsp+0D60h+var_D04], eax
0x18001ec2c  mov     [rsp+0D60h+var_D08], esi
0x18001ec30  jz      loc_18001ECC3
0x18001ec36  mov     r8d, [rsp+0D60h+var_D0C]
0x18001ec3b  lea     rdx, aIpcpRasactivat_1; "IPCP: RasActivateRoute(u=%x,a=%x,nf=%d)"...
0x18001ec42  lea     rcx, [rbp+0C60h+var_850]
0x18001ec49  mov     word ptr [rbp+0C60h+var_850], si
0x18001ec50  mov     dword ptr [rsp+0D60h+lpWideCharStr], esi
0x18001ec54  call    FormatRRASErrorString
0x18001ec59  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001ec60  lea     r8, [rbp+0C60h+var_850]
0x18001ec67  mov     rcx, cs:gRasIpcpEtwContext
0x18001ec6e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ec75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec7a  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001ec81  jz      short loc_18001ECC3
0x18001ec83  mov     r8d, [rsp+0D60h+var_D00]
0x18001ec88  lea     rdx, aIpcpRasactivat; "IPCP: RasActivateRoute ICB# == %d"
0x18001ec8f  lea     rcx, [rbp+0C60h+var_850]
0x18001ec96  mov     word ptr [rbp+0C60h+var_850], si
0x18001ec9d  call    FormatRRASErrorString
0x18001eca2  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001eca9  lea     r8, [rbp+0C60h+var_850]
0x18001ecb0  mov     rcx, cs:gRasIpcpEtwContext
0x18001ecb7  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ecbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecc3  cmp     [rsp+0D60h+var_D0C], r13d
0x18001ecc8  jnz     short loc_18001ED34
0x18001ecca  mov     rcx, [rbx+8]
0x18001ecce  lea     rsi, [rbx+2C0h]
0x18001ecd5  mov     rdx, rsi
0x18001ecd8  call    cs:__imp_RasAllocInterfaceLuidIndex
0x18001ecdf  nop     dword ptr [rax+rax+00h]
0x18001ece4  xor     ecx, ecx
0x18001ece6  mov     edi, eax
0x18001ece8  cmp     qword ptr cs:xmmword_18004D860+8, rcx
0x18001ecef  jz      short loc_18001ED32
0x18001ecf1  mov     r8d, [rsi]
0x18001ecf4  lea     rdx, aIpcpRasallocat_0; "IPCP: RasAllocateInterfaceLuidIndex ret"...
0x18001ecfb  mov     word ptr [rbp+0C60h+var_850], cx
0x18001ed02  mov     r9d, eax
0x18001ed05  lea     rcx, [rbp+0C60h+var_850]
0x18001ed0c  call    FormatRRASErrorString
0x18001ed11  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001ed18  lea     r8, [rbp+0C60h+var_850]
0x18001ed1f  mov     rcx, cs:gRasIpcpEtwContext
0x18001ed26  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ed2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed32  xor     esi, esi
0x18001ed34  mov     eax, [rsp+0D60h+var_D0C]
0x18001ed38  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001ed3c  cmp     eax, r13d
0x18001ed3f  jnz     short loc_18001EDAC
0x18001ed41  lea     r8, [rbx+714h]; lpMultiByteStr
0x18001ed48  cmp     [r8], sil
0x18001ed4b  jz      loc_18001EE00
0x18001ed51  lea     rax, [rbx+2C4h]
0x18001ed58  mov     dword ptr [rsp+0D60h+cchWideChar], 100h; cchWideChar
0x18001ed60  mov     r9d, r15d; cbMultiByte
0x18001ed63  mov     [rsp+0D60h+lpWideCharStr], rax; lpWideCharStr
0x18001ed68  xor     edx, edx; dwFlags
0x18001ed6a  xor     ecx, ecx; CodePage
0x18001ed6c  call    cs:__imp_MultiByteToWideChar
0x18001ed73  nop     dword ptr [rax+rax+00h]
0x18001ed78  test    eax, eax
0x18001ed7a  jnz     loc_18001EE00
0x18001ed80  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001ed87  jz      loc_18001F674
0x18001ed8d  mov     word ptr [rbp+0C60h+var_850], si
0x18001ed94  call    cs:__imp_GetLastError
0x18001ed9b  nop     dword ptr [rax+rax+00h]
0x18001eda0  lea     rdx, aIpcpMultibytet; "IPCP:MultiByteToWideChar failed. Error "...
0x18001eda7  jmp     loc_18001EBD4
0x18001edac  test    eax, eax
0x18001edae  jnz     short loc_18001EE00
0x18001edb0  lea     rsi, [rbx+848h]
0x18001edb7  mov     dword ptr [rsp+0D60h+var_D30], r13d
0x18001edbc  mov     rcx, rsi
0x18001edbf  lea     rdx, [rsp+0D60h+var_D30]
0x18001edc4  call    NsiGetCompartmentIdForRoutingDomain
0x18001edc9  mov     edi, eax
0x18001edcb  test    eax, eax
0x18001edcd  jz      short loc_18001EDEA
0x18001edcf  xor     esi, esi
0x18001edd1  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001edd8  jz      loc_18001F674
0x18001edde  lea     rdx, aIpcpNsigetcomp; "IPCP: NsiGetCompartmentIdForRoutingDoma"...
0x18001ede5  jmp     loc_18001EBCD
0x18001edea  movups  xmm0, xmmword ptr [rsi]
0x18001eded  mov     eax, dword ptr [rsp+0D60h+var_D30]
0x18001edf1  xor     esi, esi
0x18001edf3  mov     [rbp+0C60h+var_CDC], eax
0x18001edf6  movdqu  [rbp+0C60h+var_86C], xmm0
0x18001edfe  jmp     short loc_18001EE08
0x18001ee00  test    edi, edi
0x18001ee02  jnz     loc_18001F674
0x18001ee08  cmp     [rsp+0D60h+var_D0C], r13d
0x18001ee0d  mov     eax, [rbx+2C0h]
0x18001ee13  cmovz   r14d, r13d
0x18001ee17  mov     [rbx+4E8h], eax
0x18001ee1d  lea     r13, [rbx+4F0h]
0x18001ee24  mov     [rbx+4D4h], esi
0x18001ee2a  mov     dword ptr [rsp+0D60h+var_D30], r14d
0x18001ee2f  cmp     [r13+0], si
0x18001ee34  jz      short loc_18001EE4C
0x18001ee36  mov     r8, r13; pszSrc
0x18001ee39  lea     rcx, [rbp+0C60h+pszDest]; pszDest
0x18001ee40  mov     edx, 111h; cchDest
0x18001ee45  call    StringCchCopyW
0x18001ee4a  jmp     short loc_18001EE53
0x18001ee4c  mov     [rbp+0C60h+pszDest], si
0x18001ee53  mov     rcx, [rbx+8]
0x18001ee57  lea     r8, [rbx+0B8h]
0x18001ee5e  mov     rax, qword ptr cs:xmmword_18004D440+8
0x18001ee65  lea     r9, [rsp+0D60h+var_D10]
0x18001ee6a  mov     edx, 800h
0x18001ee6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee74  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001ee7b  mov     edi, eax
0x18001ee7d  jz      short loc_18001EEBD
0x18001ee7f  mov     r8d, eax
0x18001ee82  mov     word ptr [rbp+0C60h+var_850], si
0x18001ee89  lea     rdx, aIpcpRasactivat_0; "IPCP: RasActivateRoute done(%d)"
0x18001ee90  lea     rcx, [rbp+0C60h+var_850]
0x18001ee97  call    FormatRRASErrorString
0x18001ee9c  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001eea3  lea     r8, [rbp+0C60h+var_850]
0x18001eeaa  mov     rcx, cs:gRasIpcpEtwContext
0x18001eeb1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001eeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebd  test    edi, edi
0x18001eebf  jnz     loc_18001F66E
0x18001eec5  cmp     [rsp+0D60h+var_D0C], 2
0x18001eeca  mov     dword ptr [rbx+4Ch], 1
0x18001eed1  jnz     short loc_18001EEDF
0x18001eed3  mov     eax, [rbx+2C0h]
0x18001eed9  mov     [rbx+4E8h], eax
0x18001eedf  mov     edx, 5Ch ; '\'; Ch
0x18001eee4  lea     rcx, [rbx+1C0h]; Str
0x18001eeeb  call    cs:__imp_wcschr
0x18001eef2  nop     dword ptr [rax+rax+00h]
0x18001eef7  mov     [rbx+4E0h], rax
0x18001eefe  test    rax, rax
0x18001ef01  jnz     short loc_18001EF33
0x18001ef03  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001ef0a  test    rdx, rdx
0x18001ef0d  jz      short loc_18001EF29
0x18001ef0f  mov     rcx, cs:gRasIpcpEtwContext
0x18001ef16  lea     r8, aIpcpNoDevice; "IPCP: No device?"
0x18001ef1d  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ef24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef29  mov     edi, 57h ; 'W'
0x18001ef2e  jmp     loc_18001F66E
0x18001ef33  add     rax, 2
0x18001ef37  mov     [rbx+4E0h], rax
0x18001ef3e  cmp     [rbx], esi
0x18001ef40  jz      short loc_18001EF4F
0x18001ef42  cmp     dword ptr [rbx+828h], 2
0x18001ef49  jnz     loc_18001F366
0x18001ef4f  mov     edx, 4B0h; uBytes
0x18001ef54  mov     ecx, 40h ; '@'; uFlags
0x18001ef59  call    cs:__imp_LocalAlloc
0x18001ef60  nop     dword ptr [rax+rax+00h]
0x18001ef65  mov     [rbx+840h], rax
0x18001ef6c  test    rax, rax
0x18001ef6f  jnz     short loc_18001EFCD
0x18001ef71  cmp     qword ptr cs:xmmword_18004D860+8, rsi
0x18001ef78  jz      loc_18001F366
0x18001ef7e  mov     word ptr [rbp+0C60h+var_850], si
0x18001ef85  call    cs:__imp_GetLastError
0x18001ef8c  nop     dword ptr [rax+rax+00h]
0x18001ef91  mov     r8d, eax
0x18001ef94  lea     rdx, aIpcpLocalalloc_0; "IPCP: LocalAlloc for pLinkup Info =%d"
0x18001ef9b  lea     rcx, [rbp+0C60h+var_850]
0x18001efa2  call    FormatRRASErrorString
0x18001efa7  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001efae  lea     r8, [rbp+0C60h+var_850]
0x18001efb5  mov     rcx, cs:gRasIpcpEtwContext
0x18001efbc  mov     rax, cs:gRasIpcpTemplateFunc
0x18001efc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efc8  jmp     loc_18001F366
0x18001efcd  mov     edx, 9
0x18001efd2  lea     rcx, [rsp+0D60h+var_D0C]
0x18001efd7  lea     r8d, [rdx+77h]
0x18001efdb  movups  xmm0, xmmword ptr [rcx]
0x18001efde  movups  xmmword ptr [rax], xmm0
0x18001efe1  movups  xmm1, xmmword ptr [rcx+10h]
0x18001efe5  movups  xmmword ptr [rax+10h], xmm1
0x18001efe9  movups  xmm0, xmmword ptr [rcx+20h]
0x18001efed  movups  xmmword ptr [rax+20h], xmm0
0x18001eff1  movups  xmm1, xmmword ptr [rcx+30h]
0x18001eff5  movups  xmmword ptr [rax+30h], xmm1
0x18001eff9  movups  xmm0, xmmword ptr [rcx+40h]
0x18001effd  movups  xmmword ptr [rax+40h], xmm0
0x18001f001  movups  xmm1, xmmword ptr [rcx+50h]
0x18001f005  movups  xmmword ptr [rax+50h], xmm1
0x18001f009  movups  xmm0, xmmword ptr [rcx+60h]
0x18001f00d  movups  xmmword ptr [rax+60h], xmm0
0x18001f011  movups  xmm1, xmmword ptr [rcx+70h]
0x18001f015  add     rcx, r8
0x18001f018  movups  xmmword ptr [rax+70h], xmm1
0x18001f01c  add     rax, r8
0x18001f01f  sub     rdx, 1
0x18001f023  jnz     short loc_18001EFDB
0x18001f025  movups  xmm0, xmmword ptr [rcx]
0x18001f028  lea     r8, [rsp+0D60h+var_D28]
0x18001f02d  lea     rdx, [rsp+0D60h+var_D0C]
0x18001f032  movups  xmmword ptr [rax], xmm0
0x18001f035  movups  xmm1, xmmword ptr [rcx+10h]
0x18001f039  movups  xmmword ptr [rax+10h], xmm1
0x18001f03d  movups  xmm0, xmmword ptr [rcx+20h]
  ... truncated ...
```
