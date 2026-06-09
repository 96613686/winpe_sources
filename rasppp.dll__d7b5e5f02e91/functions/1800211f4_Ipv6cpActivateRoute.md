# Ipv6cpActivateRoute

- ea: `0x1800211f4`
- end: `0x180021b35`
- name: `Ipv6cpActivateRoute`
- size: `2369`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024110`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180018630`
- `0x180018674`
- `0x180020b1c`
- `0x180020b90`
- `0x1800211f4`
- `0x18002b0dc`
- `0x18002d88c`
- `0x18002dc44`
- `0x18002df00`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021604`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002140c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002140c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800213e7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800213e7`
- `DNSAPI!DnsSetConfigDword` at `0x18002168c`
- `DNSAPI!DnsSetConfigDword` at `0x1800216b0`
- `DNSAPI!DnsSetConfigDword` at `0x1800216fb`
- `DNSAPI!DnsSetConfigDword` at `0x18002171f`
- `DNSAPI!DnsSetConfigDword` at `0x18002168c`
- `DNSAPI!DnsSetConfigDword` at `0x1800216b0`
- `DNSAPI!DnsSetConfigDword` at `0x1800216fb`
- `DNSAPI!DnsSetConfigDword` at `0x18002171f`
- `rasman!RasFreeInterfaceLuidIndex` at `0x180021ab8`
- `rasman!RasFreeInterfaceLuidIndex` at `0x180021ab8`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18002146a`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18002146a`

## string_xrefs

- `0x180021837`: `IPCP:RasUpdateDefaultRouteSettings failed. Error %d`
- `0x18002188e`: `IPCP:RasUpdateDefaultRouteSettings success`
- `0x180021508`: `Ipv6cpProjectionNotification: NsiGetCompartmentIdForRoutingDomain: failed Err: %d`

## pseudocode

