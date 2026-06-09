# QmpInitialize(wchar_t const *)

- ea: `0x18002cd84`
- end: `0x18002e008`
- name: `?QmpInitialize@@YAJPEB_W@Z`
- size: `4740`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `73`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b398`

## callees

- `0x1800010b0`
- `0x18000d1f0`
- `0x18000dc78`
- `0x18000f35c`
- `0x180011578`
- `0x1800129a8`
- `0x1800129cc`
- `0x180014748`
- `0x180016054`
- `0x180016188`
- `0x18001a408`
- `0x18001ba98`
- `0x180024ec8`
- `0x1800256c8`
- `0x18002bd84`
- `0x18002bf20`
- `0x18002bfc4`
- `0x18002c0ec`
- `0x18002c2a4`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18002c95c`
- `0x18002ca48`
- `0x18002cd84`
- `0x18002e010`
- `0x18002e3dc`
- `0x18002e55c`
- `0x18002e880`
- `0x18002e9bc`
- `0x18002ed40`
- `0x1800321d4`
- `0x180038514`
- `0x18003c664`
- `0x1800480bc`
- `0x18004c4d0`
- `0x18004cbe0`
- `0x18004d32c`
- `0x1800504e8`
- `0x18005c91c`
- `0x18005e1c4`
- `0x18005e250`
- `0x18005e564`
- `0x18005e808`
- `0x18005ebd4`
- `0x18005ed6c`
- `0x18006cea0`
- `0x18006d94c`
- `0x18006da50`
- `0x18006db38`
- `0x18007038c`

## import_xrefs

- `msvcrt!free` at `0x18002d83e`
- `msvcrt!free` at `0x18002d8bd`
- `msvcrt!free` at `0x18002d94c`
- `msvcrt!free` at `0x18002d9bd`
- `msvcrt!free` at `0x18002da40`
- `msvcrt!free` at `0x18002dabf`
- `msvcrt!free` at `0x18002db2f`
- `msvcrt!free` at `0x18002dbaf`
- `msvcrt!free` at `0x18002dc37`
- `msvcrt!free` at `0x18002dc8b`
- `msvcrt!free` at `0x18002dd26`
- `msvcrt!free` at `0x18002dd8d`
- `msvcrt!free` at `0x18002df8d`
- `msvcrt!free` at `0x18002dfd2`
- `msvcrt!free` at `0x18002d83e`
- `msvcrt!free` at `0x18002d8bd`
- `msvcrt!free` at `0x18002d94c`
- `msvcrt!free` at `0x18002d9bd`
- `msvcrt!free` at `0x18002da40`
- `msvcrt!free` at `0x18002dabf`
- `msvcrt!free` at `0x18002db2f`
- `msvcrt!free` at `0x18002dbaf`
- `msvcrt!free` at `0x18002dc37`
- `msvcrt!free` at `0x18002dc8b`
- `msvcrt!free` at `0x18002dd26`
- `msvcrt!free` at `0x18002dd8d`
- `msvcrt!free` at `0x18002df8d`
- `msvcrt!free` at `0x18002dfd2`
- `ADVAPI32!RegGetValueW` at `0x18002d1a2`
- `ADVAPI32!RegGetValueW` at `0x18002d1a2`
- `ADVAPI32!EventRegister` at `0x18002d45a`
- `ADVAPI32!EventRegister` at `0x18002d45a`
- `KERNEL32!GetLastError` at `0x18002dbdb`
- `KERNEL32!GetLastError` at `0x18002dca4`
- `KERNEL32!GetLastError` at `0x18002dbdb`
- `KERNEL32!GetLastError` at `0x18002dca4`
- `KERNEL32!CloseHandle` at `0x18002dc6a`
- `KERNEL32!CloseHandle` at `0x18002dcc5`
- `KERNEL32!CloseHandle` at `0x18002dc6a`
- `KERNEL32!CloseHandle` at `0x18002dcc5`
- `KERNEL32!WaitForSingleObject` at `0x18002dc9a`
- `KERNEL32!WaitForSingleObject` at `0x18002dc9a`
- `KERNEL32!CompareStringW` at `0x18002d2de`
- `KERNEL32!CompareStringW` at `0x18002d2de`
- `KERNEL32!SetEnvironmentVariableW` at `0x18002ce7e`
- `KERNEL32!SetEnvironmentVariableW` at `0x18002ce7e`
- `KERNEL32!CreateEventW` at `0x18002dbcd`
- `KERNEL32!CreateEventW` at `0x18002dbcd`
- `mqsec!GetFalconKeyValue` at `0x18002da80`
- `mqsec!GetFalconKeyValue` at `0x18002da80`
- `mqsec!DeleteFalconKeyValue` at `0x18002d61b`
- `mqsec!DeleteFalconKeyValue` at `0x18002d61b`
- `mqsec!SetFalconKeyValue` at `0x18002d650`
- `mqsec!SetFalconKeyValue` at `0x18002d650`
- `mqsec!MSMQGetOperatingSystem` at `0x18002d593`
- `mqsec!MSMQGetOperatingSystem` at `0x18002d593`
- `mqsec!IsLocalSystemCluster` at `0x18002ce2c`
- `mqsec!IsLocalSystemCluster` at `0x18002ce2c`
- `mqsec!GetComputerNameInternal` at `0x18002ced5`
- `mqsec!GetComputerNameInternal` at `0x18002ced5`
- `mqsec!GetComputerDnsNameInternal` at `0x18002cf1a`
- `mqsec!GetComputerDnsNameInternal` at `0x18002cf4e`
- `mqsec!GetComputerDnsNameInternal` at `0x18002cf1a`
- `mqsec!GetComputerDnsNameInternal` at `0x18002cf4e`
- `mqsec!SetFalconServiceName` at `0x18002cfa2`
- `mqsec!SetFalconServiceName` at `0x18002cfa2`
- `mqsec!?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z` at `0x18002cfcd`
- `mqsec!?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z` at `0x18002cfcd`
- `mqsec!?Init@CCancelRpc@@QEAAXXZ` at `0x18002d282`
- `mqsec!?Init@CCancelRpc@@QEAAXXZ` at `0x18002d282`
- `mqsec!g_CancelRpc` at `0x18002d27b`

