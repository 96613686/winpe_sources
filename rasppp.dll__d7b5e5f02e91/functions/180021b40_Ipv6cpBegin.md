# Ipv6cpBegin

- ea: `0x180021b40`
- end: `0x180022845`
- name: `Ipv6cpBegin`
- size: `3333`
- prototype: `DWORD __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800041d0`
- `0x1800186d4`
- `0x180018770`
- `0x180021b40`
- `0x180022de8`
- `0x1800231e4`
- `0x18002b0dc`
- `0x18002e090`
- `0x18002e0d0`
- `0x18002e12c`
- `0x180034010`

## import_xrefs

- `ntdll!RtlIpv6StringToAddressA` at `0x1800221cf`
- `ntdll!RtlIpv6StringToAddressA` at `0x180022406`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800225b0`
- `ntdll!RtlIpv6StringToAddressA` at `0x180022675`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800221cf`
- `ntdll!RtlIpv6StringToAddressA` at `0x180022406`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800225b0`
- `ntdll!RtlIpv6StringToAddressA` at `0x180022675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021bd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021ca5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021d43`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021ca5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021d43`

## string_xrefs

- `0x1800223d2`: `Ipv6CachedAddress`

## pseudocode

```c
DWORD __fastcall Ipv6cpBegin(_QWORD *a1, __int64 a2)
{
  char *v4; // rax
  char *v5; // rsi
  DWORD result; // eax
  DWORD LastError; // eax
  unsigned int UniqueInterfaceId; // ebx
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned __int8 *v11; // rdi
  __int64 v12; // rax
  int FlagInParamBuf; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rdx
  LONG v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdx
  bool v20; // zf
  const char *v21; // r8
  const wchar_t *v22; // rdx
  LONG v23; // eax
  __int64 v24; // rcx
  LONG v25; // eax
  __int64 v26; // rdx
  LONG v27; // eax
  __int64 v28; // r10
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  __int64 cchWideChar; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h]
  __int64 v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+48h] [rbp-B8h]
  unsigned int v35; // [rsp+50h] [rbp-B0h] BYREF
  PCSTR Terminator; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  in6_addr Addr; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v39[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h]
  int v41; // [rsp+A8h] [rbp-58h]
  CHAR v42[80]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR S[80]; // [rsp+100h] [rbp+0h] BYREF
  CHAR pszDest[80]; // [rsp+150h] [rbp+50h] BYREF
  int v45; // [rsp+1A0h] [rbp+A0h] BYREF
  char v46[2044]; // [rsp+1A4h] [rbp+A4h] BYREF
  char pszSrc[256]; // [rsp+9A0h] [rbp+8A0h] BYREF

  v41 = 0;
  v45 = 0;
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  memset_0(v46, 0, sizeof(v46));
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"IPv6CP: Begin");
  v4 = (char *)LocalAlloc(0x40u, 0x850u);
  v5 = v4;
  if ( !v4 )
    return GetLastError();
  memset_0(v4, 0, 0x850u);
  *(_DWORD *)v5 = *(_DWORD *)a2;
  *((_QWORD *)v5 + 1) = *(_QWORD *)(a2 + 8);
  *((_QWORD *)v5 + 2) = *(_QWORD *)(a2 + 1136);
  *((_QWORD *)v5 + 3) = *(_QWORD *)(a2 + 1144);
  *((_DWORD *)v5 + 8) = *(_DWORD *)(a2 + 1152);
  *(_OWORD *)(v5 + 2084) = *(_OWORD *)(a2 + 1176);
  *(_OWORD *)(v5 + 2100) = *(_OWORD *)(a2 + 1192);
  *((_OWORD *)v5 + 132) = *(_OWORD *)(a2 + 1204);
  *((_QWORD *)v5 + 6) = v5 + 40;
  *((_QWORD *)v5 + 5) = v5 + 40;
  *((_QWORD *)v5 + 8) = v5 + 56;
  *((_QWORD *)v5 + 7) = v5 + 56;
  if ( MultiByteToWideChar(0, 0, *(LPCCH *)(a2 + 1120), -1, (LPWSTR)v5 + 628, 256) )
  {
    *((_WORD *)v5 + 884) = 0;
    if ( !MultiByteToWideChar(0, 0, *(LPCCH *)(a2 + 1128), -1, (LPWSTR)v5 + 885, 16) )
    {
      LastError = GetLastError();
      UniqueInterfaceId = LastError;
      if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
        goto LABEL_40;
      v9 = *(_QWORD *)(a2 + 1128);
      goto LABEL_8;
    }
    *((_WORD *)v5 + 901) = 0;
    v10 = (*((__int64 (__fastcall **)(_QWORD, __int64, bool, char *))&xmmword_18004D3F0 + 1))(
            *((_QWORD *)v5 + 1),
            34525,
            *(_DWORD *)v5 == 0,
            v5 + 180);
    UniqueInterfaceId = v10;
    if ( v10 )
    {
      if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
        goto LABEL_40;
      LOWORD(v45) = 0;
      FormatRRASErrorString((wchar_t *)&v45, L"Ipv6CpBegin: RasAllocateRoute=%d", v10);
      goto LABEL_9;
    }
    *((_DWORD *)v5 + 42) |= 0x200u;
    if ( *(_DWORD *)v5 )
    {
      UniqueInterfaceId = RasPPPSrvrAcquireIpv6AddressForClient(
                            *((_QWORD *)v5 + 1),
                            (__int64)(v5 + 1256),
                            (__int64)(v5 + 1770),
                            (__int128 *)(v5 + 2084),
                            (__int64)(v5 + 104));
      if ( UniqueInterfaceId )
        goto LABEL_40;
      if ( *((_DWORD *)v5 + 8) == 2 )
      {
        v11 = (unsigned __int8 *)(v5 + 72);
        UniqueInterfaceId = Ipv6cpGetUniqueInterfaceId(
                              (BYTE *)v5 + 72,
                              (unsigned int (__fastcall *)(__int64, BYTE *))IsLocalInterfaceIdUnique,
                              (__int64)v5);
        if ( UniqueInterfaceId )
          goto LABEL_40;
      }
      else
      {
        UniqueInterfaceId = RasPPPQueryIpv6ServerAddress((__int64)v39, (__int128 *)(v5 + 2084));
        if ( UniqueInterfaceId )
          goto LABEL_40;
        v11 = (unsigned __int8 *)(v5 + 72);
        *((_QWORD *)v5 + 9) = *((_QWORD *)&v40 + 1);
      }
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
      {
        LOWORD(v45) = 0;
        LODWORD(cchWideChar) = (unsigned __int8)v5[75];
        LODWORD(lpWideCharStr) = (unsigned __int8)v5[74];
        FormatRRASErrorString(
          (wchar_t *)&v45,
          L"Ipv6CpBegin: LocalInterface Id is %x %x %x %x %x %x %x %x",
          *v11,
          (unsigned __int8)v5[73],
          lpWideCharStr,
          cchWideChar,
          (unsigned __int8)v5[76],
          (unsigned __int8)v5[77],
          (unsigned __int8)v5[78],
          (unsigned __int8)v5[79]);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          &v45);
      }
    }
    else
    {
      if ( *((_DWORD *)v5 + 8) == 2 )
      {
        UniqueInterfaceId = RasPPPSrvrAcquireIpv6AddressForClient(
                              *((_QWORD *)v5 + 1),
                              (__int64)(v5 + 1256),
                              (__int64)(v5 + 1770),
                              (__int128 *)(v5 + 2084),
                              (__int64)(v5 + 104));
        if ( UniqueInterfaceId )
          goto LABEL_40;
      }
      UniqueInterfaceId = Ipv6cpGenerateInterfaceId((BYTE *)v5 + 72);
      if ( UniqueInterfaceId )
        goto LABEL_40;
    }
    if ( *(_DWORD *)v5 && *((_DWORD *)v5 + 8) != 2 )
    {
LABEL_108:
      *((_DWORD *)v5 + 515) = 0;
      result = 0;
      *a1 = v5;
      return result;
    }
    v12 = *(_QWORD *)(a2 + 32);
    v35 = 0;
    Terminator = 0;
    if ( !v12 )
    {
LABEL_106:
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
      {
        LOWORD(v45) = 0;
        FormatRRASErrorString((wchar_t *)&v45, L"Ipv6cpBegin: PrioritizeRemote = %d", *((_DWORD *)v5 + 42) & 4);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          &v45);
      }
      goto LABEL_108;
    }
    if ( qword_18004D820 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
        gRasIpv6cpEtwContext,
        qword_18004D820,
        L"Dumping Bytes pszzParameters",
        512,
        v12);
    FlagInParamBuf = FindFlagInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6Remote", &v35);
    v14 = v35;
    if ( FlagInParamBuf && v35 )
      *((_DWORD *)v5 + 42) |= 4u;
    if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    {
      v15 = *(unsigned int *)(a2 + 16);
      LOWORD(v45) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v45,
        L"IPv6CP: devideType=%x UI parameters for ForceTunneling Ipv6=%d",
        v15,
        v14);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004D800 + 1),
        &v45);
    }
    *((_DWORD *)v5 + 39) = 0;
    if ( (unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6InterfaceMetric", v5 + 156) )
    {
      if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
        goto LABEL_48;
      LOWORD(v45) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v45,
        L"Parameter: %hs  Value: %d",
        "Ipv6InterfaceMetric",
        *((unsigned int *)v5 + 39));
      v16 = *((_QWORD *)&xmmword_18004D800 + 1);
    }
    else
    {
      if ( !(_QWORD)xmmword_18004D800 )
        goto LABEL_48;
      LOWORD(v45) = 0;
      FormatRRASErrorString((wchar_t *)&v45, L"Failed to get Parameter: %hs", "Ipv6InterfaceMetric");
      v16 = xmmword_18004D800;
    }
    ((void (__fastcall *)(__int64, __int64, int *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v16, &v45);
LABEL_48:
    if ( !(unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6AddrSrc", &v35) )
      goto LABEL_71;
    if ( v35 != 2 )
    {
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
      {
        v21 = "Ipv6AddrSrc";
        v22 = L"Parameter: %hs  Value: FALSE %d";
        goto LABEL_70;
      }
LABEL_71:
      if ( (*((_DWORD *)v5 + 42) & 0x100) == 0
        && (unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "Ipv6CachedAddress", pszDest, 0x41u) )
      {
        Addr = 0;
        v23 = RtlIpv6StringToAddressA(pszDest, &Terminator, &Addr);
        if ( v23 < 0 || *Terminator )
        {
          if ( *((_QWORD *)&xmmword_18004D800 + 1) )
          {
            LOWORD(v45) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v45,
              L"Error parsing parambuf Parameter: %hs  Error: %d",
              "Ipv6CachedAddress",
              (unsigned int)v23);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              *((_QWORD *)&xmmword_18004D800 + 1),
              &v45);
          }
        }
        else if ( *(_QWORD *)&Addr.u.Word[4] )
        {
          v20 = *((_QWORD *)&xmmword_18004D800 + 1) == 0;
          *((_QWORD *)v5 + 9) = *(_QWORD *)&Addr.u.Word[4];
          if ( !v20 )
          {
            LOWORD(v45) = 0;
            FormatRRASErrorString((wchar_t *)&v45, L"Parameter: %hs  Value: %hs", "Ipv6CachedAddress", pszDest);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              *((_QWORD *)&xmmword_18004D800 + 1),
              &v45);
            if ( *((_QWORD *)&xmmword_18004D800 + 1) )
            {
              LOWORD(v45) = 0;
              LODWORD(v34) = (unsigned __int8)v5[79];
              LODWORD(v33) = (unsigned __int8)v5[78];
              LODWORD(v32) = (unsigned __int8)v5[77];
              LODWORD(v31) = (unsigned __int8)v5[76];
              LODWORD(cchWideChar) = (unsigned __int8)v5[75];
              LODWORD(lpWideCharStr) = (unsigned __int8)v5[74];
              FormatRRASErrorString(
                (wchar_t *)&v45,
                L"Parsed Interface ID : %x %x %x %x %x %x %x %x",
                (unsigned __int8)v5[72],
                (unsigned __int8)v5[73],
                lpWideCharStr,
                cchWideChar,
                v31,
                v32,
                v33,
                v34);
              ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
                gRasIpv6cpEtwContext,
                *((_QWORD *)&xmmword_18004D800 + 1),
                &v45);
            }
          }
        }
      }
      v24 = *(_QWORD *)(a2 + 32);
      v37 = 1;
      FindLongInParamBuf(v24, "Ipv6NameSrc", &v37);
      if ( v37 != 2 )
        goto LABEL_98;
      if ( (unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "Ipv6Dns", v42, 0x41u) )
      {
        v25 = RtlIpv6StringToAddressA(v42, &Terminator, (struct in6_addr *)(v5 + 124));
        if ( v25 < 0 || *Terminator )
        {
          if ( !(_QWORD)xmmword_18004D800 )
            goto LABEL_90;
          LOWORD(v45) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v45,
            L"Error parsing parambuf Parameter: %hs  Error: %d",
            "Ipv6Dns",
            (unsigned int)v25);
          v26 = xmmword_18004D800;
        }
        else
        {
          if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
            goto LABEL_90;
          LOWORD(v45) = 0;
          FormatRRASErrorString((wchar_t *)&v45, L"Parameter: %hs  Value: %hs", "Ipv6Dns", v42);
          v26 = *((_QWORD *)&xmmword_18004D800 + 1);
        }
        ((void (__fastcall *)(__int64, __int64, int *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v26, &v45);
      }
LABEL_90:
      if ( !(unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "Ipv6Dns2", v42, 0x41u) )
        goto LABEL_98;
      v27 = RtlIpv6StringToAddressA(v42, &Terminator, (struct in6_addr *)(v5 + 140));
      if ( v27 < 0 || *Terminator )
      {
        if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
          goto LABEL_98;
        LOWORD(v45) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v45,
          L"Error parsing parambuf Parameter: %hs  Error: %d",
          "Ipv6Dns2",
          (unsigned int)v27);
      }
      else
      {
        if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
          goto LABEL_98;
        LOWORD(v45) = 0;
        FormatRRASErrorString((wchar_t *)&v45, L"Parameter: %hs  Value: %hs", "Ipv6Dns2", v42);
      }
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004D800 + 1),
        &v45);
LABEL_98:
      if ( (unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "IpDnsSuffix", pszSrc, 0x100u) )
      {
        StringCbCopyA(v5 + 1804, 0x100u, pszSrc);
        if ( *((_QWORD *)&xmmword_18004D800 + 1) )
        {
          LOWORD(v45) = 0;
          FormatRRASErrorString((wchar_t *)&v45, L"Parameter: %hs  Value: %hs", "IpDnsSuffix", v28);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            *((_QWORD *)&xmmword_18004D800 + 1),
            &v45);
        }
      }
      if ( (unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "IpDnsFlags", &v35) )
      {
        if ( (v35 & 1) != 0 )
          *((_DWORD *)v5 + 42) |= 8u;
        if ( (v35 & 6) != 0 )
          *((_DWORD *)v5 + 42) |= 0x10u;
      }
      goto LABEL_106;
    }
    if ( (_QWORD)xmmword_18004D800 )
    {
      LOWORD(v45) = 0;
      FormatRRASErrorString((wchar_t *)&v45, L"Parameter: %hs  Value: TRUE", "Ipv6AddrSrc");
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        xmmword_18004D800,
        &v45);
    }
    if ( (unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "Ipv6Addr", S, 0x41u) )
    {
      v17 = RtlIpv6StringToAddressA(S, &Terminator, (struct in6_addr *)v5 + 129);
      if ( v17 < 0 || *Terminator )
      {
        if ( !(_QWORD)xmmword_18004D800 )
          goto LABEL_63;
        LOWORD(v45) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v45,
          L"Error parsing parambuf Parameter: %hs  Error: d",
          "Ipv6Addr",
          (unsigned int)v17);
        v19 = xmmword_18004D800;
        goto LABEL_62;
      }
      if ( *((_QWORD *)v5 + 259) )
      {
        v18 = *((_QWORD *)&xmmword_18004D800 + 1);
        if ( *((_QWORD *)&xmmword_18004D800 + 1) )
        {
          LOWORD(v45) = 0;
          FormatRRASErrorString((wchar_t *)&v45, L"Parameter: %hs  Value: %hs", "Ipv6Addr", S);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            *((_QWORD *)&xmmword_18004D800 + 1),
            &v45);
          v18 = *((_QWORD *)&xmmword_18004D800 + 1);
        }
        *((_DWORD *)v5 + 42) |= 0x100u;
        *((_QWORD *)v5 + 9) = *((_QWORD *)v5 + 259);
        if ( v18 )
        {
          LOWORD(v45) = 0;
          LODWORD(v34) = (unsigned __int8)v5[79];
          LODWORD(v33) = (unsigned __int8)v5[78];
          LODWORD(v32) = (unsigned __int8)v5[77];
          LODWORD(v31) = (unsigned __int8)v5[76];
          LODWORD(cchWideChar) = (unsigned __int8)v5[75];
          LODWORD(lpWideCharStr) = (unsigned __int8)v5[74];
          FormatRRASErrorString(
            (wchar_t *)&v45,
            L"Parsed Interface ID : %x %x %x %x %x %x %x %x",
            (unsigned __int8)v5[72],
            (unsigned __int8)v5[73],
            lpWideCharStr,
            cchWideChar,
            v31,
            v32,
            v33,
            v34);
          v19 = *((_QWORD *)&xmmword_18004D800 + 1);
LABEL_62:
          ((void (__fastcall *)(__int64, __int64, int *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v19, &v45);
        }
      }
    }
LABEL_63:
    if ( (unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6PrefixLength", &v35) )
    {
      v20 = *((_QWORD *)&xmmword_18004D800 + 1) == 0;
      *((_DWORD *)v5 + 520) = v35;
      if ( !v20 )
      {
        v21 = "Ipv6PrefixLength";
        v22 = L"Parameter: %hs  Value: %d";
LABEL_70:
        LOWORD(v45) = 0;
        FormatRRASErrorString((wchar_t *)&v45, v22, v21);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          &v45);
        goto LABEL_71;
      }
    }
    else if ( (*((_DWORD *)v5 + 42) & 0x100) != 0 )
    {
      *((_DWORD *)v5 + 520) = 64;
    }
    goto LABEL_71;
  }
  LastError = GetLastError();
  UniqueInterfaceId = LastError;
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    v9 = *(_QWORD *)(a2 + 1120);
LABEL_8:
    LOWORD(v45) = 0;
    FormatRRASErrorString((wchar_t *)&v45, L"Ipv6CpBegin: MultiByteToWideChar(%hs) failed: %d", v9, LastError);
LABEL_9:
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v45);
  }
LABEL_40:
  if ( (*((_DWORD *)v5 + 42) & 0x200) != 0 )
  {
    ((void (__fastcall *)(_QWORD, __int64))xmmword_18004D440)(*((_QWORD *)v5 + 2), 34525);
    *((_DWORD *)v5 + 42) &= ~0x200u;
  }
  LocalFree(v5);
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    LOWORD(v45) = 0;
    FormatRRASErrorString((wchar_t *)&v45, L"Ipv6cpBegin: done %d", UniqueInterfaceId);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v45);
  }
  return UniqueInterfaceId;
}

```

