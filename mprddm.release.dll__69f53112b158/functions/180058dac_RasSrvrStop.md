# RasSrvrStop

- ea: `0x180058dac`
- end: `0x1800593bd`
- name: `RasSrvrStop`
- size: `1553`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b520`
- `0x1800205b0`
- `0x180051a00`

## callees

- `0x180027ec0`
- `0x18005015c`
- `0x1800582b0`
- `0x180058dac`
- `0x18005a844`
- `0x18005aa10`
- `0x18005aaf8`
- `0x18005ad18`
- `0x18005adcc`
- `0x18005af78`
- `0x18005e83c`
- `0x180060cac`
- `0x18006b414`
- `0x1800755b8`
- `0x1800771b8`
- `0x18007ef74`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800592b0`
- `KERNEL32!DeviceIoControl` at `0x1800592b0`
- `KERNEL32!GetLastError` at `0x1800592c0`
- `KERNEL32!GetLastError` at `0x1800592c0`
- `KERNEL32!LeaveCriticalSection` at `0x18005936c`
- `KERNEL32!LeaveCriticalSection` at `0x18005936c`
- `KERNEL32!EnterCriticalSection` at `0x180059010`
- `KERNEL32!EnterCriticalSection` at `0x180059010`
- `ntdll!RtlIpv4AddressToStringA` at `0x18005905f`
- `ntdll!RtlIpv4AddressToStringA` at `0x18005905f`
- `rtutils!LogEventA` at `0x180059087`
- `rtutils!LogEventA` at `0x180059087`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800591e8`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800591e8`

## string_xrefs

- `0x180058ef3`: `RasSrvrStop: GetRoutingDomainConfigData (compartmentId=%d) failed and returned %d`
- `0x180058f6d`: `GetRoutingDomainConfigData (compartmentId) failed and returned %d`
- `0x18005920f`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`

## pseudocode

```c
void __fastcall RasSrvrStop(_QWORD *a1, char a2, int a3)
{
  bool v3; // zf
  __int64 v4; // rax
  _BOOL8 v8; // r15
  int v9; // r13d
  int v10; // esi
  unsigned int RoutingDomainConfigData; // eax
  __int64 v12; // rdx
  int v13; // r14d
  DWORD NboServerIpv4Address; // edi
  __int64 v15; // rsi
  __int64 v16; // r9
  __int64 v17; // r8
  int v18; // edx
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int ServerAdapterLuidIndex; // eax
  unsigned int v22; // eax
  DWORD LastError; // eax
  struct in_addr Addr; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD BytesReturned[3]; // [rsp+60h] [rbp-A8h] BYREF
  LPSTR plpwsSubStrings; // [rsp+78h] [rbp-90h] BYREF
  LPSTR plpwsSubStrings_8[2]; // [rsp+80h] [rbp-88h] BYREF
  int v30; // [rsp+90h] [rbp-78h]
  _OWORD v31[4]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-30h]
  int v33; // [rsp+E0h] [rbp-28h]
  wchar_t v34; // [rsp+E4h] [rbp-24h]
  __int16 v35; // [rsp+E6h] [rbp-22h]
  CHAR S[32]; // [rsp+E8h] [rbp-20h] BYREF
  __int16 v37; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v38[526]; // [rsp+10Ah] [rbp+2h] BYREF
  int v39; // [rsp+318h] [rbp+210h] BYREF
  _BYTE v40[2044]; // [rsp+31Ch] [rbp+214h] BYREF

  v4 = *a1 - *(_QWORD *)&GUID_NULL.Data1;
  v3 = *a1 == *(_QWORD *)&GUID_NULL.Data1;
  plpwsSubStrings = 0;
  LODWORD(BytesReturned[0]) = 0;
  LODWORD(v25) = 1;
  v26 = 0;
  if ( v3 )
    v4 = a1[1] - *(_QWORD *)GUID_NULL.Data4;
  v31[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  *(_OWORD *)plpwsSubStrings_8 = 0;
  v8 = v4 == 0;
  v31[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v30 = 0;
  v33 = *(_DWORD *)L"0}";
  v34 = a00000000000000[38];
  v31[3] = *(_OWORD *)L"-000000000000}";
  v35 = 0;
  v31[2] = *(_OWORD *)L"000-0000-000000000000}";
  v32 = *(_QWORD *)L"00000}";
  v37 = 0;
  memset_0(v38, 0, 0x202u);
  v39 = 0;
  v9 = a2 & 1;
  v10 = a2 & 4;
  memset_0(v40, 0, sizeof(v40));
  if ( !v8 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v25);
    if ( RoutingDomainConfigData && (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(
        &v39,
        L"RasSrvrStop: GetRoutingDomainConfigData (compartmentId=%d) failed and returned %d",
        (unsigned int)v25,
        RoutingDomainConfigData);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v39);
    }
    MprConvertGuidToString(a1, v12, v31);
    if ( (unsigned int)GetRoutingDomainConfigData(a1, 256, 4, &v25) )
    {
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_12;
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"GetRoutingDomainConfigData (compartmentId) failed and returned %d", 0);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v39);
    }
  }
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v39) = 0;
    FormatRRASErrorString(&v39, L"RasSrvrStop - RDID:%ws", v31);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v39);
  }
