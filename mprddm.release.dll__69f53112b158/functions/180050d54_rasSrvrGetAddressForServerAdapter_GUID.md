# rasSrvrGetAddressForServerAdapter(_GUID)

- ea: `0x180050d54`
- end: `0x18005159d`
- name: `?rasSrvrGetAddressForServerAdapter@@YAKU_GUID@@@Z`
- size: `2121`
- prototype: `unsigned int __fastcall(struct _GUID *__struct_ptr)`
- caller_count: `4`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800538b0`
- `0x180054d50`
- `0x1800580c0`
- `0x1800582b0`

## callees

- `0x180027ec0`
- `0x180050d54`
- `0x180051888`
- `0x1800597d4`
- `0x18005aa10`
- `0x18005adcc`
- `0x18005af78`
- `0x18005e620`
- `0x180060b00`
- `0x18006b414`
- `0x18006e7e8`
- `0x18006e9f0`
- `0x180073f90`
- `0x1800755b8`
- `0x180079618`
- `0x1800796f8`
- `0x18007ef74`
- `0x180081d58`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180050f39`
- `KERNEL32!DeviceIoControl` at `0x180050f39`
- `KERNEL32!GetLastError` at `0x180050f49`
- `KERNEL32!GetLastError` at `0x180050f49`
- `KERNEL32!LeaveCriticalSection` at `0x18005155e`
- `KERNEL32!LeaveCriticalSection` at `0x18005155e`
- `KERNEL32!EnterCriticalSection` at `0x180050e43`
- `KERNEL32!EnterCriticalSection` at `0x180050e43`
- `ntdll!RtlIpv4AddressToStringA` at `0x1800513dd`
- `ntdll!RtlIpv4AddressToStringA` at `0x1800513dd`
- `rtutils!LogEventA` at `0x180051405`
- `rtutils!LogEventA` at `0x180051405`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x180051269`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x180051269`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18005123b`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18005123b`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x18005134f`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800514f8`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x18005134f`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800514f8`

## string_xrefs