```c
__int64 __fastcall Ipv6cpActivateRoute(__int64 a1)
{
  unsigned int v2; // esi
  int v3; // r14d
  int v4; // r12d
  bool v5; // zf
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int *v8; // r15
  unsigned int v9; // eax
  __int64 v10; // r8
  const wchar_t *v11; // rdx
  __int128 v12; // xmm1
  __int64 v13; // r9
  const CHAR *v14; // r8
  DWORD LastError; // eax
  unsigned int v16; // eax
  __int64 v17; // r8
  unsigned int CompartmentIdForRoutingDomain; // eax
  GUID v19; // xmm0
  unsigned int v20; // eax
  wchar_t *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  const wchar_t *v24; // r8
  __int64 v25; // rdx
  __int128 *v26; // rcx
  __int64 v27; // rdx
  const wchar_t *v28; // r8
  unsigned int v29; // eax
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rdx
  __int128 v35; // xmm1
  __int64 v36; // rax
  __int128 v37; // xmm1
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int lpWideCharStra; // [rsp+20h] [rbp-E0h]
  _QWORD v41[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v42; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v45; // [rsp+64h] [rbp-9Ch]
  int v46; // [rsp+6Ch] [rbp-94h]
  int v47; // [rsp+70h] [rbp-90h]
  int v48; // [rsp+74h] [rbp-8Ch]
  int v49; // [rsp+94h] [rbp-6Ch]
  unsigned int v50; // [rsp+2ACh] [rbp+1ACh]
  __int64 v51; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v52[28]; // [rsp+2C4h] [rbp+1C4h]
  wchar_t pszDest[274]; // [rsp+2E0h] [rbp+1E0h] BYREF
  GUID v54; // [rsp+504h] [rbp+404h]
  int v55; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v56[2044]; // [rsp+524h] [rbp+424h] BYREF

  v55 = 0;
  v2 = 0;
  memset_0(v56, 0, sizeof(v56));
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"Ipv6cpProjectionNotification");
  v3 = *(_DWORD *)(a1 + 168);
  if ( (v3 & 2) != 0 )
  {
    v4 = 0;
    memset_0(&v44, 0, 0x4B8u);
    v5 = *(_DWORD *)(a1 + 32) == 2;
    v44 = 1200;
    if ( v5 )
      v6 = 2;
    else
      v6 = *(_DWORD *)a1 == 0;
    v45 = v6;
    if ( (v3 & 4) != 0 )
      v46 = 1;
    v7 = *(_QWORD *)(a1 + 72);
    v8 = (unsigned int *)(a1 + 2060);
    *(_DWORD *)(a1 + 2060) = 0;
    v51 = v7;
    if ( v6 )
    {
      v48 = 0;
    }
    else
    {
      v9 = RasPPPGetNewSubInterfaceIndex();
      v2 = v9;
      if ( v9 )
      {
        if ( (_QWORD)xmmword_18004D800 )
        {
          v10 = v9;
          v11 = L"IPV6CP: GetNewSubInterfaceIndex: failed Err: %d";
LABEL_73:
          LOWORD(v55) = 0;
          FormatRRASErrorString((wchar_t *)&v55, v11, v10);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            xmmword_18004D800,
            &v55);
          goto LABEL_100;
        }
        goto LABEL_100;
      }
      v6 = v45;
      v48 = *v8;
    }
    v12 = *(_OWORD *)(a1 + 2112);
    v47 = *(_DWORD *)(a1 + 24);
    v54 = GUID_NULL;
    v49 = 1;
    *(_OWORD *)v52 = *(_OWORD *)(a1 + 2100);
    *(_OWORD *)&v52[12] = v12;
    if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString((wchar_t *)&v55, L"IPv6CP: RasActivateRoute(u=%x,a=%x)...", v6, v50);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004D800 + 1),
        &v55);
      v6 = v45;
    }
    memset_0((void *)(a1 + 704), 0, 0x218u);
    if ( v6 == 1 )
    {
      v14 = (const CHAR *)(a1 + 1804);
      if ( *(_BYTE *)(a1 + 1804) )
      {
        if ( !MultiByteToWideChar(0, 0, v14, -1, (LPWSTR)(a1 + 704), 254) )
        {
          if ( (_QWORD)xmmword_18004D800 )
          {
            LOWORD(v55) = 0;
            LastError = GetLastError();
            FormatRRASErrorString((wchar_t *)&v55, L"IPCP:MultiByteToWideChar failed. Error %d", LastError);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              xmmword_18004D800,
              &v55);
          }
          goto LABEL_105;
        }
        *(_WORD *)(a1 + 1214) = 0;
      }
      v16 = RasAllocInterfaceLuidIndex(*(_QWORD *)(a1 + 8), a1 + 700, v14, v13);
      v2 = v16;
      LOBYTE(v4) = v16 == 0;
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
      {
        v17 = *(unsigned int *)(a1 + 700);
        LOWORD(v55) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v55,
          L"Ipv6cpProjectionNotification: RasAllocateInterfaceLuidIndex returns %d as the LuidIndex %x as the return value",
          v17,
          v16);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          &v55);
      }
      if ( v2 )
        goto LABEL_100;
    }
    else if ( !v6 )
    {
      LODWORD(v41[0]) = 1;
      CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain((_QWORD *)(a1 + 2084), v41);
      v2 = CompartmentIdForRoutingDomain;
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (_QWORD)xmmword_18004D800 )
        {
          v10 = CompartmentIdForRoutingDomain;
          v11 = L"Ipv6cpProjectionNotification: NsiGetCompartmentIdForRoutingDomain: failed Err: %d";
          goto LABEL_73;
        }
LABEL_100:
        if ( (*(_DWORD *)(a1 + 168) & 0x201) != 0 )
        {
          ((void (__fastcall *)(_QWORD, __int64))xmmword_18004D440)(*(_QWORD *)(a1 + 16), 34525);
          *(_DWORD *)(a1 + 168) &= 0xFFFFFDFE;
        }
        if ( v4 )
          RasFreeInterfaceLuidIndex(*(_QWORD *)(a1 + 8), *(unsigned int *)(a1 + 1244));
        *v8 = 0;
        goto LABEL_105;
      }
      v19 = *(GUID *)(a1 + 2084);
      v49 = v41[0];
      v54 = v19;
    }
    *(_DWORD *)(a1 + 1244) = *(_DWORD *)(a1 + 700);
    if ( *(_WORD *)(a1 + 1256) )
      StringCchCopyW(pszDest, 0x111u, (STRSAFE_LPCWSTR)(a1 + 1256));
    else
      pszDest[0] = 0;
    v20 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, int *))&xmmword_18004D440 + 1))(
            *(_QWORD *)(a1 + 8),
            34525,
            a1 + 180,
            &v44);
    v2 = v20;
    if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString((wchar_t *)&v55, L"Ipv6cpProjectionNotification: RasActivateRoute done(%d)", v20);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004D800 + 1),
        &v55);
    }
    if ( v2 )
      goto LABEL_100;
    *(_DWORD *)(a1 + 168) |= 1u;
    if ( *(_DWORD *)(a1 + 1240) )
      *(_DWORD *)(a1 + 168) |= 0x80u;
    if ( v45 == 2 )
      *(_DWORD *)(a1 + 1244) = *(_DWORD *)(a1 + 700);
    v21 = wcschr((const wchar_t *)(a1 + 444), 0x5Cu);
    *(_QWORD *)(a1 + 1248) = v21;
    if ( v21 )
    {
      *(_QWORD *)(a1 + 1248) = v21 + 1;
    }
    else
    {
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          L"IPv6CP: No device?");
      v2 = 87;
    }
    if ( *(_DWORD *)a1 && *(_DWORD *)(a1 + 32) != 2 )
      goto LABEL_82;
    ApplyIpcpV6Settings(a1);
    v22 = *(_QWORD *)(a1 + 1248);
    if ( (*(_BYTE *)(a1 + 168) & 8) != 0 )
    {
      DnsSetConfigDword(65552, v22, 1);
      v23 = *((_QWORD *)&xmmword_18004D800 + 1);
      if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
        goto LABEL_55;
      v24 = L"DnsEnableDynamicRegistration";
    }
    else
    {
      DnsSetConfigDword(65552, v22, 0);
      v23 = *((_QWORD *)&xmmword_18004D800 + 1);
      if ( !*((_QWORD *)&xmmword_18004D800 + 1) )
        goto LABEL_55;
      v24 = L"DnsDisableDynamicRegistration";
    }
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v23, v24);
LABEL_55:
    v25 = *(_QWORD *)(a1 + 1248);
    if ( (*(_BYTE *)(a1 + 168) & 0x10) != 0 )
    {
      DnsSetConfigDword(10, v25, 1);
      v27 = *((_QWORD *)&xmmword_18004D800 + 1);
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
      {
        v28 = L"DnsEnableAdapterDomainNameRegistration";
LABEL_60:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v27, v28);
      }
    }
    else
    {
      DnsSetConfigDword(10, v25, 0);
      v27 = *((_QWORD *)&xmmword_18004D800 + 1);
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
      {
        v28 = L"DnsDisableAdapterDomainNameRegistration";
        goto LABEL_60;
      }
    }
    if ( !*(_DWORD *)a1 )
    {
      if ( (*(_DWORD *)(a1 + 168) & 0x100) != 0 )
      {
        v26 = (__int128 *)(a1 + 2064);
        *(_QWORD *)(a1 + 2072) = *(_QWORD *)(a1 + 72);
        if ( *(_QWORD *)(a1 + 2064) )
        {
          v29 = SetIPv6AddressOnInterface(v26, *(_DWORD *)(a1 + 1244), *(_DWORD *)(a1 + 2080));
          if ( (_QWORD)xmmword_18004D800 )
          {
            LOWORD(v55) = 0;
            FormatRRASErrorString((wchar_t *)&v55, L"Ipv6 prefix and address plumbig %d", v29);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              xmmword_18004D800,
              &v55);
          }
        }
      }
      if ( !*(_DWORD *)a1 )
      {
        v30 = *(_DWORD *)(a1 + 168);
        if ( (v30 & 0x40) == 0 )
        {
          v31 = (*(_DWORD *)(a1 + 1244) & 0xFFFFFFLL | 0x17000000) << 24;
          if ( (v30 & 4) != 0 )
          {
            LOBYTE(v26) = 1;
            if ( (unsigned int)((__int64 (__fastcall *)(__int128 *, _QWORD, __int64))xmmword_18004D450)(
                                 v26,
                                 0,
                                 (*(_DWORD *)(a1 + 1244) & 0xFFFFFFLL | 0x17000000) << 24) )
            {
              v2 = 1003;
              if ( !(_QWORD)xmmword_18004D800 )
                goto LABEL_100;
              v11 = L"IPCP:RasUpdateDefaultRouteSettings failed. Error %d";
LABEL_72:
              v10 = 1003;
              goto LABEL_73;
            }
            if ( *((_QWORD *)&xmmword_18004D800 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
                gRasIpv6cpEtwContext,
                *((_QWORD *)&xmmword_18004D800 + 1),
                L"IPCP:RasUpdateDefaultRouteSettings success");
            *(_DWORD *)(a1 + 168) |= 0x40u;
          }
          if ( (unsigned int)AdjustSelfInterfaceMetrics(0, *(_DWORD *)(a1 + 156), v31) )
          {
            v2 = 1003;
            if ( !(_QWORD)xmmword_18004D800 )
              goto LABEL_100;
            v11 = L"IPCP:AdjustSelfInterfaceMetrics failed. Error %d";
            goto LABEL_72;
          }
          if ( *((_QWORD *)&xmmword_18004D800 + 1) )
          {
            v32 = *(unsigned int *)(a1 + 156);
            LOWORD(v55) = 0;
            FormatRRASErrorString((wchar_t *)&v55, L"IPCP:AdjustSelfInterfaceMetrics to value %d successful", v32);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              *((_QWORD *)&xmmword_18004D800 + 1),
              &v55);
          }
        }
      }
    }
LABEL_82:
    if ( !v2 )
      *(_DWORD *)(a1 + 168) |= 0x20u;
    *(_QWORD *)(a1 + 112) = *(_QWORD *)(a1 + 80);
    if ( *(_DWORD *)a1 )
    {
      if ( *(_DWORD *)(a1 + 32) != 2 )
      {
        v33 = *v8;
        goto LABEL_90;
      }
    }
    else if ( *(_DWORD *)(a1 + 32) != 2 )
    {
      goto LABEL_99;
    }
    v33 = (*(_DWORD *)(a1 + 1244) & 0xFFFFFFLL | 0x17000000) << 24;
LABEL_90:
    v41[0] = v33;
    if ( *(&xmmword_18004D500 + 1) )
    {
      v34 = *(_QWORD *)(a1 + 8);
      lpWideCharStra = *(_DWORD *)(a1 + 120);
      v42 = *(_OWORD *)(a1 + 2084);
      ((void (__fastcall *)(__int128 *, __int64, __int64, _QWORD *, int))*(&xmmword_18004D500 + 1))(
        &v42,
        v34,
        a1 + 80,
        v41,
        lpWideCharStra);
    }
    if ( *(&xmmword_18004D510 + 1) )
    {
      v35 = *(_OWORD *)(a1 + 2084);
      LOBYTE(lpWideCharStr) = v45 == 2;
      v42 = *(_OWORD *)(a1 + 104);
      v43 = v35;
      ((void (__fastcall *)(__int128 *, __int128 *, _QWORD, _QWORD *, int))*(&xmmword_18004D510 + 1))(
        &v43,
        &v42,
        v45,
        v41,
        lpWideCharStr);
    }
    if ( *(_DWORD *)(a1 + 32) == 2 )
    {
      v36 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)&v42 = 0;
      *((_QWORD *)&v42 + 1) = v36;
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          L"Ipv6cpActivateRoute: RasPPPActivateIpv6DoDSpecificRoute...");
      v37 = *(_OWORD *)(a1 + 104);
      v43 = v42;
      v42 = v37;
      RasPPPActivateIpv6DoDSpecificRoute(&v42, &v43);
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          L"Ipv6cpActivateRoute: RasPPPActivateIpv6DoDSpecificRoute done");
    }
LABEL_99:
    if ( !v2 )
      goto LABEL_105;
    goto LABEL_100;
  }
LABEL_105:
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    LOWORD(v55) = 0;
    FormatRRASErrorString((wchar_t *)&v55, L"Ipv6cpProjectionNotification: done %d", v2);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v55);
  }
  return v2;
}

```