## string_xrefs

- `0x18002d649`: `security\LqsUpdatedSD`
- `0x18002d104`: `MaxXmlDepth`
- `0x18002d614`: `LogDataCreated`
- `0x18002da79`: `XactAbortCommitRetryInterval`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall QmpInitialize(wchar_t *a1)
{
  int ComputerNameInternal; // ebx
  unsigned __int16 v3; // r8
  WCHAR *v5; // rax
  int FalconSectionName; // eax
  HKEY v7; // rcx
  unsigned int v8; // r8d
  __int64 v9; // rdx
  const wchar_t *v10; // rdx
  __int64 v11; // rdx
  unsigned int ValueW; // eax
  PVOID *v13; // rcx
  const wchar_t *v14; // rcx
  PVOID *v15; // rcx
  CQueueAlias *v16; // rax
  CMSMQTrace *v17; // rax
  signed int v18; // eax
  int v19; // r14d
  CQPrivate *v20; // rcx
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // ecx
  struct sockaddr *ListenAddressForFamily; // rbx
  bool v25; // cl
  wchar_t *QueueAliasPath; // rbx
  CQueueAlias *v27; // rax
  CQueueAlias *v28; // rax
  unsigned int v29; // edi
  signed int v30; // eax
  CSessionMgr *v31; // rcx
  CQueueMgr *v32; // rcx
  int inited; // eax
  CAdmin *v34; // rcx
  unsigned int v35; // r14d
  int v36; // eax
  int v37; // eax
  int *v38; // rcx
  int v39; // eax
  int v40; // eax
  HANDLE EventW; // r14
  signed int LastError; // eax
  CLogger *v43; // rcx
  DWORD v44; // eax
  CLogger *v45; // rcx
  signed int v46; // eax
  signed int v47; // eax
  CResourceManager *v48; // rcx
  int v49; // eax
  unsigned int v50; // r14d
  CQueueMgr *v51; // rcx
  __int64 v52; // rcx
  signed int v53; // eax
  DWORD pcbData; // [rsp+44h] [rbp-B4h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-B0h] BYREF
  unsigned int v56; // [rsp+4Ch] [rbp-ACh] BYREF
  CQueueAlias *v57; // [rsp+50h] [rbp-A8h] BYREF
  int pvData; // [rsp+58h] [rbp-A0h] BYREF
  unsigned int v59; // [rsp+5Ch] [rbp-9Ch]
  int v60; // [rsp+60h] [rbp-98h]
  struct _GUID v61; // [rsp+70h] [rbp-88h] BYREF
  struct _GUID v62; // [rsp+90h] [rbp-68h] BYREF
  int v63; // [rsp+A0h] [rbp-58h] BYREF
  wchar_t *v64; // [rsp+A8h] [rbp-50h] BYREF
  const wchar_t *v65; // [rsp+B0h] [rbp-48h]
  __int64 v66; // [rsp+B8h] [rbp-40h]
  unsigned __int64 v67; // [rsp+C0h] [rbp-38h]

  pvData = 1;
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  ComputerNameInternal = RestrictServicePrivileges();
  if ( ComputerNameInternal < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
    v3 = 1204;
    goto LABEL_6;
  }
  if ( IsLocalSystemCluster() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
    SetEnvironmentVariableW(L"DnsFilterClusterIp", L"1");
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  pcbData = 16;
  v5 = (WCHAR *)MmAllocate(0x20u);
  g_szMachineName = v5;
  *v5 = 0;
  ComputerNameInternal = GetComputerNameInternal(v5, &pcbData);
  if ( ComputerNameInternal < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
    v3 = 1201;
    goto LABEL_6;
  }
  pcbData = 0;
  GetComputerDnsNameInternal(0, &pcbData);
  g_szComputerDnsName = (LPCWSTR)MmAllocate(saturated_mul(pcbData, 2u));
  if ( (int)GetComputerDnsNameInternal((wchar_t *)g_szComputerDnsName, &pcbData) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
    AP<wchar_t>::free(&g_szComputerDnsName);
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  SetFalconServiceName(a1);
  v67 = 7;
  v66 = 0;
  LOWORD(v64) = 0;
  FalconSectionName = GetFalconSectionName(&v63);
  ComputerNameInternal = FalconSectionName;
  if ( FalconSectionName < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
        (unsigned int)FalconSectionName);
    LogMsgHR(ComputerNameInternal, (wchar_t *)L"main", 0x44Cu);
    LOBYTE(v9) = 1;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(&v63, v9, 0);
    return (unsigned int)ComputerNameInternal;
  }
  v10 = (const wchar_t *)&v64;
  if ( v67 >= 8 )
    v10 = v64;
  CmInitialize(v7, v10, v8);
  LOBYTE(v11) = 1;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(&v63, v11, 0);
  v63 = 0;
  v64 = 0;
  v65 = L"SetupStatus";
  LODWORD(v66) = 0;
  v67 = 0;
  QueryValueInternal((struct RegEntry *)&v63);
  v63 = 0;
  v64 = 0;
  v65 = L"Workgroup";
  LODWORD(v66) = 0;
  v67 = 0;
  CmQueryValue((const struct RegEntry *)&v63, (int *)g_fWorkGroupInstallation);
  v63 = 0;
  v64 = 0;
  v65 = L"MaxXmlDepth";
  LODWORD(v66) = 256;
  v67 = 0;
  g_dwMaxXmlDepth = 256;
  QueryValueInternal((struct RegEntry *)&v63);
  InitLogging(a1, 0);
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\MSMQ\\Parameters",
             L"EnableTrace",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, ValueW);
    goto LABEL_45;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, 0);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( pvData )
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_Dd(v13[2], 34, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, 0, pvData);
LABEL_45:
    QmpEnableMSMQTracing();
    goto LABEL_46;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
    WPP_SF_Dd(v13[2], 35, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, 0, 0);
  QmpDisableMSMQTracing();