- `0x18005137c`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`
- `0x180051523`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`
- `0x180050e88`: `Error %d in finding compartment for routing domain`
- `0x180050f68`: `Error %d mapping server adapter for compartment %d`
- `0x180050fd3`: `RasSrvrAdapterMapped, LuidIndex %d index = %d, Compartment = %d`
- `0x180051208`: `DirectAccess registry keys not found. Continuing in normal mode.`
- `0x18005129e`: `IsDirectAccessConfigured failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall rasSrvrGetAddressForServerAdapter(struct _GUID *a1)
{
  u_long S_addr; // r12d
  int v2; // r14d
  unsigned int NboServerIpv4Address; // esi
  unsigned __int64 v5; // r13
  __int64 v6; // rcx
  BOOL v7; // r15d
  unsigned int RoutingDomainConfigData; // eax
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  DWORD LastError; // eax
  CHAR *v12; // rbx
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  unsigned int Parameter; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  const wchar_t *v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // eax
  LPVOID lpOutBuffer; // [rsp+28h] [rbp-E0h]
  struct in_addr Addr; // [rsp+58h] [rbp-B0h] BYREF
  int v27; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-A0h] BYREF
  LPSTR plpwsSubStrings; // [rsp+70h] [rbp-98h] BYREF
  int v30; // [rsp+78h] [rbp-90h] BYREF
  struct in_addr v31; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v32; // [rsp+80h] [rbp-88h] BYREF
  int v33; // [rsp+84h] [rbp-84h]
  DWORD BytesReturned; // [rsp+88h] [rbp-80h] BYREF
  __int128 OutBuffer; // [rsp+90h] [rbp-78h] BYREF
  int v36; // [rsp+A0h] [rbp-68h]
  CHAR S[16]; // [rsp+A8h] [rbp-60h] BYREF
  struct _MIB_IPINTERFACE_ROW Row; // [rsp+C8h] [rbp-40h] BYREF
  int v39; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v40[2044]; // [rsp+1CCh] [rbp+C4h] BYREF
  _BYTE v41[528]; // [rsp+9C8h] [rbp+8C0h] BYREF

  LODWORD(v28) = 1;
  S_addr = 0;
  v31 = 0;
  Addr = 0;
  v2 = 0;
  v33 = 0;
  BytesReturned = 0;
  v32 = 0;
  NboServerIpv4Address = RasRdGetNboServerIpv4Address();
  memset_0(v41, 0, 0x204u);
  LODWORD(v5) = 0;
  v6 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v6 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_NULL.Data4;
  v39 = 0;
  v7 = v6 == 0;
  v36 = 0;
  OutBuffer = 0;
  memset_0(v40, 0, sizeof(v40));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"rasSrvrGetAddressForServerAdapter");
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !v7 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v28);
    v9 = RoutingDomainConfigData;
    if ( RoutingDomainConfigData )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"Error %d in finding compartment for routing domain", RoutingDomainConfigData);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
      goto LABEL_57;
    }
  }
  v30 = 0;
  v27 = 4;
  RasRoutingDomainGetConfigParam(a1, 4, &v27, &v30);
  if ( !v30 )
  {
    DWORD2(OutBuffer) = v28;
    plpwsSubStrings = 0;
    *(_QWORD *)&OutBuffer = 0xFFFFFFFF00000001uLL;
    if ( !DeviceIoControl(HelperWanArpHandle, 0x90018014, &OutBuffer, 0x14u, &OutBuffer, 0x14u, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_51;
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"Error %d mapping server adapter for compartment %d", LastError, DWORD2(OutBuffer));
      goto LABEL_50;
    }
    NsiConvertInterfaceIndexToLuid((char *)&OutBuffer + 4, &plpwsSubStrings);
    v12 = plpwsSubStrings;
    v5 = ((unsigned __int64)plpwsSubStrings >> 24) & 0xFFFFFF;
    v27 = ((unsigned __int64)plpwsSubStrings >> 24) & 0xFFFFFF;
    RasRoutingDomainSetConfigParam(a1, 7, 4, &v27);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LODWORD(lpOutBuffer) = DWORD2(OutBuffer);
      LOWORD(v39) = 0;
      FormatRRASErrorString(
        &v39,
        L"RasSrvrAdapterMapped, LuidIndex %d index = %d, Compartment = %d",
        (unsigned int)v5,
        DWORD1(OutBuffer));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v39);
    }
    if ( v7 )
    {
      *(_OWORD *)S = 0;
      memset_0(&Row, 0, 0x100u);
      plpwsSubStrings = v12;
      Parameter = GetParameter(
                    v14,
                    v13,
                    v15,
                    (unsigned int)&plpwsSubStrings,
                    (_DWORD)lpOutBuffer,
                    2,
                    (__int64)S,
                    16,
                    536);
      v17 = Parameter;
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"GetInterfaceGuid returns with 0x%x for index %d", Parameter, DWORD1(OutBuffer));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
      if ( !v17 )
      {
        v18 = DwAddLegacyKeysForInterface(S);
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(
            &v39,
            L"DwAddLegacyKeysForInterface returns with 0x%x for index %d",
            v18,
            DWORD1(OutBuffer));
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
        if ( (unsigned int)RegHelpStringFromGuid(S, &Row, 128) )
          DwBindServerToAdapter(&Row);
      }
    }
    v27 = 1;
    RasRoutingDomainSetConfigParam(a1, 4, 4, &v27);
    v2 = 1;
  }
  if ( NboServerIpv4Address )
  {
LABEL_27:
    *(struct _GUID *)S = *a1;
    v9 = rasSrvrSetIpAddressOnInterface((struct _GUID *)S, NboServerIpv4Address, v10);
    if ( v9 )
      goto LABEL_52;
    if ( !v2 )
      goto LABEL_61;
    v20 = IsDirectAccessConfigured(v19, &v32);
    v9 = v20;
    if ( v20 )
    {
      if ( v20 != 2 )
      {
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_52;
        v21 = L"IsDirectAccessConfigured failed with error 0x%x";
LABEL_39:
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, v21, v20);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
LABEL_52:
        if ( v33 )
        {
          if ( dword_1800D08DC )
          {
            RasDhcpReleaseAddress(S_addr);
          }
          else
          {
            *(struct _GUID *)S = *a1;
            RasStatReleaseAddress(S, S_addr);
          }
          RasTcpSetProxyArp(NboServerIpv4Address, 0, NboServerIpv4Address, v28);
        }
        goto LABEL_57;
      }
      v9 = 0;
      if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800D0740 + 1),
          L"DirectAccess registry keys not found. Continuing in normal mode.");
    }
    if ( v32 == 1 )
    {
      memset_0(&Row, 0, sizeof(Row));
      InitializeIpInterfaceEntry(&Row);
      Row.ForwardingEnabled = 1;
      Row.Family = 2;
      Row.InterfaceLuid.Value = ((unsigned int)v5 | 0x17000000LL) << 24;
      v20 = SetIpInterfaceEntry(&Row);
      v9 = v20;
      if ( v20 )
      {
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_52;
        v21 = L"Failed to enable IPv4 forwarding on the server interfarce. SetIpInterfaceEntry failed with error 0x%x.";
        goto LABEL_39;
      }
      if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800D0740 + 1),
          L"Successfully enabled IPv4 forwarding on the server interface.");
    }
    if ( v7 )
    {
      Addr = (struct in_addr)516;
      RasRoutingDomainGetConfigParam(a1, 6, &Addr, v41);
      v22 = DhcpNotifyConfigChange(0, v41, 0, 0, NboServerIpv4Address, -1, 0);
      v9 = v22;
      if ( v22 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", v41, v22);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
        v9 = 0;
      }
    }
    RasTcpSetProxyArp(NboServerIpv4Address, 1, NboServerIpv4Address, v28);
    if ( !v7
      || (Addr = (struct in_addr)NboServerIpv4Address,
          RtlIpv4AddressToStringA(&Addr, S),
          plpwsSubStrings = S,
          LogEventA(4u, 0x4E78u, 1u, &plpwsSubStrings),
          !(_QWORD)xmmword_1800D0740) )
    {
LABEL_51:
      if ( !v9 )
        goto LABEL_61;
      goto LABEL_52;
    }
    LODWORD(lpOutBuffer) = -1;
    LOWORD(v39) = 0;
    FormatRRASErrorString(
      &v39,
      L"Acquired IP address 0x%x(%hs) and subnet mask 0x%x for the server",
      NboServerIpv4Address,
      S,
      lpOutBuffer);
LABEL_50:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v39);
    goto LABEL_51;
  }
  *(struct _GUID *)S = *a1;
  v9 = rasSrvrAcquireAddressEx((unsigned int)S, -300481434, (unsigned int)&v31, (unsigned int)&Addr, 0);
  if ( !v9 )
  {
    S_addr = v31.S_un.S_addr;
    Addr = v31;
    v33 = 1;
    NboServerIpv4Address = v31.S_un.S_addr;
    RasRoutingDomainSetConfigParam(a1, 0, 4, &Addr);
    goto LABEL_27;
  }
LABEL_57:
  ResetIpAddressOnInterface((unsigned int)v5, NboServerIpv4Address);
  Addr = 0;
  RasRoutingDomainSetConfigParam(a1, 0, 4, &Addr);
  if ( v7 )
  {
    v23 = DhcpNotifyConfigChange(0, v41, 0, 0, 0, 0, 0);
    if ( v23 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", v41, v23);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
    }
  }
LABEL_61:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x180050d54  mov     rax, rsp
0x180050d57  mov     [rax+10h], rbx
0x180050d5b  mov     [rax+18h], rsi
0x180050d5f  mov     [rax+20h], rdi
0x180050d63  push    rbp
0x180050d64  push    r12
0x180050d66  push    r13
0x180050d68  push    r14
0x180050d6a  push    r15
0x180050d6c  lea     rbp, [rax-0B08h]
0x180050d73  sub     rsp, 0BE0h
0x180050d7a  mov     rax, cs:__security_cookie
0x180050d81  xor     rax, rsp
0x180050d84  mov     [rbp+0B00h+var_30], rax
0x180050d8b  xor     ebx, ebx
0x180050d8d  mov     dword ptr [rsp+0C00h+var_BA0], 1
0x180050d95  mov     r12d, ebx
0x180050d98  mov     [rsp+0C00h+var_B8C], ebx
0x180050d9c  mov     dword ptr [rsp+0C00h+Addr.S_un], ebx
0x180050da0  mov     r14d, ebx
0x180050da3  mov     [rsp+0C00h+var_B84], ebx
0x180050da7  mov     rdi, rcx
0x180050daa  mov     [rbp+0B00h+BytesReturned], ebx
0x180050dad  mov     [rsp+0C00h+var_B88], ebx
0x180050db1  call    RasRdGetNboServerIpv4Address
0x180050db6  xor     edx, edx; Val
0x180050db8  lea     rcx, [rbp+0B00h+var_240]; void *
0x180050dbf  mov     r8d, 204h; Size
0x180050dc5  mov     esi, eax
0x180050dc7  call    memset_0
0x180050dcc  mov     rcx, [rdi]
0x180050dcf  mov     r13d, ebx
0x180050dd2  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x180050dd9  jnz     short loc_180050DE6
0x180050ddb  mov     rcx, [rdi+8]
0x180050ddf  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x180050de6  test    rcx, rcx
0x180050de9  mov     [rbp+0B00h+var_A40], ebx
0x180050def  xorps   xmm0, xmm0
0x180050df2  lea     rcx, [rbp+0B00h+var_A3C]; void *
0x180050df9  mov     r15d, ebx
0x180050dfc  mov     r8d, 7FCh; Size
0x180050e02  setz    r15b
0x180050e06  xor     eax, eax
0x180050e08  xor     edx, edx; Val
0x180050e0a  mov     [rbp+0B00h+var_B68], eax
0x180050e0d  movups  [rbp+0B00h+OutBuffer], xmm0
0x180050e11  call    memset_0
0x180050e16  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x180050e1d  test    rdx, rdx
0x180050e20  jz      short loc_180050E3C
0x180050e22  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050e29  lea     r8, aRassrvrgetaddr; "rasSrvrGetAddressForServerAdapter"
0x180050e30  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e3c  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180050e43  call    cs:__imp_EnterCriticalSection
0x180050e4a  nop     dword ptr [rax+rax+00h]
0x180050e4f  test    r15d, r15d
0x180050e52  jnz     short loc_180050EC3
0x180050e54  lea     r9, [rsp+0C00h+var_BA0]
0x180050e59  mov     edx, 100h
0x180050e5e  lea     r8d, [r15+4]
0x180050e62  mov     rcx, rdi
0x180050e65  call    GetRoutingDomainConfigData
0x180050e6a  mov     ebx, eax
0x180050e6c  test    eax, eax
0x180050e6e  jz      short loc_180050EC1
0x180050e70  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180050e77  jz      loc_1800514B3
0x180050e7d  mov     r8d, eax
0x180050e80  mov     word ptr [rbp+0B00h+var_A40], r14w
0x180050e88  lea     rdx, aErrorDInFindin; "Error %d in finding compartment for rou"...
0x180050e8f  lea     rcx, [rbp+0B00h+var_A40]
0x180050e96  call    FormatRRASErrorString
0x180050e9b  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180050ea2  lea     r8, [rbp+0B00h+var_A40]
0x180050ea9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050eb0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ebc  jmp     loc_1800514B3
0x180050ec1  xor     ebx, ebx
0x180050ec3  lea     r9, [rsp+0C00h+var_B90]
0x180050ec8  mov     [rsp+0C00h+var_B90], ebx
0x180050ecc  lea     r8, [rsp+0C00h+var_BA8]
0x180050ed1  mov     [rsp+0C00h+var_BA8], 4
0x180050ed9  mov     edx, 4
0x180050ede  mov     rcx, rdi
0x180050ee1  call    RasRoutingDomainGetConfigParam
0x180050ee6  cmp     [rsp+0C00h+var_B90], ebx
0x180050eea  jnz     loc_180051155
0x180050ef0  mov     eax, dword ptr [rsp+0C00h+var_BA0]
0x180050ef4  lea     r8, [rbp+0B00h+OutBuffer]; lpInBuffer
0x180050ef8  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hDevice
0x180050eff  mov     r9d, 14h; nInBufferSize
0x180050f05  or      dword ptr [rbp+0B00h+OutBuffer+4], 0FFFFFFFFh
0x180050f09  mov     edx, 90018014h; dwIoControlCode
0x180050f0e  mov     dword ptr [rbp+0B00h+OutBuffer+8], eax
0x180050f11  lea     rax, [rbp+0B00h+BytesReturned]
0x180050f15  mov     [rsp+0C00h+lpOverlapped], r14; lpOverlapped
0x180050f1a  mov     [rsp+0C00h+lpBytesReturned], rax; lpBytesReturned
0x180050f1f  lea     rax, [rbp+0B00h+OutBuffer]
0x180050f23  mov     [rsp+0C00h+nOutBufferSize], r9d; nOutBufferSize
0x180050f28  mov     [rsp+0C00h+lpOutBuffer], rax; lpOutBuffer
0x180050f2d  mov     [rsp+0C00h+plpwsSubStrings], r14
0x180050f32  mov     dword ptr [rbp+0B00h+OutBuffer], 1
0x180050f39  call    cs:__imp_DeviceIoControl
0x180050f40  nop     dword ptr [rax+rax+00h]
0x180050f45  test    eax, eax
0x180050f47  jnz     short loc_180050F8B
0x180050f49  call    cs:__imp_GetLastError
0x180050f50  nop     dword ptr [rax+rax+00h]
0x180050f55  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180050f5c  mov     ebx, eax
0x180050f5e  jz      loc_180051462
0x180050f64  mov     r9d, dword ptr [rbp+0B00h+OutBuffer+8]
0x180050f68  lea     rdx, aErrorDMappingS; "Error %d mapping server adapter for com"...
0x180050f6f  mov     r8d, eax
0x180050f72  mov     word ptr [rbp+0B00h+var_A40], r14w
0x180050f7a  lea     rcx, [rbp+0B00h+var_A40]
0x180050f81  call    FormatRRASErrorString
0x180050f86  jmp     loc_180051441
0x180050f8b  lea     rdx, [rsp+0C00h+plpwsSubStrings]
0x180050f90  lea     rcx, [rbp+0B00h+OutBuffer+4]
0x180050f94  call    NsiConvertInterfaceIndexToLuid
0x180050f99  mov     rbx, [rsp+0C00h+plpwsSubStrings]
0x180050f9e  lea     r9, [rsp+0C00h+var_BA8]
0x180050fa3  mov     edx, 7
0x180050fa8  mov     r13, rbx
0x180050fab  shr     r13, 18h
0x180050faf  mov     rcx, rdi
0x180050fb2  and     r13d, 0FFFFFFh
0x180050fb9  mov     [rsp+0C00h+var_BA8], r13d
0x180050fbe  lea     r8d, [rdx-3]
0x180050fc2  call    RasRoutingDomainSetConfigParam
0x180050fc7  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180050fce  jz      short loc_18005101A
0x180050fd0  mov     eax, dword ptr [rbp+0B00h+OutBuffer+8]
0x180050fd3  lea     rdx, aRassrvradapter_0; "RasSrvrAdapterMapped, LuidIndex %d inde"...
0x180050fda  mov     r9d, dword ptr [rbp+0B00h+OutBuffer+4]
0x180050fde  lea     rcx, [rbp+0B00h+var_A40]
0x180050fe5  mov     r8d, r13d
0x180050fe8  mov     dword ptr [rsp+0C00h+lpOutBuffer], eax
0x180050fec  mov     word ptr [rbp+0B00h+var_A40], r14w
0x180050ff4  call    FormatRRASErrorString
0x180050ff9  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180051000  lea     r8, [rbp+0B00h+var_A40]
0x180051007  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005100e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005101a  test    r15d, r15d
0x18005101d  jz      loc_180051132
0x180051023  xorps   xmm0, xmm0
0x180051026  lea     rcx, [rbp+0B00h+Row]; void *
0x18005102a  xor     edx, edx; Val
0x18005102c  mov     r8d, 100h; Size
0x180051032  movups  xmmword ptr [rbp+0B00h+S], xmm0
0x180051036  call    memset_0
0x18005103b  mov     [rsp+0C00h+var_BC0], 218h
0x180051043  lea     rax, [rbp+0B00h+S]
0x180051047  mov     dword ptr [rsp+0C00h+lpOverlapped], 10h
0x18005104f  lea     r9, [rsp+0C00h+plpwsSubStrings]
0x180051054  mov     [rsp+0C00h+lpBytesReturned], rax
0x180051059  mov     [rsp+0C00h+nOutBufferSize], 2
0x180051061  mov     [rsp+0C00h+plpwsSubStrings], rbx
0x180051066  call    GetParameter
0x18005106b  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180051072  mov     ebx, eax
0x180051074  jz      short loc_1800510B9
0x180051076  mov     r9d, dword ptr [rbp+0B00h+OutBuffer+4]
0x18005107a  lea     rdx, aGetinterfacegu; "GetInterfaceGuid returns with 0x%x for "...
0x180051081  mov     r8d, eax
0x180051084  mov     word ptr [rbp+0B00h+var_A40], r14w
0x18005108c  lea     rcx, [rbp+0B00h+var_A40]
0x180051093  call    FormatRRASErrorString
0x180051098  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005109f  lea     r8, [rbp+0B00h+var_A40]
0x1800510a6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800510ad  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800510b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510b9  test    ebx, ebx
0x1800510bb  jnz     short loc_180051132
0x1800510bd  lea     rcx, [rbp+0B00h+S]
0x1800510c1  call    DwAddLegacyKeysForInterface
0x1800510c6  cmp     qword ptr cs:xmmword_1800D0740, r14
0x1800510cd  jz      short loc_180051112
0x1800510cf  mov     r9d, dword ptr [rbp+0B00h+OutBuffer+4]
0x1800510d3  lea     rdx, aDwaddlegacykey_5; "DwAddLegacyKeysForInterface returns wit"...
0x1800510da  mov     r8d, eax
0x1800510dd  mov     word ptr [rbp+0B00h+var_A40], r14w
0x1800510e5  lea     rcx, [rbp+0B00h+var_A40]
0x1800510ec  call    FormatRRASErrorString
0x1800510f1  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800510f8  lea     r8, [rbp+0B00h+var_A40]
0x1800510ff  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051106  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005110d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051112  mov     r8d, 80h
0x180051118  lea     rdx, [rbp+0B00h+Row]
0x18005111c  lea     rcx, [rbp+0B00h+S]
0x180051120  call    RegHelpStringFromGuid
0x180051125  test    eax, eax
0x180051127  jz      short loc_180051132
0x180051129  lea     rcx, [rbp+0B00h+Row]
0x18005112d  call    DwBindServerToAdapter
0x180051132  mov     ebx, 1
0x180051137  lea     r9, [rsp+0C00h+var_BA8]
0x18005113c  mov     rcx, rdi
0x18005113f  mov     [rsp+0C00h+var_BA8], ebx
0x180051143  lea     eax, [rbx+3]
0x180051146  mov     r8d, eax
0x180051149  mov     edx, eax
0x18005114b  call    RasRoutingDomainSetConfigParam
0x180051150  mov     r14d, ebx
0x180051153  xor     ebx, ebx
0x180051155  test    esi, esi
0x180051157  jnz     short loc_1800511B0
0x180051159  movaps  xmm0, xmmword ptr [rdi]
0x18005115c  lea     r9, [rsp+0C00h+Addr]
0x180051161  lea     r8, [rsp+0C00h+var_B8C]
0x180051166  movdqa  xmmword ptr [rbp+0B00h+S], xmm0
0x18005116b  mov     edx, 0EE170466h
0x180051170  mov     [rsp+0C00h+lpOutBuffer], rbx
0x180051175  lea     rcx, [rbp+0B00h+S]
0x180051179  call    rasSrvrAcquireAddressEx
0x18005117e  mov     ebx, eax
0x180051180  test    eax, eax
0x180051182  jnz     loc_1800514B0
0x180051188  mov     r12d, [rsp+0C00h+var_B8C]
0x18005118d  lea     r9, [rsp+0C00h+Addr]
0x180051192  xor     edx, edx
0x180051194  mov     dword ptr [rsp+0C00h+Addr.S_un], r12d
0x180051199  lea     r8d, [rax+4]
0x18005119d  mov     [rsp+0C00h+var_B84], 1
0x1800511a5  mov     rcx, rdi
0x1800511a8  mov     esi, r12d
0x1800511ab  call    RasRoutingDomainSetConfigParam
0x1800511b0  movaps  xmm0, xmmword ptr [rdi]
0x1800511b3  lea     rcx, [rbp+0B00h+S]; struct _GUID
0x1800511b7  mov     edx, esi; unsigned int
0x1800511b9  movdqa  xmmword ptr [rbp+0B00h+S], xmm0
0x1800511be  call    ?rasSrvrSetIpAddressOnInterface@@YAKU_GUID@@KK@Z; rasSrvrSetIpAddressOnInterface(_GUID,ulong,ulong)
0x1800511c3  mov     ebx, eax
0x1800511c5  test    eax, eax
0x1800511c7  jnz     loc_18005146C
0x1800511cd  test    r14d, r14d
0x1800511d0  jz      loc_180051557
0x1800511d6  lea     rdx, [rsp+0C00h+var_B88]
0x1800511db  call    IsDirectAccessConfigured
0x1800511e0  xor     r14d, r14d
0x1800511e3  mov     ebx, eax
0x1800511e5  test    eax, eax
0x1800511e7  jz      short loc_18005121B
0x1800511e9  cmp     eax, 2
0x1800511ec  jnz     loc_180051291
0x1800511f2  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x1800511f9  mov     ebx, r14d
0x1800511fc  test    rdx, rdx
0x1800511ff  jz      short loc_18005121B
0x180051201  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051208  lea     r8, aDirectaccessRe; "DirectAccess registry keys not found. C"...
0x18005120f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005121b  cmp     [rsp+0C00h+var_B88], 1
0x180051220  jnz     loc_180051308
0x180051226  xor     edx, edx; Val
0x180051228  lea     rcx, [rbp+0B00h+Row]; void *
0x18005122c  mov     r8d, 0A8h; Size
0x180051232  call    memset_0
0x180051237  lea     rcx, [rbp+0B00h+Row]; Row
0x18005123b  call    cs:__imp_InitializeIpInterfaceEntry
0x180051242  nop     dword ptr [rax+rax+00h]
0x180051247  mov     eax, 2
0x18005124c  mov     [rbp+0B00h+Row.ForwardingEnabled], 1
0x180051250  mov     [rbp+0B00h+Row.Family], ax
0x180051254  lea     rcx, [rbp+0B00h+Row]; Row
0x180051258  mov     eax, r13d
0x18005125b  or      rax, 17000000h
0x180051261  shl     rax, 18h
0x180051265  mov     qword ptr [rbp+0B00h+Row.InterfaceLuid], rax
0x180051269  call    cs:__imp_SetIpInterfaceEntry
0x180051270  nop     dword ptr [rax+rax+00h]
0x180051275  mov     ebx, eax
0x180051277  test    eax, eax
0x180051279  jz      short loc_1800512E2
0x18005127b  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180051282  jz      loc_18005146F
0x180051288  lea     rdx, aFailedToEnable; "Failed to enable IPv4 forwarding on the"...
0x18005128f  jmp     short loc_1800512A5
0x180051291  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180051298  jz      loc_18005146F
0x18005129e  lea     rdx, aIsdirectaccess; "IsDirectAccessConfigured failed with er"...
0x1800512a5  mov     r8d, eax
0x1800512a8  mov     word ptr [rbp+0B00h+var_A40], r14w
0x1800512b0  lea     rcx, [rbp+0B00h+var_A40]
0x1800512b7  call    FormatRRASErrorString
0x1800512bc  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800512c3  lea     r8, [rbp+0B00h+var_A40]
0x1800512ca  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800512d1  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
  ... truncated ...
```
