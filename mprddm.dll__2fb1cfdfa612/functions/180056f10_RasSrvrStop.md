# RasSrvrStop

- ea: `0x180056f10`
- end: `0x180057490`
- name: `RasSrvrStop`
- size: `1408`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001abb0`
- `0x18001f8e0`
- `0x180050110`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x18004e9b8`
- `0x1800564e0`
- `0x180056f10`
- `0x1800588f4`
- `0x180058ab0`
- `0x180058b94`
- `0x180058dc4`
- `0x180058e78`
- `0x180059030`
- `0x18005c610`
- `0x18005e838`
- `0x1800689f0`
- `0x180071cec`
- `0x180073664`
- `0x18007a104`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800573ac`
- `KERNEL32!DeviceIoControl` at `0x1800573ac`
- `KERNEL32!GetLastError` at `0x1800573b6`
- `KERNEL32!GetLastError` at `0x1800573b6`
- `KERNEL32!LeaveCriticalSection` at `0x180057453`
- `KERNEL32!LeaveCriticalSection` at `0x180057453`
- `KERNEL32!EnterCriticalSection` at `0x18005712a`
- `KERNEL32!EnterCriticalSection` at `0x18005712a`
- `ntdll!RtlIpv4AddressToStringA` at `0x180057172`
- `ntdll!RtlIpv4AddressToStringA` at `0x180057172`
- `rtutils!LogEventA` at `0x180057194`
- `rtutils!LogEventA` at `0x180057194`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800572ec`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800572ec`

## string_xrefs

- `0x180057025`: `RasSrvrStop: GetRoutingDomainConfigData (compartmentId=%d) failed and returned %d`
- `0x18005708d`: `GetRoutingDomainConfigData (compartmentId) failed and returned %d`
- `0x18005730d`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`

## pseudocode

