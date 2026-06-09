# Ipv6cpBegin

- ea: `0x180020ee0`
- end: `0x180021ba2`
- name: `Ipv6cpBegin`
- size: `3266`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180004134`
- `0x180017e6c`
- `0x180017f08`
- `0x180020ee0`
- `0x180022130`
- `0x180022504`
- `0x18002a138`
- `0x18002cf18`
- `0x18002cf58`
- `0x18002cfb4`
- `0x180033010`

## import_xrefs

- `ntdll!RtlIpv6StringToAddressA` at `0x180021545`
- `ntdll!RtlIpv6StringToAddressA` at `0x180021776`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002191a`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800219d9`
- `ntdll!RtlIpv6StringToAddressA` at `0x180021545`
- `ntdll!RtlIpv6StringToAddressA` at `0x180021776`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002191a`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800219d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800213fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800213fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020f79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210d5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021039`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800210cb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021039`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800210cb`

## string_xrefs

- `0x180021742`: `Ipv6CachedAddress`

## pseudocode

```c
DWORD __fastcall Ipv6cpBegin(_QWORD *a1, __int64 a2)
{
  char *v4; // rax
  char *v5; // rsi
  DWORD result; // eax
  DWORD LastError; // eax
  DWORD UniqueInterfaceId; // ebx
  __int64 v9; // r8
  DWORD v10; // eax
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
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
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
      if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
        goto LABEL_40;
      v9 = *(_QWORD *)(a2 + 1128);
      goto LABEL_8;
    }
    *((_WORD *)v5 + 901) = 0;
    v10 = (*((__int64 (__fastcall **)(_QWORD, __int64, bool, char *))&xmmword_18004C3F0 + 1))(
            *((_QWORD *)v5 + 1),
            34525,
            *(_DWORD *)v5 == 0,
            v5 + 180);
    UniqueInterfaceId = v10;
    if ( v10 )
    {
      if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
        goto LABEL_40;
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v45, L"Ipv6CpBegin: RasAllocateRoute=%d", v10);
      goto LABEL_9;
    }
    *((_DWORD *)v5 + 42) |= 0x200u;
    if ( *(_DWORD *)v5 )
    {
      UniqueInterfaceId = RasPPPSrvrAcquireIpv6AddressForClient(
                            *((_QWORD *)v5 + 1),
                            (int)v5 + 1256,
                            (int)v5 + 1770,
                            (int)v5 + 2084,
                            (__int64)(v5 + 104));
      if ( UniqueInterfaceId )
        goto LABEL_40;
      if ( *((_DWORD *)v5 + 8) == 2 )
      {
        v11 = (unsigned __int8 *)(v5 + 72);
        UniqueInterfaceId = Ipv6cpGetUniqueInterfaceId((BYTE *)v5 + 72);
        if ( UniqueInterfaceId )
          goto LABEL_40;
      }
      else
      {
        UniqueInterfaceId = RasPPPQueryIpv6ServerAddress(v39, v5 + 2084);
        if ( UniqueInterfaceId )
          goto LABEL_40;
        v11 = (unsigned __int8 *)(v5 + 72);
        *((_QWORD *)v5 + 9) = *((_QWORD *)&v40 + 1);
      }
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
      {
        LOWORD(v45) = 0;
        LODWORD(cchWideChar) = (unsigned __int8)v5[75];
        LODWORD(lpWideCharStr) = (unsigned __int8)v5[74];
        FormatRRASErrorString(
          &v45,
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
          *((_QWORD *)&xmmword_18004C800 + 1),
          &v45);
      }
    }
    else
    {
      if ( *((_DWORD *)v5 + 8) == 2 )
      {
        UniqueInterfaceId = RasPPPSrvrAcquireIpv6AddressForClient(
                              *((_QWORD *)v5 + 1),
                              (int)v5 + 1256,
                              (int)v5 + 1770,
                              (int)v5 + 2084,
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
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
      {
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, L"Ipv6cpBegin: PrioritizeRemote = %d", *((_DWORD *)v5 + 42) & 4);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
          &v45);
      }
      goto LABEL_108;
    }
    if ( qword_18004C820 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
        gRasIpv6cpEtwContext,
        qword_18004C820,
        L"Dumping Bytes pszzParameters",
        512,
        v12);
    FlagInParamBuf = FindFlagInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6Remote", &v35);
    v14 = v35;
    if ( FlagInParamBuf && v35 )
      *((_DWORD *)v5 + 42) |= 4u;
    if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    {
      v15 = *(unsigned int *)(a2 + 16);
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v45, L"IPv6CP: devideType=%x UI parameters for ForceTunneling Ipv6=%d", v15, v14);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004C800 + 1),
        &v45);
    }
    *((_DWORD *)v5 + 39) = 0;
    if ( (unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6InterfaceMetric", v5 + 156) )
    {
      if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
        goto LABEL_48;
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v45, L"Parameter: %hs  Value: %d", "Ipv6InterfaceMetric", *((unsigned int *)v5 + 39));
      v16 = *((_QWORD *)&xmmword_18004C800 + 1);
    }
    else
    {
      if ( !(_QWORD)xmmword_18004C800 )
        goto LABEL_48;
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v45, L"Failed to get Parameter: %hs", "Ipv6InterfaceMetric");
      v16 = xmmword_18004C800;
    }
    ((void (__fastcall *)(__int64, __int64, int *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v16, &v45);
LABEL_48:
    if ( !(unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6AddrSrc", &v35) )
      goto LABEL_71;
    if ( v35 != 2 )
    {
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
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
          if ( *((_QWORD *)&xmmword_18004C800 + 1) )
          {
            LOWORD(v45) = 0;
            FormatRRASErrorString(
              &v45,
              L"Error parsing parambuf Parameter: %hs  Error: %d",
              "Ipv6CachedAddress",
              (unsigned int)v23);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              *((_QWORD *)&xmmword_18004C800 + 1),
              &v45);
          }
        }
        else if ( *(_QWORD *)&Addr.u.Word[4] )
        {
          v20 = *((_QWORD *)&xmmword_18004C800 + 1) == 0;
          *((_QWORD *)v5 + 9) = *(_QWORD *)&Addr.u.Word[4];
          if ( !v20 )
          {
            LOWORD(v45) = 0;
            FormatRRASErrorString(&v45, L"Parameter: %hs  Value: %hs", "Ipv6CachedAddress", pszDest);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              *((_QWORD *)&xmmword_18004C800 + 1),
              &v45);
            if ( *((_QWORD *)&xmmword_18004C800 + 1) )
            {
              LOWORD(v45) = 0;
              LODWORD(v34) = (unsigned __int8)v5[79];
              LODWORD(v33) = (unsigned __int8)v5[78];
              LODWORD(v32) = (unsigned __int8)v5[77];
              LODWORD(v31) = (unsigned __int8)v5[76];
              LODWORD(cchWideChar) = (unsigned __int8)v5[75];
              LODWORD(lpWideCharStr) = (unsigned __int8)v5[74];
              FormatRRASErrorString(
                &v45,
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
                *((_QWORD *)&xmmword_18004C800 + 1),
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
          if ( !(_QWORD)xmmword_18004C800 )
            goto LABEL_90;
          LOWORD(v45) = 0;
          FormatRRASErrorString(&v45, L"Error parsing parambuf Parameter: %hs  Error: %d", "Ipv6Dns", (unsigned int)v25);
          v26 = xmmword_18004C800;
        }
        else
        {
          if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
            goto LABEL_90;
          LOWORD(v45) = 0;
          FormatRRASErrorString(&v45, L"Parameter: %hs  Value: %hs", "Ipv6Dns", v42);
          v26 = *((_QWORD *)&xmmword_18004C800 + 1);
        }
        ((void (__fastcall *)(__int64, __int64, int *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v26, &v45);
      }
LABEL_90:
      if ( !(unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "Ipv6Dns2", v42, 0x41u) )
        goto LABEL_98;
      v27 = RtlIpv6StringToAddressA(v42, &Terminator, (struct in6_addr *)(v5 + 140));
      if ( v27 < 0 || *Terminator )
      {
        if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
          goto LABEL_98;
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, L"Error parsing parambuf Parameter: %hs  Error: %d", "Ipv6Dns2", (unsigned int)v27);
      }
      else
      {
        if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
          goto LABEL_98;
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, L"Parameter: %hs  Value: %hs", "Ipv6Dns2", v42);
      }
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004C800 + 1),
        &v45);
LABEL_98:
      if ( (unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "IpDnsSuffix", pszSrc, 0x100u) )
      {
        StringCbCopyA(v5 + 1804, 0x100u, pszSrc);
        if ( *((_QWORD *)&xmmword_18004C800 + 1) )
        {
          LOWORD(v45) = 0;
          FormatRRASErrorString(&v45, L"Parameter: %hs  Value: %hs", "IpDnsSuffix", v28);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            *((_QWORD *)&xmmword_18004C800 + 1),
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
    if ( (_QWORD)xmmword_18004C800 )
    {
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v45, L"Parameter: %hs  Value: TRUE", "Ipv6AddrSrc");
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        xmmword_18004C800,
        &v45);
    }
    if ( (unsigned int)FindStringInParamBuf(*(char **)(a2 + 32), "Ipv6Addr", S, 0x41u) )
    {
      v17 = RtlIpv6StringToAddressA(S, &Terminator, (struct in6_addr *)v5 + 129);
      if ( v17 < 0 || *Terminator )
      {
        if ( !(_QWORD)xmmword_18004C800 )
          goto LABEL_63;
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, L"Error parsing parambuf Parameter: %hs  Error: d", "Ipv6Addr", (unsigned int)v17);
        v19 = xmmword_18004C800;
        goto LABEL_62;
      }
      if ( *((_QWORD *)v5 + 259) )
      {
        v18 = *((_QWORD *)&xmmword_18004C800 + 1);
        if ( *((_QWORD *)&xmmword_18004C800 + 1) )
        {
          LOWORD(v45) = 0;
          FormatRRASErrorString(&v45, L"Parameter: %hs  Value: %hs", "Ipv6Addr", S);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            *((_QWORD *)&xmmword_18004C800 + 1),
            &v45);
          v18 = *((_QWORD *)&xmmword_18004C800 + 1);
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
            &v45,
            L"Parsed Interface ID : %x %x %x %x %x %x %x %x",
            (unsigned __int8)v5[72],
            (unsigned __int8)v5[73],
            lpWideCharStr,
            cchWideChar,
            v31,
            v32,
            v33,
            v34);
          v19 = *((_QWORD *)&xmmword_18004C800 + 1);
LABEL_62:
          ((void (__fastcall *)(__int64, __int64, int *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v19, &v45);
        }
      }
    }
LABEL_63:
    if ( (unsigned int)FindLongInParamBuf(*(_QWORD *)(a2 + 32), "Ipv6PrefixLength", &v35) )
    {
      v20 = *((_QWORD *)&xmmword_18004C800 + 1) == 0;
      *((_DWORD *)v5 + 520) = v35;
      if ( !v20 )
      {
        v21 = "Ipv6PrefixLength";
        v22 = L"Parameter: %hs  Value: %d";
LABEL_70:
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, v22, v21);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
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
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    v9 = *(_QWORD *)(a2 + 1120);
LABEL_8:
    LOWORD(v45) = 0;
    FormatRRASErrorString(&v45, L"Ipv6CpBegin: MultiByteToWideChar(%hs) failed: %d", v9, LastError);
LABEL_9:
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v45);
  }
