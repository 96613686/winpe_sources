# ServiceStart(ulong,ushort * *,int)

- ea: `0x180037a5c`
- end: `0x180038274`
- name: `?ServiceStart@@YAKKPEAPEAGH@Z`
- size: `2072`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180037730`

## callees

- `0x18000205c`
- `0x180005665`
- `0x18000bb98`
- `0x18000d060`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001ebc0`
- `0x180021968`
- `0x180021994`
- `0x180021a4c`
- `0x180025be0`
- `0x180025c1c`
- `0x180036ef8`
- `0x18003736c`
- `0x180037a5c`
- `0x1800385d8`
- `0x180077e18`
- `0x180077fd4`
- `0x18007e864`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `mstlsapi!__imp_TLSIsBetaNTServer` at `0x180037efe`
- `mstlsapi!__imp_TLSIsBetaNTServer` at `0x180037efe`
- `mstlsapi!__imp_TLSInDomain` at `0x180037dc8`
- `mstlsapi!__imp_TLSInDomain` at `0x180037dc8`
- `mstlsapi!__imp_TLSSetConnectPolicy` at `0x180037cbd`
- `mstlsapi!__imp_TLSSetConnectPolicy` at `0x180037cbd`
- `WS2_32!__imp_WSAStartup` at `0x180037c13`
- `WS2_32!__imp_WSAStartup` at `0x180037c13`
- `WS2_32!__imp_WSACleanup` at `0x1800380e7`
- `WS2_32!__imp_WSACleanup` at `0x1800380e7`
- `ole32!CoInitializeEx` at `0x180037aef`
- `ole32!CoInitializeEx` at `0x180037aef`
- `ole32!CoInitializeSecurity` at `0x180037b67`
- `ole32!CoInitializeSecurity` at `0x180037b67`
- `ole32!CoUninitialize` at `0x180038202`
- `ole32!CoUninitialize` at `0x180038202`
- `RPCRT4!RpcBindingVectorFree` at `0x180038090`
- `RPCRT4!RpcBindingVectorFree` at `0x180038090`
- `RPCRT4!RpcServerInqBindings` at `0x180038077`
- `RPCRT4!RpcServerInqBindings` at `0x180038077`
- `RPCRT4!RpcServerListen` at `0x180037f7c`
- `RPCRT4!RpcServerListen` at `0x180037f7c`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x180037fd6`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x180037fd6`
- `RPCRT4!RpcServerUnregisterIf` at `0x180038043`
- `RPCRT4!RpcServerUnregisterIf` at `0x180038043`
- `RPCRT4!RpcEpUnregister` at `0x180038062`
- `RPCRT4!RpcEpUnregister` at `0x180038062`
- `VSSAPI!?Uninitialize@CVssJetWriter@@QEAAXXZ` at `0x1800381d0`
- `VSSAPI!?Uninitialize@CVssJetWriter@@QEAAXXZ` at `0x1800381d0`
- `KERNEL32!GetExitCodeThread` at `0x180037d7f`
- `KERNEL32!GetExitCodeThread` at `0x180037e4f`
- `KERNEL32!GetExitCodeThread` at `0x180037d7f`
- `KERNEL32!GetExitCodeThread` at `0x180037e4f`
- `KERNEL32!CreateThread` at `0x180037d2d`
- `KERNEL32!CreateThread` at `0x180037e04`
- `KERNEL32!CreateThread` at `0x180038124`
- `KERNEL32!CreateThread` at `0x180037d2d`
- `KERNEL32!CreateThread` at `0x180037e04`
- `KERNEL32!CreateThread` at `0x180038124`
- `KERNEL32!GetComputerNameW` at `0x180037c2f`
- `KERNEL32!GetComputerNameW` at `0x180037c2f`
- `KERNEL32!CreateEventW` at `0x180037cd4`
- `KERNEL32!CreateEventW` at `0x180037cd4`
- `KERNEL32!GetLastError` at `0x180037c3f`
- `KERNEL32!GetLastError` at `0x180037c3f`
- `KERNEL32!WaitForSingleObject` at `0x180037d52`
- `KERNEL32!WaitForSingleObject` at `0x180037e29`
- `KERNEL32!WaitForSingleObject` at `0x180037fef`
- `KERNEL32!WaitForSingleObject` at `0x18003815c`
- `KERNEL32!WaitForSingleObject` at `0x180038191`
- `KERNEL32!WaitForSingleObject` at `0x180037d52`
- `KERNEL32!WaitForSingleObject` at `0x180037e29`
- `KERNEL32!WaitForSingleObject` at `0x180037fef`
- `KERNEL32!WaitForSingleObject` at `0x18003815c`
- `KERNEL32!WaitForSingleObject` at `0x180038191`
- `KERNEL32!CloseHandle` at `0x180037d99`
- `KERNEL32!CloseHandle` at `0x180037dad`
- `KERNEL32!CloseHandle` at `0x180037e72`
- `KERNEL32!CloseHandle` at `0x1800380d7`
- `KERNEL32!CloseHandle` at `0x1800381a5`
- `KERNEL32!CloseHandle` at `0x180037d99`
- `KERNEL32!CloseHandle` at `0x180037dad`
- `KERNEL32!CloseHandle` at `0x180037e72`
- `KERNEL32!CloseHandle` at `0x1800380d7`
- `KERNEL32!CloseHandle` at `0x1800381a5`
- `TlsBrand!GetRdlsSupportedFeatureMask` at `0x180037f0c`
- `TlsBrand!GetRdlsSupportedFeatureMask` at `0x180037f0c`
- `TlsBrand!CleanupRDLSConfig` at `0x1800381b8`
- `TlsBrand!CleanupRDLSConfig` at `0x1800381b8`

