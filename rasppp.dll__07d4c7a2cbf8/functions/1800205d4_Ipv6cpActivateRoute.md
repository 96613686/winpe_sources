# Ipv6cpActivateRoute

- ea: `0x1800205d4`
- end: `0x180020eda`
- name: `Ipv6cpActivateRoute`
- size: `2310`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023400`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180017dc8`
- `0x180017e0c`
- `0x18001ff50`
- `0x18001ffc4`
- `0x1800205d4`
- `0x18002a138`
- `0x18002c76c`
- `0x18002cb08`
- `0x18002cda0`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800209ce`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800209ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207e2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800207c3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800207c3`
- `DNSAPI!DnsSetConfigDword` at `0x180020a50`
- `DNSAPI!DnsSetConfigDword` at `0x180020a6e`
- `DNSAPI!DnsSetConfigDword` at `0x180020ab3`
- `DNSAPI!DnsSetConfigDword` at `0x180020ad1`
- `DNSAPI!DnsSetConfigDword` at `0x180020a50`
- `DNSAPI!DnsSetConfigDword` at `0x180020a6e`
- `DNSAPI!DnsSetConfigDword` at `0x180020ab3`
- `DNSAPI!DnsSetConfigDword` at `0x180020ad1`
- `rasman!RasFreeInterfaceLuidIndex` at `0x180020e64`
- `rasman!RasFreeInterfaceLuidIndex` at `0x180020e64`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18002083a`
- `rasman!RasAllocInterfaceLuidIndex` at `0x18002083a`

## string_xrefs

- `0x180020be3`: `IPCP:RasUpdateDefaultRouteSettings failed. Error %d`
- `0x180020c3a`: `IPCP:RasUpdateDefaultRouteSettings success`
- `0x1800208d2`: `Ipv6cpProjectionNotification: NsiGetCompartmentIdForRoutingDomain: failed Err: %d`

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
  __int64 v13; // r8
  __int64 v14; // r9
  const CHAR *v15; // r8
  DWORD LastError; // eax
  unsigned int v17; // eax
  __int64 v18; // r8
  unsigned int CompartmentIdForRoutingDomain; // eax
  GUID v20; // xmm0
  unsigned int v21; // eax
  wchar_t *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  const wchar_t *v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  const wchar_t *v29; // r8
  unsigned int v30; // eax
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int128 v36; // xmm1
  __int64 v37; // rax
  __int128 v38; // xmm1
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int lpWideCharStra; // [rsp+20h] [rbp-E0h]
  _QWORD v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v43; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v46; // [rsp+64h] [rbp-9Ch]
  int v47; // [rsp+6Ch] [rbp-94h]
  int v48; // [rsp+70h] [rbp-90h]
  int v49; // [rsp+74h] [rbp-8Ch]
  int v50; // [rsp+94h] [rbp-6Ch]
  unsigned int v51; // [rsp+2ACh] [rbp+1ACh]
  __int64 v52; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v53[28]; // [rsp+2C4h] [rbp+1C4h]
  wchar_t pszDest[274]; // [rsp+2E0h] [rbp+1E0h] BYREF
  GUID v55; // [rsp+504h] [rbp+404h]
  int v56; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v57[2044]; // [rsp+524h] [rbp+424h] BYREF

  v56 = 0;
  v2 = 0;
  memset_0(v57, 0, sizeof(v57));
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      L"Ipv6cpProjectionNotification");
  v3 = *(_DWORD *)(a1 + 168);
  if ( (v3 & 2) != 0 )
  {
    v4 = 0;
    memset_0(&v45, 0, 0x4B8u);
    v5 = *(_DWORD *)(a1 + 32) == 2;
    v45 = 1200;
    if ( v5 )
      v6 = 2;
    else
      v6 = *(_DWORD *)a1 == 0;
    v46 = v6;
    if ( (v3 & 4) != 0 )
      v47 = 1;
    v7 = *(_QWORD *)(a1 + 72);
    v8 = (unsigned int *)(a1 + 2060);
    *(_DWORD *)(a1 + 2060) = 0;
    v52 = v7;
    if ( v6 )
    {
      v49 = 0;
    }
    else
    {
      v9 = RasPPPGetNewSubInterfaceIndex(a1 + 2060);
      v2 = v9;
      if ( v9 )
      {
        if ( (_QWORD)xmmword_18004C800 )
        {
          v10 = v9;
          v11 = L"IPV6CP: GetNewSubInterfaceIndex: failed Err: %d";
LABEL_73:
          LOWORD(v56) = 0;
          FormatRRASErrorString(&v56, v11, v10);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            xmmword_18004C800,
            &v56);
          goto LABEL_100;
        }
        goto LABEL_100;
      }
      v6 = v46;
      v49 = *v8;
    }
    v12 = *(_OWORD *)(a1 + 2112);
    v48 = *(_DWORD *)(a1 + 24);
    v55 = GUID_NULL;
    v50 = 1;
    *(_OWORD *)v53 = *(_OWORD *)(a1 + 2100);
    *(_OWORD *)&v53[12] = v12;
    if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    {
      LOWORD(v56) = 0;
      FormatRRASErrorString(&v56, L"IPv6CP: RasActivateRoute(u=%x,a=%x)...", v6, v51);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004C800 + 1),
        &v56);
      v6 = v46;
    }
    memset_0((void *)(a1 + 704), 0, 0x218u);
    if ( v6 == 1 )
    {
      v15 = (const CHAR *)(a1 + 1804);
      if ( *(_BYTE *)(a1 + 1804) )
      {
        if ( !MultiByteToWideChar(0, 0, v15, -1, (LPWSTR)(a1 + 704), 254) )
        {
          if ( (_QWORD)xmmword_18004C800 )
          {
            LOWORD(v56) = 0;
            LastError = GetLastError();
            FormatRRASErrorString(&v56, L"IPCP:MultiByteToWideChar failed. Error %d", LastError);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              xmmword_18004C800,
              &v56);
          }
          goto LABEL_105;
        }
        *(_WORD *)(a1 + 1214) = 0;
      }
      v17 = RasAllocInterfaceLuidIndex(*(_QWORD *)(a1 + 8), a1 + 700, v15, v14);
      v2 = v17;
      LOBYTE(v4) = v17 == 0;
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
      {
        v18 = *(unsigned int *)(a1 + 700);
        LOWORD(v56) = 0;
        FormatRRASErrorString(
          &v56,
          L"Ipv6cpProjectionNotification: RasAllocateInterfaceLuidIndex returns %d as the LuidIndex %x as the return value",
          v18,
          v17);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
          &v56);
      }
      if ( v2 )
        goto LABEL_100;
    }
    else if ( !v6 )
    {
      LODWORD(v42[0]) = 1;
      CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain(a1 + 2084, v42, v13, v14);
      v2 = CompartmentIdForRoutingDomain;
      if ( CompartmentIdForRoutingDomain )
      {
        if ( (_QWORD)xmmword_18004C800 )
        {
          v10 = CompartmentIdForRoutingDomain;
          v11 = L"Ipv6cpProjectionNotification: NsiGetCompartmentIdForRoutingDomain: failed Err: %d";
          goto LABEL_73;
        }
LABEL_100:
        if ( (*(_DWORD *)(a1 + 168) & 0x201) != 0 )
        {
          ((void (__fastcall *)(_QWORD, __int64))xmmword_18004C440)(*(_QWORD *)(a1 + 16), 34525);
          *(_DWORD *)(a1 + 168) &= 0xFFFFFDFE;
        }
        if ( v4 )
          RasFreeInterfaceLuidIndex(*(_QWORD *)(a1 + 8), *(unsigned int *)(a1 + 1244));
        *v8 = 0;
        goto LABEL_105;
      }
      v20 = *(GUID *)(a1 + 2084);
      v50 = v42[0];
      v55 = v20;
    }
    *(_DWORD *)(a1 + 1244) = *(_DWORD *)(a1 + 700);
    if ( *(_WORD *)(a1 + 1256) )
      StringCchCopyW(pszDest, 0x111u, (STRSAFE_LPCWSTR)(a1 + 1256));
    else
      pszDest[0] = 0;
    v21 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, int *))&xmmword_18004C440 + 1))(
            *(_QWORD *)(a1 + 8),
            34525,
            a1 + 180,
            &v45);
    v2 = v21;
    if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    {
      LOWORD(v56) = 0;
      FormatRRASErrorString(&v56, L"Ipv6cpProjectionNotification: RasActivateRoute done(%d)", v21);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        *((_QWORD *)&xmmword_18004C800 + 1),
        &v56);
    }
    if ( v2 )
      goto LABEL_100;
    *(_DWORD *)(a1 + 168) |= 1u;
    if ( *(_DWORD *)(a1 + 1240) )
      *(_DWORD *)(a1 + 168) |= 0x80u;
    if ( v46 == 2 )
      *(_DWORD *)(a1 + 1244) = *(_DWORD *)(a1 + 700);
    v22 = wcschr((const wchar_t *)(a1 + 444), 0x5Cu);
    *(_QWORD *)(a1 + 1248) = v22;
    if ( v22 )
    {
      *(_QWORD *)(a1 + 1248) = v22 + 1;
    }
    else
    {
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
          L"IPv6CP: No device?");
      v2 = 87;
    }
    if ( *(_DWORD *)a1 && *(_DWORD *)(a1 + 32) != 2 )
      goto LABEL_82;
    ApplyIpcpV6Settings(a1);
    v23 = *(_QWORD *)(a1 + 1248);
    if ( (*(_BYTE *)(a1 + 168) & 8) != 0 )
    {
      DnsSetConfigDword(65552, v23, 1);
      v24 = *((_QWORD *)&xmmword_18004C800 + 1);
      if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
        goto LABEL_55;
      v25 = L"DnsEnableDynamicRegistration";
    }
    else
    {
      DnsSetConfigDword(65552, v23, 0);
      v24 = *((_QWORD *)&xmmword_18004C800 + 1);
      if ( !*((_QWORD *)&xmmword_18004C800 + 1) )
        goto LABEL_55;
      v25 = L"DnsDisableDynamicRegistration";
    }
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v24, v25);
LABEL_55:
    v26 = *(_QWORD *)(a1 + 1248);
    if ( (*(_BYTE *)(a1 + 168) & 0x10) != 0 )
    {
      DnsSetConfigDword(10, v26, 1);
      v28 = *((_QWORD *)&xmmword_18004C800 + 1);
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
      {
        v29 = L"DnsEnableAdapterDomainNameRegistration";
LABEL_60:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(gRasIpv6cpEtwContext, v28, v29);
      }
    }
    else
    {
      DnsSetConfigDword(10, v26, 0);
      v28 = *((_QWORD *)&xmmword_18004C800 + 1);
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
      {
        v29 = L"DnsDisableAdapterDomainNameRegistration";
        goto LABEL_60;
      }
    }
    if ( !*(_DWORD *)a1 )
    {
      if ( (*(_DWORD *)(a1 + 168) & 0x100) != 0 )
      {
        v27 = a1 + 2064;
        *(_QWORD *)(a1 + 2072) = *(_QWORD *)(a1 + 72);
        if ( *(_QWORD *)(a1 + 2064) )
        {
          v30 = SetIPv6AddressOnInterface(v27, *(unsigned int *)(a1 + 1244), *(unsigned int *)(a1 + 2080));
          if ( (_QWORD)xmmword_18004C800 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"Ipv6 prefix and address plumbig %d", v30);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              xmmword_18004C800,
              &v56);
          }
        }
      }
      if ( !*(_DWORD *)a1 )
      {
        v31 = *(_DWORD *)(a1 + 168);
        if ( (v31 & 0x40) == 0 )
        {
          v32 = (*(_DWORD *)(a1 + 1244) & 0xFFFFFFLL | 0x17000000) << 24;
          if ( (v31 & 4) != 0 )
          {
            LOBYTE(v27) = 1;
            if ( (unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64))xmmword_18004C450)(
                                 v27,
                                 0,
                                 (*(_DWORD *)(a1 + 1244) & 0xFFFFFFLL | 0x17000000) << 24) )
            {
              v2 = 1003;
              if ( !(_QWORD)xmmword_18004C800 )
                goto LABEL_100;
              v11 = L"IPCP:RasUpdateDefaultRouteSettings failed. Error %d";
LABEL_72:
              v10 = 1003;
              goto LABEL_73;
            }
            if ( *((_QWORD *)&xmmword_18004C800 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
                gRasIpv6cpEtwContext,
                *((_QWORD *)&xmmword_18004C800 + 1),
                L"IPCP:RasUpdateDefaultRouteSettings success");
            *(_DWORD *)(a1 + 168) |= 0x40u;
          }
          if ( (unsigned int)AdjustSelfInterfaceMetrics(0, *(unsigned int *)(a1 + 156), v32) )
          {
            v2 = 1003;
            if ( !(_QWORD)xmmword_18004C800 )
              goto LABEL_100;
            v11 = L"IPCP:AdjustSelfInterfaceMetrics failed. Error %d";
            goto LABEL_72;
          }
          if ( *((_QWORD *)&xmmword_18004C800 + 1) )
          {
            v33 = *(unsigned int *)(a1 + 156);
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"IPCP:AdjustSelfInterfaceMetrics to value %d successful", v33);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
              gRasIpv6cpEtwContext,
              *((_QWORD *)&xmmword_18004C800 + 1),
              &v56);
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
        v34 = *v8;
        goto LABEL_90;
      }
    }
    else if ( *(_DWORD *)(a1 + 32) != 2 )
    {
      goto LABEL_99;
    }
    v34 = (*(_DWORD *)(a1 + 1244) & 0xFFFFFFLL | 0x17000000) << 24;
LABEL_90:
    v42[0] = v34;
    if ( *((_QWORD *)&xmmword_18004C500 + 1) )
    {
      v35 = *(_QWORD *)(a1 + 8);
      lpWideCharStra = *(_DWORD *)(a1 + 120);
      v43 = *(_OWORD *)(a1 + 2084);
      (*((void (__fastcall **)(__int128 *, __int64, __int64, _QWORD *, int))&xmmword_18004C500 + 1))(
        &v43,
        v35,
        a1 + 80,
        v42,
        lpWideCharStra);
    }
    if ( *(&xmmword_18004C510 + 1) )
    {
      v36 = *(_OWORD *)(a1 + 2084);
      LOBYTE(lpWideCharStr) = v46 == 2;
      v43 = *(_OWORD *)(a1 + 104);
      v44 = v36;
      ((void (__fastcall *)(__int128 *, __int128 *, _QWORD, _QWORD *, int))*(&xmmword_18004C510 + 1))(
        &v44,
        &v43,
        v46,
        v42,
        lpWideCharStr);
    }
    if ( *(_DWORD *)(a1 + 32) == 2 )
    {
      v37 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)&v43 = 0;
      *((_QWORD *)&v43 + 1) = v37;
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
          L"Ipv6cpActivateRoute: RasPPPActivateIpv6DoDSpecificRoute...");
      v38 = *(_OWORD *)(a1 + 104);
      v44 = v43;
      v43 = v38;
      RasPPPActivateIpv6DoDSpecificRoute(&v43, &v44, v42, 0);
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
          L"Ipv6cpActivateRoute: RasPPPActivateIpv6DoDSpecificRoute done");
    }
LABEL_99:
    if ( !v2 )
      goto LABEL_105;
    goto LABEL_100;
  }
LABEL_105:
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    LOWORD(v56) = 0;
    FormatRRASErrorString(&v56, L"Ipv6cpProjectionNotification: done %d", v2);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v56);
  }
  return v2;
}

```

