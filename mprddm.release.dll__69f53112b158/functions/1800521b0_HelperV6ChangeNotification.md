# HelperV6ChangeNotification

- ea: `0x1800521b0`
- end: `0x180052ae3`
- name: `HelperV6ChangeNotification`
- size: `2355`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b520`
- `0x180056f10`

## callees

- `0x1800521b0`
- `0x180052b74`
- `0x180052d5c`
- `0x180055e54`
- `0x18005a844`
- `0x18005ad18`
- `0x18005adcc`
- `0x18005b290`
- `0x18005ba30`
- `0x18005c090`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180052673`
- `KERNEL32!LeaveCriticalSection` at `0x1800528c3`
- `KERNEL32!LeaveCriticalSection` at `0x180052a3f`
- `KERNEL32!LeaveCriticalSection` at `0x180052673`
- `KERNEL32!LeaveCriticalSection` at `0x1800528c3`
- `KERNEL32!LeaveCriticalSection` at `0x180052a3f`
- `KERNEL32!EnterCriticalSection` at `0x180052539`
- `KERNEL32!EnterCriticalSection` at `0x18005269f`
- `KERNEL32!EnterCriticalSection` at `0x1800528ef`
- `KERNEL32!EnterCriticalSection` at `0x180052539`
- `KERNEL32!EnterCriticalSection` at `0x18005269f`
- `KERNEL32!EnterCriticalSection` at `0x1800528ef`
- `ADVAPI32!RegCloseKey` at `0x1800524ed`
- `ADVAPI32!RegCloseKey` at `0x1800524ed`
- `ADVAPI32!RegOpenKeyExA` at `0x180052357`
- `ADVAPI32!RegOpenKeyExA` at `0x180052357`
- `ADVAPI32!RegQueryValueExA` at `0x18005239b`
- `ADVAPI32!RegQueryValueExA` at `0x1800523e1`
- `ADVAPI32!RegQueryValueExA` at `0x180052478`
- `ADVAPI32!RegQueryValueExA` at `0x18005239b`
- `ADVAPI32!RegQueryValueExA` at `0x1800523e1`
- `ADVAPI32!RegQueryValueExA` at `0x180052478`

## string_xrefs