## disassembly

```asm
0x180021b40  mov     [rsp-8+arg_10], rbx
0x180021b45  push    rbp
0x180021b46  push    rsi
0x180021b47  push    rdi
0x180021b48  push    r12
0x180021b4a  push    r13
0x180021b4c  push    r14
0x180021b4e  push    r15
0x180021b50  lea     rbp, [rsp-9B0h]
0x180021b58  sub     rsp, 0AB0h
0x180021b5f  mov     rax, cs:__security_cookie
0x180021b66  xor     rax, rsp
0x180021b69  mov     [rbp+9E0h+var_40], rax
0x180021b70  xorps   xmm0, xmm0
0x180021b73  mov     r14, rdx
0x180021b76  mov     r13, rcx
0x180021b79  xor     eax, eax
0x180021b7b  xor     edi, edi
0x180021b7d  mov     [rbp+9E0h+var_A38], eax
0x180021b80  xor     edx, edx; Val
0x180021b82  mov     [rbp+9E0h+var_940], edi
0x180021b88  lea     rcx, [rbp+9E0h+var_93C]; void *
0x180021b8f  mov     r8d, 7FCh; Size
0x180021b95  movups  [rsp+0AE0h+var_A68], xmm0
0x180021b9a  movups  [rbp+9E0h+var_A58], xmm0
0x180021b9e  movups  [rbp+9E0h+var_A48], xmm0
0x180021ba2  call    memset_0
0x180021ba7  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021bae  test    rdx, rdx
0x180021bb1  jz      short loc_180021BCD
0x180021bb3  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021bba  lea     r8, aIpv6cpBegin; "IPv6CP: Begin"
0x180021bc1  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bcd  mov     ebx, 850h
0x180021bd2  mov     ecx, 40h ; '@'; uFlags
0x180021bd7  mov     edx, ebx; uBytes
0x180021bd9  call    cs:__imp_LocalAlloc
0x180021be0  nop     dword ptr [rax+rax+00h]
0x180021be5  mov     rsi, rax
0x180021be8  test    rax, rax
0x180021beb  jnz     short loc_180021BFE
0x180021bed  call    cs:__imp_GetLastError
0x180021bf4  nop     dword ptr [rax+rax+00h]
0x180021bf9  jmp     loc_18002281A
0x180021bfe  mov     r8, rbx; Size
0x180021c01  xor     edx, edx; Val
0x180021c03  mov     rcx, rsi; void *
0x180021c06  call    memset_0
0x180021c0b  mov     eax, [r14]
0x180021c0e  lea     r15, [rsi+824h]
0x180021c15  mov     [rsi], eax
0x180021c17  lea     r12, [rsi+4E8h]
0x180021c1e  mov     rax, [r14+8]
0x180021c22  or      ebx, 0FFFFFFFFh
0x180021c25  mov     [rsi+8], rax
0x180021c29  mov     r9d, ebx; cbMultiByte
0x180021c2c  mov     rax, [r14+470h]
0x180021c33  xor     edx, edx; dwFlags
0x180021c35  mov     [rsi+10h], rax
0x180021c39  xor     ecx, ecx; CodePage
0x180021c3b  mov     rax, [r14+478h]
0x180021c42  mov     [rsi+18h], rax
0x180021c46  mov     eax, [r14+480h]
0x180021c4d  mov     [rsi+20h], eax
0x180021c50  lea     rax, [rsi+28h]
0x180021c54  movups  xmm0, xmmword ptr [r14+498h]
0x180021c5c  mov     dword ptr [rsp+0AE0h+cchWideChar], 100h; cchWideChar
0x180021c64  mov     [rsp+0AE0h+lpWideCharStr], r12; lpWideCharStr
0x180021c69  movdqu  xmmword ptr [r15], xmm0
0x180021c6e  movups  xmm0, xmmword ptr [r14+4A8h]
0x180021c76  movups  xmmword ptr [rsi+834h], xmm0
0x180021c7d  movups  xmm1, xmmword ptr [r14+4B4h]
0x180021c85  movups  xmmword ptr [rsi+840h], xmm1
0x180021c8c  mov     [rax+8], rax
0x180021c90  mov     [rax], rax
0x180021c93  lea     rax, [rsi+38h]
0x180021c97  mov     [rax+8], rax
0x180021c9b  mov     [rax], rax
0x180021c9e  mov     r8, [r14+460h]; lpMultiByteStr
0x180021ca5  call    cs:__imp_MultiByteToWideChar
0x180021cac  nop     dword ptr [rax+rax+00h]
0x180021cb1  test    eax, eax
0x180021cb3  jnz     short loc_180021D1A
0x180021cb5  call    cs:__imp_GetLastError
0x180021cbc  nop     dword ptr [rax+rax+00h]
0x180021cc1  cmp     qword ptr cs:xmmword_18004D800+8, rdi
0x180021cc8  mov     ebx, eax
0x180021cca  jz      loc_180022054
0x180021cd0  mov     r8, [r14+460h]
0x180021cd7  mov     r9d, eax
0x180021cda  mov     word ptr [rbp+9E0h+var_940], di
0x180021ce1  lea     rdx, aIpv6cpbeginMul; "Ipv6CpBegin: MultiByteToWideChar(%hs) f"...
0x180021ce8  lea     rcx, [rbp+9E0h+var_940]
0x180021cef  call    FormatRRASErrorString
0x180021cf4  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021cfb  lea     r8, [rbp+9E0h+var_940]
0x180021d02  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021d09  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d15  jmp     loc_180022054
0x180021d1a  mov     [rsi+6E8h], di
0x180021d21  mov     r9d, ebx; cbMultiByte
0x180021d24  mov     r8, [r14+468h]; lpMultiByteStr
0x180021d2b  lea     rdi, [rsi+6EAh]
0x180021d32  mov     dword ptr [rsp+0AE0h+cchWideChar], 10h; cchWideChar
0x180021d3a  xor     edx, edx; dwFlags
0x180021d3c  xor     ecx, ecx; CodePage
0x180021d3e  mov     [rsp+0AE0h+lpWideCharStr], rdi; lpWideCharStr
0x180021d43  call    cs:__imp_MultiByteToWideChar
0x180021d4a  nop     dword ptr [rax+rax+00h]
0x180021d4f  test    eax, eax
0x180021d51  jnz     short loc_180021D7C
0x180021d53  call    cs:__imp_GetLastError
0x180021d5a  nop     dword ptr [rax+rax+00h]
0x180021d5f  xor     edi, edi
0x180021d61  mov     ebx, eax
0x180021d63  cmp     qword ptr cs:xmmword_18004D800+8, rdi
0x180021d6a  jz      loc_180022054
0x180021d70  mov     r8, [r14+468h]
0x180021d77  jmp     loc_180021CD7
0x180021d7c  xor     eax, eax
0x180021d7e  lea     r9, [rsi+0B4h]
0x180021d85  mov     [rsi+70Ah], ax
0x180021d8c  xor     r8d, r8d
0x180021d8f  cmp     [rsi], eax
0x180021d91  mov     edx, 86DDh
0x180021d96  mov     rcx, [rsi+8]
0x180021d9a  mov     rax, qword ptr cs:xmmword_18004D3F0+8
0x180021da1  setz    r8b
0x180021da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021daa  mov     ebx, eax
0x180021dac  test    eax, eax
0x180021dae  jz      short loc_180021DE1
0x180021db0  xor     edi, edi
0x180021db2  cmp     qword ptr cs:xmmword_18004D800+8, rdi
0x180021db9  jz      loc_180022054
0x180021dbf  mov     r8d, eax
0x180021dc2  mov     word ptr [rbp+9E0h+var_940], di
0x180021dc9  lea     rdx, aIpv6cpbeginRas; "Ipv6CpBegin: RasAllocateRoute=%d"
0x180021dd0  lea     rcx, [rbp+9E0h+var_940]
0x180021dd7  call    FormatRRASErrorString
0x180021ddc  jmp     loc_180021CF4
0x180021de1  bts     dword ptr [rsi+0A8h], 9
0x180021de9  cmp     dword ptr [rsi], 0
0x180021dec  jz      loc_180022010
0x180021df2  mov     rcx, [rsi+8]
0x180021df6  lea     rax, [rsi+68h]
0x180021dfa  mov     r9, r15
0x180021dfd  mov     [rsp+0AE0h+lpWideCharStr], rax
0x180021e02  mov     r8, rdi
0x180021e05  mov     rdx, r12
0x180021e08  call    RasPPPSrvrAcquireIpv6AddressForClient
0x180021e0d  xor     edi, edi
0x180021e0f  mov     ebx, eax
0x180021e11  test    eax, eax
0x180021e13  jnz     loc_180022054
0x180021e19  cmp     dword ptr [rsi+20h], 2
0x180021e1d  jz      short loc_180021E43
0x180021e1f  mov     rdx, r15
0x180021e22  lea     rcx, [rsp+0AE0h+var_A68]
0x180021e27  call    RasPPPQueryIpv6ServerAddress
0x180021e2c  mov     ebx, eax
0x180021e2e  test    eax, eax
0x180021e30  jnz     loc_180022054
0x180021e36  mov     rax, qword ptr [rbp+9E0h+var_A48+8]
0x180021e3a  lea     rdi, [rsi+48h]
0x180021e3e  mov     [rdi], rax
0x180021e41  jmp     short loc_180021E63
0x180021e43  lea     rdi, [rsi+48h]
0x180021e47  mov     r8, rsi
0x180021e4a  mov     rcx, rdi; pbBuffer
0x180021e4d  lea     rdx, IsLocalInterfaceIdUnique
0x180021e54  call    Ipv6cpGetUniqueInterfaceId
0x180021e59  mov     ebx, eax
0x180021e5b  test    eax, eax
0x180021e5d  jnz     loc_180022052
0x180021e63  cmp     qword ptr cs:xmmword_18004D800+8, 0
0x180021e6b  jz      short loc_180021EE7
0x180021e6d  xor     eax, eax
0x180021e6f  mov     word ptr [rbp+9E0h+var_940], ax
0x180021e76  movzx   ecx, byte ptr [rsi+4Eh]
0x180021e7a  movzx   edx, byte ptr [rsi+4Dh]
0x180021e7e  movzx   eax, byte ptr [rsi+4Fh]
0x180021e82  movzx   r10d, byte ptr [rsi+4Ch]
0x180021e87  movzx   r11d, byte ptr [rsi+4Bh]
0x180021e8c  movzx   ebx, byte ptr [rsi+4Ah]
0x180021e90  movzx   r9d, byte ptr [rsi+49h]
0x180021e95  movzx   r8d, byte ptr [rdi]
0x180021e99  mov     dword ptr [rsp+0AE0h+var_A98], eax
0x180021e9d  mov     dword ptr [rsp+0AE0h+var_AA0], ecx
0x180021ea1  lea     rcx, [rbp+9E0h+var_940]
0x180021ea8  mov     dword ptr [rsp+0AE0h+var_AA8], edx
0x180021eac  lea     rdx, aIpv6cpbeginLoc; "Ipv6CpBegin: LocalInterface Id is %x %x"...
0x180021eb3  mov     dword ptr [rsp+0AE0h+var_AB0], r10d
0x180021eb8  mov     dword ptr [rsp+0AE0h+cchWideChar], r11d
0x180021ebd  mov     dword ptr [rsp+0AE0h+lpWideCharStr], ebx
0x180021ec1  call    FormatRRASErrorString
0x180021ec6  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021ecd  lea     r8, [rbp+9E0h+var_940]
0x180021ed4  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021edb  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ee7  xor     edi, edi
0x180021ee9  cmp     [rsi], edi
0x180021eeb  jz      short loc_180021EF7
0x180021eed  cmp     dword ptr [rsi+20h], 2
0x180021ef1  jnz     loc_18002280E
0x180021ef7  mov     rax, [r14+20h]
0x180021efb  mov     [rsp+0AE0h+var_A90], edi
0x180021eff  mov     [rsp+0AE0h+Terminator], rdi
0x180021f04  test    rax, rax
0x180021f07  jz      loc_1800227BF
0x180021f0d  mov     rdx, cs:qword_18004D820
0x180021f14  test    rdx, rdx
0x180021f17  jz      short loc_180021F3E
0x180021f19  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021f20  lea     r8, aDumpingBytesPs; "Dumping Bytes pszzParameters"
0x180021f27  mov     [rsp+0AE0h+lpWideCharStr], rax
0x180021f2c  mov     r9d, 200h
0x180021f32  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x180021f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f3e  mov     rcx, [r14+20h]
0x180021f42  lea     r8, [rsp+0AE0h+var_A90]
0x180021f47  lea     rdx, aIpv6remote; "Ipv6Remote"
0x180021f4e  call    FindFlagInParamBuf
0x180021f53  mov     r9d, [rsp+0AE0h+var_A90]
0x180021f58  test    eax, eax
0x180021f5a  jz      short loc_180021F68
0x180021f5c  test    r9d, r9d
0x180021f5f  jz      short loc_180021F68
0x180021f61  or      dword ptr [rsi+0A8h], 4
0x180021f68  cmp     qword ptr cs:xmmword_18004D800+8, rdi
0x180021f6f  jz      short loc_180021FB0
0x180021f71  mov     r8d, [r14+10h]
0x180021f75  lea     rdx, aIpv6cpDevidety; "IPv6CP: devideType=%x UI parameters for"...
0x180021f7c  lea     rcx, [rbp+9E0h+var_940]
0x180021f83  mov     word ptr [rbp+9E0h+var_940], di
0x180021f8a  call    FormatRRASErrorString
0x180021f8f  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021f96  lea     r8, [rbp+9E0h+var_940]
0x180021f9d  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021fa4  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb0  lea     rbx, [rsi+9Ch]
0x180021fb7  mov     [rbx], edi
0x180021fb9  lea     r15, aIpv6interfacem; "Ipv6InterfaceMetric"
0x180021fc0  mov     rcx, [r14+20h]
0x180021fc4  mov     r8, rbx
0x180021fc7  mov     rdx, r15
0x180021fca  call    FindLongInParamBuf
0x180021fcf  test    eax, eax
0x180021fd1  jz      loc_1800220DA
0x180021fd7  cmp     qword ptr cs:xmmword_18004D800+8, rdi
0x180021fde  jz      loc_180022121
0x180021fe4  mov     word ptr [rbp+9E0h+var_940], di
0x180021feb  lea     rdx, aParameterHsVal_1; "Parameter: %hs  Value: %d"
0x180021ff2  mov     r9d, [rbx]
0x180021ff5  lea     rcx, [rbp+9E0h+var_940]
0x180021ffc  mov     r8, r15
0x180021fff  call    FormatRRASErrorString
0x180022004  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x18002200b  jmp     loc_180022107
0x180022010  cmp     dword ptr [rsi+20h], 2
0x180022014  jnz     short loc_18002203B
0x180022016  mov     rcx, [rsi+8]
0x18002201a  lea     rax, [rsi+68h]
0x18002201e  mov     r9, r15
0x180022021  mov     [rsp+0AE0h+lpWideCharStr], rax
0x180022026  mov     r8, rdi
0x180022029  mov     rdx, r12
0x18002202c  call    RasPPPSrvrAcquireIpv6AddressForClient
0x180022031  xor     edi, edi
0x180022033  mov     ebx, eax
0x180022035  test    eax, eax
0x180022037  jnz     short loc_180022054
0x180022039  jmp     short loc_18002203D
0x18002203b  xor     edi, edi
0x18002203d  lea     rcx, [rsi+48h]; pbBuffer
0x180022041  call    Ipv6cpGenerateInterfaceId
0x180022046  mov     ebx, eax
0x180022048  test    eax, eax
0x18002204a  jz      loc_180021EE9
0x180022050  jmp     short loc_180022054
0x180022052  xor     edi, edi
0x180022054  test    dword ptr [rsi+0A8h], 200h
0x18002205e  jz      short loc_18002207D
0x180022060  mov     rcx, [rsi+10h]
0x180022064  mov     edx, 86DDh
0x180022069  mov     rax, qword ptr cs:xmmword_18004D440
0x180022070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022075  btr     dword ptr [rsi+0A8h], 9
0x18002207d  mov     rcx, rsi; hMem
0x180022080  call    cs:__imp_LocalFree
0x180022087  nop     dword ptr [rax+rax+00h]
0x18002208c  cmp     qword ptr cs:xmmword_18004D800+8, rdi
0x180022093  jz      short loc_1800220D3
0x180022095  mov     r8d, ebx
0x180022098  mov     word ptr [rbp+9E0h+var_940], di
0x18002209f  lea     rdx, aIpv6cpbeginDon; "Ipv6cpBegin: done %d"
  ... truncated ...
```