```c
void __fastcall RasSrvrStop(__int128 *a1, char a2, int a3)
{
  BOOL v6; // r12d
  unsigned int RoutingDomainConfigData; // eax
  __int64 v8; // rdx
  int v9; // r15d
  int v10; // edi
  int v11; // r14d
  DWORD NboServerIpv4Address; // esi
  __int64 v13; // r14
  __int64 v14; // r9
  __int64 v15; // r8
  int v16; // edx
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int ServerAdapterLuidIndex; // eax
  unsigned int v20; // eax
  DWORD LastError; // eax
  struct in_addr Addr; // [rsp+40h] [rbp-C0h] BYREF
  NET_IF_COMPARTMENT_ID v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  LPSTR plpwsSubStrings; // [rsp+70h] [rbp-90h] BYREF
  __int128 OutBuffer; // [rsp+78h] [rbp-88h] BYREF
  int v29; // [rsp+88h] [rbp-78h]
  _OWORD v30[3]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[30]; // [rsp+C0h] [rbp-40h]
  __int16 v32; // [rsp+DEh] [rbp-22h]
  CHAR S[32]; // [rsp+E0h] [rbp-20h] BYREF
  int v34; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v35[2044]; // [rsp+104h] [rbp+4h] BYREF
  __int16 v36; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v37[526]; // [rsp+902h] [rbp+802h] BYREF

  v23 = 1;
  plpwsSubStrings = 0;
  BytesReturned = 0;
  v24 = 0;
  v30[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  OutBuffer = 0;
  v6 = memcmp_0(a1, &GUID_NULL, 0x10u) == 0;
  v30[2] = *(_OWORD *)L"000-0000-000000000000}";
  v29 = 0;
  v30[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v31 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v31[14] = *(_OWORD *)L"000000}";
  v32 = 0;
  v36 = 0;
  memset_0(v37, 0, 0x202u);
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( !v6 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v23);
    if ( RoutingDomainConfigData && (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v34) = 0;
      FormatRRASErrorString(
        &v34,
        L"RasSrvrStop: GetRoutingDomainConfigData (compartmentId=%d) failed and returned %d",
        v23,
        RoutingDomainConfigData);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v34);
    }
    MprConvertGuidToString(a1, v8, v30);
    if ( (unsigned int)GetRoutingDomainConfigData(a1, 256, 4, &v23) )
    {
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_10;
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v34, L"GetRoutingDomainConfigData (compartmentId) failed and returned %d", 0);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v34);
    }
  }
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v34, L"RasSrvrStop - RDID:%ws", v30);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v34);
  }
LABEL_10:
  v9 = dword_1800C8650;
  v10 = a2 & 1;
  v11 = a2 & 4;
  NboServerIpv4Address = RasRdGetNboServerIpv4Address(a1);
  if ( !v9 || v6 )
    RasDhcpUninitialize();
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !v10 && !v11 )
  {
    Addr = 0;
    RasRoutingDomainSetConfigParam(a1, 2, 4, &Addr);
  }
  if ( (!v9 || v6) && a3 && NboServerIpv4Address )
  {
    Addr = (struct in_addr)NboServerIpv4Address;
    RtlIpv4AddressToStringA(&Addr, S);
    plpwsSubStrings = S;
    LogEventA(2u, 0x4E74u, 1u, &plpwsSubStrings);
  }
  if ( !v10 )
  {
    if ( !v11 )
    {
      if ( !a3 )
      {
        v26 = *a1;
        if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v26, 1, &v24) )
        {
          v13 = v24;
          if ( v24 )
          {
            while ( 1 )
            {
              v17 = *(_QWORD *)(v13 + 24);
              if ( !v17 )
                break;
              v14 = *(_QWORD *)(v17 + 32);
              v15 = *(_QWORD *)(v17 + 24);
              v16 = *(_DWORD *)(v17 + 16);
              v26 = *a1;
              RasSrvrReleaseAddress((unsigned int)&v26, v16, v15, v14, 1);
            }
          }
          v26 = *a1;
          v18 = RasReleaseRoutingDomainAddressPool(&v26);
          if ( v18 && (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v18);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v34);
          }
        }
      }
      v26 = *a1;
      RasStatUninitialize(&v26);
    }
    RasTcpSetProxyArp(NboServerIpv4Address, 0, NboServerIpv4Address, v23);
    ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(a1);
    ResetIpAddressOnInterface(ServerAdapterLuidIndex, NboServerIpv4Address);
  }
  if ( !v9 || v6 )
  {
    Addr = (struct in_addr)516;
    RasRoutingDomainGetConfigParam(a1, 6, &Addr, &v36);
    v20 = DhcpNotifyConfigChange(0, &v36, 0, 0, 0, 0, 0);
    if ( v20 )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", &v36, v20);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v34);
      }
    }
  }
  if ( !v10 )
  {
    Addr = 0;
    LODWORD(v24) = 4;
    RasRoutingDomainGetConfigParam(a1, 4, &v24, &Addr);
    if ( Addr )
    {
      DWORD2(OutBuffer) = v23;
      LODWORD(OutBuffer) = 0;
      if ( !DeviceIoControl(HelperWanArpHandle, 0x90018014, &OutBuffer, 0x14u, &OutBuffer, 0x14u, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(&v34, L"Error %d unmapping server adapter", LastError);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v34);
        }
      }
      if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800C9740 + 1),
          L"RasSrvrAdapterUnMapped");
      LODWORD(v24) = 0;
      RasRoutingDomainSetConfigParam(a1, 4, 4, &v24);
    }
    LODWORD(v24) = 0;
    RasRoutingDomainSetConfigParam(a1, 0, 4, &v24);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !v9 || v6 )
    WriteDialinInterfaceIndexIntoRegistry(1u, 0);
}

```

## disassembly

