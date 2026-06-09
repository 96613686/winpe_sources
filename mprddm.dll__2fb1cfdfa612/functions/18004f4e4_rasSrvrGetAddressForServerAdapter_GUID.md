# rasSrvrGetAddressForServerAdapter(_GUID)

- ea: `0x18004f4e4`
- end: `0x18004fce5`
- name: `?rasSrvrGetAddressForServerAdapter@@YAKU_GUID@@@Z`
- size: `2049`
- prototype: `unsigned int __fastcall(struct _GUID *Buf1)`
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051e80`
- `0x180053230`
- `0x180056300`
- `0x1800564e0`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x18004f4e4`
- `0x18004ff9c`
- `0x1800578ec`
- `0x180058ab0`
- `0x180058e78`
- `0x180059030`
- `0x18005c3ec`
- `0x18005e6a0`
- `0x1800689f0`
- `0x18006bc40`
- `0x18006be30`
- `0x18007079c`
- `0x180071cec`
- `0x180075850`
- `0x18007593c`
- `0x18007a104`
- `0x18007ccd0`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18004f6bc`
- `KERNEL32!DeviceIoControl` at `0x18004f6bc`
- `KERNEL32!GetLastError` at `0x18004f6c6`
- `KERNEL32!GetLastError` at `0x18004f6c6`
- `KERNEL32!LeaveCriticalSection` at `0x18004fcba`
- `KERNEL32!LeaveCriticalSection` at `0x18004fcba`
- `KERNEL32!EnterCriticalSection` at `0x18004f5c3`
- `KERNEL32!EnterCriticalSection` at `0x18004f5c3`
- `ntdll!RtlIpv4AddressToStringA` at `0x18004fb48`
- `ntdll!RtlIpv4AddressToStringA` at `0x18004fb48`
- `rtutils!LogEventA` at `0x18004fb6a`
- `rtutils!LogEventA` at `0x18004fb6a`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18004f9d8`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18004f9d8`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18004f9b0`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18004f9b0`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x18004fabb`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x18004fc5a`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x18004fabb`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x18004fc5a`

## string_xrefs

- `0x18004fae2`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`
- `0x18004fc7f`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`
- `0x18004f603`: `Error %d in finding compartment for routing domain`
- `0x18004f6df`: `Error %d mapping server adapter for compartment %d`
- `0x18004f74a`: `RasSrvrAdapterMapped, LuidIndex %d index = %d, Compartment = %d`
- `0x18004f97d`: `DirectAccess registry keys not found. Continuing in normal mode.`
- `0x18004fa07`: `IsDirectAccessConfigured failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall rasSrvrGetAddressForServerAdapter(struct _GUID *Buf1)
{
  int v1; // r14d
  u_long S_addr; // r15d
  unsigned int NboServerIpv4Address; // edi
  unsigned __int64 v5; // r13
  BOOL v6; // r12d
  unsigned int RoutingDomainConfigData; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r8d
  DWORD LastError; // eax
  CHAR *v11; // rbx
  int v12; // edx
  int v13; // ecx
  int v14; // r8d
  unsigned int Parameter; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // eax
  const wchar_t *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // eax
  LPVOID lpOutBuffer; // [rsp+20h] [rbp-E0h]
  struct in_addr Addr; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  LPSTR plpwsSubStrings; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+70h] [rbp-90h] BYREF
  struct in_addr v30; // [rsp+74h] [rbp-8Ch] BYREF
  int v31; // [rsp+78h] [rbp-88h] BYREF
  int v32; // [rsp+7Ch] [rbp-84h]
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  __int128 OutBuffer; // [rsp+88h] [rbp-78h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  CHAR S[16]; // [rsp+A0h] [rbp-60h] BYREF
  struct _MIB_IPINTERFACE_ROW Row; // [rsp+C0h] [rbp-40h] BYREF
  int v38; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v39[2044]; // [rsp+1C4h] [rbp+C4h] BYREF
  _BYTE v40[528]; // [rsp+9C0h] [rbp+8C0h] BYREF

  v1 = 0;
  v27 = 1;
  S_addr = 0;
  v30 = 0;
  Addr = 0;
  BytesReturned = 0;
  v31 = 0;
  NboServerIpv4Address = RasRdGetNboServerIpv4Address();
  memset_0(v40, 0, 0x204u);
  LODWORD(v5) = 0;
  v38 = 0;
  v6 = memcmp_0(Buf1, &GUID_NULL, 0x10u) == 0;
  v35 = 0;
  OutBuffer = 0;
  memset_0(v39, 0, sizeof(v39));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"rasSrvrGetAddressForServerAdapter");
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !v6 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(Buf1, 256, 4, &v27);
    v8 = RoutingDomainConfigData;
    if ( RoutingDomainConfigData )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, L"Error %d in finding compartment for routing domain", RoutingDomainConfigData);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v38);
      }
      goto LABEL_55;
    }
  }
  v32 = 0;
  v29 = 0;
  v26 = 4;
  RasRoutingDomainGetConfigParam(Buf1, 4, &v26, &v29);
  if ( !v29 )
  {
    DWORD2(OutBuffer) = v27;
    plpwsSubStrings = 0;
    *(_QWORD *)&OutBuffer = 0xFFFFFFFF00000001uLL;
    if ( !DeviceIoControl(HelperWanArpHandle, 0x90018014, &OutBuffer, 0x14u, &OutBuffer, 0x14u, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_49;
      LOWORD(v38) = 0;
      FormatRRASErrorString(&v38, L"Error %d mapping server adapter for compartment %d", LastError, DWORD2(OutBuffer));
      goto LABEL_48;
    }
    NsiConvertInterfaceIndexToLuid((char *)&OutBuffer + 4, &plpwsSubStrings);
    v11 = plpwsSubStrings;
    v5 = ((unsigned __int64)plpwsSubStrings >> 24) & 0xFFFFFF;
    v26 = ((unsigned __int64)plpwsSubStrings >> 24) & 0xFFFFFF;
    RasRoutingDomainSetConfigParam(Buf1, 7, 4, &v26);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LODWORD(lpOutBuffer) = DWORD2(OutBuffer);
      LOWORD(v38) = 0;
      FormatRRASErrorString(
        &v38,
        L"RasSrvrAdapterMapped, LuidIndex %d index = %d, Compartment = %d",
        (unsigned int)v5,
        DWORD1(OutBuffer));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v38);
    }
    if ( v6 )
    {
      *(_OWORD *)S = 0;
      memset_0(&Row, 0, 0x100u);
      plpwsSubStrings = v11;
      Parameter = GetParameter(
                    v13,
                    v12,
                    v14,
                    (unsigned int)&plpwsSubStrings,
                    (_DWORD)lpOutBuffer,
                    2,
                    (__int64)S,
                    16,
                    536);
      v16 = Parameter;
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, L"GetInterfaceGuid returns with 0x%x for index %d", Parameter, DWORD1(OutBuffer));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v38);
      }
      if ( !v16 )
      {
        v17 = DwAddLegacyKeysForInterface(S);
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v38) = 0;
          FormatRRASErrorString(
            &v38,
            L"DwAddLegacyKeysForInterface returns with 0x%x for index %d",
            v17,
            DWORD1(OutBuffer));
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v38);
        }
        if ( (unsigned int)RegHelpStringFromGuid(S, &Row, 128) )
          DwBindServerToAdapter(&Row);
      }
    }
    v26 = 1;
    RasRoutingDomainSetConfigParam(Buf1, 4, 4, &v26);
    v1 = 1;
  }
  if ( NboServerIpv4Address )
  {
LABEL_25:
    *(struct _GUID *)S = *Buf1;
    v8 = rasSrvrSetIpAddressOnInterface((struct _GUID *)S, NboServerIpv4Address, v9);
    if ( v8 )
      goto LABEL_50;
    if ( !v1 )
      goto LABEL_59;
    v19 = IsDirectAccessConfigured(v18, &v31);
    v8 = v19;
    if ( v19 )
    {
      if ( v19 != 2 )
      {
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_50;
        v20 = L"IsDirectAccessConfigured failed with error 0x%x";
LABEL_37:
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, v20, v19);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v38);
LABEL_50:
        if ( v32 )
        {
          if ( dword_1800C98DC )
          {
            RasDhcpReleaseAddress(S_addr);
          }
          else
          {
            *(struct _GUID *)S = *Buf1;
            RasStatReleaseAddress(S, S_addr);
          }
          RasTcpSetProxyArp(NboServerIpv4Address);
        }
        goto LABEL_55;
      }
      v8 = 0;
      if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800C9740 + 1),
          L"DirectAccess registry keys not found. Continuing in normal mode.");
    }
    if ( v31 == 1 )
    {
      memset_0(&Row, 0, sizeof(Row));
      InitializeIpInterfaceEntry(&Row);
      Row.ForwardingEnabled = 1;
      Row.Family = 2;
      Row.InterfaceLuid.Value = ((unsigned int)v5 | 0x17000000LL) << 24;
      v19 = SetIpInterfaceEntry(&Row);
      v8 = v19;
      if ( v19 )
      {
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_50;
        v20 = L"Failed to enable IPv4 forwarding on the server interfarce. SetIpInterfaceEntry failed with error 0x%x.";
        goto LABEL_37;
      }
      if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800C9740 + 1),
          L"Successfully enabled IPv4 forwarding on the server interface.");
    }
    if ( v6 )
    {
      Addr = (struct in_addr)516;
      RasRoutingDomainGetConfigParam(Buf1, 6, &Addr, v40);
      v21 = DhcpNotifyConfigChange(0, v40, 0, 0, NboServerIpv4Address, -1, 0);
      v8 = v21;
      if ( v21 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v38) = 0;
          FormatRRASErrorString(&v38, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", v40, v21);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v38);
        }
        v8 = 0;
      }
    }
    RasTcpSetProxyArp(NboServerIpv4Address);
    if ( !v6
      || (plpwsSubStrings = 0,
          Addr = (struct in_addr)NboServerIpv4Address,
          RtlIpv4AddressToStringA(&Addr, S),
          plpwsSubStrings = S,
          LogEventA(4u, 0x4E78u, 1u, &plpwsSubStrings),
          !(_QWORD)xmmword_1800C9740) )
    {
LABEL_49:
      if ( !v8 )
        goto LABEL_59;
      goto LABEL_50;
    }
    LOWORD(v38) = 0;
    LODWORD(lpOutBuffer) = -1;
    FormatRRASErrorString(
      &v38,
      L"Acquired IP address 0x%x(%hs) and subnet mask 0x%x for the server",
      NboServerIpv4Address,
      S,
      lpOutBuffer);