LABEL_40:
  if ( (*((_DWORD *)v5 + 42) & 0x200) != 0 )
  {
    ((void (__fastcall *)(_QWORD, __int64))xmmword_18004C440)(*((_QWORD *)v5 + 2), 34525);
    *((_DWORD *)v5 + 42) &= ~0x200u;
  }
  LocalFree(v5);
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    LOWORD(v45) = 0;
    FormatRRASErrorString(&v45, L"Ipv6cpBegin: done %d", UniqueInterfaceId);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v45);
  }
  return UniqueInterfaceId;
}

```

## disassembly

```asm
0x180020ee0  mov     [rsp-8+arg_10], rbx
0x180020ee5  push    rbp
0x180020ee6  push    rsi
0x180020ee7  push    rdi
0x180020ee8  push    r12
0x180020eea  push    r13
0x180020eec  push    r14
0x180020eee  push    r15
0x180020ef0  lea     rbp, [rsp-9B0h]
0x180020ef8  sub     rsp, 0AB0h
0x180020eff  mov     rax, cs:__security_cookie
0x180020f06  xor     rax, rsp
0x180020f09  mov     [rbp+9E0h+var_40], rax
0x180020f10  xorps   xmm0, xmm0
0x180020f13  mov     r14, rdx
0x180020f16  mov     r13, rcx
0x180020f19  xor     eax, eax
0x180020f1b  xor     edi, edi
0x180020f1d  mov     [rbp+9E0h+var_A38], eax
0x180020f20  xor     edx, edx; Val
0x180020f22  mov     [rbp+9E0h+var_940], edi
0x180020f28  lea     rcx, [rbp+9E0h+var_93C]; void *
0x180020f2f  mov     r8d, 7FCh; Size
0x180020f35  movups  [rsp+0AE0h+var_A68], xmm0
0x180020f3a  movups  [rbp+9E0h+var_A58], xmm0
0x180020f3e  movups  [rbp+9E0h+var_A48], xmm0
0x180020f42  call    memset_0
0x180020f47  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020f4e  test    rdx, rdx
0x180020f51  jz      short loc_180020F6D
0x180020f53  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020f5a  lea     r8, aIpv6cpBegin; "IPv6CP: Begin"
0x180020f61  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f6d  mov     ebx, 850h
0x180020f72  mov     ecx, 40h ; '@'; uFlags
0x180020f77  mov     edx, ebx; uBytes
0x180020f79  call    cs:__imp_LocalAlloc
0x180020f7f  mov     rsi, rax
0x180020f82  test    rax, rax
0x180020f85  jnz     short loc_180020F92
0x180020f87  call    cs:__imp_GetLastError
0x180020f8d  jmp     loc_180021B78
0x180020f92  mov     r8, rbx; Size
0x180020f95  xor     edx, edx; Val
0x180020f97  mov     rcx, rsi; void *
0x180020f9a  call    memset_0
0x180020f9f  mov     eax, [r14]
0x180020fa2  lea     r15, [rsi+824h]
0x180020fa9  mov     [rsi], eax
0x180020fab  lea     r12, [rsi+4E8h]
0x180020fb2  mov     rax, [r14+8]
0x180020fb6  or      ebx, 0FFFFFFFFh
0x180020fb9  mov     [rsi+8], rax
0x180020fbd  mov     r9d, ebx; cbMultiByte
0x180020fc0  mov     rax, [r14+470h]
0x180020fc7  xor     edx, edx; dwFlags
0x180020fc9  mov     [rsi+10h], rax
0x180020fcd  xor     ecx, ecx; CodePage
0x180020fcf  mov     rax, [r14+478h]
0x180020fd6  mov     [rsi+18h], rax
0x180020fda  mov     eax, [r14+480h]
0x180020fe1  mov     [rsi+20h], eax
0x180020fe4  lea     rax, [rsi+28h]
0x180020fe8  movups  xmm0, xmmword ptr [r14+498h]
0x180020ff0  mov     dword ptr [rsp+0AE0h+cchWideChar], 100h; cchWideChar
0x180020ff8  mov     [rsp+0AE0h+lpWideCharStr], r12; lpWideCharStr
0x180020ffd  movdqu  xmmword ptr [r15], xmm0
0x180021002  movups  xmm0, xmmword ptr [r14+4A8h]
0x18002100a  movups  xmmword ptr [rsi+834h], xmm0
0x180021011  movups  xmm1, xmmword ptr [r14+4B4h]
0x180021019  movups  xmmword ptr [rsi+840h], xmm1
0x180021020  mov     [rax+8], rax
0x180021024  mov     [rax], rax
0x180021027  lea     rax, [rsi+38h]
0x18002102b  mov     [rax+8], rax
0x18002102f  mov     [rax], rax
0x180021032  mov     r8, [r14+460h]; lpMultiByteStr
0x180021039  call    cs:__imp_MultiByteToWideChar
0x18002103f  test    eax, eax
0x180021041  jnz     short loc_1800210A2
0x180021043  call    cs:__imp_GetLastError
0x180021049  cmp     qword ptr cs:xmmword_18004C800+8, rdi
0x180021050  mov     ebx, eax
0x180021052  jz      loc_1800213D0
0x180021058  mov     r8, [r14+460h]
0x18002105f  mov     r9d, eax
0x180021062  mov     word ptr [rbp+9E0h+var_940], di
0x180021069  lea     rdx, aIpv6cpbeginMul; "Ipv6CpBegin: MultiByteToWideChar(%hs) f"...
0x180021070  lea     rcx, [rbp+9E0h+var_940]
0x180021077  call    FormatRRASErrorString
0x18002107c  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021083  lea     r8, [rbp+9E0h+var_940]
0x18002108a  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021091  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002109d  jmp     loc_1800213D0
0x1800210a2  mov     [rsi+6E8h], di
0x1800210a9  mov     r9d, ebx; cbMultiByte
0x1800210ac  mov     r8, [r14+468h]; lpMultiByteStr
0x1800210b3  lea     rdi, [rsi+6EAh]
0x1800210ba  mov     dword ptr [rsp+0AE0h+cchWideChar], 10h; cchWideChar
0x1800210c2  xor     edx, edx; dwFlags
0x1800210c4  xor     ecx, ecx; CodePage
0x1800210c6  mov     [rsp+0AE0h+lpWideCharStr], rdi; lpWideCharStr
0x1800210cb  call    cs:__imp_MultiByteToWideChar
0x1800210d1  test    eax, eax
0x1800210d3  jnz     short loc_1800210F8
0x1800210d5  call    cs:__imp_GetLastError
0x1800210db  xor     edi, edi
0x1800210dd  mov     ebx, eax
0x1800210df  cmp     qword ptr cs:xmmword_18004C800+8, rdi
0x1800210e6  jz      loc_1800213D0
0x1800210ec  mov     r8, [r14+468h]
0x1800210f3  jmp     loc_18002105F
0x1800210f8  xor     eax, eax
0x1800210fa  lea     r9, [rsi+0B4h]
0x180021101  mov     [rsi+70Ah], ax
0x180021108  xor     r8d, r8d
0x18002110b  cmp     [rsi], eax
0x18002110d  mov     edx, 86DDh
0x180021112  mov     rcx, [rsi+8]
0x180021116  mov     rax, qword ptr cs:xmmword_18004C3F0+8
0x18002111d  setz    r8b
0x180021121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021126  mov     ebx, eax
0x180021128  test    eax, eax
0x18002112a  jz      short loc_18002115D
0x18002112c  xor     edi, edi
0x18002112e  cmp     qword ptr cs:xmmword_18004C800+8, rdi
0x180021135  jz      loc_1800213D0
0x18002113b  mov     r8d, eax
0x18002113e  mov     word ptr [rbp+9E0h+var_940], di
0x180021145  lea     rdx, aIpv6cpbeginRas; "Ipv6CpBegin: RasAllocateRoute=%d"
0x18002114c  lea     rcx, [rbp+9E0h+var_940]
0x180021153  call    FormatRRASErrorString
0x180021158  jmp     loc_18002107C
0x18002115d  bts     dword ptr [rsi+0A8h], 9
0x180021165  cmp     dword ptr [rsi], 0
0x180021168  jz      loc_18002138C
0x18002116e  mov     rcx, [rsi+8]
0x180021172  lea     rax, [rsi+68h]
0x180021176  mov     r9, r15
0x180021179  mov     [rsp+0AE0h+lpWideCharStr], rax
0x18002117e  mov     r8, rdi
0x180021181  mov     rdx, r12
0x180021184  call    RasPPPSrvrAcquireIpv6AddressForClient
0x180021189  xor     edi, edi
0x18002118b  mov     ebx, eax
0x18002118d  test    eax, eax
0x18002118f  jnz     loc_1800213D0
0x180021195  cmp     dword ptr [rsi+20h], 2
0x180021199  jz      short loc_1800211BF
0x18002119b  mov     rdx, r15
0x18002119e  lea     rcx, [rsp+0AE0h+var_A68]
0x1800211a3  call    RasPPPQueryIpv6ServerAddress
0x1800211a8  mov     ebx, eax
0x1800211aa  test    eax, eax
0x1800211ac  jnz     loc_1800213D0
0x1800211b2  mov     rax, qword ptr [rbp+9E0h+var_A48+8]
0x1800211b6  lea     rdi, [rsi+48h]
0x1800211ba  mov     [rdi], rax
0x1800211bd  jmp     short loc_1800211DF
0x1800211bf  lea     rdi, [rsi+48h]
0x1800211c3  mov     r8, rsi
0x1800211c6  mov     rcx, rdi; pbBuffer
0x1800211c9  lea     rdx, IsLocalInterfaceIdUnique
0x1800211d0  call    Ipv6cpGetUniqueInterfaceId
0x1800211d5  mov     ebx, eax
0x1800211d7  test    eax, eax
0x1800211d9  jnz     loc_1800213CE
0x1800211df  cmp     qword ptr cs:xmmword_18004C800+8, 0
0x1800211e7  jz      short loc_180021263
0x1800211e9  xor     eax, eax
0x1800211eb  mov     word ptr [rbp+9E0h+var_940], ax
0x1800211f2  movzx   ecx, byte ptr [rsi+4Eh]
0x1800211f6  movzx   edx, byte ptr [rsi+4Dh]
0x1800211fa  movzx   eax, byte ptr [rsi+4Fh]
0x1800211fe  movzx   r10d, byte ptr [rsi+4Ch]
0x180021203  movzx   r11d, byte ptr [rsi+4Bh]
0x180021208  movzx   ebx, byte ptr [rsi+4Ah]
0x18002120c  movzx   r9d, byte ptr [rsi+49h]
0x180021211  movzx   r8d, byte ptr [rdi]
0x180021215  mov     dword ptr [rsp+0AE0h+var_A98], eax
0x180021219  mov     dword ptr [rsp+0AE0h+var_AA0], ecx
0x18002121d  lea     rcx, [rbp+9E0h+var_940]
0x180021224  mov     dword ptr [rsp+0AE0h+var_AA8], edx
0x180021228  lea     rdx, aIpv6cpbeginLoc; "Ipv6CpBegin: LocalInterface Id is %x %x"...
0x18002122f  mov     dword ptr [rsp+0AE0h+var_AB0], r10d
0x180021234  mov     dword ptr [rsp+0AE0h+cchWideChar], r11d
0x180021239  mov     dword ptr [rsp+0AE0h+lpWideCharStr], ebx
0x18002123d  call    FormatRRASErrorString
0x180021242  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021249  lea     r8, [rbp+9E0h+var_940]
0x180021250  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021257  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002125e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021263  xor     edi, edi
0x180021265  cmp     [rsi], edi
0x180021267  jz      short loc_180021273
0x180021269  cmp     dword ptr [rsi+20h], 2
0x18002126d  jnz     loc_180021B6C
0x180021273  mov     rax, [r14+20h]
0x180021277  mov     [rsp+0AE0h+var_A90], edi
0x18002127b  mov     [rsp+0AE0h+Terminator], rdi
0x180021280  test    rax, rax
0x180021283  jz      loc_180021B1D
0x180021289  mov     rdx, cs:qword_18004C820
0x180021290  test    rdx, rdx
0x180021293  jz      short loc_1800212BA
0x180021295  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002129c  lea     r8, aDumpingBytesPs; "Dumping Bytes pszzParameters"
0x1800212a3  mov     [rsp+0AE0h+lpWideCharStr], rax
0x1800212a8  mov     r9d, 200h
0x1800212ae  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x1800212b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ba  mov     rcx, [r14+20h]
0x1800212be  lea     r8, [rsp+0AE0h+var_A90]
0x1800212c3  lea     rdx, aIpv6remote; "Ipv6Remote"
0x1800212ca  call    FindFlagInParamBuf
0x1800212cf  mov     r9d, [rsp+0AE0h+var_A90]
0x1800212d4  test    eax, eax
0x1800212d6  jz      short loc_1800212E4
0x1800212d8  test    r9d, r9d
0x1800212db  jz      short loc_1800212E4
0x1800212dd  or      dword ptr [rsi+0A8h], 4
0x1800212e4  cmp     qword ptr cs:xmmword_18004C800+8, rdi
0x1800212eb  jz      short loc_18002132C
0x1800212ed  mov     r8d, [r14+10h]
0x1800212f1  lea     rdx, aIpv6cpDevidety; "IPv6CP: devideType=%x UI parameters for"...
0x1800212f8  lea     rcx, [rbp+9E0h+var_940]
0x1800212ff  mov     word ptr [rbp+9E0h+var_940], di
0x180021306  call    FormatRRASErrorString
0x18002130b  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021312  lea     r8, [rbp+9E0h+var_940]
0x180021319  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021320  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002132c  lea     rbx, [rsi+9Ch]
0x180021333  mov     [rbx], edi
0x180021335  lea     r15, aIpv6interfacem; "Ipv6InterfaceMetric"
0x18002133c  mov     rcx, [r14+20h]
0x180021340  mov     r8, rbx
0x180021343  mov     rdx, r15
0x180021346  call    FindLongInParamBuf
0x18002134b  test    eax, eax
0x18002134d  jz      loc_180021450
0x180021353  cmp     qword ptr cs:xmmword_18004C800+8, rdi
0x18002135a  jz      loc_180021497
0x180021360  mov     word ptr [rbp+9E0h+var_940], di
0x180021367  lea     rdx, aParameterHsVal_1; "Parameter: %hs  Value: %d"
0x18002136e  mov     r9d, [rbx]
0x180021371  lea     rcx, [rbp+9E0h+var_940]
0x180021378  mov     r8, r15
0x18002137b  call    FormatRRASErrorString
0x180021380  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021387  jmp     loc_18002147D
0x18002138c  cmp     dword ptr [rsi+20h], 2
0x180021390  jnz     short loc_1800213B7
0x180021392  mov     rcx, [rsi+8]
0x180021396  lea     rax, [rsi+68h]
0x18002139a  mov     r9, r15
0x18002139d  mov     [rsp+0AE0h+lpWideCharStr], rax
0x1800213a2  mov     r8, rdi
0x1800213a5  mov     rdx, r12
0x1800213a8  call    RasPPPSrvrAcquireIpv6AddressForClient
0x1800213ad  xor     edi, edi
0x1800213af  mov     ebx, eax
0x1800213b1  test    eax, eax
0x1800213b3  jnz     short loc_1800213D0
0x1800213b5  jmp     short loc_1800213B9
0x1800213b7  xor     edi, edi
0x1800213b9  lea     rcx, [rsi+48h]; pbBuffer
0x1800213bd  call    Ipv6cpGenerateInterfaceId
0x1800213c2  mov     ebx, eax
0x1800213c4  test    eax, eax
0x1800213c6  jz      loc_180021265
0x1800213cc  jmp     short loc_1800213D0
0x1800213ce  xor     edi, edi
0x1800213d0  test    dword ptr [rsi+0A8h], 200h
0x1800213da  jz      short loc_1800213F9
0x1800213dc  mov     rcx, [rsi+10h]
0x1800213e0  mov     edx, 86DDh
0x1800213e5  mov     rax, qword ptr cs:xmmword_18004C440
0x1800213ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f1  btr     dword ptr [rsi+0A8h], 9
0x1800213f9  mov     rcx, rsi; hMem
0x1800213fc  call    cs:__imp_LocalFree
0x180021402  cmp     qword ptr cs:xmmword_18004C800+8, rdi
0x180021409  jz      short loc_180021449
0x18002140b  mov     r8d, ebx
0x18002140e  mov     word ptr [rbp+9E0h+var_940], di
0x180021415  lea     rdx, aIpv6cpbeginDon; "Ipv6cpBegin: done %d"
0x18002141c  lea     rcx, [rbp+9E0h+var_940]
0x180021423  call    FormatRRASErrorString
0x180021428  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x18002142f  lea     r8, [rbp+9E0h+var_940]
0x180021436  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002143d  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021444  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