## string_xrefs

- `0x180037ad4`: `ServiceStart`
- `0x180038228`: `ServiceStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceStart(__int64 a1, unsigned __int16 **a2)
{
  char v2; // r14
  HRESULT v3; // eax
  const struct _GUID *v4; // rdx
  struct CTlsVssJetWriter *v5; // rax
  int v6; // esi
  DWORD LastError; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  HANDLE Thread; // rax
  HANDLE v10; // rbx
  DWORD v11; // eax
  int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // ebx
  unsigned int RdlsSupportedFeatureMask; // eax
  int updated; // eax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  int v19; // eax
  CRdlsDBManager *v20; // rcx
  int i; // ebx
  HANDLE v22; // rax
  void *v23; // rbx
  unsigned int v24; // edi
  DWORD j; // eax
  unsigned int v26; // eax
  DWORD ExitCode; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A8h] BYREF
  struct CTlsVssJetWriter *ThreadId; // [rsp+68h] [rbp-A0h] BYREF
  DWORD v31[2]; // [rsp+70h] [rbp-98h] BYREF
  RPC_BINDING_VECTOR *BindingVector[2]; // [rsp+78h] [rbp-90h] BYREF
  WSAData WSAData; // [rsp+88h] [rbp-80h] BYREF

  BindingVector[0] = 0;
  v31[0] = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, L"ServiceStart");
  v3 = CoInitializeEx(0, 0);
  hrStatus = v3;
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, (unsigned int)v3);
    v3 = hrStatus;
  }
  if ( v3 < 0 || (v3 = CoInitializeSecurity(0, -1, 0, 0, 2u, 2u, 0, 0, 0), hrStatus = v3, v3 < 0) )
  {
    if ( v3 != -2147417831 )
    {
      ExitCode = v3;
      goto LABEL_81;
    }
  }
  v2 = 1;
  CrimsonHelper::Init((CrimsonHelper *)CrimsonHelper::s_instance, v4);
  v5 = (struct CTlsVssJetWriter *)operator new(0x18u);
  ThreadId = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = &CVssJetWriter::`vftable';
    *((_QWORD *)v5 + 1) = 0;
    *(_QWORD *)v5 = &CTlsVssJetWriter::`vftable';
  }
  else
  {
    v5 = 0;
  }
  g_pWriter = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids);
    hrStatus = -2147024888;
  }
  v6 = WSAStartup(0x101u, &WSAData);
  if ( GetComputerNameW(&g_szComputerName, &g_cbComputerName) )
  {
    StringCbCopyW(&g_szHostName, 0x802u, &g_szComputerName);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_1594457400>::GetImpl'::`2'::impl) )
      TLSSetConnectPolicy(1);
    hRpcPause = CreateEventW(0, 1, 1, 0);
    if ( !hRpcPause )
    {
      CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_E_ALLOCATE_RESOURCE, 0, 0);
      ExitCode = 36;
      goto LABEL_70;
    }
    LODWORD(ThreadId) = 0;
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)StartServerInitThread, 0, 0, (LPDWORD)&ThreadId);
    v10 = Thread;
    if ( Thread )
    {
      ExitCode = 0;
      if ( WaitForSingleObject(Thread, 0x493E0u) )
      {
        v11 = 31;
        ExitCode = 31;
      }
      else
      {
        v11 = ExitCode;
      }
      if ( v11 )
        goto LABEL_37;
      GetExitCodeThread(v10, &ExitCode);
      if ( ExitCode )
      {
        ExitCode = 31;
        goto LABEL_37;
      }
      CloseHandle(v10);
      LODWORD(v29) = 0;
      v12 = 0;
      if ( !(unsigned int)TLSInDomain(&v29, 0) && (_DWORD)v29 == 1 )
      {
        TSLSLoadLocalGroupSecDes();
        v12 = 1;
      }
      v10 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)RPCServiceStartThread, 0, 0, v31);
      if ( v10 )
      {
        ExitCode = 0;
        while ( WaitForSingleObject(v10, 0x64u) == 258 )
          ;
        if ( !ExitCode )
        {
          GetExitCodeThread(v10, &ExitCode);
          if ( !ExitCode )
          {
            CloseHandle(v10);
            StringCchPrintfW(&g_szReportDir, 0x105u, L"%s%s", g_RdlsDBManager + 1028, L"reports\\");
            if ( !(unsigned int)ReportStatusToSCMgr(4u, 0, 0) )
            {
              ExitCode = 28;
              goto LABEL_70;
            }
            if ( !(unsigned int)InitCryptoAndCertificate(v14, v13) )
            {
              if ( v12 )
              {
                LODWORD(ThreadId) = 0;
                IsLSSCPRegistered((int *)&ThreadId);
                v15 = TLSIsBetaNTServer();
                RdlsSupportedFeatureMask = GetRdlsSupportedFeatureMask();
                updated = UpdateSCP(RdlsSupportedFeatureMask, v15);
                if ( !(_DWORD)ThreadId )
                {
                  v18 = (const struct _EVENT_DESCRIPTOR *)TLS_I_LS_REGISTERED_TO_SCP;
                  if ( updated )
                    v18 = &TLS_E_LS_REGISTERED_TO_SCP;
                  CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, v18, 0, 0);
                }
              }
              CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_I_SERVICE_START, 0, 0);
              v19 = CanIssuePermLicense();
              CRdlsDBManager::LogSettingsTelemetryData(v20, v19);
              for ( i = 0; ; i = 1 )
              {
                WaitForSingleObject(hRpcPause, 0xFFFFFFFF);
                if ( ssCurrentStatus == 3 )
                  break;
                ExitCode = RpcServerListen(1u, 0x4D2u, 1u);
                if ( ExitCode )
                {
                  CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_E_RPC_LISTEN, 0, 0);
                  ExitCode = 34;
                  break;
                }
                if ( !i )
                {
                  ExitCode = PostServiceInit();
                  if ( ExitCode )
                    break;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids);
                ExitCode = RpcMgmtWaitServerListen();
              }
              ReportStatusToSCMgr(3u, 0, 0xEA60u);
              ExitCode = RpcServerUnregisterIf(qword_1800AC110, 0, 1u);
              ExitCode = RpcEpUnregister(qword_1800AC110, BindingVector[0], 0);
              ExitCode = RpcServerInqBindings(BindingVector);
              if ( !ExitCode )
                ExitCode = RpcBindingVectorFree(BindingVector);
              goto LABEL_70;
            }
            ExitCode = 4097;
            v8 = (const struct _EVENT_DESCRIPTOR *)TLS_E_SERVICE_STARTUP_POST_INIT;
            goto LABEL_25;
          }
          ExitCode = 32;
        }
