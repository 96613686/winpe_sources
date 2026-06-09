# DownstreamTransport::SetupBinding(_GUID const &,Config::Connection const *,int,INetwork::RemotePartnerInfo &,void * *,ScopedImpersonator<TokenImpersonator> &)

- ea: `0x1401ad9ac`
- end: `0x1401ae1ff`
- name: `?SetupBinding@DownstreamTransport@@CAPEAVFrsStatus@@AEBU_GUID@@PEBVConnection@Config@@HAEAVRemotePartnerInfo@INetwork@@PEAPEAXAEAV?$ScopedImpersonator@VTokenImpersonator@@@@@Z`
- size: `2131`
- prototype: `__int64 __fastcall(int, int, int, int, RPC_BINDING_HANDLE *Binding, __int64)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401a5d04`
- `0x1401a6c74`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cd1c`
- `0x14000daa0`
- `0x140010680`
- `0x1400191fc`
- `0x140024868`
- `0x140024be4`
- `0x140028fcc`
- `0x140029064`
- `0x140041814`
- `0x140041cd0`
- `0x140047e14`
- `0x140047e4c`
- `0x1401979c8`
- `0x140197d18`
- `0x1401a2844`
- `0x1401a2910`
- `0x1401a4da4`
- `0x1401a52dc`
- `0x1401a75c8`
- `0x1401a7cc0`
- `0x1401a7f28`
- `0x1401ad9ac`
- `0x1401af778`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401adb39`
- `KERNEL32!GetCurrentThreadId` at `0x1401adb9b`
- `KERNEL32!GetCurrentThreadId` at `0x1401adc2a`
- `KERNEL32!GetCurrentThreadId` at `0x1401add01`
- `KERNEL32!GetCurrentThreadId` at `0x1401addd0`
- `KERNEL32!GetCurrentThreadId` at `0x1401ade6f`
- `KERNEL32!GetCurrentThreadId` at `0x1401ae144`
- `KERNEL32!GetCurrentThreadId` at `0x1401adb39`
- `KERNEL32!GetCurrentThreadId` at `0x1401adb9b`
- `KERNEL32!GetCurrentThreadId` at `0x1401adc2a`
- `KERNEL32!GetCurrentThreadId` at `0x1401add01`
- `KERNEL32!GetCurrentThreadId` at `0x1401addd0`
- `KERNEL32!GetCurrentThreadId` at `0x1401ade6f`
- `KERNEL32!GetCurrentThreadId` at `0x1401ae144`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1401ade61`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1401ade61`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x1401adcf3`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x1401adcf3`
- `RPCRT4!RpcBindingSetOption` at `0x1401adc1c`
- `RPCRT4!RpcBindingSetOption` at `0x1401adc1c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1401adb8d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1401adb8d`
- `RPCRT4!RpcStringBindingComposeW` at `0x1401adb2b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1401adb2b`
- `WS2_32!WSAAddressToStringW` at `0x1401ae0c3`
- `WS2_32!WSAAddressToStringW` at `0x1401ae0c3`
- `WS2_32!GetAddrInfoW` at `0x1401ae03f`
- `WS2_32!GetAddrInfoW` at `0x1401ae03f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DownstreamTransport::SetupBinding(
        struct _GUID *a1,
        __int64 a2,
        INT a3,
        __int64 a4,
        RPC_BINDING_HANDLE *Binding,
        __int64 a6)
{
  __int64 v9; // rbx
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r9
  unsigned __int16 *v14; // rcx
  unsigned int v15; // esi
  DWORD CurrentThreadId; // eax
  __int64 v17; // rcx
  ConfigContext *v18; // rcx
  unsigned int *v19; // rdi
  DWORD v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  DWORD v26; // eax
  __int64 v27; // rcx
  RPC_WSTR v28; // r14
  DWORD v29; // eax
  __int64 v30; // rcx
  DWORD v31; // eax
  __int64 v32; // rcx
  DWORD v33; // eax
  __int64 v34; // rcx
  int v35; // edx
  int v36; // edx
  const WCHAR *v37; // rax
  struct _GUID **p_AddrInfoW; // r8
  const wchar_t *v39; // rdx
  DWORD v40; // eax
  __int64 v41; // rcx
  PADDRINFOW ppResult; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+60h] [rbp-A0h]
  int v46; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v47; // [rsp+68h] [rbp-98h]
  INT AddrInfoW; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID *v49; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwAddressStringLength[2]; // [rsp+80h] [rbp-80h] BYREF
  RPC_WSTR StringBinding; // [rsp+88h] [rbp-78h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+90h] [rbp-70h] BYREF
  struct Config::Machine *Machine; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v56[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v57[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v58; // [rsp+E8h] [rbp-18h]
  _BYTE v59[40]; // [rsp+F8h] [rbp-8h] BYREF
  void **v60; // [rsp+120h] [rbp+20h] BYREF
  char v61; // [rsp+150h] [rbp+50h] BYREF
  WCHAR szAddressString[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  v54 = a4;
  AddrInfoW = a3;
  v49 = a1;
  std::wstring::wstring(v57);
  std::wstring::wstring(v56);
  std::wstring::wstring(v59);
  v9 = 0;
  StringBinding = 0;
  ServerPrincName = 0;
  Config::GuidParam::GuidParam((Config::GuidParam *)&v60, v10);
  Machine = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v44 = L"DownstreamTransport::SetupBinding";
    v45 = 3232;
    v46 = 5;
    v47 = L"DOWN";
    dbgobj::DbgPrint<unsigned short>(&v44, L"Entering SetupBinding");
  }
  DownstreamTransport::GetRemoteAddress(a2, v56, v57);
  if ( a3 )
  {
    std::wstring::find_first_of(v56);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
    std::wstring::assign(v59);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    FrsStringImpl<unsigned short,char>::Set(a4, v11);
  }
  else
  {
    std::wstring::operator=(v59, v56);
  }
  if ( v58 )
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
  v12 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  v14 = (unsigned __int16 *)&v61;
  if ( v13 )
    v14 = 0;
  v15 = RpcStringBindingComposeW(v14, (RPC_WSTR)L"ncacn_ip_tcp", v12, v13, 0, &StringBinding);
  CurrentThreadId = GetCurrentThreadId();
  v19 = (unsigned int *)FrsStatusList::PushNewError(
                          v17,
                          v15,
                          0,
                          1,
                          "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                          "DownstreamTransport::SetupBinding",
                          3260,
                          CurrentThreadId,
                          0);
  if ( !v19 )
  {
    v15 = RpcBindingFromStringBindingW(StringBinding, Binding);
    v20 = GetCurrentThreadId();
    v19 = (unsigned int *)FrsStatusList::PushNewError(
                            v21,
                            v15,
                            0,
                            1,
                            "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                            "DownstreamTransport::SetupBinding",
                            3266,
                            v20,
                            0);
  }
  SecurityQOS.Version = 1;
  *(_QWORD *)&SecurityQOS.Capabilities = 1;
  SecurityQOS.ImpersonationType = 3;
  Machine = ConfigContext::GetMachine(v18);
  v22 = Config::BoolParam::Get((struct Config::Machine *)((char *)Machine + 736));
  if ( v19 )
    goto LABEL_38;
  v15 = RpcBindingSetOption(*Binding, 0xCu, v22);
  v26 = GetCurrentThreadId();
  v19 = (unsigned int *)FrsStatusList::PushNewError(
                          v27,
                          v15,
                          0,
                          1,
                          "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                          "DownstreamTransport::SetupBinding",
                          3291,
                          v26,
                          0);
  if ( v19 )
    goto LABEL_38;
  v28 = (RPC_WSTR)Config::StringParam::Get((Config::StringParam *)(a2 + 520));
  ppResult = (PADDRINFOW)v28;
  if ( !v28 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v44 = L"DownstreamTransport::SetupBinding";
      v45 = 3299;
      v46 = 4;
      v47 = L"DOWN";
      dbgobj::DbgPrint<unsigned short>(&v44, L"Obtaining princName anonymously using RPC. This is disabled by default.");
    }
    v15 = RpcMgmtInqServerPrincNameW(*Binding, 9u, &ServerPrincName);
    v29 = GetCurrentThreadId();
    v19 = (unsigned int *)FrsStatusList::PushNewError(
                            v30,
                            v15,
                            0,
                            1,
                            "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                            "DownstreamTransport::SetupBinding",
                            3308,
                            v29,
                            0);
    v28 = ServerPrincName;
    ppResult = (PADDRINFOW)ServerPrincName;
    if ( v19 )
      goto LABEL_38;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v44 = L"DownstreamTransport::SetupBinding";
    v45 = 3314;
    v46 = 4;
    v47 = L"DOWN";
    dbgobj::DbgPrint<unsigned short,unsigned short const *>(
      &v44,
      L"Setting authentication information for partner: %ws",
      &ppResult);
  }
  ppResult = 0;
  ppResult = (PADDRINFOW)ConfigContext::GetReplicaSet(g_ConfigContext, v49);
  if ( ppResult
    || (v31 = GetCurrentThreadId(),
        (v19 = (unsigned int *)FrsStatusList::PushNewError(
                                 v32,
                                 9026,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                 "DownstreamTransport::SetupBinding",
                                 3324,
                                 v31,
                                 0)) == 0) )
  {
    if ( !*(_QWORD *)(*(_QWORD *)a6 + 24LL)
      || (v19 = (unsigned int *)ScopedImpersonator<TokenImpersonator>::Impersonate(a6)) == 0 )
    {
      v15 = RpcBindingSetAuthInfoExW(*Binding, v28, 6u, 9u, 0, 0, &SecurityQOS);
      v33 = GetCurrentThreadId();
      v19 = (unsigned int *)FrsStatusList::PushNewError(
                              v34,
                              v15,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                              "DownstreamTransport::SetupBinding",
                              3345,
                              v33,
                              0);
    }
  }
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&ppResult);
  if ( v19 )
  {
LABEL_38:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v44 = L"DownstreamTransport::SetupBinding";
      v45 = 3351;
      v46 = 2;
      v47 = L"DOWN";
      ppResult = (PADDRINFOW)StringBinding;
      v49 = (struct _GUID *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
      *(_QWORD *)dwAddressStringLength = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,unsigned short *,FrsStatus>(
        (unsigned int)&v44,
        v36,
        a2 + 136,
        (unsigned int)dwAddressStringLength,
        (__int64)&v49,
        (__int64)&ppResult,
        (__int64)v19);
    }
    if ( v15 )
      LogExtendedErrorInformation_0(v24, v23, v25);
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v44 = L"DownstreamTransport::SetupBinding";
    v45 = 3365;
    v46 = 4;
    v47 = L"DOWN";
    ppResult = (PADDRINFOW)StringBinding;
    v49 = (struct _GUID *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
    *(_QWORD *)dwAddressStringLength = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,unsigned short *>(
      (unsigned int)&v44,
      v35,
      a2 + 136,
      (unsigned int)dwAddressStringLength,
      (__int64)&v49,
      (__int64)&ppResult);
  }
  if ( AddrInfoW )
  {
    ppResult = 0;
    v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
    AddrInfoW = GetAddrInfoW(v37, &pServiceName, 0, &ppResult);
    if ( AddrInfoW )
    {
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 3 )
        goto LABEL_56;
      v45 = 3379;
      p_AddrInfoW = (struct _GUID **)&AddrInfoW;
      v39 = L"Could not retrieve address %d";
      goto LABEL_55;
    }
    if ( ppResult )
    {
      dwAddressStringLength[0] = 259;
      LODWORD(v49) = WSAAddressToStringW(
                       ppResult->ai_addr,
                       ppResult->ai_addrlen,
                       0,
                       szAddressString,
                       dwAddressStringLength);
      if ( (_DWORD)v49 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 3 )
          goto LABEL_56;
        v45 = 3398;
        p_AddrInfoW = &v49;
        v39 = L"Ignored %d";
LABEL_55:
        v44 = L"DownstreamTransport::SetupBinding";
        v46 = 3;
        v47 = L"DOWN";
        dbgobj::DbgPrint<unsigned short,int>(&v44, v39, p_AddrInfoW);
        goto LABEL_56;
      }
      FrsStringImpl<unsigned short,char>::Set(v54 + 8, szAddressString);
    }
LABEL_56:
    scoped_any<addrinfoW *,AddrInfoFree,null_t,0>::~scoped_any<addrinfoW *,AddrInfoFree,null_t,0>(&ppResult);
  }
  if ( v19 )
  {
    v40 = GetCurrentThreadId();
    v9 = FrsStatusList::PushNewError(
           v41,
           v19[1],
           v19[2],
           *v19,
           "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
           "DownstreamTransport::SetupBinding",
           3403,
           v40,
           v19);
  }
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&Machine);
  v60 = &Config::Parameter::`vftable';
  scoped_any<unsigned short *,close_rpc_string,null_t,0>::~scoped_any<unsigned short *,close_rpc_string,null_t,0>(&ServerPrincName);
  scoped_any<unsigned short *,close_rpc_string,null_t,0>::~scoped_any<unsigned short *,close_rpc_string,null_t,0>(&StringBinding);
  std::wstring::~wstring(v59);
  std::wstring::~wstring(v56);
  std::wstring::~wstring(v57);
  return v9;
}