- `0x180052326`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x180052459`: `AllowNetworkAccess`
- `0x1800524ac`: `AllowNetworkAccess`

## pseudocode

```c
void __fastcall HelperV6ChangeNotification(GUID *a1)
{
  int v1; // r14d
  int v3; // r13d
  struct _IPv6PREFIX_POOL *v4; // rdi
  _QWORD *v5; // rsi
  int v6; // r12d
  __m128i v7; // xmm6
  __int64 v8; // rdx
  int v9; // r15d
  int v10; // eax
  int RoutingDomainAddressPool; // edx
  BOOL v12; // r14d
  struct _IPv6PREFIX_POOL *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  const wchar_t *v18; // rdx
  int v19; // edx
  struct _IPv6PREFIX_POOL *v20; // rcx
  BOOL v21; // esi
  unsigned int v22; // eax
  GUID v23; // xmm0
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  BYTE Data[8]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v28[3]; // [rsp+40h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-A0h] BYREF
  struct _IPv6PREFIX_POOL *v32; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v33[2]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v34[4]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-40h]
  int v36; // [rsp+D0h] [rbp-38h]
  wchar_t v37; // [rsp+D4h] [rbp-34h]
  __int16 v38; // [rsp+D6h] [rbp-32h]
  int v39; // [rsp+D8h] [rbp-30h] BYREF
  char v40[2044]; // [rsp+DCh] [rbp-2Ch] BYREF

  v1 = 0;
  v34[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v36 = *(_DWORD *)L"0}";
  v3 = 0;
  v4 = 0;
  v34[2] = *(_OWORD *)L"000-0000-000000000000}";
  v5 = 0;
  v6 = 0;
  v34[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v7 = 0;
  v37 = a00000000000000[38];
  v35 = *(_QWORD *)L"00000}";
  *(_DWORD *)Data = 1;
  v32 = 0;
  cbData[0] = 0;
  hKey = 0;
  cbData[1] = 0;
  v33[0] = 0;
  v34[3] = *(_OWORD *)L"-000000000000}";
  v38 = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v9 = dword_1800CF650;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    v1 = 1;
  else
    MprConvertGuidToString(a1, v8, v34);
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v39) = 0;
    FormatRRASErrorString(&v39, L"HelperV6ChangeNotification RDID: %ws", v34);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v39);
  }
  if ( v9 && !v1 )
    goto LABEL_23;
  v3 = dword_1800D0930;
  v6 = HIDWORD(qword_1800D08F0);
  v7 = (__m128i)pclsid;
  dword_1800D0938 = 1;
  *a1 = GUID_NULL;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6",
          0,
          0x20019u,
          &hKey) )
  {
    cbData[0] = 4;
    if ( RegQueryValueExA(hKey, "UseDhcpAddressing", 0, 0, Data, cbData) )
      *(_DWORD *)Data = 1;
    cbData[0] = 4;
    if ( !RegQueryValueExA(hKey, "AdvertiseDefaultRoute", 0, 0, (LPBYTE)&cbData[1], cbData) )
      dword_1800D0938 = cbData[1];
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"%hs: %d", "AdvertiseDefaultRoute");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v39);
    }
    cbData[0] = 4;
    if ( !RegQueryValueExA(hKey, "AllowNetworkAccess", 0, 0, (LPBYTE)&cbData[1], cbData) )
      dword_1800D0934 = cbData[1];
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"%hs: %d", "AllowNetworkAccess");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v39);
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v9 )
  {
LABEL_23:
    v10 = 0;
    *(_DWORD *)Data = 0;
  }
  else
  {
    v10 = *(_DWORD *)Data;
  }
  if ( !v10 )
  {
    *(GUID *)&v28[1] = *a1;
    RasStatIpv6CreatePrefixList(&v28[1], &v32);
    v4 = v32;
  }
  EnterCriticalSection(&RasSrvrCriticalSection);
  LODWORD(v32) = 4;
  LODWORD(v31) = 0;
  RasRoutingDomainGetConfigParam(a1, 3, &v32, &v31);
  *(GUID *)&v28[1] = *a1;
  if ( (_DWORD)v31 )
  {
    RasSrvrEnableIpv6Router(&v28[1], (unsigned int)dword_1800D0934);
    if ( v9 && !v1 )
    {
      *(GUID *)&v28[1] = *a1;
      RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v28[1], 2, v33);
      v12 = RoutingDomainAddressPool == 0;
      if ( !RoutingDomainAddressPool && v33[0] )
        v5 = *(_QWORD **)(v33[0] + 40LL);
      v13 = v4;
      while ( v5 )
      {
        if ( !v13 || v5[1] != *((_QWORD *)v13 + 1) || v5[3] != *((_QWORD *)v13 + 3) )
          goto LABEL_40;
        v5 = (_QWORD *)*v5;
        v13 = *(struct _IPv6PREFIX_POOL **)v13;
      }
      if ( !v13 )
        goto LABEL_52;
LABEL_40:
      if ( !RoutingDomainAddressPool )
      {
        *(GUID *)&v28[1] = *a1;
        v14 = RasReleaseRoutingDomainAddressPool(&v28[1]);
        if ( v14 )
        {
          if ( (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v39) = 0;
            FormatRRASErrorString(
              &v39,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v14);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v39);
          }
        }
        else
        {
          v12 = 0;
        }
      }
      LeaveCriticalSection(&RasSrvrCriticalSection);
      *(GUID *)&v28[1] = *a1;
      RasIpv6SrvrStop((struct _GUID *)&v28[1]);
      EnterCriticalSection(&RasSrvrCriticalSection);
      *(GUID *)&v28[1] = *a1;
      v15 = RasStatv6AddRoutingDomainAddressPool(v4);
      if ( v15 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v15);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
      }
      else
      {
        v4 = 0;
      }
      *(GUID *)&v28[1] = *a1;
      v16 = RasIpv6SrvrStart((struct _GUID *)&v28[1]);
      if ( v16 && (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"RasSrvrStart failed and returned %d", v16);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
LABEL_52:
      if ( !v12 )
        goto LABEL_93;
      *(GUID *)&v28[1] = *a1;
      v17 = RasReleaseRoutingDomainAddressPool(&v28[1]);
      if ( !v17 || !(_QWORD)xmmword_1800D0740 )
        goto LABEL_93;
      v18 = L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d";
      goto LABEL_99;
    }
    *(GUID *)&v28[1] = *a1;
    v19 = RasGetRoutingDomainAddressPool(&v28[1], 2, v33);
    if ( !v19 && v33[0] )
      v5 = *(_QWORD **)(v33[0] + 40LL);
    if ( v3 != *(_DWORD *)Data )
      goto LABEL_73;
    if ( !*(_DWORD *)Data )
    {
      v20 = v4;
      while ( v5 )
      {
        if ( !v20 || v5[1] != *((_QWORD *)v20 + 1) || v5[3] != *((_QWORD *)v20 + 3) )
          goto LABEL_73;
        v5 = (_QWORD *)*v5;
        v20 = *(struct _IPv6PREFIX_POOL **)v20;
      }
      if ( v20 )
        goto LABEL_73;
    }
    v21 = v19 == 0;
    if ( *(_DWORD *)Data )
    {
      if ( v6 != HIDWORD(qword_1800D08F0)
        || v6
        && (v7.m128i_i64[0] != *(_QWORD *)&pclsid.Data1 || _mm_srli_si128(v7, 8).m128i_u64[0] != *(_QWORD *)pclsid.Data4) )
      {
LABEL_73:
        v21 = v19 == 0;
        if ( !v19 )
        {
          *(GUID *)&v28[1] = *a1;
          v22 = RasReleaseRoutingDomainAddressPool(&v28[1]);
          if ( v22 )
          {
            if ( (_QWORD)xmmword_1800D0740 )
            {
              LOWORD(v39) = 0;
              FormatRRASErrorString(
                &v39,
                L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
                v22);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800D0740,
                &v39);
            }
          }
          else
          {
            v21 = 0;
          }
        }
        LeaveCriticalSection(&RasSrvrCriticalSection);
        *(GUID *)&v28[1] = *a1;
        RasIpv6SrvrStop((struct _GUID *)&v28[1]);
        EnterCriticalSection(&RasSrvrCriticalSection);
        v23 = *a1;
        dword_1800D0930 = *(_DWORD *)Data;
        *(GUID *)&v28[1] = v23;
        v24 = RasStatv6AddRoutingDomainAddressPool(v4);
        if ( v24 )
        {
          if ( (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v39) = 0;
            FormatRRASErrorString(&v39, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v24);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v39);
          }
        }
        else
        {
          v4 = 0;
        }
        *(GUID *)&v28[1] = *a1;
        v25 = RasIpv6SrvrStart((struct _GUID *)&v28[1]);
        if ( v25 && (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"RasSrvrStart failed and returned %d", v25);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
      }
    }
    if ( v21 )
    {
      *(GUID *)&v28[1] = *a1;
      v26 = RasReleaseRoutingDomainAddressPool(&v28[1]);
      if ( v26 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v26);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
      }
    }
    if ( *(_DWORD *)Data )
      goto LABEL_93;
    if ( !v4 )
      goto LABEL_95;
    RasStatFreeAddrPool(v4);