LABEL_37:
        CloseHandle(v10);
        goto LABEL_70;
      }
    }
    CrimsonHelper::RaiseEventInternal(
      (CrimsonHelper *)CrimsonHelper::s_instance,
      &TLS_E_SERVICE_STARTUP_CREATE_THREAD,
      0,
      0);
    ExitCode = 30;
    goto LABEL_70;
  }
  LastError = GetLastError();
  ExitCode = LastError;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, LastError);
  v8 = &TLS_E_INIT_GENERAL;
LABEL_25:
  CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, v8, 0, 0);
LABEL_70:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_1594457400>::GetImpl'::`2'::impl);
  if ( hRpcPause )
    CloseHandle(hRpcPause);
  if ( !v6 )
    WSACleanup();
  ReportStatusToSCMgr(3u, ExitCode, 0xEA60u);
  v22 = CreateThread(0, 0, ServiceShutdownThread, 0, 0, v31);
  v23 = v22;
  if ( v22 )
  {
    v24 = 0;
    for ( j = WaitForSingleObject(v22, 0xBB8u); j == 258; j = WaitForSingleObject(v23, 0xBB8u) )
    {
      v26 = v24++;
      if ( v26 >= 0xB4 )
        break;
      ReportStatusToSCMgr(3u, 0, 0xEA60u);
    }
    CloseHandle(v23);
  }
  else
  {
    ReportStatusToSCMgr(3u, 0, 0xDBBA0u);
    ServerShutdown();
  }