LABEL_12:
  v13 = dword_1800CF650;
  NboServerIpv4Address = RasRdGetNboServerIpv4Address(a1);
  if ( !v13 || v8 )
    RasDhcpUninitialize();
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !v9 && !v10 )
  {
    Addr = 0;
    RasRoutingDomainSetConfigParam(a1, 2, 4, &Addr);
  }
  if ( (!v13 || v8) && a3 && NboServerIpv4Address )
  {
    Addr = (struct in_addr)NboServerIpv4Address;
    RtlIpv4AddressToStringA(&Addr, S);
    plpwsSubStrings = S;
    LogEventA(2u, 0x4E74u, 1u, &plpwsSubStrings);
  }
  if ( !v9 )
  {
    if ( !v10 )
    {
      if ( !a3 )
      {
        *(_OWORD *)&BytesReturned[1] = *(_OWORD *)a1;
        if ( !(unsigned int)RasGetRoutingDomainAddressPool(&BytesReturned[1], 1, &v26) )
        {
          v15 = v26;
          if ( v26 )
          {
            while ( 1 )
            {
              v19 = *(_QWORD *)(v15 + 24);
              if ( !v19 )
                break;
              v16 = *(_QWORD *)(v19 + 32);
              v17 = *(_QWORD *)(v19 + 24);
              v18 = *(_DWORD *)(v19 + 16);
              *(_OWORD *)&BytesReturned[1] = *(_OWORD *)a1;
              RasSrvrReleaseAddress((unsigned int)&BytesReturned[1], v18, v17, v16, 1);
            }
          }
          *(_OWORD *)&BytesReturned[1] = *(_OWORD *)a1;
          v20 = RasReleaseRoutingDomainAddressPool(&BytesReturned[1]);
          if ( v20 && (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v39) = 0;
            FormatRRASErrorString(&v39, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v20);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v39);
          }
        }
      }
      *(_OWORD *)&BytesReturned[1] = *(_OWORD *)a1;
      RasStatUninitialize(&BytesReturned[1]);
    }
    RasTcpSetProxyArp(NboServerIpv4Address, 0, NboServerIpv4Address, v25);
    ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(a1);
    ResetIpAddressOnInterface(ServerAdapterLuidIndex, NboServerIpv4Address);
  }
  if ( !v13 || v8 )
  {
    Addr = (struct in_addr)516;
    RasRoutingDomainGetConfigParam(a1, 6, &Addr, &v37);
    v22 = DhcpNotifyConfigChange(0, &v37, 0, 0, 0, 0, 0);
    if ( v22 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", &v37, v22);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
    }
  }
  if ( !v9 )
  {
    Addr = 0;
    LODWORD(v26) = 4;
    RasRoutingDomainGetConfigParam(a1, 4, &v26, &Addr);
    if ( Addr )
    {
      LODWORD(plpwsSubStrings_8[1]) = v25;
      if ( !DeviceIoControl(
              HelperWanArpHandle,
              0x90018014,
              plpwsSubStrings_8,
              0x14u,
              plpwsSubStrings_8,
              0x14u,
              (LPDWORD)BytesReturned,
              0) )
      {
        LastError = GetLastError();
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"Error %d unmapping server adapter", LastError);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
      }
      if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800D0740 + 1),
          L"RasSrvrAdapterUnMapped");
      LODWORD(v26) = 0;
      RasRoutingDomainSetConfigParam(a1, 4, 4, &v26);
    }
    LODWORD(v26) = 0;
    RasRoutingDomainSetConfigParam(a1, 0, 4, &v26);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !v13 || v8 )
    WriteDialinInterfaceIndexIntoRegistry(1u, 0);
}

