# IpcpProjectionNotification

- ea: `0x18001df60`
- end: `0x18001ebbd`
- name: `IpcpProjectionNotification`
- size: `3165`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180017d70`
- `0x180017e0c`
- `0x18001b074`
- `0x18001df60`
- `0x18001ff50`
- `0x18002a138`
- `0x18002cb08`
- `0x18003078c`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e3b5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e3b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e41d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e5e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e684`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e41d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e5e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6a8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e246`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e246`
- `DNSAPI!DnsSetConfigDword` at `0x18001e51e`
- `DNSAPI!DnsSetConfigDword` at `0x18001e53c`
- `DNSAPI!DnsSetConfigDword` at `0x18001e57d`
- `DNSAPI!DnsSetConfigDword` at `0x18001e59b`
- `DNSAPI!DnsSetConfigDword` at `0x18001e51e`
- `DNSAPI!DnsSetConfigDword` at `0x18001e53c`
- `DNSAPI!DnsSetConfigDword` at `0x18001e57d`
- `DNSAPI!DnsSetConfigDword` at `0x18001e59b`
- `rtutils!LogEventW` at `0x18001eaa2`
- `rtutils!LogEventW` at `0x18001ead8`
- `rtutils!LogEventW` at `0x18001eaa2`
- `rtutils!LogEventW` at `0x18001ead8`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18001eb8c`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18001eb8c`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18001e1b8`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18001e1b8`

## string_xrefs