```asm
0x180056f10  push    rbp
0x180056f12  push    rbx
0x180056f13  push    rsi
0x180056f14  push    rdi
0x180056f15  push    r12
0x180056f17  push    r13
0x180056f19  push    r14
0x180056f1b  push    r15
0x180056f1d  lea     rbp, [rsp-0A28h]
0x180056f25  sub     rsp, 0B28h
0x180056f2c  mov     rax, cs:__security_cookie
0x180056f33  xor     rax, rsp
0x180056f36  mov     [rbp+0A60h+var_50], rax
0x180056f3d  xor     edi, edi
0x180056f3f  mov     [rsp+0B60h+var_B18], 1
0x180056f47  mov     r13d, r8d
0x180056f4a  mov     [rsp+0B60h+plpwsSubStrings], rdi
0x180056f4f  mov     r14d, edx
0x180056f52  mov     [rsp+0B60h+BytesReturned], edi
0x180056f56  lea     rdx, GUID_NULL; Buf2
0x180056f5d  mov     [rsp+0B60h+var_B10], rdi
0x180056f62  lea     r8d, [rdi+10h]; Size
0x180056f66  mov     rbx, rcx
0x180056f69  call    memcmp_0
0x180056f6e  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180056f75  lea     rcx, [rbp+0A60h+var_25E]; void *
0x180056f7c  xorps   xmm0, xmm0
0x180056f7f  movaps  [rbp+0A60h+var_AD0], xmm1
0x180056f83  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180056f8a  test    eax, eax
0x180056f8c  movups  [rsp+0B60h+OutBuffer], xmm0
0x180056f91  mov     r12d, edi
0x180056f94  mov     r8d, 202h; Size
0x180056f9a  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180056fa1  setz    r12b
0x180056fa5  xor     eax, eax
0x180056fa7  movaps  [rbp+0A60h+var_AB0], xmm1
0x180056fab  movups  xmm1, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x180056fb2  xor     edx, edx; Val
0x180056fb4  mov     [rbp+0A60h+var_AD8], eax
0x180056fb7  movaps  [rbp+0A60h+var_AC0], xmm0
0x180056fbb  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180056fc2  movaps  xmmword ptr [rbp+0A60h+var_AA0], xmm0
0x180056fc6  movups  xmmword ptr [rbp+0A60h+var_AA0+0Eh], xmm1
0x180056fca  mov     [rbp+0A60h+var_A82], ax
0x180056fce  mov     [rbp+0A60h+var_260], di
0x180056fd5  call    memset_0
0x180056fda  xor     edx, edx; Val
0x180056fdc  mov     [rbp+0A60h+var_A60], edi
0x180056fdf  mov     r8d, 7FCh; Size
0x180056fe5  lea     rcx, [rbp+0A60h+var_A5C]; void *
0x180056fe9  call    memset_0
0x180056fee  lea     esi, [rdi+4]
0x180056ff1  test    r12d, r12d
0x180056ff4  jnz     loc_1800570BB
0x180056ffa  mov     r15d, 100h
0x180057000  lea     r9, [rsp+0B60h+var_B18]
0x180057005  mov     edx, r15d
0x180057008  mov     r8d, esi
0x18005700b  mov     rcx, rbx
0x18005700e  call    GetRoutingDomainConfigData
0x180057013  test    eax, eax
0x180057015  jz      short loc_18005705A
0x180057017  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x18005701e  jz      short loc_18005705A
0x180057020  mov     r8d, [rsp+0B60h+var_B18]
0x180057025  lea     rdx, aRassrvrstopGet_0; "RasSrvrStop: GetRoutingDomainConfigData"...
0x18005702c  mov     r9d, eax
0x18005702f  mov     word ptr [rbp+0A60h+var_A60], di
0x180057033  lea     rcx, [rbp+0A60h+var_A60]
0x180057037  call    FormatRRASErrorString
0x18005703c  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180057043  lea     r8, [rbp+0A60h+var_A60]
0x180057047  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005704e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005705a  lea     r8, [rbp+0A60h+var_AD0]
0x18005705e  mov     rcx, rbx
0x180057061  call    MprConvertGuidToString
0x180057066  lea     r9, [rsp+0B60h+var_B18]
0x18005706b  mov     r8d, esi
0x18005706e  mov     edx, r15d
0x180057071  mov     rcx, rbx
0x180057074  call    GetRoutingDomainConfigData
0x180057079  test    eax, eax
0x18005707b  jz      short loc_1800570BB
0x18005707d  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x180057084  jz      short loc_1800570FA
0x180057086  xor     r8d, r8d
0x180057089  mov     word ptr [rbp+0A60h+var_A60], di
0x18005708d  lea     rdx, aGetroutingdoma; "GetRoutingDomainConfigData (compartment"...
0x180057094  lea     rcx, [rbp+0A60h+var_A60]
0x180057098  call    FormatRRASErrorString
0x18005709d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800570a4  lea     r8, [rbp+0A60h+var_A60]
0x1800570a8  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800570af  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800570b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570bb  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x1800570c2  jz      short loc_1800570FA
0x1800570c4  lea     r8, [rbp+0A60h+var_AD0]
0x1800570c8  mov     word ptr [rbp+0A60h+var_A60], di
0x1800570cc  lea     rdx, aRassrvrstopRdi; "RasSrvrStop - RDID:%ws"
0x1800570d3  lea     rcx, [rbp+0A60h+var_A60]
0x1800570d7  call    FormatRRASErrorString
0x1800570dc  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800570e3  lea     r8, [rbp+0A60h+var_A60]
0x1800570e7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800570ee  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800570f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570fa  mov     r15d, cs:dword_1800C8650
0x180057101  mov     edi, r14d
0x180057104  mov     rcx, rbx
0x180057107  and     edi, 1
0x18005710a  and     r14d, esi
0x18005710d  call    RasRdGetNboServerIpv4Address
0x180057112  mov     esi, eax
0x180057114  test    r15d, r15d
0x180057117  jz      short loc_18005711E
0x180057119  test    r12d, r12d
0x18005711c  jz      short loc_180057123
0x18005711e  call    RasDhcpUninitialize
0x180057123  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005712a  call    cs:__imp_EnterCriticalSection
0x180057130  test    edi, edi
0x180057132  jnz     short loc_180057152
0x180057134  test    r14d, r14d
0x180057137  jnz     short loc_180057152
0x180057139  lea     r9, [rsp+0B60h+Addr]
0x18005713e  mov     dword ptr [rsp+0B60h+Addr.S_un], r14d
0x180057143  lea     edx, [rdi+2]
0x180057146  mov     rcx, rbx
0x180057149  lea     r8d, [rdi+4]
0x18005714d  call    RasRoutingDomainSetConfigParam
0x180057152  test    r15d, r15d
0x180057155  jz      short loc_18005715C
0x180057157  test    r12d, r12d
0x18005715a  jz      short loc_18005719A
0x18005715c  test    r13d, r13d
0x18005715f  jz      short loc_18005719A
0x180057161  test    esi, esi
0x180057163  jz      short loc_18005719A
0x180057165  lea     rdx, [rbp+0A60h+S]; S
0x180057169  mov     dword ptr [rsp+0B60h+Addr.S_un], esi
0x18005716d  lea     rcx, [rsp+0B60h+Addr]; Addr
0x180057172  call    cs:__imp_RtlIpv4AddressToStringA
0x180057178  mov     ecx, 2; wEventType
0x18005717d  lea     rax, [rbp+0A60h+S]
0x180057181  lea     r9, [rsp+0B60h+plpwsSubStrings]; plpwsSubStrings
0x180057186  mov     [rsp+0B60h+plpwsSubStrings], rax
0x18005718b  mov     edx, 4E74h; dwMessageId
0x180057190  lea     r8d, [rcx-1]; cNumberOfSubStrings
0x180057194  call    cs:__imp_LogEventA
0x18005719a  test    edi, edi
0x18005719c  jnz     loc_1800572A0
0x1800571a2  test    r14d, r14d
0x1800571a5  jnz     loc_18005727E
0x1800571ab  test    r13d, r13d
0x1800571ae  jnz     loc_18005726B
0x1800571b4  movaps  xmm0, xmmword ptr [rbx]
0x1800571b7  lea     r13d, [rdi+1]
0x1800571bb  mov     edx, r13d
0x1800571be  movdqa  [rsp+0B60h+var_B00], xmm0
0x1800571c4  lea     r8, [rsp+0B60h+var_B10]
0x1800571c9  lea     rcx, [rsp+0B60h+var_B00]
0x1800571ce  call    RasGetRoutingDomainAddressPool
0x1800571d3  test    eax, eax
0x1800571d5  jnz     loc_18005726B
0x1800571db  mov     r14, [rsp+0B60h+var_B10]
0x1800571e0  test    r14, r14
0x1800571e3  jz      short loc_180057213
0x1800571e5  jmp     short loc_18005720A
0x1800571e7  movaps  xmm0, xmmword ptr [rbx]
0x1800571ea  lea     rcx, [rsp+0B60h+var_B00]
0x1800571ef  mov     r9, [rax+20h]
0x1800571f3  mov     r8, [rax+18h]
0x1800571f7  mov     edx, [rax+10h]
0x1800571fa  movdqa  [rsp+0B60h+var_B00], xmm0
0x180057200  mov     dword ptr [rsp+0B60h+lpOutBuffer], r13d
0x180057205  call    RasSrvrReleaseAddress
0x18005720a  mov     rax, [r14+18h]
0x18005720e  test    rax, rax
0x180057211  jnz     short loc_1800571E7
0x180057213  movaps  xmm0, xmmword ptr [rbx]
0x180057216  lea     rcx, [rsp+0B60h+var_B00]
0x18005721b  movdqa  [rsp+0B60h+var_B00], xmm0
0x180057221  call    RasReleaseRoutingDomainAddressPool
0x180057226  test    eax, eax
0x180057228  jz      short loc_18005726B
0x18005722a  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180057232  jz      short loc_18005726B
0x180057234  xor     ecx, ecx
0x180057236  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x18005723d  mov     word ptr [rbp+0A60h+var_A60], cx
0x180057241  mov     r8d, eax
0x180057244  lea     rcx, [rbp+0A60h+var_A60]
0x180057248  call    FormatRRASErrorString
0x18005724d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180057254  lea     r8, [rbp+0A60h+var_A60]
0x180057258  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005725f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005726b  movaps  xmm0, xmmword ptr [rbx]
0x18005726e  lea     rcx, [rsp+0B60h+var_B00]
0x180057273  movdqa  [rsp+0B60h+var_B00], xmm0
0x180057279  call    RasStatUninitialize
0x18005727e  mov     r9d, [rsp+0B60h+var_B18]
0x180057283  mov     r8d, esi
0x180057286  xor     edx, edx
0x180057288  mov     ecx, esi; dwAddress
0x18005728a  call    RasTcpSetProxyArp
0x18005728f  mov     rcx, rbx
0x180057292  call    RasRdGetServerAdapterLuidIndex
0x180057297  mov     ecx, eax
0x180057299  mov     edx, esi
0x18005729b  call    ResetIpAddressOnInterface
0x1800572a0  xor     esi, esi
0x1800572a2  test    r15d, r15d
0x1800572a5  jz      short loc_1800572B0
0x1800572a7  test    r12d, r12d
0x1800572aa  jz      loc_18005733B
0x1800572b0  lea     r9, [rbp+0A60h+var_260]
0x1800572b7  mov     dword ptr [rsp+0B60h+Addr.S_un], 204h
0x1800572bf  lea     r8, [rsp+0B60h+Addr]
0x1800572c4  mov     edx, 6
0x1800572c9  mov     rcx, rbx
0x1800572cc  call    RasRoutingDomainGetConfigParam
0x1800572d1  mov     dword ptr [rsp+0B60h+lpBytesReturned], esi
0x1800572d5  lea     rdx, [rbp+0A60h+var_260]
0x1800572dc  mov     [rsp+0B60h+nOutBufferSize], esi
0x1800572e0  xor     r9d, r9d
0x1800572e3  xor     r8d, r8d
0x1800572e6  mov     dword ptr [rsp+0B60h+lpOutBuffer], esi
0x1800572ea  xor     ecx, ecx
0x1800572ec  call    cs:__imp_DhcpNotifyConfigChange
0x1800572f2  test    eax, eax
0x1800572f4  jz      short loc_18005733B
0x1800572f6  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x1800572fd  jz      short loc_18005733B
0x1800572ff  mov     r9d, eax
0x180057302  mov     word ptr [rbp+0A60h+var_A60], si
0x180057306  lea     r8, [rbp+0A60h+var_260]
0x18005730d  lea     rdx, aDhcpnotifyconf; "DhcpNotifyConfigChange(%ws) failed and "...
0x180057314  lea     rcx, [rbp+0A60h+var_A60]
0x180057318  call    FormatRRASErrorString
0x18005731d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180057324  lea     r8, [rbp+0A60h+var_A60]
0x180057328  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005732f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005733b  test    edi, edi
0x18005733d  jnz     loc_18005744C
0x180057343  mov     edi, 4
0x180057348  mov     dword ptr [rsp+0B60h+Addr.S_un], esi
0x18005734c  mov     edx, edi
0x18005734e  mov     dword ptr [rsp+0B60h+var_B10], edi
0x180057352  lea     r9, [rsp+0B60h+Addr]
0x180057357  mov     rcx, rbx
0x18005735a  lea     r8, [rsp+0B60h+var_B10]
0x18005735f  call    RasRoutingDomainGetConfigParam
0x180057364  cmp     dword ptr [rsp+0B60h+Addr.S_un], esi
0x180057368  jz      loc_180057436
0x18005736e  mov     eax, [rsp+0B60h+var_B18]
0x180057372  lea     r9d, [rdi+10h]; nInBufferSize
0x180057376  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hDevice
0x18005737d  lea     r8, [rsp+0B60h+OutBuffer]; lpInBuffer
0x180057382  mov     dword ptr [rbp+0A60h+OutBuffer+8], eax
0x180057385  mov     edx, 90018014h; dwIoControlCode
0x18005738a  mov     [rsp+0B60h+lpOverlapped], rsi; lpOverlapped
0x18005738f  lea     rax, [rsp+0B60h+BytesReturned]
0x180057394  mov     [rsp+0B60h+lpBytesReturned], rax; lpBytesReturned
0x180057399  lea     rax, [rsp+0B60h+OutBuffer]
0x18005739e  mov     [rsp+0B60h+nOutBufferSize], r9d; nOutBufferSize
0x1800573a3  mov     [rsp+0B60h+lpOutBuffer], rax; lpOutBuffer
0x1800573a8  mov     dword ptr [rsp+0B60h+OutBuffer], esi
0x1800573ac  call    cs:__imp_DeviceIoControl
0x1800573b2  test    eax, eax
0x1800573b4  jnz     short loc_1800573FA
0x1800573b6  call    cs:__imp_GetLastError
0x1800573bc  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x1800573c3  jz      short loc_1800573FA
0x1800573c5  mov     r8d, eax
0x1800573c8  mov     word ptr [rbp+0A60h+var_A60], si
0x1800573cc  lea     rdx, aErrorDUnmappin; "Error %d unmapping server adapter"
0x1800573d3  lea     rcx, [rbp+0A60h+var_A60]
0x1800573d7  call    FormatRRASErrorString
0x1800573dc  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800573e3  lea     r8, [rbp+0A60h+var_A60]
0x1800573e7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800573ee  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800573f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800573fa  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180057401  test    rdx, rdx
0x180057404  jz      short loc_180057420
0x180057406  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005740d  lea     r8, aRassrvradapter; "RasSrvrAdapterUnMapped"
0x180057414  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005741b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057420  lea     r9, [rsp+0B60h+var_B10]
0x180057425  mov     dword ptr [rsp+0B60h+var_B10], esi
  ... truncated ...
```