```

## disassembly

```asm
0x180058dac  mov     rax, rsp
0x180058daf  mov     [rax+10h], rbx
0x180058db3  mov     [rax+18h], rsi
0x180058db7  mov     [rax+20h], rdi
0x180058dbb  push    rbp
0x180058dbc  push    r12
0x180058dbe  push    r13
0x180058dc0  push    r14
0x180058dc2  push    r15
0x180058dc4  lea     rbp, [rax-0A48h]
0x180058dcb  sub     rsp, 0B20h
0x180058dd2  mov     rax, cs:__security_cookie
0x180058dd9  xor     rax, rsp
0x180058ddc  mov     [rbp+0A40h+var_30], rax
0x180058de3  mov     rax, [rcx]
0x180058de6  xor     edi, edi
0x180058de8  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180058def  mov     r12d, r8d
0x180058df2  mov     esi, edx
0x180058df4  mov     [rsp+0B40h+plpwsSubStrings], rdi
0x180058df9  mov     rbx, rcx
0x180058dfc  mov     dword ptr [rsp+0B40h+BytesReturned], edi
0x180058e00  mov     dword ptr [rsp+0B40h+var_AF8], 1
0x180058e08  mov     [rsp+0B40h+var_AF0], rdi
0x180058e0d  jnz     short loc_180058E1A
0x180058e0f  mov     rax, [rcx+8]
0x180058e13  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180058e1a  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180058e21  lea     rcx, [rbp+0A40h+var_A3E]; void *
0x180058e25  test    rax, rax
0x180058e28  movaps  [rbp+0A40h+var_AB0], xmm1
0x180058e2c  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180058e33  xorps   xmm0, xmm0
0x180058e36  movups  xmmword ptr [rsp+0B40h+plpwsSubStrings+8], xmm0
0x180058e3b  mov     r15d, edi
0x180058e3e  mov     r8d, 202h; Size
0x180058e44  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180058e4b  setz    r15b
0x180058e4f  xor     eax, eax
0x180058e51  movaps  [rbp+0A40h+var_AA0], xmm0
0x180058e55  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180058e5c  xor     edx, edx; Val
0x180058e5e  mov     [rbp+0A40h+var_AB8], eax
0x180058e61  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x180058e67  mov     [rbp+0A40h+var_A68], eax
0x180058e6a  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180058e71  mov     [rbp+0A40h+var_A64], ax
0x180058e75  xor     eax, eax
0x180058e77  movaps  [rbp+0A40h+var_A80], xmm0
0x180058e7b  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x180058e83  mov     [rbp+0A40h+var_A62], ax
0x180058e87  movaps  [rbp+0A40h+var_A90], xmm1
0x180058e8b  movsd   [rbp+0A40h+var_A70], xmm0
0x180058e90  mov     [rbp+0A40h+var_A40], di
0x180058e94  call    memset_0
0x180058e99  mov     r13d, esi
0x180058e9c  mov     [rbp+0A40h+var_830], edi
0x180058ea2  mov     r14d, 4
0x180058ea8  lea     rcx, [rbp+0A40h+var_82C]; void *
0x180058eaf  xor     edx, edx; Val
0x180058eb1  mov     r8d, 7FCh; Size
0x180058eb7  and     r13d, 1
0x180058ebb  and     esi, r14d
0x180058ebe  call    memset_0
0x180058ec3  test    r15d, r15d
0x180058ec6  jnz     loc_180058FA1
0x180058ecc  lea     r9, [rsp+0B40h+var_AF8]
0x180058ed1  mov     r8d, r14d
0x180058ed4  mov     edx, 100h
0x180058ed9  mov     rcx, rbx
0x180058edc  call    GetRoutingDomainConfigData
0x180058ee1  test    eax, eax
0x180058ee3  jz      short loc_180058F31
0x180058ee5  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x180058eec  jz      short loc_180058F31
0x180058eee  mov     r8d, dword ptr [rsp+0B40h+var_AF8]
0x180058ef3  lea     rdx, aRassrvrstopGet_0; "RasSrvrStop: GetRoutingDomainConfigData"...
0x180058efa  mov     r9d, eax
0x180058efd  mov     word ptr [rbp+0A40h+var_830], di
0x180058f04  lea     rcx, [rbp+0A40h+var_830]
0x180058f0b  call    FormatRRASErrorString
0x180058f10  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058f17  lea     r8, [rbp+0A40h+var_830]
0x180058f1e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058f25  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180058f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f31  lea     r8, [rbp+0A40h+var_AB0]
0x180058f35  mov     rcx, rbx
0x180058f38  call    MprConvertGuidToString
0x180058f3d  lea     r9, [rsp+0B40h+var_AF8]
0x180058f42  mov     r8d, r14d
0x180058f45  mov     edx, 100h
0x180058f4a  mov     rcx, rbx
0x180058f4d  call    GetRoutingDomainConfigData
0x180058f52  test    eax, eax
0x180058f54  jz      short loc_180058FA1
0x180058f56  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x180058f5d  jz      loc_180058FE9
0x180058f63  xor     r8d, r8d
0x180058f66  mov     word ptr [rbp+0A40h+var_830], di
0x180058f6d  lea     rdx, aGetroutingdoma; "GetRoutingDomainConfigData (compartment"...
0x180058f74  lea     rcx, [rbp+0A40h+var_830]
0x180058f7b  call    FormatRRASErrorString
0x180058f80  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058f87  lea     r8, [rbp+0A40h+var_830]
0x180058f8e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058f95  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180058f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fa1  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x180058fa8  jz      short loc_180058FE9
0x180058faa  lea     r8, [rbp+0A40h+var_AB0]
0x180058fae  mov     word ptr [rbp+0A40h+var_830], di
0x180058fb5  lea     rdx, aRassrvrstopRdi; "RasSrvrStop - RDID:%ws"
0x180058fbc  lea     rcx, [rbp+0A40h+var_830]
0x180058fc3  call    FormatRRASErrorString
0x180058fc8  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058fcf  lea     r8, [rbp+0A40h+var_830]
0x180058fd6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058fdd  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180058fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fe9  mov     r14d, cs:dword_1800CF650
0x180058ff0  mov     rcx, rbx
0x180058ff3  call    RasRdGetNboServerIpv4Address
0x180058ff8  mov     edi, eax
0x180058ffa  test    r14d, r14d
0x180058ffd  jz      short loc_180059004
0x180058fff  test    r15d, r15d
0x180059002  jz      short loc_180059009
0x180059004  call    RasDhcpUninitialize
0x180059009  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059010  call    cs:__imp_EnterCriticalSection
0x180059017  nop     dword ptr [rax+rax+00h]
0x18005901c  xor     eax, eax
0x18005901e  test    r13d, r13d
0x180059021  jnz     short loc_18005903F
0x180059023  test    esi, esi
0x180059025  jnz     short loc_18005903F
0x180059027  lea     r9, [rsp+0B40h+Addr]
0x18005902c  mov     dword ptr [rsp+0B40h+Addr.S_un], eax
0x180059030  lea     edx, [rax+2]
0x180059033  mov     rcx, rbx
0x180059036  lea     r8d, [rax+4]
0x18005903a  call    RasRoutingDomainSetConfigParam
0x18005903f  test    r14d, r14d
0x180059042  jz      short loc_180059049
0x180059044  test    r15d, r15d
0x180059047  jz      short loc_180059093
0x180059049  test    r12d, r12d
0x18005904c  jz      short loc_180059093
0x18005904e  test    edi, edi
0x180059050  jz      short loc_180059093
0x180059052  lea     rdx, [rbp+0A40h+S]; S
0x180059056  mov     dword ptr [rsp+0B40h+Addr.S_un], edi
0x18005905a  lea     rcx, [rsp+0B40h+Addr]; Addr
0x18005905f  call    cs:__imp_RtlIpv4AddressToStringA
0x180059066  nop     dword ptr [rax+rax+00h]
0x18005906b  mov     ecx, 2; wEventType
0x180059070  lea     rax, [rbp+0A40h+S]
0x180059074  lea     r9, [rsp+0B40h+plpwsSubStrings]; plpwsSubStrings
0x180059079  mov     [rsp+0B40h+plpwsSubStrings], rax
0x18005907e  mov     edx, 4E74h; dwMessageId
0x180059083  lea     r8d, [rcx-1]; cNumberOfSubStrings
0x180059087  call    cs:__imp_LogEventA
0x18005908e  nop     dword ptr [rax+rax+00h]
0x180059093  test    r13d, r13d
0x180059096  jnz     loc_1800591A2
0x18005909c  test    esi, esi
0x18005909e  jnz     loc_180059180
0x1800590a4  test    r12d, r12d
0x1800590a7  jnz     loc_18005916D
0x1800590ad  movaps  xmm0, xmmword ptr [rbx]
0x1800590b0  lea     r8, [rsp+0B40h+var_AF0]
0x1800590b5  lea     edx, [rsi+1]
0x1800590b8  movdqa  xmmword ptr [rsp+0B40h+BytesReturned+8], xmm0
0x1800590be  lea     rcx, [rsp+0B40h+BytesReturned+8]
0x1800590c3  call    RasGetRoutingDomainAddressPool
0x1800590c8  xor     r12d, r12d
0x1800590cb  test    eax, eax
0x1800590cd  jnz     loc_18005916D
0x1800590d3  mov     rsi, [rsp+0B40h+var_AF0]
0x1800590d8  test    rsi, rsi
0x1800590db  jz      short loc_18005910E
0x1800590dd  jmp     short loc_180059105
0x1800590df  movaps  xmm0, xmmword ptr [rbx]
0x1800590e2  lea     rcx, [rsp+0B40h+BytesReturned+8]
0x1800590e7  mov     r9, [rax+20h]
0x1800590eb  mov     r8, [rax+18h]
0x1800590ef  mov     edx, [rax+10h]
0x1800590f2  movdqa  xmmword ptr [rsp+0B40h+BytesReturned+8], xmm0
0x1800590f8  mov     dword ptr [rsp+0B40h+lpOutBuffer], 1
0x180059100  call    RasSrvrReleaseAddress
0x180059105  mov     rax, [rsi+18h]
0x180059109  test    rax, rax
0x18005910c  jnz     short loc_1800590DF
0x18005910e  movaps  xmm0, xmmword ptr [rbx]
0x180059111  lea     rcx, [rsp+0B40h+BytesReturned+8]
0x180059116  movdqa  xmmword ptr [rsp+0B40h+BytesReturned+8], xmm0
0x18005911c  call    RasReleaseRoutingDomainAddressPool
0x180059121  test    eax, eax
0x180059123  jz      short loc_18005916D
0x180059125  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18005912c  jz      short loc_18005916D
0x18005912e  mov     r8d, eax
0x180059131  mov     word ptr [rbp+0A40h+var_830], r12w
0x180059139  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x180059140  lea     rcx, [rbp+0A40h+var_830]
0x180059147  call    FormatRRASErrorString
0x18005914c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180059153  lea     r8, [rbp+0A40h+var_830]
0x18005915a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059161  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005916d  movaps  xmm0, xmmword ptr [rbx]
0x180059170  lea     rcx, [rsp+0B40h+BytesReturned+8]
0x180059175  movdqa  xmmword ptr [rsp+0B40h+BytesReturned+8], xmm0
0x18005917b  call    RasStatUninitialize
0x180059180  mov     r9d, dword ptr [rsp+0B40h+var_AF8]
0x180059185  mov     r8d, edi
0x180059188  xor     edx, edx
0x18005918a  mov     ecx, edi; dwAddress
0x18005918c  call    RasTcpSetProxyArp
0x180059191  mov     rcx, rbx
0x180059194  call    RasRdGetServerAdapterLuidIndex
0x180059199  mov     ecx, eax
0x18005919b  mov     edx, edi
0x18005919d  call    ResetIpAddressOnInterface
0x1800591a2  xor     edi, edi
0x1800591a4  test    r14d, r14d
0x1800591a7  jz      short loc_1800591B2
0x1800591a9  test    r15d, r15d
0x1800591ac  jz      loc_180059243
0x1800591b2  lea     r9, [rbp+0A40h+var_A40]
0x1800591b6  mov     dword ptr [rsp+0B40h+Addr.S_un], 204h
0x1800591be  lea     r8, [rsp+0B40h+Addr]
0x1800591c3  mov     edx, 6
0x1800591c8  mov     rcx, rbx
0x1800591cb  call    RasRoutingDomainGetConfigParam
0x1800591d0  mov     dword ptr [rsp+0B40h+lpBytesReturned], edi
0x1800591d4  lea     rdx, [rbp+0A40h+var_A40]
0x1800591d8  mov     [rsp+0B40h+nOutBufferSize], edi
0x1800591dc  xor     r9d, r9d
0x1800591df  xor     r8d, r8d
0x1800591e2  mov     dword ptr [rsp+0B40h+lpOutBuffer], edi
0x1800591e6  xor     ecx, ecx
0x1800591e8  call    cs:__imp_DhcpNotifyConfigChange
0x1800591ef  nop     dword ptr [rax+rax+00h]
0x1800591f4  test    eax, eax
0x1800591f6  jz      short loc_180059243
0x1800591f8  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x1800591ff  jz      short loc_180059243
0x180059201  mov     r9d, eax
0x180059204  mov     word ptr [rbp+0A40h+var_830], di
0x18005920b  lea     r8, [rbp+0A40h+var_A40]
0x18005920f  lea     rdx, aDhcpnotifyconf; "DhcpNotifyConfigChange(%ws) failed and "...
0x180059216  lea     rcx, [rbp+0A40h+var_830]
0x18005921d  call    FormatRRASErrorString
0x180059222  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180059229  lea     r8, [rbp+0A40h+var_830]
0x180059230  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059237  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005923e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059243  test    r13d, r13d
0x180059246  jnz     loc_180059365
0x18005924c  lea     esi, [r13+4]
0x180059250  mov     dword ptr [rsp+0B40h+Addr.S_un], edi
0x180059254  mov     edx, esi
0x180059256  mov     dword ptr [rsp+0B40h+var_AF0], esi
0x18005925a  lea     r9, [rsp+0B40h+Addr]
0x18005925f  mov     rcx, rbx
0x180059262  lea     r8, [rsp+0B40h+var_AF0]
0x180059267  call    RasRoutingDomainGetConfigParam
0x18005926c  cmp     dword ptr [rsp+0B40h+Addr.S_un], edi
0x180059270  jz      loc_18005934F
0x180059276  mov     eax, dword ptr [rsp+0B40h+var_AF8]
0x18005927a  lea     r9d, [r13+14h]; nInBufferSize
0x18005927e  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hDevice
0x180059285  lea     r8, [rsp+0B40h+plpwsSubStrings+8]; lpInBuffer
0x18005928a  mov     [rbp+0A40h+var_AC0], eax
0x18005928d  mov     edx, 90018014h; dwIoControlCode
0x180059292  mov     [rsp+0B40h+lpOverlapped], rdi; lpOverlapped
0x180059297  lea     rax, [rsp+0B40h+BytesReturned]
0x18005929c  mov     [rsp+0B40h+lpBytesReturned], rax; lpBytesReturned
0x1800592a1  lea     rax, [rsp+0B40h+plpwsSubStrings+8]
0x1800592a6  mov     [rsp+0B40h+nOutBufferSize], r9d; nOutBufferSize
0x1800592ab  mov     [rsp+0B40h+lpOutBuffer], rax; lpOutBuffer
0x1800592b0  call    cs:__imp_DeviceIoControl
0x1800592b7  nop     dword ptr [rax+rax+00h]
0x1800592bc  test    eax, eax
0x1800592be  jnz     short loc_180059313
0x1800592c0  call    cs:__imp_GetLastError
0x1800592c7  nop     dword ptr [rax+rax+00h]
0x1800592cc  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x1800592d3  jz      short loc_180059313
0x1800592d5  mov     r8d, eax
0x1800592d8  mov     word ptr [rbp+0A40h+var_830], di
0x1800592df  lea     rdx, aErrorDUnmappin; "Error %d unmapping server adapter"
0x1800592e6  lea     rcx, [rbp+0A40h+var_830]
0x1800592ed  call    FormatRRASErrorString
0x1800592f2  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800592f9  lea     r8, [rbp+0A40h+var_830]
  ... truncated ...
```