LABEL_92:
    v4 = 0;
    goto LABEL_93;
  }
  dword_1800D0930 = *(_DWORD *)Data;
  v17 = RasStatv6AddRoutingDomainAddressPool(v4);
  if ( !v17 )
    goto LABEL_92;
  if ( !(_QWORD)xmmword_1800D0740 )
    goto LABEL_93;
  v18 = L"RasStatAddRoutingDomainv4AddressPool failed and returned %d";
LABEL_99:
  LOWORD(v39) = 0;
  FormatRRASErrorString(&v39, v18, v17);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
    gRasIpAddrMgmtEtwContext,
    xmmword_1800D0740,
    &v39);
LABEL_93:
  if ( v4 )
    RasStatFreeAddrPool(v4);
LABEL_95:
  LeaveCriticalSection(&RasSrvrCriticalSection);
}

```

## disassembly

```asm
0x1800521b0  mov     rax, rsp
0x1800521b3  mov     [rax+10h], rbx
0x1800521b7  mov     [rax+18h], rsi
0x1800521bb  mov     [rax+20h], rdi
0x1800521bf  push    rbp
0x1800521c0  push    r12
0x1800521c2  push    r13
0x1800521c4  push    r14
0x1800521c6  push    r15
0x1800521c8  lea     rbp, [rax-818h]
0x1800521cf  sub     rsp, 8F0h
0x1800521d6  movaps  xmmword ptr [rax-38h], xmm6
0x1800521da  mov     rax, cs:__security_cookie
0x1800521e1  xor     rax, rsp
0x1800521e4  mov     [rbp+810h+var_40], rax
0x1800521eb  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800521f2  xor     r14d, r14d
0x1800521f5  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x1800521fb  mov     rbx, rcx
0x1800521fe  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180052205  lea     rcx, [rbp+810h+var_83C]; void *
0x180052209  movaps  [rbp+810h+var_890], xmm0
0x18005220d  xor     edx, edx; Val
0x18005220f  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180052216  mov     r8d, 7FCh; Size
0x18005221c  mov     [rbp+810h+var_848], eax
0x18005221f  mov     r13d, r14d
0x180052222  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180052229  mov     edi, r14d
0x18005222c  movaps  [rbp+810h+var_870], xmm0
0x180052230  mov     esi, r14d
0x180052233  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x18005223b  mov     r12d, r14d
0x18005223e  movaps  [rbp+810h+var_880], xmm1
0x180052242  xorps   xmm6, xmm6
0x180052245  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18005224c  mov     [rbp+810h+var_844], ax
0x180052250  xor     eax, eax
0x180052252  movsd   [rbp+810h+var_850], xmm0
0x180052257  mov     dword ptr [rsp+910h+Data], 1
0x18005225f  mov     [rsp+910h+var_8A8], r14
0x180052264  mov     [rsp+910h+cbData], r14d
0x180052269  mov     [rsp+910h+hKey], r14
0x18005226e  mov     [rsp+910h+cbData+4], r14d
0x180052273  mov     [rsp+910h+var_8A0], r14
0x180052278  movaps  [rbp+810h+var_860], xmm1
0x18005227c  mov     [rbp+810h+var_842], ax
0x180052280  mov     [rbp+810h+var_840], r14d
0x180052284  call    memset_0
0x180052289  mov     rax, [rbx]
0x18005228c  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180052293  mov     r15d, cs:dword_1800CF650
0x18005229a  jnz     short loc_1800522AF
0x18005229c  mov     rax, [rbx+8]
0x1800522a0  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800522a7  jnz     short loc_1800522AF
0x1800522a9  lea     r14d, [rsi+1]
0x1800522ad  jmp     short loc_1800522BB
0x1800522af  lea     r8, [rbp+810h+var_890]
0x1800522b3  mov     rcx, rbx
0x1800522b6  call    MprConvertGuidToString
0x1800522bb  xor     edx, edx
0x1800522bd  cmp     qword ptr cs:xmmword_1800D0740, rdx
0x1800522c4  jz      short loc_1800522FE
0x1800522c6  mov     word ptr [rbp+810h+var_840], dx
0x1800522ca  lea     r8, [rbp+810h+var_890]
0x1800522ce  lea     rdx, aHelperv6change; "HelperV6ChangeNotification RDID: %ws"
0x1800522d5  lea     rcx, [rbp+810h+var_840]
0x1800522d9  call    FormatRRASErrorString
0x1800522de  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800522e5  lea     r8, [rbp+810h+var_840]
0x1800522e9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800522f0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800522f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522fc  xor     edx, edx
0x1800522fe  test    r15d, r15d
0x180052301  jz      short loc_18005230C
0x180052303  test    r14d, r14d
0x180052306  jz      loc_180052505
0x18005230c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180052313  mov     r13d, cs:dword_1800D0930
0x18005231a  lea     rax, [rsp+910h+hKey]
0x18005231f  mov     r12d, dword ptr cs:qword_1800D08F0+4
0x180052326  lea     rdx, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x18005232d  movups  xmm6, xmmword ptr cs:pclsid.Data1
0x180052334  mov     r9d, 20019h; samDesired
0x18005233a  mov     cs:dword_1800D0938, 1
0x180052344  xor     r8d, r8d; ulOptions
0x180052347  mov     [rsp+910h+phkResult], rax; phkResult
0x18005234c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052353  movdqu  xmmword ptr [rbx], xmm0
0x180052357  call    cs:__imp_RegOpenKeyExA
0x18005235e  nop     dword ptr [rax+rax+00h]
0x180052363  xor     edx, edx
0x180052365  test    eax, eax
0x180052367  jnz     loc_1800524E3
0x18005236d  mov     rcx, [rsp+910h+hKey]; hKey
0x180052372  lea     rax, [rsp+910h+cbData]
0x180052377  mov     [rsp+910h+lpcbData], rax; lpcbData
0x18005237c  lea     rdx, aUsedhcpaddress; "UseDhcpAddressing"
0x180052383  lea     rax, [rsp+910h+Data]
0x180052388  mov     [rsp+910h+cbData], 4
0x180052390  xor     r9d, r9d; lpType
0x180052393  mov     [rsp+910h+phkResult], rax; lpData
0x180052398  xor     r8d, r8d; lpReserved
0x18005239b  call    cs:__imp_RegQueryValueExA
0x1800523a2  nop     dword ptr [rax+rax+00h]
0x1800523a7  test    eax, eax
0x1800523a9  jz      short loc_1800523B3
0x1800523ab  mov     dword ptr [rsp+910h+Data], 1
0x1800523b3  mov     rcx, [rsp+910h+hKey]; hKey
0x1800523b8  lea     rax, [rsp+910h+cbData]
0x1800523bd  mov     [rsp+910h+lpcbData], rax; lpcbData
0x1800523c2  lea     rdx, aAdvertisedefau; "AdvertiseDefaultRoute"
0x1800523c9  lea     rax, [rsp+910h+cbData+4]
0x1800523ce  mov     [rsp+910h+cbData], 4
0x1800523d6  xor     r9d, r9d; lpType
0x1800523d9  mov     [rsp+910h+phkResult], rax; lpData
0x1800523de  xor     r8d, r8d; lpReserved
0x1800523e1  call    cs:__imp_RegQueryValueExA
0x1800523e8  nop     dword ptr [rax+rax+00h]
0x1800523ed  xor     ecx, ecx
0x1800523ef  test    eax, eax
0x1800523f1  jnz     short loc_180052401
0x1800523f3  mov     r9d, [rsp+910h+cbData+4]
0x1800523f8  mov     cs:dword_1800D0938, r9d
0x1800523ff  jmp     short loc_180052408
0x180052401  mov     r9d, cs:dword_1800D0938
0x180052408  cmp     qword ptr cs:xmmword_1800D0740, rcx
0x18005240f  jz      short loc_18005244A
0x180052411  mov     word ptr [rbp+810h+var_840], cx
0x180052415  lea     r8, aAdvertisedefau; "AdvertiseDefaultRoute"
0x18005241c  lea     rcx, [rbp+810h+var_840]
0x180052420  lea     rdx, aHsD; "%hs: %d"
0x180052427  call    FormatRRASErrorString
0x18005242c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180052433  lea     r8, [rbp+810h+var_840]
0x180052437  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005243e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005244a  mov     rcx, [rsp+910h+hKey]; hKey
0x18005244f  lea     rax, [rsp+910h+cbData]
0x180052454  mov     [rsp+910h+lpcbData], rax; lpcbData
0x180052459  lea     rdx, aAllownetworkac; "AllowNetworkAccess"
0x180052460  lea     rax, [rsp+910h+cbData+4]
0x180052465  mov     [rsp+910h+cbData], 4
0x18005246d  xor     r9d, r9d; lpType
0x180052470  mov     [rsp+910h+phkResult], rax; lpData
0x180052475  xor     r8d, r8d; lpReserved
0x180052478  call    cs:__imp_RegQueryValueExA
0x18005247f  nop     dword ptr [rax+rax+00h]
0x180052484  xor     edx, edx
0x180052486  test    eax, eax
0x180052488  jnz     short loc_180052498
0x18005248a  mov     r9d, [rsp+910h+cbData+4]
0x18005248f  mov     cs:dword_1800D0934, r9d
0x180052496  jmp     short loc_18005249F
0x180052498  mov     r9d, cs:dword_1800D0934
0x18005249f  cmp     qword ptr cs:xmmword_1800D0740, rdx
0x1800524a6  jz      short loc_1800524E3
0x1800524a8  mov     word ptr [rbp+810h+var_840], dx
0x1800524ac  lea     r8, aAllownetworkac; "AllowNetworkAccess"
0x1800524b3  lea     rdx, aHsD; "%hs: %d"
0x1800524ba  lea     rcx, [rbp+810h+var_840]
0x1800524be  call    FormatRRASErrorString
0x1800524c3  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800524ca  lea     r8, [rbp+810h+var_840]
0x1800524ce  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800524d5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800524dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524e1  xor     edx, edx
0x1800524e3  mov     rcx, [rsp+910h+hKey]; hKey
0x1800524e8  test    rcx, rcx
0x1800524eb  jz      short loc_180052500
0x1800524ed  call    cs:__imp_RegCloseKey
0x1800524f4  nop     dword ptr [rax+rax+00h]
0x1800524f9  xor     edx, edx
0x1800524fb  mov     [rsp+910h+hKey], rdx
0x180052500  test    r15d, r15d
0x180052503  jz      short loc_18005250D
0x180052505  mov     eax, edx
0x180052507  mov     dword ptr [rsp+910h+Data], edx
0x18005250b  jmp     short loc_180052511
0x18005250d  mov     eax, dword ptr [rsp+910h+Data]
0x180052511  test    eax, eax
0x180052513  jnz     short loc_180052532
0x180052515  movups  xmm0, xmmword ptr [rbx]
0x180052518  lea     rdx, [rsp+910h+var_8A8]
0x18005251d  lea     rcx, [rsp+910h+var_8D8+8]
0x180052522  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180052528  call    RasStatIpv6CreatePrefixList
0x18005252d  mov     rdi, [rsp+910h+var_8A8]
0x180052532  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180052539  call    cs:__imp_EnterCriticalSection
0x180052540  nop     dword ptr [rax+rax+00h]
0x180052545  xor     ecx, ecx
0x180052547  mov     dword ptr [rsp+910h+var_8A8], 4
0x18005254f  mov     dword ptr [rsp+910h+var_8B0], ecx
0x180052553  lea     r9, [rsp+910h+var_8B0]
0x180052558  lea     r8, [rsp+910h+var_8A8]
0x18005255d  lea     edx, [rcx+3]
0x180052560  mov     rcx, rbx
0x180052563  call    RasRoutingDomainGetConfigParam
0x180052568  movups  xmm0, xmmword ptr [rbx]
0x18005256b  xor     eax, eax
0x18005256d  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180052573  cmp     dword ptr [rsp+910h+var_8B0], eax
0x180052577  jz      loc_180052A81
0x18005257d  mov     edx, cs:dword_1800D0934
0x180052583  lea     rcx, [rsp+910h+var_8D8+8]
0x180052588  call    RasSrvrEnableIpv6Router
0x18005258d  test    r15d, r15d
0x180052590  jz      loc_18005279D
0x180052596  xor     r15d, r15d
0x180052599  test    r14d, r14d
0x18005259c  jnz     loc_1800527A0
0x1800525a2  movups  xmm0, xmmword ptr [rbx]
0x1800525a5  lea     r8, [rsp+910h+var_8A0]
0x1800525aa  lea     edx, [r15+2]
0x1800525ae  lea     rcx, [rsp+910h+var_8D8+8]
0x1800525b3  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x1800525b9  call    RasGetRoutingDomainAddressPool
0x1800525be  test    eax, eax
0x1800525c0  mov     r14d, r15d
0x1800525c3  mov     edx, eax
0x1800525c5  setz    r14b
0x1800525c9  test    eax, eax
0x1800525cb  jnz     short loc_1800525DB
0x1800525cd  mov     rcx, [rsp+910h+var_8A0]
0x1800525d2  test    rcx, rcx
0x1800525d5  jz      short loc_1800525DB
0x1800525d7  mov     rsi, [rcx+28h]
0x1800525db  mov     rcx, rdi
0x1800525de  test    rsi, rsi
0x1800525e1  jz      short loc_180052604
0x1800525e3  test    rcx, rcx
0x1800525e6  jz      short loc_18005260D
0x1800525e8  mov     rax, [rsi+8]
0x1800525ec  cmp     rax, [rcx+8]
0x1800525f0  jnz     short loc_18005260D
0x1800525f2  mov     rax, [rsi+18h]
0x1800525f6  cmp     rax, [rcx+18h]
0x1800525fa  jnz     short loc_18005260D
0x1800525fc  mov     rsi, [rsi]
0x1800525ff  mov     rcx, [rcx]
0x180052602  jmp     short loc_1800525DE
0x180052604  test    rcx, rcx
0x180052607  jz      loc_18005275F
0x18005260d  test    edx, edx
0x18005260f  jnz     short loc_18005266C
0x180052611  movups  xmm0, xmmword ptr [rbx]
0x180052614  lea     rcx, [rsp+910h+var_8D8+8]
0x180052619  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x18005261f  call    RasReleaseRoutingDomainAddressPool
0x180052624  test    eax, eax
0x180052626  jz      short loc_180052669
0x180052628  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18005262f  jz      short loc_18005266C
0x180052631  mov     r8d, eax
0x180052634  mov     word ptr [rbp+810h+var_840], r15w
0x180052639  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180052640  lea     rcx, [rbp+810h+var_840]
0x180052644  call    FormatRRASErrorString
0x180052649  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180052650  lea     r8, [rbp+810h+var_840]
0x180052654  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005265b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052667  jmp     short loc_18005266C
0x180052669  mov     r14d, r15d
0x18005266c  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180052673  call    cs:__imp_LeaveCriticalSection
0x18005267a  nop     dword ptr [rax+rax+00h]
0x18005267f  movups  xmm0, xmmword ptr [rbx]
0x180052682  xor     edx, edx
0x180052684  lea     rcx, [rsp+910h+var_8D8+8]; struct _GUID *
0x180052689  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x18005268f  lea     r8d, [rdx+1]
0x180052693  call    RasIpv6SrvrStop
0x180052698  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005269f  call    cs:__imp_EnterCriticalSection
0x1800526a6  nop     dword ptr [rax+rax+00h]
0x1800526ab  movups  xmm0, xmmword ptr [rbx]
0x1800526ae  lea     rdx, [rsp+910h+var_8D8+8]
0x1800526b3  mov     rcx, rdi; struct _IPv6PREFIX_POOL *
0x1800526b6  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x1800526bc  call    RasStatv6AddRoutingDomainAddressPool
0x1800526c1  test    eax, eax
0x1800526c3  jz      short loc_180052706
0x1800526c5  cmp     qword ptr cs:xmmword_1800D0740, r15
0x1800526cc  jz      short loc_180052709
0x1800526ce  mov     r8d, eax
0x1800526d1  mov     word ptr [rbp+810h+var_840], r15w
0x1800526d6  lea     rdx, aRasstataddrout; "RasStatAddRoutingDomainv4AddressPool fa"...
0x1800526dd  lea     rcx, [rbp+810h+var_840]
0x1800526e1  call    FormatRRASErrorString
0x1800526e6  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800526ed  lea     r8, [rbp+810h+var_840]
0x1800526f1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800526f8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
  ... truncated ...
```