LABEL_48:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v38);
    goto LABEL_49;
  }
  *(struct _GUID *)S = *Buf1;
  v8 = rasSrvrAcquireAddressEx((unsigned int)S, -300481434, (unsigned int)&v30, (unsigned int)&Addr, 0);
  if ( !v8 )
  {
    S_addr = v30.S_un.S_addr;
    Addr = v30;
    v32 = 1;
    NboServerIpv4Address = v30.S_un.S_addr;
    RasRoutingDomainSetConfigParam(Buf1, 0, 4, &Addr);
    goto LABEL_25;
  }
LABEL_55:
  ResetIpAddressOnInterface((unsigned int)v5, NboServerIpv4Address);
  Addr = 0;
  RasRoutingDomainSetConfigParam(Buf1, 0, 4, &Addr);
  if ( v6 )
  {
    v22 = DhcpNotifyConfigChange(0, v40, 0, 0, 0, 0, 0);
    if ( v22 )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", v40, v22);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v38);
      }
    }
  }
LABEL_59:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x18004f4e4  push    rbp
0x18004f4e6  push    rbx
0x18004f4e7  push    rsi
0x18004f4e8  push    rdi
0x18004f4e9  push    r12
0x18004f4eb  push    r13
0x18004f4ed  push    r14
0x18004f4ef  push    r15
0x18004f4f1  lea     rbp, [rsp-0AE8h]
0x18004f4f9  sub     rsp, 0BE8h
0x18004f500  mov     rax, cs:__security_cookie
0x18004f507  xor     rax, rsp
0x18004f50a  mov     [rbp+0B20h+var_50], rax
0x18004f511  xor     r14d, r14d
0x18004f514  mov     [rsp+0C20h+var_BC0], 1
0x18004f51c  mov     r15d, r14d
0x18004f51f  mov     [rsp+0C20h+var_BAC], r14d
0x18004f524  mov     dword ptr [rsp+0C20h+Addr.S_un], r14d
0x18004f529  mov     rsi, rcx
0x18004f52c  mov     [rbp+0B20h+BytesReturned], r14d
0x18004f530  mov     [rsp+0C20h+var_BA8], r14d
0x18004f535  call    RasRdGetNboServerIpv4Address
0x18004f53a  xor     edx, edx; Val
0x18004f53c  lea     rcx, [rbp+0B20h+var_260]; void *
0x18004f543  mov     r8d, 204h; Size
0x18004f549  mov     edi, eax
0x18004f54b  call    memset_0
0x18004f550  lea     r8d, [r14+10h]; Size
0x18004f554  mov     rcx, rsi; Buf1
0x18004f557  lea     rdx, GUID_NULL; Buf2
0x18004f55e  mov     r13d, r14d
0x18004f561  call    memcmp_0
0x18004f566  test    eax, eax
0x18004f568  mov     [rbp+0B20h+var_A60], r14d
0x18004f56f  xorps   xmm0, xmm0
0x18004f572  lea     rcx, [rbp+0B20h+var_A5C]; void *
0x18004f579  mov     r12d, r14d
0x18004f57c  mov     r8d, 7FCh; Size
0x18004f582  setz    r12b
0x18004f586  xor     eax, eax
0x18004f588  xor     edx, edx; Val
0x18004f58a  mov     [rbp+0B20h+var_B88], eax
0x18004f58d  movups  [rbp+0B20h+OutBuffer], xmm0
0x18004f591  call    memset_0
0x18004f596  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004f59d  test    rdx, rdx
0x18004f5a0  jz      short loc_18004F5BC
0x18004f5a2  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f5a9  lea     r8, aRassrvrgetaddr; "rasSrvrGetAddressForServerAdapter"
0x18004f5b0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5bc  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004f5c3  call    cs:__imp_EnterCriticalSection
0x18004f5c9  test    r12d, r12d
0x18004f5cc  jnz     short loc_18004F63C
0x18004f5ce  lea     r9, [rsp+0C20h+var_BC0]
0x18004f5d3  mov     edx, 100h
0x18004f5d8  lea     r8d, [r12+4]
0x18004f5dd  mov     rcx, rsi
0x18004f5e0  call    GetRoutingDomainConfigData
0x18004f5e5  mov     ebx, eax
0x18004f5e7  test    eax, eax
0x18004f5e9  jz      short loc_18004F63C
0x18004f5eb  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004f5f2  jz      loc_18004FC15
0x18004f5f8  mov     r8d, eax
0x18004f5fb  mov     word ptr [rbp+0B20h+var_A60], r14w
0x18004f603  lea     rdx, aErrorDInFindin; "Error %d in finding compartment for rou"...
0x18004f60a  lea     rcx, [rbp+0B20h+var_A60]
0x18004f611  call    FormatRRASErrorString
0x18004f616  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004f61d  lea     r8, [rbp+0B20h+var_A60]
0x18004f624  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f62b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f637  jmp     loc_18004FC15
0x18004f63c  lea     r9, [rsp+0C20h+var_BB0]
0x18004f641  mov     [rsp+0C20h+var_BA4], r14d
0x18004f646  lea     r8, [rsp+0C20h+var_BC8]
0x18004f64b  mov     [rsp+0C20h+var_BB0], r14d
0x18004f650  mov     edx, 4
0x18004f655  mov     [rsp+0C20h+var_BC8], 4
0x18004f65d  mov     rcx, rsi
0x18004f660  call    RasRoutingDomainGetConfigParam
0x18004f665  cmp     [rsp+0C20h+var_BB0], r14d
0x18004f66a  jnz     loc_18004F8CA
0x18004f670  mov     eax, [rsp+0C20h+var_BC0]
0x18004f674  lea     r8, [rbp+0B20h+OutBuffer]; lpInBuffer
0x18004f678  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hDevice
0x18004f67f  mov     r9d, 14h; nInBufferSize
0x18004f685  mov     dword ptr [rbp+0B20h+OutBuffer+8], eax
0x18004f688  mov     edx, 90018014h; dwIoControlCode
0x18004f68d  mov     [rsp+0C20h+lpOverlapped], r14; lpOverlapped
0x18004f692  lea     rax, [rbp+0B20h+BytesReturned]
0x18004f696  mov     [rsp+0C20h+lpBytesReturned], rax; lpBytesReturned
0x18004f69b  lea     rax, [rbp+0B20h+OutBuffer]
0x18004f69f  mov     [rsp+0C20h+nOutBufferSize], r9d; nOutBufferSize
0x18004f6a4  mov     [rsp+0C20h+lpOutBuffer], rax; lpOutBuffer
0x18004f6a9  mov     [rsp+0C20h+plpwsSubStrings], r14
0x18004f6ae  mov     dword ptr [rbp+0B20h+OutBuffer], 1
0x18004f6b5  mov     dword ptr [rbp+0B20h+OutBuffer+4], 0FFFFFFFFh
0x18004f6bc  call    cs:__imp_DeviceIoControl
0x18004f6c2  test    eax, eax
0x18004f6c4  jnz     short loc_18004F702
0x18004f6c6  call    cs:__imp_GetLastError
0x18004f6cc  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004f6d3  mov     ebx, eax
0x18004f6d5  jz      loc_18004FBC4
0x18004f6db  mov     r9d, dword ptr [rbp+0B20h+OutBuffer+8]
0x18004f6df  lea     rdx, aErrorDMappingS; "Error %d mapping server adapter for com"...
0x18004f6e6  mov     r8d, eax
0x18004f6e9  mov     word ptr [rbp+0B20h+var_A60], r14w
0x18004f6f1  lea     rcx, [rbp+0B20h+var_A60]
0x18004f6f8  call    FormatRRASErrorString
0x18004f6fd  jmp     loc_18004FBA3
0x18004f702  lea     rdx, [rsp+0C20h+plpwsSubStrings]
0x18004f707  lea     rcx, [rbp+0B20h+OutBuffer+4]
0x18004f70b  call    NsiConvertInterfaceIndexToLuid
0x18004f710  mov     rbx, [rsp+0C20h+plpwsSubStrings]
0x18004f715  lea     r9, [rsp+0C20h+var_BC8]
0x18004f71a  mov     edx, 7
0x18004f71f  mov     r13, rbx
0x18004f722  shr     r13, 18h
0x18004f726  mov     rcx, rsi
0x18004f729  and     r13d, 0FFFFFFh
0x18004f730  mov     [rsp+0C20h+var_BC8], r13d
0x18004f735  lea     r8d, [rdx-3]
0x18004f739  call    RasRoutingDomainSetConfigParam
0x18004f73e  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004f745  jz      short loc_18004F791
0x18004f747  mov     eax, dword ptr [rbp+0B20h+OutBuffer+8]
0x18004f74a  lea     rdx, aRassrvradapter_0; "RasSrvrAdapterMapped, LuidIndex %d inde"...
0x18004f751  mov     r9d, dword ptr [rbp+0B20h+OutBuffer+4]
0x18004f755  lea     rcx, [rbp+0B20h+var_A60]
0x18004f75c  mov     r8d, r13d
0x18004f75f  mov     dword ptr [rsp+0C20h+lpOutBuffer], eax
0x18004f763  mov     word ptr [rbp+0B20h+var_A60], r14w
0x18004f76b  call    FormatRRASErrorString
0x18004f770  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004f777  lea     r8, [rbp+0B20h+var_A60]
0x18004f77e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f785  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f791  test    r12d, r12d
0x18004f794  jz      loc_18004F8A9
0x18004f79a  xorps   xmm0, xmm0
0x18004f79d  lea     rcx, [rbp+0B20h+Row]; void *
0x18004f7a1  xor     edx, edx; Val
0x18004f7a3  mov     r8d, 100h; Size
0x18004f7a9  movups  xmmword ptr [rbp+0B20h+S], xmm0
0x18004f7ad  call    memset_0
0x18004f7b2  mov     [rsp+0C20h+var_BE0], 218h
0x18004f7ba  lea     rax, [rbp+0B20h+S]
0x18004f7be  mov     dword ptr [rsp+0C20h+lpOverlapped], 10h
0x18004f7c6  lea     r9, [rsp+0C20h+plpwsSubStrings]
0x18004f7cb  mov     [rsp+0C20h+lpBytesReturned], rax
0x18004f7d0  mov     [rsp+0C20h+nOutBufferSize], 2
0x18004f7d8  mov     [rsp+0C20h+plpwsSubStrings], rbx
0x18004f7dd  call    GetParameter
0x18004f7e2  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004f7e9  mov     ebx, eax
0x18004f7eb  jz      short loc_18004F830
0x18004f7ed  mov     r9d, dword ptr [rbp+0B20h+OutBuffer+4]
0x18004f7f1  lea     rdx, aGetinterfacegu; "GetInterfaceGuid returns with 0x%x for "...
0x18004f7f8  mov     r8d, eax
0x18004f7fb  mov     word ptr [rbp+0B20h+var_A60], r14w
0x18004f803  lea     rcx, [rbp+0B20h+var_A60]
0x18004f80a  call    FormatRRASErrorString
0x18004f80f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004f816  lea     r8, [rbp+0B20h+var_A60]
0x18004f81d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f824  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f830  test    ebx, ebx
0x18004f832  jnz     short loc_18004F8A9
0x18004f834  lea     rcx, [rbp+0B20h+S]
0x18004f838  call    DwAddLegacyKeysForInterface
0x18004f83d  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004f844  jz      short loc_18004F889
0x18004f846  mov     r9d, dword ptr [rbp+0B20h+OutBuffer+4]
0x18004f84a  lea     rdx, aDwaddlegacykey_5; "DwAddLegacyKeysForInterface returns wit"...
0x18004f851  mov     r8d, eax
0x18004f854  mov     word ptr [rbp+0B20h+var_A60], r14w
0x18004f85c  lea     rcx, [rbp+0B20h+var_A60]
0x18004f863  call    FormatRRASErrorString
0x18004f868  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004f86f  lea     r8, [rbp+0B20h+var_A60]
0x18004f876  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f87d  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f889  mov     r8d, 80h
0x18004f88f  lea     rdx, [rbp+0B20h+Row]
0x18004f893  lea     rcx, [rbp+0B20h+S]
0x18004f897  call    RegHelpStringFromGuid
0x18004f89c  test    eax, eax
0x18004f89e  jz      short loc_18004F8A9
0x18004f8a0  lea     rcx, [rbp+0B20h+Row]
0x18004f8a4  call    DwBindServerToAdapter
0x18004f8a9  mov     ebx, 1
0x18004f8ae  lea     r9, [rsp+0C20h+var_BC8]
0x18004f8b3  mov     rcx, rsi
0x18004f8b6  mov     [rsp+0C20h+var_BC8], ebx
0x18004f8ba  lea     eax, [rbx+3]
0x18004f8bd  mov     r8d, eax
0x18004f8c0  mov     edx, eax
0x18004f8c2  call    RasRoutingDomainSetConfigParam
0x18004f8c7  mov     r14d, ebx
0x18004f8ca  test    edi, edi
0x18004f8cc  jnz     short loc_18004F925
0x18004f8ce  movaps  xmm0, xmmword ptr [rsi]
0x18004f8d1  lea     r9, [rsp+0C20h+Addr]
0x18004f8d6  lea     r8, [rsp+0C20h+var_BAC]
0x18004f8db  movdqa  xmmword ptr [rbp+0B20h+S], xmm0
0x18004f8e0  mov     edx, 0EE170466h
0x18004f8e5  mov     [rsp+0C20h+lpOutBuffer], r15
0x18004f8ea  lea     rcx, [rbp+0B20h+S]
0x18004f8ee  call    rasSrvrAcquireAddressEx
0x18004f8f3  mov     ebx, eax
0x18004f8f5  test    eax, eax
0x18004f8f7  jnz     loc_18004FC12
0x18004f8fd  mov     r15d, [rsp+0C20h+var_BAC]
0x18004f902  lea     r9, [rsp+0C20h+Addr]
0x18004f907  xor     edx, edx
0x18004f909  mov     dword ptr [rsp+0C20h+Addr.S_un], r15d
0x18004f90e  lea     r8d, [rax+4]
0x18004f912  mov     [rsp+0C20h+var_BA4], 1
0x18004f91a  mov     rcx, rsi
0x18004f91d  mov     edi, r15d
0x18004f920  call    RasRoutingDomainSetConfigParam
0x18004f925  movaps  xmm0, xmmword ptr [rsi]
0x18004f928  lea     rcx, [rbp+0B20h+S]; struct _GUID
0x18004f92c  mov     edx, edi; unsigned int
0x18004f92e  movdqa  xmmword ptr [rbp+0B20h+S], xmm0
0x18004f933  call    ?rasSrvrSetIpAddressOnInterface@@YAKU_GUID@@KK@Z; rasSrvrSetIpAddressOnInterface(_GUID,ulong,ulong)
0x18004f938  mov     ebx, eax
0x18004f93a  test    eax, eax
0x18004f93c  jnz     loc_18004FBCE
0x18004f942  test    r14d, r14d
0x18004f945  jz      loc_18004FCB3
0x18004f94b  lea     rdx, [rsp+0C20h+var_BA8]
0x18004f950  call    IsDirectAccessConfigured
0x18004f955  xor     r14d, r14d
0x18004f958  mov     ebx, eax
0x18004f95a  test    eax, eax
0x18004f95c  jz      short loc_18004F990
0x18004f95e  cmp     eax, 2
0x18004f961  jnz     loc_18004F9FA
0x18004f967  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004f96e  mov     ebx, r14d
0x18004f971  test    rdx, rdx
0x18004f974  jz      short loc_18004F990
0x18004f976  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f97d  lea     r8, aDirectaccessRe; "DirectAccess registry keys not found. C"...
0x18004f984  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f990  cmp     [rsp+0C20h+var_BA8], 1
0x18004f995  jnz     loc_18004FA71
0x18004f99b  xor     edx, edx; Val
0x18004f99d  lea     rcx, [rbp+0B20h+Row]; void *
0x18004f9a1  mov     r8d, 0A8h; Size
0x18004f9a7  call    memset_0
0x18004f9ac  lea     rcx, [rbp+0B20h+Row]; Row
0x18004f9b0  call    cs:__imp_InitializeIpInterfaceEntry
0x18004f9b6  mov     eax, 2
0x18004f9bb  mov     [rbp+0B20h+Row.ForwardingEnabled], 1
0x18004f9bf  mov     [rbp+0B20h+Row.Family], ax
0x18004f9c3  lea     rcx, [rbp+0B20h+Row]; Row
0x18004f9c7  mov     eax, r13d
0x18004f9ca  or      rax, 17000000h
0x18004f9d0  shl     rax, 18h
0x18004f9d4  mov     qword ptr [rbp+0B20h+Row.InterfaceLuid], rax
0x18004f9d8  call    cs:__imp_SetIpInterfaceEntry
0x18004f9de  mov     ebx, eax
0x18004f9e0  test    eax, eax
0x18004f9e2  jz      short loc_18004FA4B
0x18004f9e4  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004f9eb  jz      loc_18004FBD1
0x18004f9f1  lea     rdx, aFailedToEnable; "Failed to enable IPv4 forwarding on the"...
0x18004f9f8  jmp     short loc_18004FA0E
0x18004f9fa  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004fa01  jz      loc_18004FBD1
0x18004fa07  lea     rdx, aIsdirectaccess; "IsDirectAccessConfigured failed with er"...
0x18004fa0e  mov     r8d, eax
0x18004fa11  mov     word ptr [rbp+0B20h+var_A60], r14w
0x18004fa19  lea     rcx, [rbp+0B20h+var_A60]
0x18004fa20  call    FormatRRASErrorString
0x18004fa25  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004fa2c  lea     r8, [rbp+0B20h+var_A60]
0x18004fa33  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fa3a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fa41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa46  jmp     loc_18004FBD1
0x18004fa4b  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004fa52  test    rdx, rdx
0x18004fa55  jz      short loc_18004FA71
0x18004fa57  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fa5e  lea     r8, aSuccessfullyEn; "Successfully enabled IPv4 forwarding on"...
0x18004fa65  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fa6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa71  test    r12d, r12d
  ... truncated ...
```