LABEL_46:
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  RegisterFloodingEvents(v14);
  CCancelRpc::Init(g_CancelRpc);
  QmpSetServiceProgressReportTime();
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  ComputerNameInternal = _InitFromRegistry();
  if ( ComputerNameInternal < 0 )
  {
    v3 = 1200;
LABEL_6:
    LogMsgHR(ComputerNameInternal, (wchar_t *)L"main", v3);
    return (unsigned int)ComputerNameInternal;
  }
  if ( CompareStringW(0x7Fu, 1u, a1, -1, L"MSMQ", -1) == 2 )
    HandleChangeOfJoinStatus();
  InitPureWorkgroupFlag();
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v15 + 28) & 4) != 0 )
      {
        WPP_SF_d(v15[2], 38, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, 0);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v15 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v15 + 28) & 4) != 0 )
        {
          WPP_SF_d(
            v15[2],
            39,
            &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
            *(unsigned int *)g_fWorkGroupInstallation);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v15 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v15 + 28) & 4) != 0 )
          {
            WPP_SF_d(
              v15[2],
              40,
              &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
              (unsigned int)g_fPureWorkGroupMachine);
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v15 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v15 + 28) & 4) != 0 )
            {
              WPP_SF_S((TRACEHANDLE)v15[2]);
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
              WPP_SF_S((TRACEHANDLE)v15[2]);
          }
        }
      }
    }
  }
  v16 = (CQueueAlias *)MmAllocate(0x90u);
  v57 = v16;
  if ( v16 )
  {
    v61 = (struct _GUID)xmmword_1800FEFE0;
    v62 = (struct _GUID)xmmword_1800FEFF0;
    v17 = CMSMQTrace::CMSMQTrace(v16, &v62, &v61);
  }
  else
  {
    v17 = 0;
  }
  g_pMSMQErrorLoggingTrace = v17;
  v18 = EventRegister(&MSMQ_E2E, 0, 0, &g_e2eTraceHandle);
  if ( v18 >= 0 )
  {
    bE2EInitialized = 1;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
      (unsigned int)v18);
  }
  v19 = 3;
  InitDeferredItemsPool();
  v21 = CQPrivate::PrivateQueueInit(v20);
  ComputerNameInternal = v21;
  if ( v21 < 0 )
  {
    v3 = 1250;
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
      (unsigned int)v21);
  v22 = MSMQGetOperatingSystem();
  g_dwOperatingSystem = v22;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, v22);
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  QMSecurityInit();
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  g_dwThreadsNo = GetThreadPoolCount();
  ExInitialize(v23);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, g_dwThreadsNo);
  if ( !*(_DWORD *)g_fWorkGroupInstallation )
    McInitialize();
  NoInitialize();
  InitBindingIPAddress();
  ListenAddressForFamily = GetListenAddressForFamily(2u);
  StpCreateCredentials();
  CWinsockSSl::m_fIsPipelineSupported = IsSslPipeLineSupported();
  CSimpleWinsock::m_fIsPipelineSupported = IsSimpleSocketPipeLineSupported();
  CPgmWinsockConnection::InitClass(ListenAddressForFamily);
  InitTransportTimeouts();
  v63 = 0;
  v64 = 0;
  v65 = L"SendWindowinBytes";
  LODWORD(v66) = 200000;
  v67 = 0;
  dword_18013234C = 200000;
  QueryValueInternal((struct RegEntry *)&v63);
  InitTransportTimeouts_0();
  MsmpInitConfiguration();
  if ( g_fPureWorkGroupMachine == 1 )
  {
    g_msmqMode = 0;
  }
  else
  {
    if ( *(_DWORD *)g_fWorkGroupInstallation == 1 )
      v19 = 1;
    g_msmqMode = v19;
  }
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  MsmqUalStart(v25);
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  QueueAliasPath = (wchar_t *)GetQueueAliasPath();
  *(_QWORD *)&v61.Data1 = QueueAliasPath;
  if ( !QueueAliasPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
    free(0);
    return 3222142977LL;
  }
  v27 = (CQueueAlias *)MmAllocate(0x30u);
  v57 = v27;
  if ( v27 )
    v28 = CQueueAlias::CQueueAlias(v27, QueueAliasPath);
  else
    v28 = 0;
  qword_18013B858 = (__int64)v28;
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  if ( (unsigned int)QmpInitializeInternal(0) != 1 )
  {
    v29 = -2147467259;
    LogMsgHR(-2147467259, (wchar_t *)L"main", 0x4B2u);
    free(QueueAliasPath);
    return v29;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v30 = QMPrfInit();
  if ( v30 < 0 )
    EvReportWithError(0x400007E8u, v30, 0);
  CSessionMgr::Init(v31);
  inited = CQueueMgr::InitQueueMgr(v32);
  v35 = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
        (unsigned int)inited);
    LogMsgHR(v35, (wchar_t *)L"main", 0x67Du);
    free(QueueAliasPath);
    return v35;
  }
  v36 = CAdmin::Init(v34);
  v35 = v36;
  if ( v36 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
        (unsigned int)v36);
    EvReportWithError(0xC00007E4, v35, 1u, L"admin_queue$");
    LogMsgHR(v35, (wchar_t *)L"main", 0x67Eu);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v37 = QMInitOrderQueue();
  v35 = v37;
  if ( v37 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
        (unsigned int)v37);
    EvReportWithError(0xC00007E4, v35, 1u, L"order_queue$");
    LogMsgHR(v35, (wchar_t *)L"main", 0x67Fu);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(v57) = 1500;
  v56 = 4;
  v55 = 4;
  GetFalconKeyValue(L"XactAbortCommitRetryInterval", &v55, &dword_180128E98, &v56, (const wchar_t *)&v57);
  v39 = InDefaultCommit(v38);
  v35 = v39;
  if ( v39 < 0 )
  {
    LogMsgHR(v39, (wchar_t *)L"xactmode", 0x1Eu);
    LogMsgHR(v35, (wchar_t *)L"main", 0x4B7u);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v35 = RecoverLoggedSubsystems(0);
  if ( (v35 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
    LogMsgHR(v35, (wchar_t *)L"main", 0x4B8u);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v40 = RecoverPackets();
  v35 = v40;
  if ( v40 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_339425af71df30c3a20d2281bf86e224_Traceguids,
        (unsigned int)v40);
    EvReportWithError(0xC00007E7, v35, 0);
    LogMsgHR(v35, (wchar_t *)L"main", 0x4B9u);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(qword_18013B188) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v35 = LastError;
    if ( LastError > 0 )
      v35 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, v35);
    if ( (v35 & 0x80000000) != 0 )
      LogMsgHR(v35, (wchar_t *)L"main", 0xABu);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  if ( !(unsigned int)CLogger::MakeCheckpoint(v43, EventW) )
  {
    CloseHandle(EventW);
    LogMsgHR(-1072824319, (wchar_t *)L"main", 0xBFu);
    free(QueueAliasPath);
    return 3222142977LL;
  }
  if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
  {
    v44 = GetLastError();
    if ( v44 )
      LogMsgNTStatus(v44, (wchar_t *)L"main", 0xC0u);
  }
  CloseHandle(EventW);
  v46 = CLogger::SetLogFileCreated(v45);
  v35 = v46;
  if ( v46 < 0 )
  {
    EvReportWithError(0xC000081C, v46, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, v35);
    LogMsgHR(v35, (wchar_t *)L"main", 0x680u);
    free(QueueAliasPath);
    return v35;
  }
  v47 = ReconfigureXactMode();
  v35 = v47;
  if ( v47 < 0 )
  {
    EvReportWithError(0xC000081C, v47, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, v35);
    LogMsgHR(v35, (wchar_t *)L"main", 0x4BAu);
    free(QueueAliasPath);
    return v35;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v49 = CResourceManager::Init(v48);
  v50 = v49;
  if ( v49 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids);
  }
  else
  {
    LogMsgHR(v49, (wchar_t *)L"xactrm", 0xAAu);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, v50);
  }
  v63 = 0;
  v64 = 0;
  v65 = L"MsmqIpPort";
  LODWORD(v66) = 1801;
  v67 = 0;
  v59 = 1801;
  QueryValueInternal((struct RegEntry *)&v63);
  g_dwIPPort = v59;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_339425af71df30c3a20d2281bf86e224_Traceguids, v59);
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  InitOnHold();
  CQueueMgr::InitConnected();
  if ( !CQueueMgr::m_Connected )
    CQueueMgr::DisconnectNetwork(v51);
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v63 = 0;
  v64 = 0;
  v65 = L"RoutingRefreshInterval";
  LODWORD(v66) = 720;
  v67 = 0;
  v60 = 720;
  QueryValueInternal((struct RegEntry *)&v63);
  v52 = (unsigned int)(60000 * v60);
  LOBYTE(v52) = CQueueMgr::m_bMQSRouting;
  RdpInitRouteDecision(v52, 10000LL * (unsigned int)(60000 * v60));
  v53 = ADInit(QMLookForOnlineDS, 0, 1, 0);
  v29 = v53;
  if ( v53 < 0 )
  {
    EvReportWithError(0xC00007F3, v53, 0);
    LogMsgHR(v29, (wchar_t *)L"main", 0x4BFu);
    free(QueueAliasPath);
    return v29;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  ScheduleOnlineInitialization();
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  free(QueueAliasPath);
  return 0;
}