## disassembly

```asm
0x1800211f4  push    rbp
0x1800211f6  push    rbx
0x1800211f7  push    rsi
0x1800211f8  push    rdi
0x1800211f9  push    r12
0x1800211fb  push    r13
0x1800211fd  push    r14
0x1800211ff  push    r15
0x180021201  lea     rbp, [rsp-0C38h]
0x180021209  sub     rsp, 0D38h
0x180021210  mov     rax, cs:__security_cookie
0x180021217  xor     rax, rsp
0x18002121a  mov     [rbp+0C70h+var_50], rax
0x180021221  mov     rdi, rcx
0x180021224  xor     r13d, r13d
0x180021227  lea     rcx, [rbp+0C70h+var_84C]; void *
0x18002122e  mov     [rbp+0C70h+var_850], r13d
0x180021235  xor     edx, edx; Val
0x180021237  mov     r8d, 7FCh; Size
0x18002123d  mov     esi, r13d
0x180021240  call    memset_0
0x180021245  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x18002124c  test    rdx, rdx
0x18002124f  jz      short loc_18002126B
0x180021251  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021258  lea     r8, aIpv6cpprojecti; "Ipv6cpProjectionNotification"
0x18002125f  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002126b  mov     r14d, [rdi+0A8h]
0x180021272  test    r14b, 2
0x180021276  jz      loc_180021AC7
0x18002127c  xor     edx, edx; Val
0x18002127e  lea     rcx, [rsp+0D70h+var_D10]; void *
0x180021283  mov     r8d, 4B8h; Size
0x180021289  mov     r12d, r13d
0x18002128c  call    memset_0
0x180021291  cmp     dword ptr [rdi+20h], 2
0x180021295  mov     [rsp+0D70h+var_D10], 4B0h
0x18002129d  jnz     short loc_1800212A6
0x18002129f  mov     ebx, 2
0x1800212a4  jmp     short loc_1800212AF
0x1800212a6  cmp     [rdi], r13d
0x1800212a9  mov     ebx, r13d
0x1800212ac  setz    bl
0x1800212af  mov     [rsp+0D70h+var_D0C], ebx
0x1800212b3  test    r14b, 4
0x1800212b7  jz      short loc_1800212C1
0x1800212b9  mov     [rsp+0D70h+var_D04], 1
0x1800212c1  mov     rax, [rdi+48h]
0x1800212c5  lea     r15, [rdi+80Ch]
0x1800212cc  mov     [r15], r13d
0x1800212cf  mov     [rbp+0C70h+var_AC0], rax
0x1800212d6  test    ebx, ebx
0x1800212d8  jnz     short loc_180021311
0x1800212da  mov     rcx, r15
0x1800212dd  call    RasPPPGetNewSubInterfaceIndex
0x1800212e2  mov     esi, eax
0x1800212e4  test    eax, eax
0x1800212e6  jz      short loc_180021304
0x1800212e8  cmp     qword ptr cs:xmmword_18004D800, r13
0x1800212ef  jz      loc_180021A7E
0x1800212f5  mov     r8d, eax
0x1800212f8  lea     rdx, aIpv6cpGetnewsu; "IPV6CP: GetNewSubInterfaceIndex: failed"...
0x1800212ff  jmp     loc_180021841
0x180021304  mov     eax, [r15]
0x180021307  mov     ebx, [rsp+0D70h+var_D0C]
0x18002130b  mov     [rsp+0D70h+var_CFC], eax
0x18002130f  jmp     short loc_180021316
0x180021311  mov     [rsp+0D70h+var_CFC], r13d
0x180021316  cmp     qword ptr cs:xmmword_18004D800+8, r13
0x18002131d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180021324  mov     eax, [rdi+18h]
0x180021327  movups  xmm1, xmmword ptr [rdi+840h]
0x18002132e  mov     [rsp+0D70h+var_D00], eax
0x180021332  movdqu  [rbp+0C70h+var_86C], xmm0
0x18002133a  mov     [rbp+0C70h+var_CDC], 1
0x180021341  movups  xmm0, xmmword ptr [rdi+834h]
0x180021348  movups  xmmword ptr [rbp+0C70h+var_AAC], xmm0
0x18002134f  movups  xmmword ptr [rbp+0C70h+var_AAC+0Ch], xmm1
0x180021356  jz      short loc_1800213A2
0x180021358  mov     r9d, [rbp+0C70h+var_AC4]
0x18002135f  lea     rdx, aIpv6cpRasactiv; "IPv6CP: RasActivateRoute(u=%x,a=%x)..."
0x180021366  mov     r8d, ebx
0x180021369  mov     word ptr [rbp+0C70h+var_850], r13w
0x180021371  lea     rcx, [rbp+0C70h+var_850]
0x180021378  call    FormatRRASErrorString
0x18002137d  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021384  lea     r8, [rbp+0C70h+var_850]
0x18002138b  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021392  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002139e  mov     ebx, [rsp+0D70h+var_D0C]
0x1800213a2  lea     r14, [rdi+2C0h]
0x1800213a9  xor     edx, edx; Val
0x1800213ab  mov     rcx, r14; void *
0x1800213ae  mov     r8d, 218h; Size
0x1800213b4  call    memset_0
0x1800213b9  cmp     ebx, 1
0x1800213bc  jnz     loc_1800214D2
0x1800213c2  lea     r8, [rdi+70Ch]; lpMultiByteStr
0x1800213c9  cmp     [r8], r13b
0x1800213cc  jz      loc_18002145C
0x1800213d2  mov     [rsp+0D70h+cchWideChar], 0FEh; cchWideChar
0x1800213da  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800213de  xor     edx, edx; dwFlags
0x1800213e0  mov     [rsp+0D70h+lpWideCharStr], r14; lpWideCharStr
0x1800213e5  xor     ecx, ecx; CodePage
0x1800213e7  call    cs:__imp_MultiByteToWideChar
0x1800213ee  nop     dword ptr [rax+rax+00h]
0x1800213f3  test    eax, eax
0x1800213f5  jnz     short loc_180021454
0x1800213f7  cmp     qword ptr cs:xmmword_18004D800, r13
0x1800213fe  jz      loc_180021AC7
0x180021404  mov     word ptr [rbp+0C70h+var_850], r13w
0x18002140c  call    cs:__imp_GetLastError
0x180021413  nop     dword ptr [rax+rax+00h]
0x180021418  mov     r8d, eax
0x18002141b  lea     rdx, aIpcpMultibytet; "IPCP:MultiByteToWideChar failed. Error "...
0x180021422  lea     rcx, [rbp+0C70h+var_850]
0x180021429  call    FormatRRASErrorString
0x18002142e  mov     rdx, qword ptr cs:xmmword_18004D800
0x180021435  lea     r8, [rbp+0C70h+var_850]
0x18002143c  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021443  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002144a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002144f  jmp     loc_180021AC7
0x180021454  mov     [rdi+4BEh], r13w
0x18002145c  mov     rcx, [rdi+8]
0x180021460  lea     rbx, [rdi+2BCh]
0x180021467  mov     rdx, rbx
0x18002146a  call    cs:__imp_RasAllocInterfaceLuidIndex
0x180021471  nop     dword ptr [rax+rax+00h]
0x180021476  test    eax, eax
0x180021478  mov     esi, eax
0x18002147a  setz    r12b
0x18002147e  cmp     qword ptr cs:xmmword_18004D800+8, r13
0x180021485  jz      short loc_1800214C9
0x180021487  mov     r8d, [rbx]
0x18002148a  lea     rdx, aIpv6cpprojecti_0; "Ipv6cpProjectionNotification: RasAlloca"...
0x180021491  mov     r9d, eax
0x180021494  mov     word ptr [rbp+0C70h+var_850], r13w
0x18002149c  lea     rcx, [rbp+0C70h+var_850]
0x1800214a3  call    FormatRRASErrorString
0x1800214a8  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800214af  lea     r8, [rbp+0C70h+var_850]
0x1800214b6  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800214bd  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800214c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214c9  test    esi, esi
0x1800214cb  jz      short loc_180021526
0x1800214cd  jmp     loc_180021A7E
0x1800214d2  test    ebx, ebx
0x1800214d4  jnz     short loc_180021526
0x1800214d6  lea     rbx, [rdi+824h]
0x1800214dd  mov     dword ptr [rsp+0D70h+var_D40], 1
0x1800214e5  mov     rcx, rbx
0x1800214e8  lea     rdx, [rsp+0D70h+var_D40]
0x1800214ed  call    NsiGetCompartmentIdForRoutingDomain
0x1800214f2  mov     esi, eax
0x1800214f4  test    eax, eax
0x1800214f6  jz      short loc_180021514
0x1800214f8  cmp     qword ptr cs:xmmword_18004D800, r13
0x1800214ff  jz      loc_180021A7E
0x180021505  mov     r8d, eax
0x180021508  lea     rdx, aIpv6cpprojecti_3; "Ipv6cpProjectionNotification: NsiGetCom"...
0x18002150f  jmp     loc_180021841
0x180021514  movups  xmm0, xmmword ptr [rbx]
0x180021517  mov     eax, dword ptr [rsp+0D70h+var_D40]
0x18002151b  mov     [rbp+0C70h+var_CDC], eax
0x18002151e  movdqu  [rbp+0C70h+var_86C], xmm0
0x180021526  mov     eax, [rdi+2BCh]
0x18002152c  lea     r8, [rdi+4E8h]; pszSrc
0x180021533  mov     [rdi+4DCh], eax
0x180021539  cmp     [r8], r13w
0x18002153d  jz      short loc_180021552
0x18002153f  mov     edx, 111h; cchDest
0x180021544  lea     rcx, [rbp+0C70h+pszDest]; pszDest
0x18002154b  call    StringCchCopyW
0x180021550  jmp     short loc_18002155A
0x180021552  mov     [rbp+0C70h+pszDest], r13w
0x18002155a  mov     rcx, [rdi+8]
0x18002155e  lea     r8, [rdi+0B4h]
0x180021565  mov     rax, qword ptr cs:xmmword_18004D440+8
0x18002156c  lea     r9, [rsp+0D70h+var_D10]
0x180021571  mov     edx, 86DDh
0x180021576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002157b  cmp     qword ptr cs:xmmword_18004D800+8, r13
0x180021582  mov     esi, eax
0x180021584  jz      short loc_1800215C5
0x180021586  mov     r8d, eax
0x180021589  mov     word ptr [rbp+0C70h+var_850], r13w
0x180021591  lea     rdx, aIpv6cpprojecti_2; "Ipv6cpProjectionNotification: RasActiva"...
0x180021598  lea     rcx, [rbp+0C70h+var_850]
0x18002159f  call    FormatRRASErrorString
0x1800215a4  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800215ab  lea     r8, [rbp+0C70h+var_850]
0x1800215b2  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800215b9  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800215c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215c5  test    esi, esi
0x1800215c7  jnz     loc_180021A7E
0x1800215cd  or      dword ptr [rdi+0A8h], 1
0x1800215d4  cmp     [rdi+4D8h], r13d
0x1800215db  jz      short loc_1800215E5
0x1800215dd  bts     dword ptr [rdi+0A8h], 7
0x1800215e5  cmp     [rsp+0D70h+var_D0C], 2
0x1800215ea  jnz     short loc_1800215F8
0x1800215ec  mov     eax, [rdi+2BCh]
0x1800215f2  mov     [rdi+4DCh], eax
0x1800215f8  mov     edx, 5Ch ; '\'; Ch
0x1800215fd  lea     rcx, [rdi+1BCh]; Str
0x180021604  call    cs:__imp_wcschr
0x18002160b  nop     dword ptr [rax+rax+00h]
0x180021610  mov     [rdi+4E0h], rax
0x180021617  test    rax, rax
0x18002161a  jnz     short loc_180021649
0x18002161c  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021623  test    rdx, rdx
0x180021626  jz      short loc_180021642
0x180021628  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002162f  lea     r8, aIpv6cpNoDevice; "IPv6CP: No device?"
0x180021636  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002163d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021642  mov     esi, 57h ; 'W'
0x180021647  jmp     short loc_180021654
0x180021649  add     rax, 2
0x18002164d  mov     [rdi+4E0h], rax
0x180021654  mov     r14d, 0FFFFFFh
0x18002165a  cmp     [rdi], r13d
0x18002165d  jz      short loc_180021669
0x18002165f  cmp     dword ptr [rdi+20h], 2
0x180021663  jnz     loc_180021926
0x180021669  mov     rcx, rdi
0x18002166c  call    ApplyIpcpV6Settings
0x180021671  test    byte ptr [rdi+0A8h], 8
0x180021678  mov     ecx, 10010h
0x18002167d  mov     rdx, [rdi+4E0h]
0x180021684  jz      short loc_1800216AD
0x180021686  mov     r8d, 1
0x18002168c  call    cs:__imp_DnsSetConfigDword
0x180021693  nop     dword ptr [rax+rax+00h]
0x180021698  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x18002169f  test    rdx, rdx
0x1800216a2  jz      short loc_1800216E2
0x1800216a4  lea     r8, aDnsenabledynam; "DnsEnableDynamicRegistration"
0x1800216ab  jmp     short loc_1800216CF
0x1800216ad  xor     r8d, r8d
0x1800216b0  call    cs:__imp_DnsSetConfigDword
0x1800216b7  nop     dword ptr [rax+rax+00h]
0x1800216bc  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800216c3  test    rdx, rdx
0x1800216c6  jz      short loc_1800216E2
0x1800216c8  lea     r8, aDnsdisabledyna; "DnsDisableDynamicRegistration"
0x1800216cf  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800216d6  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800216dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216e2  test    byte ptr [rdi+0A8h], 10h
0x1800216e9  mov     ecx, 0Ah
0x1800216ee  mov     rdx, [rdi+4E0h]
0x1800216f5  jz      short loc_18002171C
0x1800216f7  lea     r8d, [rcx-9]
0x1800216fb  call    cs:__imp_DnsSetConfigDword
0x180021702  nop     dword ptr [rax+rax+00h]
0x180021707  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x18002170e  test    rdx, rdx
0x180021711  jz      short loc_180021751
0x180021713  lea     r8, aDnsenableadapt; "DnsEnableAdapterDomainNameRegistration"
0x18002171a  jmp     short loc_18002173E
0x18002171c  xor     r8d, r8d
0x18002171f  call    cs:__imp_DnsSetConfigDword
0x180021726  nop     dword ptr [rax+rax+00h]
0x18002172b  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180021732  test    rdx, rdx
0x180021735  jz      short loc_180021751
0x180021737  lea     r8, aDnsdisableadap; "DnsDisableAdapterDomainNameRegistration"
0x18002173e  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021745  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002174c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021751  cmp     [rdi], r13d
0x180021754  jnz     loc_180021926
0x18002175a  test    dword ptr [rdi+0A8h], 100h
0x180021764  jz      short loc_1800217D7
0x180021766  mov     rax, [rdi+48h]
0x18002176a  lea     rcx, [rdi+810h]
0x180021771  mov     [rdi+818h], rax
0x180021778  cmp     [rcx], r13
0x18002177b  jz      short loc_1800217D7
0x18002177d  mov     r8d, [rdi+820h]
0x180021784  mov     edx, [rdi+4DCh]
0x18002178a  call    SetIPv6AddressOnInterface
0x18002178f  cmp     qword ptr cs:xmmword_18004D800, r13
0x180021796  jz      short loc_1800217D7
0x180021798  mov     r8d, eax
0x18002179b  mov     word ptr [rbp+0C70h+var_850], r13w
0x1800217a3  lea     rdx, aIpv6PrefixAndA; "Ipv6 prefix and address plumbig %d"
0x1800217aa  lea     rcx, [rbp+0C70h+var_850]
0x1800217b1  call    FormatRRASErrorString
0x1800217b6  mov     rdx, qword ptr cs:xmmword_18004D800
0x1800217bd  lea     r8, [rbp+0C70h+var_850]
0x1800217c4  mov     rcx, cs:gRasIpv6cpEtwContext
  ... truncated ...
```