LABEL_81:
  CleanupRDLSConfig();
  if ( g_pWriter )
  {
    CVssJetWriter::Uninitialize(g_pWriter);
    if ( g_pWriter )
      (**(void (__fastcall ***)(struct CTlsVssJetWriter *, __int64))g_pWriter)(g_pWriter, 1);
    g_pWriter = 0;
  }
  if ( v2 )
    CoUninitialize();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, L"ServiceStart");
  return ExitCode;
}

```

## disassembly

```asm
0x180037a5c  mov     rax, rsp
0x180037a5f  mov     [rax+8], rbx
0x180037a63  mov     [rax+10h], rsi
0x180037a67  mov     [rax+18h], rdi
0x180037a6b  push    rbp
0x180037a6c  push    r12
0x180037a6e  push    r13
0x180037a70  push    r14
0x180037a72  push    r15
0x180037a74  lea     rbp, [rax-158h]
0x180037a7b  sub     rsp, 230h
0x180037a82  mov     rax, cs:__security_cookie
0x180037a89  xor     rax, rsp
0x180037a8c  mov     [rbp+150h+var_30], rax
0x180037a93  xor     r15d, r15d
0x180037a96  mov     [rsp+250h+BindingVector], r15
0x180037a9b  mov     [rsp+250h+var_1E8], r15d
0x180037aa0  xor     edx, edx; Val
0x180037aa2  mov     r8d, 198h; Size
0x180037aa8  lea     rcx, [rbp+150h+WSAData]; void *
0x180037aac  call    memset_0
0x180037ab1  mov     r14b, r15b
0x180037ab4  lea     rdi, WPP_GLOBAL_Control
0x180037abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ac2  cmp     rcx, rdi
0x180037ac5  jz      short loc_180037AEB
0x180037ac7  test    dword ptr [rcx+1Ch], 1000h
0x180037ace  jz      short loc_180037AEB
0x180037ad0  lea     edx, [r15+29h]
0x180037ad4  lea     r9, aServicestart; "ServiceStart"
0x180037adb  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x180037ae2  mov     rcx, [rcx+10h]
0x180037ae6  call    WPP_SF_S
0x180037aeb  xor     edx, edx; dwCoInit
0x180037aed  xor     ecx, ecx; pvReserved
0x180037aef  call    cs:__imp_CoInitializeEx
0x180037af6  nop     dword ptr [rax+rax+00h]
0x180037afb  mov     cs:?hrStatus@@3JA, eax; long hrStatus
0x180037b01  mov     bl, 40h ; '@'
0x180037b03  test    eax, eax
0x180037b05  jns     short loc_180037B36
0x180037b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b0e  cmp     rcx, rdi
0x180037b11  jz      short loc_180037B36
0x180037b13  test    [rcx+1Ch], bl
0x180037b16  jz      short loc_180037B36
0x180037b18  mov     edx, 2Ah ; '*'
0x180037b1d  mov     r9d, eax
0x180037b20  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x180037b27  mov     rcx, [rcx+10h]
0x180037b2b  call    WPP_SF_D
0x180037b30  mov     eax, cs:?hrStatus@@3JA; long hrStatus
0x180037b36  mov     r12d, 1
0x180037b3c  test    eax, eax
0x180037b3e  js      short loc_180037B7D
0x180037b40  mov     [rsp+250h+pReserved3], r15; pReserved3
0x180037b45  mov     [rsp+250h+dwCapabilities], r15d; dwCapabilities
0x180037b4a  mov     [rsp+250h+pAuthList], r15; pAuthList
0x180037b4f  lea     eax, [r12+1]
0x180037b54  mov     [rsp+250h+dwImpLevel], eax; dwImpLevel
0x180037b58  mov     [rsp+250h+dwAuthnLevel], eax; dwAuthnLevel
0x180037b5c  xor     r9d, r9d; pReserved1
0x180037b5f  xor     r8d, r8d; asAuthSvc
0x180037b62  or      edx, 0FFFFFFFFh; cAuthSvc
0x180037b65  xor     ecx, ecx; pSecDesc
0x180037b67  call    cs:__imp_CoInitializeSecurity
0x180037b6e  nop     dword ptr [rax+rax+00h]
0x180037b73  mov     cs:?hrStatus@@3JA, eax; long hrStatus
0x180037b79  test    eax, eax
0x180037b7b  jns     short loc_180037B8D
0x180037b7d  cmp     eax, 80010119h
0x180037b82  jz      short loc_180037B8D
0x180037b84  mov     [rsp+250h+ExitCode], eax
0x180037b88  jmp     loc_1800381B8
0x180037b8d  mov     r14b, r12b
0x180037b90  lea     r13, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180037b97  mov     rcx, r13; this
0x180037b9a  call    ?Init@CrimsonHelper@@QEAAKAEBU_GUID@@@Z; CrimsonHelper::Init(_GUID const &)
0x180037b9f  mov     ecx, 18h; Size
0x180037ba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037ba9  mov     [rsp+250h+ThreadId], rax
0x180037bae  test    rax, rax
0x180037bb1  jz      short loc_180037BCD
0x180037bb3  lea     rcx, ??_7CVssJetWriter@@6B@; const CVssJetWriter::`vftable'
0x180037bba  mov     [rax], rcx
0x180037bbd  mov     [rax+8], r15
0x180037bc1  lea     rcx, ??_7CTlsVssJetWriter@@6B@; const CTlsVssJetWriter::`vftable'
0x180037bc8  mov     [rax], rcx
0x180037bcb  jmp     short loc_180037BD0
0x180037bcd  mov     rax, r15
0x180037bd0  mov     cs:?g_pWriter@@3PEAVCTlsVssJetWriter@@EA, rax; CTlsVssJetWriter * g_pWriter
0x180037bd7  test    rax, rax
0x180037bda  jnz     short loc_180037C0A
0x180037bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180037be3  cmp     rcx, rdi
0x180037be6  jz      short loc_180037C00
0x180037be8  test    [rcx+1Ch], bl
0x180037beb  jz      short loc_180037C00
0x180037bed  lea     edx, [rax+2Bh]
0x180037bf0  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x180037bf7  mov     rcx, [rcx+10h]
0x180037bfb  call    WPP_SF_
0x180037c00  mov     cs:?hrStatus@@3JA, 80070008h; long hrStatus
0x180037c0a  mov     ecx, 101h; wVersionRequested
0x180037c0f  lea     rdx, [rbp+150h+WSAData]; lpWSAData
0x180037c13  call    cs:__imp_WSAStartup
0x180037c1a  nop     dword ptr [rax+rax+00h]
0x180037c1f  mov     esi, eax
0x180037c21  lea     rdx, ?g_cbComputerName@@3KA; nSize
0x180037c28  lea     rcx, ?g_szComputerName@@3PAGA; lpBuffer
0x180037c2f  call    cs:__imp_GetComputerNameW
0x180037c36  nop     dword ptr [rax+rax+00h]
0x180037c3b  test    eax, eax
0x180037c3d  jnz     short loc_180037C92
0x180037c3f  call    cs:__imp_GetLastError
0x180037c46  nop     dword ptr [rax+rax+00h]
0x180037c4b  mov     [rsp+250h+ExitCode], eax
0x180037c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c56  cmp     rcx, rdi
0x180037c59  jz      short loc_180037C78
0x180037c5b  test    [rcx+1Ch], bl
0x180037c5e  jz      short loc_180037C78
0x180037c60  mov     edx, 2Ch ; ','
0x180037c65  mov     r9d, eax
0x180037c68  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x180037c6f  mov     rcx, [rcx+10h]
0x180037c73  call    WPP_SF_D
0x180037c78  lea     rdx, TLS_E_INIT_GENERAL; struct _EVENT_DESCRIPTOR *
0x180037c7f  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180037c82  xor     r8d, r8d; unsigned int
0x180037c85  mov     rcx, r13; this
0x180037c88  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180037c8d  jmp     loc_1800380BF
0x180037c92  lea     r8, ?g_szComputerName@@3PAGA; unsigned __int16 *
0x180037c99  mov     edx, 802h; unsigned __int64
0x180037c9e  lea     rcx, ?g_szHostName@@3PAGA; unsigned __int16 *
0x180037ca5  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180037caa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1594457400@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1594457400@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400> `wil::Feature<__WilFeatureTraits_Feature_1594457400>::GetImpl(void)'::`2'::impl
0x180037cb1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1594457400@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1594457400>::__private_IsEnabled(void)
0x180037cb6  test    al, al
0x180037cb8  jz      short loc_180037CC9
0x180037cba  mov     ecx, r12d
0x180037cbd  call    cs:__imp_TLSSetConnectPolicy
0x180037cc4  nop     dword ptr [rax+rax+00h]
0x180037cc9  xor     r9d, r9d; lpName
0x180037ccc  mov     r8d, r12d; bInitialState
0x180037ccf  mov     edx, r12d; bManualReset
0x180037cd2  xor     ecx, ecx; lpEventAttributes
0x180037cd4  call    cs:__imp_CreateEventW
0x180037cdb  nop     dword ptr [rax+rax+00h]
0x180037ce0  mov     cs:?hRpcPause@@3PEAXEA, rax; void * hRpcPause
0x180037ce7  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180037cea  test    rax, rax
0x180037ced  jnz     short loc_180037D0E
0x180037cef  xor     r8d, r8d; unsigned int
0x180037cf2  lea     rdx, TLS_E_ALLOCATE_RESOURCE; struct _EVENT_DESCRIPTOR *
0x180037cf9  mov     rcx, r13; this
0x180037cfc  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180037d01  mov     [rsp+250h+ExitCode], 24h ; '$'
0x180037d09  jmp     loc_1800380BF
0x180037d0e  mov     dword ptr [rsp+250h+ThreadId], r15d
0x180037d13  lea     rax, [rsp+250h+ThreadId]
0x180037d18  mov     qword ptr [rsp+250h+dwImpLevel], rax; lpThreadId
0x180037d1d  mov     [rsp+250h+dwAuthnLevel], r15d; dwCreationFlags
0x180037d22  lea     r8, ?StartServerInitThread@@YAKPEAX@Z; lpStartAddress
0x180037d29  xor     edx, edx; dwStackSize
0x180037d2b  xor     ecx, ecx; lpThreadAttributes
0x180037d2d  call    cs:__imp_CreateThread
0x180037d34  nop     dword ptr [rax+rax+00h]
0x180037d39  mov     rbx, rax
0x180037d3c  test    rax, rax
0x180037d3f  jz      loc_1800380A2
0x180037d45  mov     [rsp+250h+ExitCode], r15d
0x180037d4a  mov     edx, 493E0h; dwMilliseconds
0x180037d4f  mov     rcx, rax; hHandle
0x180037d52  call    cs:__imp_WaitForSingleObject
0x180037d59  nop     dword ptr [rax+rax+00h]
0x180037d5e  mov     edi, 1Fh
0x180037d63  test    eax, eax
0x180037d65  jz      short loc_180037D6F
0x180037d67  mov     eax, edi
0x180037d69  mov     [rsp+250h+ExitCode], eax
0x180037d6d  jmp     short loc_180037D73
0x180037d6f  mov     eax, [rsp+250h+ExitCode]
0x180037d73  test    eax, eax
0x180037d75  jnz     short loc_180037D96
0x180037d77  lea     rdx, [rsp+250h+ExitCode]; lpExitCode
0x180037d7c  mov     rcx, rbx; hThread
0x180037d7f  call    cs:__imp_GetExitCodeThread
0x180037d86  nop     dword ptr [rax+rax+00h]
0x180037d8b  cmp     [rsp+250h+ExitCode], r15d
0x180037d90  jz      short loc_180037DAA
0x180037d92  mov     [rsp+250h+ExitCode], edi
0x180037d96  mov     rcx, rbx; hObject
0x180037d99  call    cs:__imp_CloseHandle
0x180037da0  nop     dword ptr [rax+rax+00h]
0x180037da5  jmp     loc_1800380BF
0x180037daa  mov     rcx, rbx; hObject
0x180037dad  call    cs:__imp_CloseHandle
0x180037db4  nop     dword ptr [rax+rax+00h]
0x180037db9  mov     dword ptr [rsp+250h+var_1F8], r15d
0x180037dbe  mov     edi, r15d
0x180037dc1  xor     edx, edx
0x180037dc3  lea     rcx, [rsp+250h+var_1F8]
0x180037dc8  call    cs:__imp_TLSInDomain
0x180037dcf  nop     dword ptr [rax+rax+00h]
0x180037dd4  test    eax, eax
0x180037dd6  jnz     short loc_180037DE7
0x180037dd8  cmp     dword ptr [rsp+250h+var_1F8], r12d
0x180037ddd  jnz     short loc_180037DE7
0x180037ddf  call    ?TSLSLoadLocalGroupSecDes@@YAHXZ; TSLSLoadLocalGroupSecDes(void)
0x180037de4  mov     edi, r12d
0x180037de7  lea     rax, [rsp+250h+var_1E8]
0x180037dec  mov     qword ptr [rsp+250h+dwImpLevel], rax; lpThreadId
0x180037df1  mov     [rsp+250h+dwAuthnLevel], r15d; dwCreationFlags
0x180037df6  xor     r9d, r9d; lpParameter
0x180037df9  lea     r8, ?RPCServiceStartThread@@YAKPEAX@Z; lpStartAddress
0x180037e00  xor     edx, edx; dwStackSize
0x180037e02  xor     ecx, ecx; lpThreadAttributes
0x180037e04  call    cs:__imp_CreateThread
0x180037e0b  nop     dword ptr [rax+rax+00h]
0x180037e10  mov     rbx, rax
0x180037e13  test    rax, rax
0x180037e16  jz      loc_1800380A2
0x180037e1c  mov     [rsp+250h+ExitCode], r15d
0x180037e21  mov     edx, 64h ; 'd'; dwMilliseconds
0x180037e26  mov     rcx, rbx; hHandle
0x180037e29  call    cs:__imp_WaitForSingleObject
0x180037e30  nop     dword ptr [rax+rax+00h]
0x180037e35  cmp     eax, 102h
0x180037e3a  jz      short loc_180037E21
0x180037e3c  cmp     [rsp+250h+ExitCode], r15d
0x180037e41  jnz     loc_180037D96
0x180037e47  lea     rdx, [rsp+250h+ExitCode]; lpExitCode
0x180037e4c  mov     rcx, rbx; hThread
0x180037e4f  call    cs:__imp_GetExitCodeThread
0x180037e56  nop     dword ptr [rax+rax+00h]
0x180037e5b  cmp     [rsp+250h+ExitCode], r15d
0x180037e60  jz      short loc_180037E6F
0x180037e62  mov     [rsp+250h+ExitCode], 20h ; ' '
0x180037e6a  jmp     loc_180037D96
0x180037e6f  mov     rcx, rbx; hObject
0x180037e72  call    cs:__imp_CloseHandle
0x180037e79  nop     dword ptr [rax+rax+00h]
0x180037e7e  mov     r9, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; CRdlsDBManager * g_RdlsDBManager
0x180037e85  add     r9, 404h
0x180037e8c  lea     rax, aReports; "reports\\"
0x180037e93  mov     qword ptr [rsp+250h+dwAuthnLevel], rax
0x180037e98  lea     r8, aSS_1; "%s%s"
0x180037e9f  mov     edx, 105h; unsigned __int64
0x180037ea4  lea     rcx, ?g_szReportDir@@3PAGA; unsigned __int16 *
0x180037eab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037eb0  xor     r8d, r8d; unsigned int
0x180037eb3  xor     edx, edx; unsigned int
0x180037eb5  lea     ecx, [rdx+4]; unsigned int
0x180037eb8  call    ?ReportStatusToSCMgr@@YAHKKK@Z; ReportStatusToSCMgr(ulong,ulong,ulong)
0x180037ebd  test    eax, eax
0x180037ebf  jnz     short loc_180037ECE
0x180037ec1  mov     [rsp+250h+ExitCode], 1Ch
0x180037ec9  jmp     loc_1800380BF
0x180037ece  call    InitCryptoAndCertificate
0x180037ed3  test    eax, eax
0x180037ed5  jz      short loc_180037EEB
0x180037ed7  mov     [rsp+250h+ExitCode], 1001h
0x180037edf  lea     rdx, TLS_E_SERVICE_STARTUP_POST_INIT
0x180037ee6  jmp     loc_180037C7F
0x180037eeb  test    edi, edi
0x180037eed  jz      short loc_180037F48
0x180037eef  mov     dword ptr [rsp+250h+ThreadId], r15d
0x180037ef4  lea     rcx, [rsp+250h+ThreadId]; int *
0x180037ef9  call    ?IsLSSCPRegistered@@YAJPEAH@Z; IsLSSCPRegistered(int *)
0x180037efe  call    cs:__imp_TLSIsBetaNTServer
0x180037f05  nop     dword ptr [rax+rax+00h]
0x180037f0a  mov     ebx, eax
0x180037f0c  call    cs:__imp_GetRdlsSupportedFeatureMask
0x180037f13  nop     dword ptr [rax+rax+00h]
0x180037f18  mov     edx, ebx; int
0x180037f1a  mov     ecx, eax; unsigned int
0x180037f1c  call    ?UpdateSCP@@YAJKH@Z; UpdateSCP(ulong,int)
0x180037f21  cmp     dword ptr [rsp+250h+ThreadId], r15d
0x180037f26  jnz     short loc_180037F48
0x180037f28  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180037f2b  xor     r8d, r8d; unsigned int
0x180037f2e  mov     rcx, r13; this
0x180037f31  test    eax, eax
0x180037f33  lea     rdx, TLS_I_LS_REGISTERED_TO_SCP
0x180037f3a  jz      short loc_180037F43
0x180037f3c  lea     rdx, TLS_E_LS_REGISTERED_TO_SCP; struct _EVENT_DESCRIPTOR *
0x180037f43  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180037f48  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180037f4b  xor     r8d, r8d; unsigned int
0x180037f4e  lea     rdx, TLS_I_SERVICE_START; struct _EVENT_DESCRIPTOR *
0x180037f55  mov     rcx, r13; this
0x180037f58  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180037f5d  call    CanIssuePermLicense
0x180037f62  mov     edx, eax; int
0x180037f64  call    ?LogSettingsTelemetryData@CRdlsDBManager@@QEAAXH@Z; CRdlsDBManager::LogSettingsTelemetryData(int)
0x180037f69  mov     ebx, r15d
0x180037f6c  or      edi, 0FFFFFFFFh
0x180037f6f  jmp     short loc_180037FE6
  ... truncated ...
```