## disassembly

```asm
0x1800205d4  push    rbp
0x1800205d6  push    rbx
0x1800205d7  push    rsi
0x1800205d8  push    rdi
0x1800205d9  push    r12
0x1800205db  push    r13
0x1800205dd  push    r14
0x1800205df  push    r15
0x1800205e1  lea     rbp, [rsp-0C38h]
0x1800205e9  sub     rsp, 0D38h
0x1800205f0  mov     rax, cs:__security_cookie
0x1800205f7  xor     rax, rsp
0x1800205fa  mov     [rbp+0C70h+var_50], rax
0x180020601  mov     rdi, rcx
0x180020604  xor     r13d, r13d
0x180020607  lea     rcx, [rbp+0C70h+var_84C]; void *
0x18002060e  mov     [rbp+0C70h+var_850], r13d
0x180020615  xor     edx, edx; Val
0x180020617  mov     r8d, 7FCh; Size
0x18002061d  mov     esi, r13d
0x180020620  call    memset_0
0x180020625  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x18002062c  test    rdx, rdx
0x18002062f  jz      short loc_18002064B
0x180020631  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020638  lea     r8, aIpv6cpprojecti; "Ipv6cpProjectionNotification"
0x18002063f  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002064b  mov     r14d, [rdi+0A8h]
0x180020652  test    r14b, 2
0x180020656  jz      loc_180020E6D
0x18002065c  xor     edx, edx; Val
0x18002065e  lea     rcx, [rsp+0D70h+var_D10]; void *
0x180020663  mov     r8d, 4B8h; Size
0x180020669  mov     r12d, r13d
0x18002066c  call    memset_0
0x180020671  cmp     dword ptr [rdi+20h], 2
0x180020675  mov     [rsp+0D70h+var_D10], 4B0h
0x18002067d  jnz     short loc_180020686
0x18002067f  mov     ebx, 2
0x180020684  jmp     short loc_18002068F
0x180020686  cmp     [rdi], r13d
0x180020689  mov     ebx, r13d
0x18002068c  setz    bl
0x18002068f  mov     [rsp+0D70h+var_D0C], ebx
0x180020693  test    r14b, 4
0x180020697  jz      short loc_1800206A1
0x180020699  mov     [rsp+0D70h+var_D04], 1
0x1800206a1  mov     rax, [rdi+48h]
0x1800206a5  lea     r15, [rdi+80Ch]
0x1800206ac  mov     [r15], r13d
0x1800206af  mov     [rbp+0C70h+var_AC0], rax
0x1800206b6  test    ebx, ebx
0x1800206b8  jnz     short loc_1800206F1
0x1800206ba  mov     rcx, r15
0x1800206bd  call    RasPPPGetNewSubInterfaceIndex
0x1800206c2  mov     esi, eax
0x1800206c4  test    eax, eax
0x1800206c6  jz      short loc_1800206E4
0x1800206c8  cmp     qword ptr cs:xmmword_18004C800, r13
0x1800206cf  jz      loc_180020E2A
0x1800206d5  mov     r8d, eax
0x1800206d8  lea     rdx, aIpv6cpGetnewsu; "IPV6CP: GetNewSubInterfaceIndex: failed"...
0x1800206df  jmp     loc_180020BED
0x1800206e4  mov     eax, [r15]
0x1800206e7  mov     ebx, [rsp+0D70h+var_D0C]
0x1800206eb  mov     [rsp+0D70h+var_CFC], eax
0x1800206ef  jmp     short loc_1800206F6
0x1800206f1  mov     [rsp+0D70h+var_CFC], r13d
0x1800206f6  cmp     qword ptr cs:xmmword_18004C800+8, r13
0x1800206fd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180020704  mov     eax, [rdi+18h]
0x180020707  movups  xmm1, xmmword ptr [rdi+840h]
0x18002070e  mov     [rsp+0D70h+var_D00], eax
0x180020712  movdqu  [rbp+0C70h+var_86C], xmm0
0x18002071a  mov     [rbp+0C70h+var_CDC], 1
0x180020721  movups  xmm0, xmmword ptr [rdi+834h]
0x180020728  movups  xmmword ptr [rbp+0C70h+var_AAC], xmm0
0x18002072f  movups  xmmword ptr [rbp+0C70h+var_AAC+0Ch], xmm1
0x180020736  jz      short loc_180020782
0x180020738  mov     r9d, [rbp+0C70h+var_AC4]
0x18002073f  lea     rdx, aIpv6cpRasactiv; "IPv6CP: RasActivateRoute(u=%x,a=%x)..."
0x180020746  mov     r8d, ebx
0x180020749  mov     word ptr [rbp+0C70h+var_850], r13w
0x180020751  lea     rcx, [rbp+0C70h+var_850]
0x180020758  call    FormatRRASErrorString
0x18002075d  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020764  lea     r8, [rbp+0C70h+var_850]
0x18002076b  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020772  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002077e  mov     ebx, [rsp+0D70h+var_D0C]
0x180020782  lea     r14, [rdi+2C0h]
0x180020789  xor     edx, edx; Val
0x18002078b  mov     rcx, r14; void *
0x18002078e  mov     r8d, 218h; Size
0x180020794  call    memset_0
0x180020799  cmp     ebx, 1
0x18002079c  jnz     loc_18002089C
0x1800207a2  lea     r8, [rdi+70Ch]; lpMultiByteStr
0x1800207a9  cmp     [r8], r13b
0x1800207ac  jz      short loc_18002082C
0x1800207ae  mov     [rsp+0D70h+cchWideChar], 0FEh; cchWideChar
0x1800207b6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800207ba  xor     edx, edx; dwFlags
0x1800207bc  mov     [rsp+0D70h+lpWideCharStr], r14; lpWideCharStr
0x1800207c1  xor     ecx, ecx; CodePage
0x1800207c3  call    cs:__imp_MultiByteToWideChar
0x1800207c9  test    eax, eax
0x1800207cb  jnz     short loc_180020824
0x1800207cd  cmp     qword ptr cs:xmmword_18004C800, r13
0x1800207d4  jz      loc_180020E6D
0x1800207da  mov     word ptr [rbp+0C70h+var_850], r13w
0x1800207e2  call    cs:__imp_GetLastError
0x1800207e8  mov     r8d, eax
0x1800207eb  lea     rdx, aIpcpMultibytet; "IPCP:MultiByteToWideChar failed. Error "...
0x1800207f2  lea     rcx, [rbp+0C70h+var_850]
0x1800207f9  call    FormatRRASErrorString
0x1800207fe  mov     rdx, qword ptr cs:xmmword_18004C800
0x180020805  lea     r8, [rbp+0C70h+var_850]
0x18002080c  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020813  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002081a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002081f  jmp     loc_180020E6D
0x180020824  mov     [rdi+4BEh], r13w
0x18002082c  mov     rcx, [rdi+8]
0x180020830  lea     rbx, [rdi+2BCh]
0x180020837  mov     rdx, rbx
0x18002083a  call    cs:__imp_RasAllocInterfaceLuidIndex
0x180020840  test    eax, eax
0x180020842  mov     esi, eax
0x180020844  setz    r12b
0x180020848  cmp     qword ptr cs:xmmword_18004C800+8, r13
0x18002084f  jz      short loc_180020893
0x180020851  mov     r8d, [rbx]
0x180020854  lea     rdx, aIpv6cpprojecti_0; "Ipv6cpProjectionNotification: RasAlloca"...
0x18002085b  mov     r9d, eax
0x18002085e  mov     word ptr [rbp+0C70h+var_850], r13w
0x180020866  lea     rcx, [rbp+0C70h+var_850]
0x18002086d  call    FormatRRASErrorString
0x180020872  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020879  lea     r8, [rbp+0C70h+var_850]
0x180020880  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020887  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002088e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020893  test    esi, esi
0x180020895  jz      short loc_1800208F0
0x180020897  jmp     loc_180020E2A
0x18002089c  test    ebx, ebx
0x18002089e  jnz     short loc_1800208F0
0x1800208a0  lea     rbx, [rdi+824h]
0x1800208a7  mov     dword ptr [rsp+0D70h+var_D40], 1
0x1800208af  mov     rcx, rbx
0x1800208b2  lea     rdx, [rsp+0D70h+var_D40]
0x1800208b7  call    NsiGetCompartmentIdForRoutingDomain
0x1800208bc  mov     esi, eax
0x1800208be  test    eax, eax
0x1800208c0  jz      short loc_1800208DE
0x1800208c2  cmp     qword ptr cs:xmmword_18004C800, r13
0x1800208c9  jz      loc_180020E2A
0x1800208cf  mov     r8d, eax
0x1800208d2  lea     rdx, aIpv6cpprojecti_3; "Ipv6cpProjectionNotification: NsiGetCom"...
0x1800208d9  jmp     loc_180020BED
0x1800208de  movups  xmm0, xmmword ptr [rbx]
0x1800208e1  mov     eax, dword ptr [rsp+0D70h+var_D40]
0x1800208e5  mov     [rbp+0C70h+var_CDC], eax
0x1800208e8  movdqu  [rbp+0C70h+var_86C], xmm0
0x1800208f0  mov     eax, [rdi+2BCh]
0x1800208f6  lea     r8, [rdi+4E8h]; pszSrc
0x1800208fd  mov     [rdi+4DCh], eax
0x180020903  cmp     [r8], r13w
0x180020907  jz      short loc_18002091C
0x180020909  mov     edx, 111h; cchDest
0x18002090e  lea     rcx, [rbp+0C70h+pszDest]; pszDest
0x180020915  call    StringCchCopyW
0x18002091a  jmp     short loc_180020924
0x18002091c  mov     [rbp+0C70h+pszDest], r13w
0x180020924  mov     rcx, [rdi+8]
0x180020928  lea     r8, [rdi+0B4h]
0x18002092f  mov     rax, qword ptr cs:xmmword_18004C440+8
0x180020936  lea     r9, [rsp+0D70h+var_D10]
0x18002093b  mov     edx, 86DDh
0x180020940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020945  cmp     qword ptr cs:xmmword_18004C800+8, r13
0x18002094c  mov     esi, eax
0x18002094e  jz      short loc_18002098F
0x180020950  mov     r8d, eax
0x180020953  mov     word ptr [rbp+0C70h+var_850], r13w
0x18002095b  lea     rdx, aIpv6cpprojecti_2; "Ipv6cpProjectionNotification: RasActiva"...
0x180020962  lea     rcx, [rbp+0C70h+var_850]
0x180020969  call    FormatRRASErrorString
0x18002096e  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020975  lea     r8, [rbp+0C70h+var_850]
0x18002097c  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020983  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002098a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002098f  test    esi, esi
0x180020991  jnz     loc_180020E2A
0x180020997  or      dword ptr [rdi+0A8h], 1
0x18002099e  cmp     [rdi+4D8h], r13d
0x1800209a5  jz      short loc_1800209AF
0x1800209a7  bts     dword ptr [rdi+0A8h], 7
0x1800209af  cmp     [rsp+0D70h+var_D0C], 2
0x1800209b4  jnz     short loc_1800209C2
0x1800209b6  mov     eax, [rdi+2BCh]
0x1800209bc  mov     [rdi+4DCh], eax
0x1800209c2  mov     edx, 5Ch ; '\'; Ch
0x1800209c7  lea     rcx, [rdi+1BCh]; Str
0x1800209ce  call    cs:__imp_wcschr
0x1800209d4  mov     [rdi+4E0h], rax
0x1800209db  test    rax, rax
0x1800209de  jnz     short loc_180020A0D
0x1800209e0  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x1800209e7  test    rdx, rdx
0x1800209ea  jz      short loc_180020A06
0x1800209ec  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800209f3  lea     r8, aIpv6cpNoDevice; "IPv6CP: No device?"
0x1800209fa  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a06  mov     esi, 57h ; 'W'
0x180020a0b  jmp     short loc_180020A18
0x180020a0d  add     rax, 2
0x180020a11  mov     [rdi+4E0h], rax
0x180020a18  mov     r14d, 0FFFFFFh
0x180020a1e  cmp     [rdi], r13d
0x180020a21  jz      short loc_180020A2D
0x180020a23  cmp     dword ptr [rdi+20h], 2
0x180020a27  jnz     loc_180020CD2
0x180020a2d  mov     rcx, rdi
0x180020a30  call    ApplyIpcpV6Settings
0x180020a35  test    byte ptr [rdi+0A8h], 8
0x180020a3c  mov     ecx, 10010h
0x180020a41  mov     rdx, [rdi+4E0h]
0x180020a48  jz      short loc_180020A6B
0x180020a4a  mov     r8d, 1
0x180020a50  call    cs:__imp_DnsSetConfigDword
0x180020a56  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020a5d  test    rdx, rdx
0x180020a60  jz      short loc_180020A9A
0x180020a62  lea     r8, aDnsenabledynam; "DnsEnableDynamicRegistration"
0x180020a69  jmp     short loc_180020A87
0x180020a6b  xor     r8d, r8d
0x180020a6e  call    cs:__imp_DnsSetConfigDword
0x180020a74  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020a7b  test    rdx, rdx
0x180020a7e  jz      short loc_180020A9A
0x180020a80  lea     r8, aDnsdisabledyna; "DnsDisableDynamicRegistration"
0x180020a87  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020a8e  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a9a  test    byte ptr [rdi+0A8h], 10h
0x180020aa1  mov     ecx, 0Ah
0x180020aa6  mov     rdx, [rdi+4E0h]
0x180020aad  jz      short loc_180020ACE
0x180020aaf  lea     r8d, [rcx-9]
0x180020ab3  call    cs:__imp_DnsSetConfigDword
0x180020ab9  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020ac0  test    rdx, rdx
0x180020ac3  jz      short loc_180020AFD
0x180020ac5  lea     r8, aDnsenableadapt; "DnsEnableAdapterDomainNameRegistration"
0x180020acc  jmp     short loc_180020AEA
0x180020ace  xor     r8d, r8d
0x180020ad1  call    cs:__imp_DnsSetConfigDword
0x180020ad7  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180020ade  test    rdx, rdx
0x180020ae1  jz      short loc_180020AFD
0x180020ae3  lea     r8, aDnsdisableadap; "DnsDisableAdapterDomainNameRegistration"
0x180020aea  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020af1  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020afd  cmp     [rdi], r13d
0x180020b00  jnz     loc_180020CD2
0x180020b06  test    dword ptr [rdi+0A8h], 100h
0x180020b10  jz      short loc_180020B83
0x180020b12  mov     rax, [rdi+48h]
0x180020b16  lea     rcx, [rdi+810h]
0x180020b1d  mov     [rdi+818h], rax
0x180020b24  cmp     [rcx], r13
0x180020b27  jz      short loc_180020B83
0x180020b29  mov     r8d, [rdi+820h]
0x180020b30  mov     edx, [rdi+4DCh]
0x180020b36  call    SetIPv6AddressOnInterface
0x180020b3b  cmp     qword ptr cs:xmmword_18004C800, r13
0x180020b42  jz      short loc_180020B83
0x180020b44  mov     r8d, eax
0x180020b47  mov     word ptr [rbp+0C70h+var_850], r13w
0x180020b4f  lea     rdx, aIpv6PrefixAndA; "Ipv6 prefix and address plumbig %d"
0x180020b56  lea     rcx, [rbp+0C70h+var_850]
0x180020b5d  call    FormatRRASErrorString
0x180020b62  mov     rdx, qword ptr cs:xmmword_18004C800
0x180020b69  lea     r8, [rbp+0C70h+var_850]
0x180020b70  mov     rcx, cs:gRasIpv6cpEtwContext
0x180020b77  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180020b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b83  cmp     [rdi], r13d
0x180020b86  jnz     loc_180020CD2
0x180020b8c  mov     eax, [rdi+0A8h]
0x180020b92  test    al, 40h
0x180020b94  jnz     loc_180020CD2
0x180020b9a  mov     ebx, [rdi+4DCh]
  ... truncated ...
```