```

## disassembly

```asm
0x18002cd84  mov     [rsp+arg_8], rbx
0x18002cd89  mov     [rsp+arg_10], rsi
0x18002cd8e  push    rdi
0x18002cd8f  push    r12
0x18002cd91  push    r13
0x18002cd93  push    r14
0x18002cd95  push    r15
0x18002cd97  sub     rsp, 0D0h
0x18002cd9e  mov     rax, cs:__security_cookie
0x18002cda5  xor     rax, rsp
0x18002cda8  mov     [rsp+0F8h+var_30], rax
0x18002cdb0  mov     r14, rcx
0x18002cdb3  mov     r15d, 1
0x18002cdb9  mov     [rsp+0F8h+var_A0], r15d
0x18002cdbe  add     dword ptr cs:qword_1801291DC, r15d
0x18002cdc5  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002cdcb  mov     dword ptr cs:qword_1801291DC+4, eax
0x18002cdd1  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x18002cdd6  call    ?RestrictServicePrivileges@@YAJXZ; RestrictServicePrivileges(void)
0x18002cddb  mov     ebx, eax
0x18002cddd  xor     r12d, r12d
0x18002cde0  test    eax, eax
0x18002cde2  jns     short loc_18002CE2C
0x18002cde4  lea     rdi, WPP_GLOBAL_Control
0x18002cdeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cdf2  cmp     rcx, rdi
0x18002cdf5  jz      short loc_18002CE11
0x18002cdf7  test    [rcx+1Ch], r15b
0x18002cdfb  jz      short loc_18002CE11
0x18002cdfd  lea     edx, [r15+1Bh]
0x18002ce01  lea     r8, WPP_339425af71df30c3a20d2281bf86e224_Traceguids
0x18002ce08  mov     rcx, [rcx+10h]
0x18002ce0c  call    WPP_SF_
0x18002ce11  mov     r8d, 4B4h; unsigned __int16
0x18002ce17  lea     rdx, aMain; "main"
0x18002ce1e  mov     ecx, ebx; int
0x18002ce20  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ce25  mov     eax, ebx
0x18002ce27  jmp     loc_18002DFDB
0x18002ce2c  call    cs:__imp_?IsLocalSystemCluster@@YA_NXZ; IsLocalSystemCluster(void)
0x18002ce32  test    al, al
0x18002ce34  jz      short loc_18002CE86
0x18002ce36  lea     rdi, WPP_GLOBAL_Control
0x18002ce3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce44  cmp     rcx, rdi
0x18002ce47  jz      short loc_18002CE69
0x18002ce49  test    [rcx+1Ch], r15b
0x18002ce4d  jz      short loc_18002CE69
0x18002ce4f  mov     edx, 1Dh
0x18002ce54  lea     rsi, WPP_339425af71df30c3a20d2281bf86e224_Traceguids
0x18002ce5b  mov     r8, rsi
0x18002ce5e  mov     rcx, [rcx+10h]
0x18002ce62  call    WPP_SF_
0x18002ce67  jmp     short loc_18002CE70
0x18002ce69  lea     rsi, WPP_339425af71df30c3a20d2281bf86e224_Traceguids
0x18002ce70  lea     rdx, Value; "1"
0x18002ce77  lea     rcx, Name; "DnsFilterClusterIp"
0x18002ce7e  call    cs:__imp_SetEnvironmentVariableW
0x18002ce84  jmp     short loc_18002CE94
0x18002ce86  lea     rdi, WPP_GLOBAL_Control
0x18002ce8d  lea     rsi, WPP_339425af71df30c3a20d2281bf86e224_Traceguids
0x18002ce94  add     dword ptr cs:qword_1801291DC, r15d
0x18002ce9b  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002cea1  mov     dword ptr cs:qword_1801291DC+4, eax
0x18002cea7  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x18002ceac  mov     [rsp+0F8h+var_B4], 10h
0x18002ceb4  mov     r13d, 20h ; ' '
0x18002ceba  mov     ecx, r13d; unsigned __int64
0x18002cebd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002cec2  mov     cs:?g_szMachineName@@3PEA_WEA, rax; wchar_t * g_szMachineName
0x18002cec9  mov     [rax], r12w
0x18002cecd  lea     rdx, [rsp+0F8h+var_B4]
0x18002ced2  mov     rcx, rax
0x18002ced5  call    cs:__imp_?GetComputerNameInternal@@YAJPEA_WPEAK@Z; GetComputerNameInternal(wchar_t *,ulong *)
0x18002cedb  mov     ebx, eax
0x18002cedd  test    eax, eax
0x18002cedf  jns     short loc_18002CF0E
0x18002cee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cee8  cmp     rcx, rdi
0x18002ceeb  jz      short loc_18002CF03
0x18002ceed  test    [rcx+1Ch], r15b
0x18002cef1  jz      short loc_18002CF03
0x18002cef3  lea     edx, [r13-2]
0x18002cef7  mov     r8, rsi
0x18002cefa  mov     rcx, [rcx+10h]
0x18002cefe  call    WPP_SF_
0x18002cf03  mov     r8d, 4B1h
0x18002cf09  jmp     loc_18002CE17
0x18002cf0e  mov     [rsp+0F8h+var_B4], r12d
0x18002cf13  lea     rdx, [rsp+0F8h+var_B4]
0x18002cf18  xor     ecx, ecx
0x18002cf1a  call    cs:__imp_?GetComputerDnsNameInternal@@YAJPEA_WPEAK@Z; GetComputerDnsNameInternal(wchar_t *,ulong *)
0x18002cf20  mov     ecx, [rsp+0F8h+var_B4]
0x18002cf24  mov     eax, 2
0x18002cf29  mul     rcx
0x18002cf2c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cf33  cmovb   rax, rcx
0x18002cf37  mov     rcx, rax; unsigned __int64
0x18002cf3a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002cf3f  mov     cs:?g_szComputerDnsName@@3V?$AP@_W@@A, rax; AP<wchar_t> g_szComputerDnsName
0x18002cf46  lea     rdx, [rsp+0F8h+var_B4]
0x18002cf4b  mov     rcx, rax
0x18002cf4e  call    cs:__imp_?GetComputerDnsNameInternal@@YAJPEA_WPEAK@Z; GetComputerDnsNameInternal(wchar_t *,ulong *)
0x18002cf54  test    eax, eax
0x18002cf56  jns     short loc_18002CF87
0x18002cf58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf5f  cmp     rcx, rdi
0x18002cf62  jz      short loc_18002CF7B
0x18002cf64  test    [rcx+1Ch], r15b
0x18002cf68  jz      short loc_18002CF7B
0x18002cf6a  mov     edx, 1Fh
0x18002cf6f  mov     r8, rsi
0x18002cf72  mov     rcx, [rcx+10h]
0x18002cf76  call    WPP_SF_
0x18002cf7b  lea     rcx, ?g_szComputerDnsName@@3V?$AP@_W@@A; AP<wchar_t> g_szComputerDnsName
0x18002cf82  call    ?free@?$AP@_W@@QEAAXXZ; AP<wchar_t>::free(void)
0x18002cf87  add     dword ptr cs:qword_1801291DC, r15d
0x18002cf8e  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002cf94  mov     dword ptr cs:qword_1801291DC+4, eax
0x18002cf9a  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x18002cf9f  mov     rcx, r14
0x18002cfa2  call    cs:__imp_?SetFalconServiceName@@YAXPEB_W@Z; SetFalconServiceName(wchar_t const *)
0x18002cfa8  mov     [rsp+0F8h+var_38], 7
0x18002cfb4  mov     [rsp+0F8h+var_40], r12
0x18002cfbc  mov     word ptr [rsp+0F8h+var_50], r12w
0x18002cfc5  lea     rcx, [rsp+0F8h+var_58]
0x18002cfcd  call    cs:__imp_?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z; GetFalconSectionName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> &)
0x18002cfd3  mov     ebx, eax
0x18002cfd5  test    eax, eax
0x18002cfd7  jns     short loc_18002D02B
0x18002cfd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfe0  cmp     rcx, rdi
0x18002cfe3  jz      short loc_18002CFFD
0x18002cfe5  test    [rcx+1Ch], r15b
0x18002cfe9  jz      short loc_18002CFFD
0x18002cfeb  mov     edx, r13d
0x18002cfee  mov     r9d, eax
0x18002cff1  mov     r8, rsi
0x18002cff4  mov     rcx, [rcx+10h]
0x18002cff8  call    WPP_SF_d
0x18002cffd  mov     r8d, 44Ch; unsigned __int16
0x18002d003  lea     rdx, aMain; "main"
0x18002d00a  mov     ecx, ebx; int
0x18002d00c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002d011  nop
0x18002d012  xor     r8d, r8d
0x18002d015  mov     dl, r15b
0x18002d018  lea     rcx, [rsp+0F8h+var_58]
0x18002d020  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18002d025  nop
0x18002d026  jmp     loc_18002CE25
0x18002d02b  lea     rdx, [rsp+0F8h+var_50]
0x18002d033  cmp     [rsp+0F8h+var_38], 8
0x18002d03c  cmovnb  rdx, [rsp+0F8h+var_50]; wchar_t *
0x18002d045  call    ?CmInitialize@@YAXPEAUHKEY__@@PEB_WK@Z; CmInitialize(HKEY__ *,wchar_t const *,ulong)
0x18002d04a  nop
0x18002d04b  xor     r8d, r8d
0x18002d04e  mov     dl, r15b
0x18002d051  lea     rcx, [rsp+0F8h+var_58]
0x18002d059  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18002d05e  nop
0x18002d05f  mov     [rsp+0F8h+var_58], r12d
0x18002d067  mov     [rsp+0F8h+var_50], r12
0x18002d06f  lea     rax, aSetupstatus; "SetupStatus"
0x18002d076  mov     [rsp+0F8h+var_48], rax
0x18002d07e  mov     dword ptr [rsp+0F8h+var_40], r12d
0x18002d086  mov     [rsp+0F8h+var_38], r12
0x18002d08e  mov     dword ptr [rsp+0F8h+var_B8], r12d
0x18002d093  mov     r13d, 4
0x18002d099  mov     r9d, r13d
0x18002d09c  lea     r8, [rsp+0F8h+var_B8]
0x18002d0a1  mov     edx, r13d
0x18002d0a4  lea     rcx, [rsp+0F8h+var_58]; struct RegEntry *
0x18002d0ac  call    QueryValueInternal
0x18002d0b1  mov     [rsp+0F8h+var_58], r12d
0x18002d0b9  mov     [rsp+0F8h+var_50], r12
0x18002d0c1  lea     rax, aWorkgroup; "Workgroup"
0x18002d0c8  mov     [rsp+0F8h+var_48], rax
0x18002d0d0  mov     dword ptr [rsp+0F8h+var_40], r12d
0x18002d0d8  mov     [rsp+0F8h+var_38], r12
0x18002d0e0  lea     rdx, ?g_fWorkGroupInstallation@@3HA; int *
0x18002d0e7  lea     rcx, [rsp+0F8h+var_58]; struct RegEntry *
0x18002d0ef  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAH@Z; CmQueryValue(RegEntry const &,int *)
0x18002d0f4  mov     [rsp+0F8h+var_58], r12d
0x18002d0fc  mov     [rsp+0F8h+var_50], r12
0x18002d104  lea     rax, aMaxxmldepth; "MaxXmlDepth"
0x18002d10b  mov     [rsp+0F8h+var_48], rax
0x18002d113  mov     eax, 100h
0x18002d118  mov     dword ptr [rsp+0F8h+var_40], eax
0x18002d11f  mov     [rsp+0F8h+var_38], r12
0x18002d127  mov     cs:?g_dwMaxXmlDepth@@3KA, eax; ulong g_dwMaxXmlDepth
0x18002d12d  mov     r9d, r13d
0x18002d130  lea     r8, ?g_dwMaxXmlDepth@@3KA; ulong g_dwMaxXmlDepth
0x18002d137  mov     edx, r13d
0x18002d13a  lea     rcx, [rsp+0F8h+var_58]; struct RegEntry *
0x18002d142  call    QueryValueInternal
0x18002d147  mov     edx, dword ptr [rsp+0F8h+var_B8]; char
0x18002d14b  mov     rcx, r14; wchar_t *
0x18002d14e  call    InitLogging
0x18002d153  add     dword ptr cs:qword_1801291DC, r15d
0x18002d15a  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002d160  mov     dword ptr cs:qword_1801291DC+4, eax
0x18002d166  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x18002d16b  mov     [rsp+0F8h+var_B4], r13d
0x18002d170  lea     rax, [rsp+0F8h+var_B4]
0x18002d175  mov     [rsp+0F8h+pcbData], rax; pcbData
0x18002d17a  lea     rax, [rsp+0F8h+var_A0]
0x18002d17f  mov     [rsp+0F8h+pvData], rax; pvData
0x18002d184  mov     [rsp+0F8h+pdwType], r12; pdwType
0x18002d189  lea     r9d, [r13+0Ch]; dwFlags
0x18002d18d  lea     r8, aEnabletrace; "EnableTrace"
0x18002d194  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSMQ\\Parameters"
0x18002d19b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002d1a2  call    cs:__imp_RegGetValueW
0x18002d1a8  test    eax, eax
0x18002d1aa  jnz     loc_18002D233
0x18002d1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1b7  cmp     rcx, rdi
0x18002d1ba  jz      short loc_18002D1DB
0x18002d1bc  test    [rcx+1Ch], r13b
0x18002d1c0  jz      short loc_18002D1DB
0x18002d1c2  lea     edx, [rax+21h]
0x18002d1c5  xor     r9d, r9d
0x18002d1c8  mov     r8, rsi
0x18002d1cb  mov     rcx, [rcx+10h]
0x18002d1cf  call    WPP_SF_d
0x18002d1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1db  mov     eax, [rsp+0F8h+var_A0]
0x18002d1df  test    eax, eax
0x18002d1e1  jz      short loc_18002D208
0x18002d1e3  cmp     rcx, rdi
0x18002d1e6  jz      short loc_18002D259
0x18002d1e8  test    [rcx+1Ch], r13b
0x18002d1ec  jz      short loc_18002D259
0x18002d1ee  mov     edx, 22h ; '"'
0x18002d1f3  mov     dword ptr [rsp+0F8h+pdwType], eax
0x18002d1f7  xor     r9d, r9d
0x18002d1fa  mov     r8, rsi
0x18002d1fd  mov     rcx, [rcx+10h]
0x18002d201  call    WPP_SF_Dd
0x18002d206  jmp     short loc_18002D259
0x18002d208  cmp     rcx, rdi
0x18002d20b  jz      short loc_18002D22C
0x18002d20d  test    [rcx+1Ch], r13b
0x18002d211  jz      short loc_18002D22C
0x18002d213  mov     edx, 23h ; '#'
0x18002d218  mov     dword ptr [rsp+0F8h+pdwType], r12d
0x18002d21d  xor     r9d, r9d
0x18002d220  mov     r8, rsi
0x18002d223  mov     rcx, [rcx+10h]
0x18002d227  call    WPP_SF_Dd
0x18002d22c  call    ?QmpDisableMSMQTracing@@YAXXZ; QmpDisableMSMQTracing(void)
0x18002d231  jmp     short loc_18002D25E
0x18002d233  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d23a  cmp     rcx, rdi
0x18002d23d  jz      short loc_18002D259
0x18002d23f  test    [rcx+1Ch], r13b
0x18002d243  jz      short loc_18002D259
0x18002d245  mov     edx, 24h ; '$'
0x18002d24a  mov     r9d, eax
0x18002d24d  mov     r8, rsi
0x18002d250  mov     rcx, [rcx+10h]
0x18002d254  call    WPP_SF_d
0x18002d259  call    ?QmpEnableMSMQTracing@@YAXXZ; QmpEnableMSMQTracing(void)
0x18002d25e  add     dword ptr cs:qword_1801291DC, r15d
0x18002d265  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002d26b  mov     dword ptr cs:qword_1801291DC+4, eax
0x18002d271  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x18002d276  call    ?RegisterFloodingEvents@@YAXPEB_W@Z; RegisterFloodingEvents(wchar_t const *)
0x18002d27b  mov     rcx, cs:__imp_?g_CancelRpc@@3VCCancelRpc@@A; CCancelRpc g_CancelRpc
0x18002d282  call    cs:__imp_?Init@CCancelRpc@@QEAAXXZ; CCancelRpc::Init(void)
0x18002d288  call    QmpSetServiceProgressReportTime
0x18002d28d  add     dword ptr cs:qword_1801291DC, r15d
0x18002d294  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002d29a  mov     dword ptr cs:qword_1801291DC+4, eax
0x18002d2a0  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x18002d2a5  call    ?_InitFromRegistry@@YAJXZ; _InitFromRegistry(void)
0x18002d2aa  mov     ebx, eax
0x18002d2ac  test    eax, eax
0x18002d2ae  jns     short loc_18002D2BB
0x18002d2b0  mov     r8d, 4B0h
0x18002d2b6  jmp     loc_18002CE17
0x18002d2bb  mov     dword ptr [rsp+0F8h+pvData], 0FFFFFFFFh; cchCount2
0x18002d2c3  lea     rax, aMsmq_0; "MSMQ"
0x18002d2ca  mov     [rsp+0F8h+pdwType], rax; lpString2
0x18002d2cf  or      r9d, 0FFFFFFFFh; cchCount1
0x18002d2d3  mov     r8, r14; lpString1
0x18002d2d6  mov     edx, r15d; dwCmpFlags
0x18002d2d9  mov     ecx, 7Fh; Locale
0x18002d2de  call    cs:__imp_CompareStringW
0x18002d2e4  cmp     eax, 2
0x18002d2e7  jnz     short loc_18002D2EE
0x18002d2e9  call    ?HandleChangeOfJoinStatus@@YAXXZ; HandleChangeOfJoinStatus(void)
0x18002d2ee  call    InitPureWorkgroupFlag
0x18002d2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2fa  cmp     rcx, rdi
0x18002d2fd  jz      loc_18002D3F5
0x18002d303  test    [rcx+1Ch], r13b
0x18002d307  jz      short loc_18002D324
0x18002d309  mov     edx, 25h ; '%'
  ... truncated ...
```