- `0x18001e2a8`: `IPCP: NsiGetCompartmentIdForRoutingDomain: failed Err: %d`
- `0x18001e44c`: `IPCP: LocalAlloc for pLinkup Info =%d`
- `0x18001e82a`: `IPCP:RasPortSetProtocolCompression(s=%d,%d r=%d,%d)`
- `0x18001e8b6`: `IPCP: RasPortSetProtocolCompression done(%d)`

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
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
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
      CompartmentIdForRoutingDomain = RasPPPGetNewSubInterfaceIndex(a1 + 2104);
      v2 = CompartmentIdForRoutingDomain;
      if ( CompartmentIdForRoutingDomain )
      {
        if ( !*((_QWORD *)&xmmword_18004C860 + 1) )
          goto LABEL_122;
        v14 = L"IPCP: RasPPPGetNewSubInterfaceIndex: failed Err: %d";
        goto LABEL_11;
      }
      v10 = v57;
      v55 = *v9;
    }
    v53[2] = *(_DWORD *)(a1 + 16);
    v53[1] = 0;
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      LOWORD(v63) = 0;
      FormatRRASErrorString(&v63, L"IPCP: RasActivateRoute(u=%x,a=%x,nf=%d)...", v53[0], v10, 0);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        &v63);
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      {
        LOWORD(v63) = 0;
        FormatRRASErrorString(&v63, L"IPCP: RasActivateRoute ICB# == %d", v54);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
          &v63);
      }
    }
    if ( v53[0] == 1 )
    {
      v15 = RasAllocInterfaceLuidIndex(*(_QWORD *)(a1 + 8), a1 + 704, v5, v10);
      v2 = v15;
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      {
        v16 = *(unsigned int *)(a1 + 704);
        LOWORD(v63) = 0;
        FormatRRASErrorString(
          &v63,
          L"IPCP: RasAllocateInterfaceLuidIndex returns %I64X as the LuidIndex %x as the return value",
          v16,
          v15);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
          &v63);
      }
    }
    v17 = -1;
    if ( v53[0] == 1 )
    {
      if ( *(_BYTE *)(a1 + 1812) && !MultiByteToWideChar(0, 0, (LPCCH)(a1 + 1812), -1, (LPWSTR)(a1 + 708), 256) )
      {
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        {
          LOWORD(v63) = 0;
          LastError = GetLastError();
          FormatRRASErrorString(&v63, L"IPCP:MultiByteToWideChar failed. Error %d", LastError);
          goto LABEL_12;
        }
        goto LABEL_122;
      }
    }
    else if ( !v53[0] )
    {
      LODWORD(v49) = 1;
      CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain(a1 + 2120, &v49, v5, v10);
      v2 = CompartmentIdForRoutingDomain;
      if ( CompartmentIdForRoutingDomain )
      {
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        {
          v14 = L"IPCP: NsiGetCompartmentIdForRoutingDomain: failed Err: %d";
LABEL_11:
          LOWORD(v63) = 0;
          FormatRRASErrorString(&v63, v14, CompartmentIdForRoutingDomain);
LABEL_12:
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004C860 + 1),
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
            ((void (__fastcall *)(_QWORD, __int64, __int64, __int64))xmmword_18004C450)(
              0,
              v4,
              (*(_DWORD *)(a1 + 1256) & 0xFFFFFF | 0x17000000LL) << 24,
              v10);
          }
          if ( *(_DWORD *)(a1 + 76) || *(_DWORD *)(a1 + 80) )
          {
            if ( *((_QWORD *)&xmmword_18004C860 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                *((_QWORD *)&xmmword_18004C860 + 1),
                L"IPCP: RasDeAllocateRoute...");
            ((void (__fastcall *)(_QWORD, __int64))xmmword_18004C440)(*(_QWORD *)(a1 + 2072), 2048);
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
      v20 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, int *))&xmmword_18004C440 + 1))(
              *(_QWORD *)(a1 + 8),
              2048,
              a1 + 184,
              &v52);
      v2 = v20;
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      {
        LOWORD(v63) = 0;
        FormatRRASErrorString(&v63, L"IPCP: RasActivateRoute done(%d)", v20);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
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
        v4 = *((_QWORD *)&xmmword_18004C860 + 1);
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004C860 + 1),
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
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        {
          LOWORD(v63) = 0;
          v23 = GetLastError();
          FormatRRASErrorString(&v63, L"IPCP: LocalAlloc for pLinkup Info =%d", v23);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004C860 + 1),
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
        v28 = *((_QWORD *)&xmmword_18004C860 + 1);
        if ( !*((_QWORD *)&xmmword_18004C860 + 1) )
          goto LABEL_59;
        v29 = L"DnsEnableDynamicRegistration";
      }
      else
      {
        DnsSetConfigDword(65552, v27, 0);
        v28 = *((_QWORD *)&xmmword_18004C860 + 1);
        if ( !*((_QWORD *)&xmmword_18004C860 + 1) )
          goto LABEL_59;
        v29 = L"DnsDisableDynamicRegistration";
      }
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v28, v29);
LABEL_59:
      v30 = *(_QWORD *)(a1 + 1248);
      if ( *(_DWORD *)(a1 + 72) )
      {
        DnsSetConfigDword(10, v30, 1);
        v4 = *((_QWORD *)&xmmword_18004C860 + 1);
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        {
          v31 = L"DnsEnableAdapterDomainNameRegistration";
LABEL_64:
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v4, v31);
        }
      }
      else
      {
        DnsSetConfigDword(10, v30, 0);
        v4 = *((_QWORD *)&xmmword_18004C860 + 1);
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
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
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        {
          LOWORD(v63) = 0;
          v34 = GetLastError();
          FormatRRASErrorString(&v63, L"IPCP: LocalAlloc 1 =%d", v34);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004C860 + 1),
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
        if ( !*((_QWORD *)&xmmword_18004C860 + 1) )
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
        FormatRRASErrorString(&v63, L"IPCP: LocalAlloc 2 =%d", v37);
LABEL_85:
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
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
        if ( !*((_QWORD *)&xmmword_18004C860 + 1) )
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
            if ( *((_QWORD *)&xmmword_18004C860 + 1) )
            {
              v40 = *(unsigned __int8 *)(a1 + 179);
              v41 = *(unsigned __int8 *)(a1 + 175);
              v42 = *(unsigned __int8 *)(a1 + 174);
              LOWORD(v63) = 0;
              LODWORD(cchWideChar) = v40;
              LODWORD(lpWideCharStr) = *(unsigned __int8 *)(a1 + 178);
              FormatRRASErrorString(
                &v63,
                L"IPCP:RasPortSetProtocolCompression(s=%d,%d r=%d,%d)",
                v42,
                v41,
                lpWideCharStr,
                cchWideChar);
              ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                *((_QWORD *)&xmmword_18004C860 + 1),
                &v63);
            }
            v43 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))&xmmword_18004C4B0 + 1))(
                    *(_QWORD *)(a1 + 8),
                    2048,
                    a1 + 172,
                    a1 + 176);
            v2 = v43;
            if ( *((_QWORD *)&xmmword_18004C860 + 1) )
            {
              LOWORD(v63) = 0;
              FormatRRASErrorString(&v63, L"IPCP: RasPortSetProtocolCompression done(%d)", v43);
              ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                *((_QWORD *)&xmmword_18004C860 + 1),
                &v63);
            }
            if ( !*(_DWORD *)a1 && *(_DWORD *)(a1 + 2088) != 2 )
              goto LABEL_122;
            v44 = *(_DWORD *)(a1 + 148);
            if ( v44 )
            {
              v4 = *((_QWORD *)&xmmword_18004C860 + 1);
              v49 = 0;
              if ( *((_QWORD *)&xmmword_18004C860 + 1) )
              {
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004C860 + 1),
                  L"IPCP: RasPPPActivateIpv4Address...");
                v44 = *(_DWORD *)(a1 + 148);
              }
              if ( *(_DWORD *)(a1 + 2088) == 2 && v44 )
                v45 = (*(_DWORD *)(a1 + 1256) & 0xFFFFFF | 0x17000000LL) << 24;
              else
                v45 = *v9;
              v49 = v45;
              if ( xmmword_18004C510 )
              {
                *(_OWORD *)plpwsSubStrings = *(_OWORD *)(a1 + 2120);
                v2 = xmmword_18004C510(plpwsSubStrings, v44, v53[0], &v49);
              }
              else
              {
                v2 = 4317;
              }
              if ( *((_QWORD *)&xmmword_18004C860 + 1) )
              {
                LOWORD(v63) = 0;
                FormatRRASErrorString(&v63, L"IPCP: RasPPPActivateIpv4Address done(%d)", v2);
                ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004C860 + 1),
                  &v63);
              }
              if ( *(_DWORD *)(a1 + 2088) != 2 )
                goto LABEL_122;
              if ( *((_QWORD *)&xmmword_18004C860 + 1) )
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004C860 + 1),
                  L"IPCP: RasPPPActivateDoDSpecificRoute...");
              RasPPPActivateDoDSpecificRoute(*(unsigned int *)(a1 + 148), *(unsigned int *)(a1 + 144), &v49, 0);
              v4 = *((_QWORD *)&xmmword_18004C860 + 1);
              if ( *((_QWORD *)&xmmword_18004C860 + 1) )
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  *((_QWORD *)&xmmword_18004C860 + 1),
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
          if ( !*((_QWORD *)&xmmword_18004C860 + 1) )
            goto LABEL_86;
          LOWORD(v63) = 0;
          FormatRRASErrorString(&v63, L"IPCP: RtlQueueWorkItem=%d", v39);
          goto LABEL_85;
        }
        LOWORD(v63) = 0;
        FormatRRASErrorString(&v63, L"IPCP: DhcpInform: DNS Suffix %hs", a1 + 1812);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
          &v63);
      }
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
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
0x18001df60  push    rbp
0x18001df62  push    rbx
0x18001df63  push    rsi
0x18001df64  push    rdi
0x18001df65  push    r12
0x18001df67  push    r13
0x18001df69  push    r14
0x18001df6b  push    r15
0x18001df6d  lea     rbp, [rsp-0C28h]
0x18001df75  sub     rsp, 0D28h
0x18001df7c  mov     rax, cs:__security_cookie
0x18001df83  xor     rax, rsp
0x18001df86  mov     [rbp+0C60h+var_50], rax
0x18001df8d  xor     esi, esi
0x18001df8f  mov     rbx, rcx
0x18001df92  lea     rcx, [rbp+0C60h+var_84C]; void *
0x18001df99  mov     [rsp+0D60h+var_D28], esi
0x18001df9d  xor     edx, edx; Val
0x18001df9f  mov     [rbp+0C60h+var_850], esi
0x18001dfa5  mov     r8d, 7FCh; Size
0x18001dfab  mov     edi, esi
0x18001dfad  call    memset_0
0x18001dfb2  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001dfb9  test    rdx, rdx
0x18001dfbc  jz      short loc_18001DFD8
0x18001dfbe  mov     rcx, cs:gRasIpcpEtwContext
0x18001dfc5  lea     r8, aIpcpIpcpprojec; "IPCP: IpcpProjectionNotification"
0x18001dfcc  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dfd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfd8  cmp     [rbx+1Ch], esi
0x18001dfdb  jz      loc_18001EB98
0x18001dfe1  xor     edx, edx; Val
0x18001dfe3  lea     rcx, [rsp+0D60h+var_D10]; void *
0x18001dfe8  mov     r8d, 4B8h; Size
0x18001dfee  mov     r14d, esi
0x18001dff1  call    memset_0
0x18001dff6  cmp     dword ptr [rbx+828h], 2
0x18001dffd  mov     [rsp+0D60h+var_D10], 4B0h
0x18001e005  jnz     short loc_18001E00E
0x18001e007  mov     ecx, 2
0x18001e00c  jmp     short loc_18001E015
0x18001e00e  cmp     [rbx], esi
0x18001e010  mov     ecx, esi
0x18001e012  setz    cl
0x18001e015  mov     eax, [rbx+820h]
0x18001e01b  lea     r12, [rbx+838h]
0x18001e022  mov     r9d, [rbx+90h]
0x18001e029  mov     r13d, 1
0x18001e02f  mov     [r12], esi
0x18001e033  mov     [rsp+0D60h+var_D00], eax
0x18001e037  mov     eax, [rbx+94h]
0x18001e03d  mov     [rsp+0D60h+var_D0C], ecx
0x18001e041  mov     [rbp+0C60h+var_AC0], 0FFFFFFFFh
0x18001e04b  mov     [rbp+0C60h+var_AC4], r9d
0x18001e052  mov     [rbp+0C60h+var_ABC], eax
0x18001e058  mov     [rbp+0C60h+var_CDC], r13d
0x18001e05c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001e063  movups  xmm1, xmmword ptr [rbx+864h]
0x18001e06a  movdqu  [rbp+0C60h+var_86C], xmm0
0x18001e072  movups  xmm0, xmmword ptr [rbx+858h]
0x18001e079  movups  xmmword ptr [rbp+0C60h+var_AAC], xmm0
0x18001e080  movups  xmmword ptr [rbp+0C60h+var_AAC+0Ch], xmm1
0x18001e087  test    ecx, ecx
0x18001e089  jnz     short loc_18001E0FA
0x18001e08b  mov     rcx, r12
0x18001e08e  call    RasPPPGetNewSubInterfaceIndex
0x18001e093  mov     edi, eax
0x18001e095  test    eax, eax
0x18001e097  jz      short loc_18001E0E9
0x18001e099  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e0a0  jz      loc_18001EAE4
0x18001e0a6  lea     rdx, aIpcpRaspppgetn; "IPCP: RasPPPGetNewSubInterfaceIndex: fa"...
0x18001e0ad  mov     word ptr [rbp+0C60h+var_850], si
0x18001e0b4  mov     r8d, eax
0x18001e0b7  lea     rcx, [rbp+0C60h+var_850]
0x18001e0be  call    FormatRRASErrorString
0x18001e0c3  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e0ca  lea     r8, [rbp+0C60h+var_850]
0x18001e0d1  mov     rcx, cs:gRasIpcpEtwContext
0x18001e0d8  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0e4  jmp     loc_18001EAE4
0x18001e0e9  mov     eax, [r12]
0x18001e0ed  mov     r9d, [rbp+0C60h+var_AC4]
0x18001e0f4  mov     [rsp+0D60h+var_CFC], eax
0x18001e0f8  jmp     short loc_18001E0FE
0x18001e0fa  mov     [rsp+0D60h+var_CFC], esi
0x18001e0fe  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e105  mov     eax, [rbx+10h]
0x18001e108  mov     [rsp+0D60h+var_D04], eax
0x18001e10c  mov     [rsp+0D60h+var_D08], esi
0x18001e110  jz      loc_18001E1A3
0x18001e116  mov     r8d, [rsp+0D60h+var_D0C]
0x18001e11b  lea     rdx, aIpcpRasactivat_1; "IPCP: RasActivateRoute(u=%x,a=%x,nf=%d)"...
0x18001e122  lea     rcx, [rbp+0C60h+var_850]
0x18001e129  mov     word ptr [rbp+0C60h+var_850], si
0x18001e130  mov     dword ptr [rsp+0D60h+lpWideCharStr], esi
0x18001e134  call    FormatRRASErrorString
0x18001e139  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e140  lea     r8, [rbp+0C60h+var_850]
0x18001e147  mov     rcx, cs:gRasIpcpEtwContext
0x18001e14e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e15a  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e161  jz      short loc_18001E1A3
0x18001e163  mov     r8d, [rsp+0D60h+var_D00]
0x18001e168  lea     rdx, aIpcpRasactivat; "IPCP: RasActivateRoute ICB# == %d"
0x18001e16f  lea     rcx, [rbp+0C60h+var_850]
0x18001e176  mov     word ptr [rbp+0C60h+var_850], si
0x18001e17d  call    FormatRRASErrorString
0x18001e182  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e189  lea     r8, [rbp+0C60h+var_850]
0x18001e190  mov     rcx, cs:gRasIpcpEtwContext
0x18001e197  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a3  cmp     [rsp+0D60h+var_D0C], r13d
0x18001e1a8  jnz     short loc_18001E20E
0x18001e1aa  mov     rcx, [rbx+8]
0x18001e1ae  lea     rsi, [rbx+2C0h]
0x18001e1b5  mov     rdx, rsi
0x18001e1b8  call    cs:__imp_RasAllocInterfaceLuidIndex
0x18001e1be  xor     ecx, ecx
0x18001e1c0  mov     edi, eax
0x18001e1c2  cmp     qword ptr cs:xmmword_18004C860+8, rcx
0x18001e1c9  jz      short loc_18001E20C
0x18001e1cb  mov     r8d, [rsi]
0x18001e1ce  lea     rdx, aIpcpRasallocat_0; "IPCP: RasAllocateInterfaceLuidIndex ret"...
0x18001e1d5  mov     word ptr [rbp+0C60h+var_850], cx
0x18001e1dc  mov     r9d, eax
0x18001e1df  lea     rcx, [rbp+0C60h+var_850]
0x18001e1e6  call    FormatRRASErrorString
0x18001e1eb  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e1f2  lea     r8, [rbp+0C60h+var_850]
0x18001e1f9  mov     rcx, cs:gRasIpcpEtwContext
0x18001e200  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e20c  xor     esi, esi
0x18001e20e  mov     eax, [rsp+0D60h+var_D0C]
0x18001e212  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001e216  cmp     eax, r13d
0x18001e219  jnz     short loc_18001E276
0x18001e21b  lea     r8, [rbx+714h]; lpMultiByteStr
0x18001e222  cmp     [r8], sil
0x18001e225  jz      loc_18001E2CA
0x18001e22b  lea     rax, [rbx+2C4h]
0x18001e232  mov     dword ptr [rsp+0D60h+cchWideChar], 100h; cchWideChar
0x18001e23a  mov     r9d, r15d; cbMultiByte
0x18001e23d  mov     [rsp+0D60h+lpWideCharStr], rax; lpWideCharStr
0x18001e242  xor     edx, edx; dwFlags
0x18001e244  xor     ecx, ecx; CodePage
0x18001e246  call    cs:__imp_MultiByteToWideChar
0x18001e24c  test    eax, eax
0x18001e24e  jnz     short loc_18001E2CA
0x18001e250  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e257  jz      loc_18001EAE4
0x18001e25d  mov     word ptr [rbp+0C60h+var_850], si
0x18001e264  call    cs:__imp_GetLastError
0x18001e26a  lea     rdx, aIpcpMultibytet; "IPCP:MultiByteToWideChar failed. Error "...
0x18001e271  jmp     loc_18001E0B4
0x18001e276  test    eax, eax
0x18001e278  jnz     short loc_18001E2CA
0x18001e27a  lea     rsi, [rbx+848h]
0x18001e281  mov     dword ptr [rsp+0D60h+var_D30], r13d
0x18001e286  mov     rcx, rsi
0x18001e289  lea     rdx, [rsp+0D60h+var_D30]
0x18001e28e  call    NsiGetCompartmentIdForRoutingDomain
0x18001e293  mov     edi, eax
0x18001e295  test    eax, eax
0x18001e297  jz      short loc_18001E2B4
0x18001e299  xor     esi, esi
0x18001e29b  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e2a2  jz      loc_18001EAE4
0x18001e2a8  lea     rdx, aIpcpNsigetcomp; "IPCP: NsiGetCompartmentIdForRoutingDoma"...
0x18001e2af  jmp     loc_18001E0AD
0x18001e2b4  movups  xmm0, xmmword ptr [rsi]
0x18001e2b7  mov     eax, dword ptr [rsp+0D60h+var_D30]
0x18001e2bb  xor     esi, esi
0x18001e2bd  mov     [rbp+0C60h+var_CDC], eax
0x18001e2c0  movdqu  [rbp+0C60h+var_86C], xmm0
0x18001e2c8  jmp     short loc_18001E2D2
0x18001e2ca  test    edi, edi
0x18001e2cc  jnz     loc_18001EAE4
0x18001e2d2  cmp     [rsp+0D60h+var_D0C], r13d
0x18001e2d7  mov     eax, [rbx+2C0h]
0x18001e2dd  cmovz   r14d, r13d
0x18001e2e1  mov     [rbx+4E8h], eax
0x18001e2e7  lea     r13, [rbx+4F0h]
0x18001e2ee  mov     [rbx+4D4h], esi
0x18001e2f4  mov     dword ptr [rsp+0D60h+var_D30], r14d
0x18001e2f9  cmp     [r13+0], si
0x18001e2fe  jz      short loc_18001E316
0x18001e300  mov     r8, r13; pszSrc
0x18001e303  lea     rcx, [rbp+0C60h+pszDest]; pszDest
0x18001e30a  mov     edx, 111h; cchDest
0x18001e30f  call    StringCchCopyW
0x18001e314  jmp     short loc_18001E31D
0x18001e316  mov     [rbp+0C60h+pszDest], si
0x18001e31d  mov     rcx, [rbx+8]
0x18001e321  lea     r8, [rbx+0B8h]
0x18001e328  mov     rax, qword ptr cs:xmmword_18004C440+8
0x18001e32f  lea     r9, [rsp+0D60h+var_D10]
0x18001e334  mov     edx, 800h
0x18001e339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e33e  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e345  mov     edi, eax
0x18001e347  jz      short loc_18001E387
0x18001e349  mov     r8d, eax
0x18001e34c  mov     word ptr [rbp+0C60h+var_850], si
0x18001e353  lea     rdx, aIpcpRasactivat_0; "IPCP: RasActivateRoute done(%d)"
0x18001e35a  lea     rcx, [rbp+0C60h+var_850]
0x18001e361  call    FormatRRASErrorString
0x18001e366  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e36d  lea     r8, [rbp+0C60h+var_850]
0x18001e374  mov     rcx, cs:gRasIpcpEtwContext
0x18001e37b  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e387  test    edi, edi
0x18001e389  jnz     loc_18001EADE
0x18001e38f  cmp     [rsp+0D60h+var_D0C], 2
0x18001e394  mov     dword ptr [rbx+4Ch], 1
0x18001e39b  jnz     short loc_18001E3A9
0x18001e39d  mov     eax, [rbx+2C0h]
0x18001e3a3  mov     [rbx+4E8h], eax
0x18001e3a9  mov     edx, 5Ch ; '\'; Ch
0x18001e3ae  lea     rcx, [rbx+1C0h]; Str
0x18001e3b5  call    cs:__imp_wcschr
0x18001e3bb  mov     [rbx+4E0h], rax
0x18001e3c2  test    rax, rax
0x18001e3c5  jnz     short loc_18001E3F7
0x18001e3c7  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e3ce  test    rdx, rdx
0x18001e3d1  jz      short loc_18001E3ED
0x18001e3d3  mov     rcx, cs:gRasIpcpEtwContext
0x18001e3da  lea     r8, aIpcpNoDevice; "IPCP: No device?"
0x18001e3e1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3ed  mov     edi, 57h ; 'W'
0x18001e3f2  jmp     loc_18001EADE
0x18001e3f7  add     rax, 2
0x18001e3fb  mov     [rbx+4E0h], rax
0x18001e402  cmp     [rbx], esi
0x18001e404  jz      short loc_18001E413
0x18001e406  cmp     dword ptr [rbx+828h], 2
0x18001e40d  jnz     loc_18001E7E2
0x18001e413  mov     edx, 4B0h; uBytes
0x18001e418  mov     ecx, 40h ; '@'; uFlags
0x18001e41d  call    cs:__imp_LocalAlloc
0x18001e423  mov     [rbx+840h], rax
0x18001e42a  test    rax, rax
0x18001e42d  jnz     short loc_18001E485
0x18001e42f  cmp     qword ptr cs:xmmword_18004C860+8, rsi
0x18001e436  jz      loc_18001E7E2
0x18001e43c  mov     word ptr [rbp+0C60h+var_850], si
0x18001e443  call    cs:__imp_GetLastError
0x18001e449  mov     r8d, eax
0x18001e44c  lea     rdx, aIpcpLocalalloc_0; "IPCP: LocalAlloc for pLinkup Info =%d"
0x18001e453  lea     rcx, [rbp+0C60h+var_850]
0x18001e45a  call    FormatRRASErrorString
0x18001e45f  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001e466  lea     r8, [rbp+0C60h+var_850]
0x18001e46d  mov     rcx, cs:gRasIpcpEtwContext
0x18001e474  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e480  jmp     loc_18001E7E2
0x18001e485  mov     edx, 9
0x18001e48a  lea     rcx, [rsp+0D60h+var_D0C]
0x18001e48f  lea     r8d, [rdx+77h]
0x18001e493  movups  xmm0, xmmword ptr [rcx]
0x18001e496  movups  xmmword ptr [rax], xmm0
0x18001e499  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e49d  movups  xmmword ptr [rax+10h], xmm1
0x18001e4a1  movups  xmm0, xmmword ptr [rcx+20h]
0x18001e4a5  movups  xmmword ptr [rax+20h], xmm0
0x18001e4a9  movups  xmm1, xmmword ptr [rcx+30h]
0x18001e4ad  movups  xmmword ptr [rax+30h], xmm1
0x18001e4b1  movups  xmm0, xmmword ptr [rcx+40h]
0x18001e4b5  movups  xmmword ptr [rax+40h], xmm0
0x18001e4b9  movups  xmm1, xmmword ptr [rcx+50h]
0x18001e4bd  movups  xmmword ptr [rax+50h], xmm1
0x18001e4c1  movups  xmm0, xmmword ptr [rcx+60h]
0x18001e4c5  movups  xmmword ptr [rax+60h], xmm0
0x18001e4c9  movups  xmm1, xmmword ptr [rcx+70h]
0x18001e4cd  add     rcx, r8
0x18001e4d0  movups  xmmword ptr [rax+70h], xmm1
0x18001e4d4  add     rax, r8
0x18001e4d7  sub     rdx, 1
0x18001e4db  jnz     short loc_18001E493
0x18001e4dd  movups  xmm0, xmmword ptr [rcx]
0x18001e4e0  lea     r8, [rsp+0D60h+var_D28]
0x18001e4e5  lea     rdx, [rsp+0D60h+var_D0C]
0x18001e4ea  movups  xmmword ptr [rax], xmm0
0x18001e4ed  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e4f1  movups  xmmword ptr [rax+10h], xmm1
0x18001e4f5  movups  xmm0, xmmword ptr [rcx+20h]
0x18001e4f9  mov     rcx, rbx
0x18001e4fc  movups  xmmword ptr [rax+20h], xmm0
0x18001e500  call    ApplyIpcpSettings
0x18001e505  mov     edi, eax
0x18001e507  mov     rdx, [rbx+4E0h]
0x18001e50e  mov     ecx, 10010h
  ... truncated ...
```