```

## disassembly

```asm
0x1401ad9ac  mov     [rsp-8+arg_0], rbx
0x1401ad9b1  push    rbp
0x1401ad9b2  push    rsi
0x1401ad9b3  push    rdi
0x1401ad9b4  push    r12
0x1401ad9b6  push    r13
0x1401ad9b8  push    r14
0x1401ad9ba  push    r15
0x1401ad9bc  lea     rbp, [rsp-2C0h]
0x1401ad9c4  sub     rsp, 3C0h
0x1401ad9cb  mov     rax, cs:__security_cookie
0x1401ad9d2  xor     rax, rsp
0x1401ad9d5  mov     [rbp+2F0h+var_40], rax
0x1401ad9dc  mov     rsi, r9
0x1401ad9df  mov     [rbp+2F0h+var_350], r9
0x1401ad9e3  mov     edi, r8d
0x1401ad9e6  mov     [rsp+3F0h+var_380], r8d
0x1401ad9eb  mov     r15, rdx
0x1401ad9ee  mov     [rsp+3F0h+var_378], rcx
0x1401ad9f3  mov     r12, [rbp+2F0h+Binding]
0x1401ad9fa  mov     r13, [rbp+2F0h+arg_28]
0x1401ada01  lea     rcx, [rbp+2F0h+var_318]
0x1401ada05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1401ada0a  nop
0x1401ada0b  lea     rcx, [rbp+2F0h+var_338]
0x1401ada0f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1401ada14  nop
0x1401ada15  lea     rcx, [rbp+2F0h+var_2F8]
0x1401ada19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1401ada1e  nop
0x1401ada1f  xor     ebx, ebx
0x1401ada21  mov     [rbp+2F0h+var_368], rbx
0x1401ada25  mov     [rbp+2F0h+ServerPrincName], rbx
0x1401ada29  lea     rcx, [rbp+2F0h+var_2D0]; this
0x1401ada2d  call    ??0GuidParam@Config@@QEAA@PEBG@Z; Config::GuidParam::GuidParam(ushort const *)
0x1401ada32  nop
0x1401ada33  mov     [rbp+2F0h+var_358], rbx
0x1401ada37  lea     r14, aDownstreamtran_26; "DownstreamTransport::SetupBinding"
0x1401ada3e  lea     rcx, aDown; "DOWN"
0x1401ada45  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ada4c  test    rax, rax
0x1401ada4f  jz      short loc_1401ADA87
0x1401ada51  cmp     [rax+40h], ebx
0x1401ada54  jz      short loc_1401ADA87
0x1401ada56  cmp     dword ptr [rax+38h], 5
0x1401ada5a  jl      short loc_1401ADA87
0x1401ada5c  mov     [rsp+3F0h+var_398], r14
0x1401ada61  mov     [rsp+3F0h+var_390], 0CA0h
0x1401ada69  mov     [rsp+3F0h+var_38C], 5
0x1401ada71  mov     [rsp+3F0h+var_388], rcx
0x1401ada76  lea     rdx, aEnteringSetupb; "Entering SetupBinding"
0x1401ada7d  lea     rcx, [rsp+3F0h+var_398]
0x1401ada82  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401ada87  lea     r8, [rbp+2F0h+var_318]
0x1401ada8b  lea     rdx, [rbp+2F0h+var_338]
0x1401ada8f  mov     rcx, r15
0x1401ada92  call    ?GetRemoteAddress@DownstreamTransport@@CAXPEBVConnection@Config@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; DownstreamTransport::GetRemoteAddress(Config::Connection const *,std::wstring &,std::wstring &)
0x1401ada97  test    edi, edi
0x1401ada99  jz      short loc_1401ADADB
0x1401ada9b  lea     rcx, [rbp+2F0h+var_338]
0x1401ada9f  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x1401adaa4  mov     r8, rax
0x1401adaa7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401adaab  cmovz   r8, [rbp+2F0h+var_328]
0x1401adab0  lea     rcx, [rbp+2F0h+var_338]
0x1401adab4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1401adab9  mov     rdx, rax
0x1401adabc  lea     rcx, [rbp+2F0h+var_2F8]; void *
0x1401adac0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1401adac5  lea     rcx, [rbp+2F0h+var_2F8]
0x1401adac9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1401adace  mov     rdx, rax
0x1401adad1  mov     rcx, rsi
0x1401adad4  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401adad9  jmp     short loc_1401ADAE8
0x1401adadb  lea     rdx, [rbp+2F0h+var_338]
0x1401adadf  lea     rcx, [rbp+2F0h+var_2F8]
0x1401adae3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1401adae8  cmp     [rbp+2F0h+var_308], rbx
0x1401adaec  jnz     short loc_1401ADAF3
0x1401adaee  mov     r9, rbx
0x1401adaf1  jmp     short loc_1401ADAFF
0x1401adaf3  lea     rcx, [rbp+2F0h+var_318]
0x1401adaf7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1401adafc  mov     r9, rax
0x1401adaff  lea     rcx, [rbp+2F0h+var_2F8]
0x1401adb03  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1401adb08  lea     rcx, [rbp+2F0h+var_2A0]
0x1401adb0c  test    r9, r9
0x1401adb0f  cmovnz  rcx, rbx; ObjUuid
0x1401adb13  lea     rdx, [rbp+2F0h+var_368]
0x1401adb17  mov     [rsp+3F0h+StringBinding], rdx; StringBinding
0x1401adb1c  mov     [rsp+3F0h+Options], rbx; Options
0x1401adb21  mov     r8, rax; NetworkAddr
0x1401adb24  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x1401adb2b  call    cs:__imp_RpcStringBindingComposeW
0x1401adb32  nop     dword ptr [rax+rax+00h]
0x1401adb37  mov     esi, eax
0x1401adb39  call    cs:__imp_GetCurrentThreadId
0x1401adb40  nop     dword ptr [rax+rax+00h]
0x1401adb45  mov     [rsp+3F0h+var_3B0], rbx
0x1401adb4a  mov     [rsp+3F0h+var_3B8], eax
0x1401adb4e  mov     dword ptr [rsp+3F0h+SecurityQOS], 0CBCh
0x1401adb56  lea     rax, aDownstreamtran_33; "DownstreamTransport::SetupBinding"
0x1401adb5d  mov     [rsp+3F0h+StringBinding], rax
0x1401adb62  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401adb69  mov     [rsp+3F0h+Options], rax
0x1401adb6e  mov     r9d, 1
0x1401adb74  xor     r8d, r8d
0x1401adb77  mov     edx, esi
0x1401adb79  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401adb7e  mov     rdi, rax
0x1401adb81  test    rax, rax
0x1401adb84  jnz     short loc_1401ADBE1
0x1401adb86  mov     rdx, r12; Binding
0x1401adb89  mov     rcx, [rbp+2F0h+var_368]; StringBinding
0x1401adb8d  call    cs:__imp_RpcBindingFromStringBindingW
0x1401adb94  nop     dword ptr [rax+rax+00h]
0x1401adb99  mov     esi, eax
0x1401adb9b  call    cs:__imp_GetCurrentThreadId
0x1401adba2  nop     dword ptr [rax+rax+00h]
0x1401adba7  mov     [rsp+3F0h+var_3B0], rbx
0x1401adbac  mov     [rsp+3F0h+var_3B8], eax
0x1401adbb0  mov     dword ptr [rsp+3F0h+SecurityQOS], 0CC2h
0x1401adbb8  lea     rax, aDownstreamtran_33; "DownstreamTransport::SetupBinding"
0x1401adbbf  mov     [rsp+3F0h+StringBinding], rax
0x1401adbc4  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401adbcb  mov     [rsp+3F0h+Options], rax
0x1401adbd0  lea     r9d, [rdi+1]
0x1401adbd4  xor     r8d, r8d
0x1401adbd7  mov     edx, esi
0x1401adbd9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401adbde  mov     rdi, rax
0x1401adbe1  mov     eax, 1
0x1401adbe6  mov     [rbp+2F0h+var_348.Version], eax
0x1401adbe9  mov     qword ptr [rbp+2F0h+var_348.Capabilities], rax
0x1401adbed  mov     [rbp+2F0h+var_348.ImpersonationType], 3
0x1401adbf4  call    ?GetMachine@ConfigContext@@QEAAPEAVMachine@Config@@XZ; ConfigContext::GetMachine(void)
0x1401adbf9  mov     [rbp+2F0h+var_358], rax
0x1401adbfd  lea     rcx, [rax+2E0h]; this
0x1401adc04  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1401adc09  test    rdi, rdi
0x1401adc0c  jnz     loc_1401ADF6E
0x1401adc12  mov     r8d, eax; optionValue
0x1401adc15  lea     edx, [rdi+0Ch]; option
0x1401adc18  mov     rcx, [r12]; hBinding
0x1401adc1c  call    cs:__imp_RpcBindingSetOption
0x1401adc23  nop     dword ptr [rax+rax+00h]
0x1401adc28  mov     esi, eax
0x1401adc2a  call    cs:__imp_GetCurrentThreadId
0x1401adc31  nop     dword ptr [rax+rax+00h]
0x1401adc36  mov     [rsp+3F0h+var_3B0], rbx
0x1401adc3b  mov     [rsp+3F0h+var_3B8], eax
0x1401adc3f  mov     dword ptr [rsp+3F0h+SecurityQOS], 0CDBh
0x1401adc47  lea     rax, aDownstreamtran_33; "DownstreamTransport::SetupBinding"
0x1401adc4e  mov     [rsp+3F0h+StringBinding], rax
0x1401adc53  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401adc5a  mov     [rsp+3F0h+Options], rax
0x1401adc5f  lea     r9d, [rdi+1]
0x1401adc63  xor     r8d, r8d
0x1401adc66  mov     edx, esi
0x1401adc68  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401adc6d  mov     rdi, rax
0x1401adc70  test    rax, rax
0x1401adc73  jnz     loc_1401ADF6E
0x1401adc79  lea     rcx, [r15+208h]; this
0x1401adc80  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x1401adc85  mov     r14, rax
0x1401adc88  mov     [rsp+3F0h+ppResult], rax
0x1401adc8d  test    rax, rax
0x1401adc90  jnz     loc_1401ADD5B
0x1401adc96  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401adc9d  test    rax, rax
0x1401adca0  jz      short loc_1401ADCE6
0x1401adca2  cmp     [rax+40h], ebx
0x1401adca5  jz      short loc_1401ADCE6
0x1401adca7  cmp     dword ptr [rax+38h], 4
0x1401adcab  jl      short loc_1401ADCE6
0x1401adcad  lea     rax, aDownstreamtran_26; "DownstreamTransport::SetupBinding"
0x1401adcb4  mov     [rsp+3F0h+var_398], rax
0x1401adcb9  mov     [rsp+3F0h+var_390], 0CE3h
0x1401adcc1  mov     [rsp+3F0h+var_38C], 4
0x1401adcc9  lea     rax, aDown; "DOWN"
0x1401adcd0  mov     [rsp+3F0h+var_388], rax
0x1401adcd5  lea     rdx, aObtainingPrinc; "Obtaining princName anonymously using R"...
0x1401adcdc  lea     rcx, [rsp+3F0h+var_398]
0x1401adce1  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401adce6  lea     r8, [rbp+2F0h+ServerPrincName]; ServerPrincName
0x1401adcea  mov     edx, 9; AuthnSvc
0x1401adcef  mov     rcx, [r12]; Binding
0x1401adcf3  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x1401adcfa  nop     dword ptr [rax+rax+00h]
0x1401adcff  mov     esi, eax
0x1401add01  call    cs:__imp_GetCurrentThreadId
0x1401add08  nop     dword ptr [rax+rax+00h]
0x1401add0d  mov     [rsp+3F0h+var_3B0], rbx
0x1401add12  mov     [rsp+3F0h+var_3B8], eax
0x1401add16  mov     dword ptr [rsp+3F0h+SecurityQOS], 0CECh
0x1401add1e  lea     rax, aDownstreamtran_33; "DownstreamTransport::SetupBinding"
0x1401add25  mov     [rsp+3F0h+StringBinding], rax
0x1401add2a  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401add31  mov     [rsp+3F0h+Options], rax
0x1401add36  mov     r9d, 1
0x1401add3c  xor     r8d, r8d
0x1401add3f  mov     edx, esi
0x1401add41  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401add46  mov     rdi, rax
0x1401add49  mov     r14, [rbp+2F0h+ServerPrincName]
0x1401add4d  mov     [rsp+3F0h+ppResult], r14
0x1401add52  test    rax, rax
0x1401add55  jnz     loc_1401ADF67
0x1401add5b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401add62  test    rax, rax
0x1401add65  jz      short loc_1401ADDB0
0x1401add67  cmp     [rax+40h], ebx
0x1401add6a  jz      short loc_1401ADDB0
0x1401add6c  cmp     dword ptr [rax+38h], 4
0x1401add70  jl      short loc_1401ADDB0
0x1401add72  lea     rax, aDownstreamtran_26; "DownstreamTransport::SetupBinding"
0x1401add79  mov     [rsp+3F0h+var_398], rax
0x1401add7e  mov     [rsp+3F0h+var_390], 0CF2h
0x1401add86  mov     [rsp+3F0h+var_38C], 4
0x1401add8e  lea     rax, aDown; "DOWN"
0x1401add95  mov     [rsp+3F0h+var_388], rax
0x1401add9a  lea     r8, [rsp+3F0h+ppResult]
0x1401add9f  lea     rdx, aSettingAuthent; "Setting authentication information for "...
0x1401adda6  lea     rcx, [rsp+3F0h+var_398]
0x1401addab  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401addb0  mov     [rsp+3F0h+ppResult], rbx
0x1401addb5  mov     rdx, [rsp+3F0h+var_378]; struct _GUID *
0x1401addba  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; this
0x1401addc1  call    ?GetReplicaSet@ConfigContext@@QEAAPEAVReplicaSet@Config@@PEBU_GUID@@@Z; ConfigContext::GetReplicaSet(_GUID const *)
0x1401addc6  mov     [rsp+3F0h+ppResult], rax
0x1401addcb  test    rax, rax
0x1401addce  jnz     short loc_1401ADE24
0x1401addd0  call    cs:__imp_GetCurrentThreadId
0x1401addd7  nop     dword ptr [rax+rax+00h]
0x1401adddc  mov     [rsp+3F0h+var_3B0], rbx
0x1401adde1  mov     [rsp+3F0h+var_3B8], eax
0x1401adde5  mov     dword ptr [rsp+3F0h+SecurityQOS], 0CFCh
0x1401added  lea     rax, aDownstreamtran_33; "DownstreamTransport::SetupBinding"
0x1401addf4  mov     [rsp+3F0h+StringBinding], rax
0x1401addf9  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ade00  mov     [rsp+3F0h+Options], rax
0x1401ade05  mov     r9d, 3
0x1401ade0b  xor     r8d, r8d
0x1401ade0e  mov     edx, 2342h
0x1401ade13  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ade18  mov     rdi, rax
0x1401ade1b  test    rax, rax
0x1401ade1e  jnz     loc_1401ADEB7
0x1401ade24  mov     rax, [r13+0]
0x1401ade28  cmp     [rax+18h], rbx
0x1401ade2c  jz      short loc_1401ADE3E
0x1401ade2e  mov     rcx, r13
0x1401ade31  call    ?Impersonate@?$ScopedImpersonator@VTokenImpersonator@@@@QEAAPEAVFrsStatus@@XZ; ScopedImpersonator<TokenImpersonator>::Impersonate(void)
0x1401ade36  mov     rdi, rax
0x1401ade39  test    rax, rax
0x1401ade3c  jnz     short loc_1401ADEB7
0x1401ade3e  lea     rax, [rbp+2F0h+var_348]
0x1401ade42  mov     [rsp+3F0h+SecurityQOS], rax; SecurityQOS
0x1401ade47  mov     dword ptr [rsp+3F0h+StringBinding], ebx; AuthzSvc
0x1401ade4b  mov     [rsp+3F0h+Options], rbx; AuthIdentity
0x1401ade50  mov     r9d, 9; AuthnSvc
0x1401ade56  lea     r8d, [r9-3]; AuthnLevel
0x1401ade5a  mov     rdx, r14; ServerPrincName
0x1401ade5d  mov     rcx, [r12]; Binding
0x1401ade61  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1401ade68  nop     dword ptr [rax+rax+00h]
0x1401ade6d  mov     esi, eax
0x1401ade6f  call    cs:__imp_GetCurrentThreadId
0x1401ade76  nop     dword ptr [rax+rax+00h]
0x1401ade7b  mov     [rsp+3F0h+var_3B0], rbx
0x1401ade80  mov     [rsp+3F0h+var_3B8], eax
0x1401ade84  mov     dword ptr [rsp+3F0h+SecurityQOS], 0D11h
0x1401ade8c  lea     rax, aDownstreamtran_33; "DownstreamTransport::SetupBinding"
0x1401ade93  mov     [rsp+3F0h+StringBinding], rax
0x1401ade98  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ade9f  mov     [rsp+3F0h+Options], rax
0x1401adea4  mov     r9d, 1
0x1401adeaa  xor     r8d, r8d
0x1401adead  mov     edx, esi
0x1401adeaf  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401adeb4  mov     rdi, rax
0x1401adeb7  lea     rcx, [rsp+3F0h+ppResult]
0x1401adebc  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x1401adec1  test    rdi, rdi
0x1401adec4  jnz     loc_1401ADF67
0x1401adeca  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401aded1  lea     rsi, aDownstreamtran_26; "DownstreamTransport::SetupBinding"
0x1401aded8  lea     r14, aDown; "DOWN"
0x1401adedf  test    rax, rax
0x1401adee2  jz      loc_1401AE015
0x1401adee8  cmp     [rax+40h], ebx
0x1401adeeb  jz      loc_1401AE015
0x1401adef1  cmp     dword ptr [rax+38h], 4
0x1401adef5  jl      loc_1401AE015
0x1401adefb  mov     [rsp+3F0h+var_398], rsi
0x1401adf00  mov     [rsp+3F0h+var_390], 0D25h
0x1401adf08  mov     [rsp+3F0h+var_38C], 4
  ... truncated ...
```
