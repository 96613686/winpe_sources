# DimCleanUp(ulong)

- ea: `0x1800115c8`
- end: `0x180011a3d`
- name: `?DimCleanUp@@YAXK@Z`
- size: `1141`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011eb0`
- `0x180012b80`

## callees

- `0x1800010b8`
- `0x1800056c4`
- `0x18000def0`
- `0x1800114b8`
- `0x180011514`
- `0x180011594`
- `0x1800115c8`
- `0x180011be4`
- `0x180014b44`
- `0x180016790`
- `0x180019744`
- `0x18001a1cc`
- `0x180027454`
- `0x18002fcbc`
- `0x180034eec`
- `0x1800458f8`
- `0x180045d40`
- `0x180045d7c`
- `0x180045ee8`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `ntdll!RtlDeleteTimerQueueEx` at `0x180011693`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180011693`
- `ntdll!RtlDeleteTimer` at `0x18001167b`
- `ntdll!RtlDeleteTimer` at `0x18001167b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800117d1`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800117d1`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800117c0`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800117c0`
- `adsldpc!ADSICloseDSObject` at `0x180011864`
- `adsldpc!ADSICloseDSObject` at `0x180011864`
- `rtutils!TraceDeregisterA` at `0x180011895`
- `rtutils!TraceDeregisterA` at `0x180011895`
- `rtutils!RouterLogDeregisterW` at `0x1800118a2`
- `rtutils!RouterLogDeregisterW` at `0x1800118a2`
- `USER32!UnregisterDeviceNotification` at `0x18001161c`
- `USER32!UnregisterDeviceNotification` at `0x18001161c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117db`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800118b4`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800118b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800116dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800116dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011852`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011852`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001187e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001187e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011871`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011871`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800116ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011753`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800116ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800117ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800117ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011808`
- `MPRDDM!IfObjectFreePhonebookContext` at `0x180011733`
- `MPRDDM!IfObjectFreePhonebookContext` at `0x180011733`
- `MPRDDM!DDMPostCleanup` at `0x180011762`
- `MPRDDM!DDMPostCleanup` at `0x180011762`
- `ADVAPI32!EventUnregister` at `0x180011943`
- `ADVAPI32!EventUnregister` at `0x180011943`
- `RASAPI32!UnInitializeRAS` at `0x180011a04`
- `RASAPI32!UnInitializeRAS` at `0x180011a04`

## string_xrefs

- `0x180011796`: `DimCleanUp: CleanUpRrasConfigurationStore failed`
- `0x1800118cb`: `DimCleanup completed for error %d`

## pseudocode

```c
void __fastcall DimCleanUp(unsigned int a1)
{
  int v2; // ebx
  HANDLE v3; // rcx
  char v4; // al
  CDimInterfaceTable *v5; // rcx
  const struct _GUID *v6; // r9
  HANDLE v7; // rcx
  HANDLE v8; // rbx
  unsigned int v9; // [rsp+20h] [rbp-878h]
  struct _GUID v10; // [rsp+38h] [rbp-860h] BYREF
  GUID ActivityId; // [rsp+48h] [rbp-850h] BYREF
  int v12; // [rsp+60h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-834h] BYREF

  v12 = 0;
  ActivityId = 0;
  memset_0(v13, 0, sizeof(v13));
  v2 = SetRasServerActivityId(&ActivityId);
  UnregisterDeviceNotification(Handle);
  qword_180070F24 = 3;
  qword_180070F34 = 0x30D4000000001LL;
  DimAnnounceServiceStatus();
  if ( (gbldwDIMComponentsLoaded & 1) != 0 )
    DimTerminateRPC();
  _InterlockedCompareExchange(&dword_180070FC0, 1, 0);
  v3 = TimerQueue;
  if ( TimerQueue )
  {
    if ( phNewTimer )
    {
      RtlDeleteTimer(TimerQueue, phNewTimer, 0);
      v3 = TimerQueue;
      phNewTimer = 0;
    }
    RtlDeleteTimerQueueEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    TimerQueue = 0;
  }
  RegisterForRoutingDomainChangeNotifications(0);
  v4 = gbldwDIMComponentsLoaded;
  if ( (gbldwDIMComponentsLoaded & 0x40) != 0 )
  {
    DimStopAllRoutingDomains();
    v4 = gbldwDIMComponentsLoaded;
  }
  if ( (v4 & 4) != 0 )
  {
    if ( (gblDIMConfigInfo & 0x12) != gblDIMConfigInfo && gblhEventDDMServiceState )
      SetEvent(gblhEventDDMServiceState);
    while ( dword_180070F44 )
      Sleep(0x3E8u);
  }
  DimAnnounceServiceStatus();
  if ( (gbldwDIMComponentsLoaded & 2) != 0 )
  {
    v5 = g_pCDimRouterManager;
    if ( g_pCDimRouterManager )
      CDimRouterManager::UnLoad(g_pCDimRouterManager);
  }
  if ( g_pCDimInterfaceTable )
    CDimInterfaceTable::RemoveInterfaces(v5, 0);
  if ( gblPbkContext )
  {
    IfObjectFreePhonebookContext();
    gblPbkContext = 0;
  }
  MediaSenseRegister(0);
  BindingsNotificationsRegister(0);
  Sleep(0x7D0u);
  if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    DDMPostCleanup();
  if ( qword_180070FC8 )
    ConfigureMiniports(0, 2, &qword_180070FC8);
  if ( (unsigned int)CleanUpRrasConfigurationStore() && (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasDimTraceError,
      L"DimCleanUp: CleanUpRrasConfigurationStore failed");
  if ( (gbldwDIMComponentsLoaded & 8) != 0 && IsValidSecurityDescriptor(NewDescriptor) )
  {
    if ( DestroyPrivateObjectSecurity(&NewDescriptor) )
    {
      if ( Sid )
      {
        LocalFree(Sid);
        Sid = 0;
      }
      if ( qword_180071160 )
      {
        LocalFree(qword_180071160);
        qword_180071160 = 0;
      }
    }
    else
    {
      GetLastError();
    }
  }
  if ( gblhEventDDMTerminated )
    CloseHandle(gblhEventDDMTerminated);
  if ( gblhEventDDMServiceState )
    CloseHandle(gblhEventDDMServiceState);
  if ( gblhEventTerminateDIM )
    CloseHandle(gblhEventTerminateDIM);
  EnterCriticalSection(&stru_180070F88);
  if ( qword_180070F60 )
    ADSICloseDSObject();
  LeaveCriticalSection(&stru_180070F88);
  DeleteCriticalSection(&stru_180070F88);
  gbldwDIMComponentsLoaded = 0;
  if ( dwTraceID != -1 )
    TraceDeregisterA(dwTraceID);
  RouterLogDeregisterW(hLogHandle);
  v7 = hHeap;
  if ( hHeap )
    HeapDestroy(hHeap);
  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"DimCleanup completed for error %d", a1);
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v12);
  }
  if ( v2 )
    ReSetActivityId(&ActivityId);
  v10 = (struct _GUID)xmmword_180066878;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
    EtwEx_tidActivityInfo((unsigned __int64)v7, &ActivityStop, &v10, v6, v9);
  if ( MICROSOFT_WINDOWS_RRAS_PROVIDER_Context )
  {
    EventUnregister(Microsoft_Windows_Networking_CorrelationHandle);
    Microsoft_Windows_Networking_CorrelationHandle = 0;
    McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context);
    gCfgStoreEtwContext = 0;
    *(_OWORD *)&gCfgStoreTracingDesc = 0;
    gCfgStoreTemplateFunc = 0;
    xmmword_180071080 = 0;
    gCfgStoreParamTemplateFunc = 0;
    xmmword_180071090 = 0;
    xmmword_1800710A0 = 0;
  }
  v8 = hRecipient;
  gbldwDIMComponentsLoaded = 0;
  gblhEventDDMTerminated = 0;
  gblhEventDDMServiceState = 0;
  gblhEventTerminateDIM = 0;
  gblpSvchostSharedGlobals = 0;
  memset_0(&gblDIMConfigInfo, 0, 0xC0u);
  hRecipient = v8;
  dword_180070F20 = 32;
  qword_180070F24 = 1;
  qword_180070F34 = 0;
  dword_180070F30 = a1;
  dword_180070F2C = a1 != 0 ? 0x42A : 0;
  UnInitializeRAS();
  gbldwDIMComponentsLoaded |= 0x20u;
  DimAnnounceServiceStatus();
  DeAllocateGlobals();
  TraceLoggingUnregister_EventUnregister();
}

```

## disassembly

```asm
0x1800115c8  push    rbx
0x1800115ca  push    rsi
0x1800115cb  push    rdi
0x1800115cc  push    r15
0x1800115ce  sub     rsp, 878h
0x1800115d5  mov     rax, cs:__security_cookie
0x1800115dc  xor     rax, rsp
0x1800115df  mov     [rsp+898h+var_38], rax
0x1800115e7  mov     edi, ecx
0x1800115e9  xorps   xmm0, xmm0
0x1800115ec  xor     esi, esi
0x1800115ee  lea     rcx, [rsp+898h+var_834]; void *
0x1800115f3  xor     edx, edx; Val
0x1800115f5  mov     [rsp+898h+var_838], esi
0x1800115f9  mov     r8d, 7FCh; Size
0x1800115ff  movups  xmmword ptr [rsp+898h+ActivityId.Data1], xmm0
0x180011604  call    memset_0
0x180011609  lea     rcx, [rsp+898h+ActivityId]; ActivityId
0x18001160e  call    SetRasServerActivityId
0x180011613  mov     rcx, cs:Handle; Handle
0x18001161a  mov     ebx, eax
0x18001161c  call    cs:__imp_UnregisterDeviceNotification
0x180011622  lea     r15d, [rsi+1]
0x180011626  mov     cs:qword_180070F24, 3
0x180011631  mov     dword ptr cs:qword_180070F34, r15d
0x180011638  mov     dword ptr cs:qword_180070F34+4, 30D40h
0x180011642  call    ?DimAnnounceServiceStatus@@YAXXZ; DimAnnounceServiceStatus(void)
0x180011647  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, r15b; ulong gbldwDIMComponentsLoaded
0x18001164e  jz      short loc_180011655
0x180011650  call    ?DimTerminateRPC@@YAXXZ; DimTerminateRPC(void)
0x180011655  xor     eax, eax
0x180011657  lock cmpxchg cs:dword_180070FC0, r15d
0x180011660  mov     rcx, cs:TimerQueue; TimerQueue
0x180011667  test    rcx, rcx
0x18001166a  jz      short loc_1800116A0
0x18001166c  mov     rdx, cs:phNewTimer; Timer
0x180011673  test    rdx, rdx
0x180011676  jz      short loc_18001168F
0x180011678  xor     r8d, r8d; CompletionEvent
0x18001167b  call    cs:__imp_RtlDeleteTimer
0x180011681  mov     rcx, cs:TimerQueue; TimerQueue
0x180011688  mov     cs:phNewTimer, rsi
0x18001168f  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180011693  call    cs:__imp_RtlDeleteTimerQueueEx
0x180011699  mov     cs:TimerQueue, rsi
0x1800116a0  xor     ecx, ecx; int
0x1800116a2  call    ?RegisterForRoutingDomainChangeNotifications@@YAKH@Z; RegisterForRoutingDomainChangeNotifications(int)
0x1800116a7  mov     eax, cs:?gbldwDIMComponentsLoaded@@3KA; ulong gbldwDIMComponentsLoaded
0x1800116ad  test    al, 40h
0x1800116af  jz      short loc_1800116BC
0x1800116b1  call    ?DimStopAllRoutingDomains@@YAKXZ; DimStopAllRoutingDomains(void)
0x1800116b6  mov     eax, cs:?gbldwDIMComponentsLoaded@@3KA; ulong gbldwDIMComponentsLoaded
0x1800116bc  test    al, 4
0x1800116be  jz      short loc_1800116F8
0x1800116c0  mov     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x1800116c6  and     eax, 12h
0x1800116c9  cmp     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x1800116cf  jz      short loc_1800116F0
0x1800116d1  mov     rcx, cs:?gblhEventDDMServiceState@@3PEAXEA; hEvent
0x1800116d8  test    rcx, rcx
0x1800116db  jz      short loc_1800116F0
0x1800116dd  call    cs:__imp_SetEvent
0x1800116e3  jmp     short loc_1800116F0
0x1800116e5  mov     ecx, 3E8h; dwMilliseconds
0x1800116ea  call    cs:__imp_Sleep
0x1800116f0  cmp     cs:dword_180070F44, esi
0x1800116f6  ja      short loc_1800116E5
0x1800116f8  call    ?DimAnnounceServiceStatus@@YAXXZ; DimAnnounceServiceStatus(void)
0x1800116fd  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 2; ulong gbldwDIMComponentsLoaded
0x180011704  jz      short loc_180011717
0x180011706  mov     rcx, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; this
0x18001170d  test    rcx, rcx
0x180011710  jz      short loc_180011717
0x180011712  call    ?UnLoad@CDimRouterManager@@QEAAKXZ; CDimRouterManager::UnLoad(void)
0x180011717  cmp     cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA, rsi; CDimInterfaceTable * g_pCDimInterfaceTable
0x18001171e  jz      short loc_180011727
0x180011720  xor     edx, edx; struct _GUID *
0x180011722  call    ?RemoveInterfaces@CDimInterfaceTable@@QEAAXPEAU_GUID@@@Z; CDimInterfaceTable::RemoveInterfaces(_GUID *)
0x180011727  mov     rcx, cs:?gblPbkContext@@3PEAXEA; void * gblPbkContext
0x18001172e  test    rcx, rcx
0x180011731  jz      short loc_180011740
0x180011733  call    cs:__imp_IfObjectFreePhonebookContext
0x180011739  mov     cs:?gblPbkContext@@3PEAXEA, rsi; void * gblPbkContext
0x180011740  xor     ecx, ecx; int
0x180011742  call    ?MediaSenseRegister@@YAKH@Z; MediaSenseRegister(int)
0x180011747  xor     ecx, ecx; int
0x180011749  call    ?BindingsNotificationsRegister@@YAKH@Z; BindingsNotificationsRegister(int)
0x18001174e  mov     ecx, 7D0h; dwMilliseconds
0x180011753  call    cs:__imp_Sleep
0x180011759  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x180011760  jz      short loc_180011768
0x180011762  call    cs:__imp_DDMPostCleanup
0x180011768  cmp     cs:qword_180070FC8, rsi
0x18001176f  jz      short loc_180011784
0x180011771  lea     r8, qword_180070FC8
0x180011778  mov     edx, 2
0x18001177d  xor     ecx, ecx
0x18001177f  call    ConfigureMiniports
0x180011784  call    CleanUpRrasConfigurationStore
0x180011789  test    eax, eax
0x18001178b  jz      short loc_1800117B0
0x18001178d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180011794  jz      short loc_1800117B0
0x180011796  lea     r8, aDimcleanupClea; "DimCleanUp: CleanUpRrasConfigurationSto"...
0x18001179d  lea     rdx, RasDimTraceError
0x1800117a4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800117ab  call    McTemplateU0z_EventWriteTransfer
0x1800117b0  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 8; ulong gbldwDIMComponentsLoaded
0x1800117b7  jz      short loc_180011815
0x1800117b9  mov     rcx, cs:NewDescriptor; pSecurityDescriptor
0x1800117c0  call    cs:__imp_IsValidSecurityDescriptor
0x1800117c6  test    eax, eax
0x1800117c8  jz      short loc_180011815
0x1800117ca  lea     rcx, NewDescriptor; ObjectDescriptor
0x1800117d1  call    cs:__imp_DestroyPrivateObjectSecurity
0x1800117d7  test    eax, eax
0x1800117d9  jnz     short loc_1800117E3
0x1800117db  call    cs:__imp_GetLastError
0x1800117e1  jmp     short loc_180011815
0x1800117e3  mov     rcx, cs:Sid; hMem
0x1800117ea  test    rcx, rcx
0x1800117ed  jz      short loc_1800117FC
0x1800117ef  call    cs:__imp_LocalFree
0x1800117f5  mov     cs:Sid, rsi
0x1800117fc  mov     rcx, cs:qword_180071160; hMem
0x180011803  test    rcx, rcx
0x180011806  jz      short loc_180011815
0x180011808  call    cs:__imp_LocalFree
0x18001180e  mov     cs:qword_180071160, rsi
0x180011815  mov     rcx, cs:?gblhEventDDMTerminated@@3PEAXEA; hObject
0x18001181c  test    rcx, rcx
0x18001181f  jz      short loc_180011827
0x180011821  call    cs:__imp_CloseHandle
0x180011827  mov     rcx, cs:?gblhEventDDMServiceState@@3PEAXEA; hObject
0x18001182e  test    rcx, rcx
0x180011831  jz      short loc_180011839
0x180011833  call    cs:__imp_CloseHandle
0x180011839  mov     rcx, cs:?gblhEventTerminateDIM@@3PEAXEA; hObject
0x180011840  test    rcx, rcx
0x180011843  jz      short loc_18001184B
0x180011845  call    cs:__imp_CloseHandle
0x18001184b  lea     rcx, stru_180070F88; lpCriticalSection
0x180011852  call    cs:__imp_EnterCriticalSection
0x180011858  mov     rcx, cs:qword_180070F60
0x18001185f  test    rcx, rcx
0x180011862  jz      short loc_18001186A
0x180011864  call    cs:__imp_ADSICloseDSObject
0x18001186a  lea     rcx, stru_180070F88; lpCriticalSection
0x180011871  call    cs:__imp_LeaveCriticalSection
0x180011877  lea     rcx, stru_180070F88; lpCriticalSection
0x18001187e  call    cs:__imp_DeleteCriticalSection
0x180011884  mov     ecx, cs:dwTraceID; dwTraceID
0x18001188a  mov     cs:?gbldwDIMComponentsLoaded@@3KA, esi; ulong gbldwDIMComponentsLoaded
0x180011890  cmp     ecx, 0FFFFFFFFh
0x180011893  jz      short loc_18001189B
0x180011895  call    cs:__imp_TraceDeregisterA
0x18001189b  mov     rcx, cs:hLogHandle; hLogHandle
0x1800118a2  call    cs:__imp_RouterLogDeregisterW
0x1800118a8  mov     rcx, cs:hHeap; hHeap
0x1800118af  test    rcx, rcx
0x1800118b2  jz      short loc_1800118BA
0x1800118b4  call    cs:__imp_HeapDestroy
0x1800118ba  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800118c1  jz      short loc_1800118FD
0x1800118c3  mov     r8d, edi
0x1800118c6  mov     word ptr [rsp+898h+var_838], si
0x1800118cb  lea     rdx, aDimcleanupComp; "DimCleanup completed for error %d"
0x1800118d2  lea     rcx, [rsp+898h+var_838]
0x1800118d7  call    FormatRRASErrorString
0x1800118dc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800118e3  jz      short loc_1800118FD
0x1800118e5  lea     r8, [rsp+898h+var_838]
0x1800118ea  lea     rdx, RasDimTraceAdminError
0x1800118f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800118f8  call    McTemplateU0z_EventWriteTransfer
0x1800118fd  test    ebx, ebx
0x1800118ff  jz      short loc_18001190B
0x180011901  lea     rcx, [rsp+898h+ActivityId]; ActivityId
0x180011906  call    ReSetActivityId
0x18001190b  movups  xmm0, cs:xmmword_180066878
0x180011912  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180011918  movdqu  xmmword ptr [rsp+898h+var_860.Data1], xmm0
0x18001191e  test    eax, eax
0x180011920  jz      short loc_180011933
0x180011922  lea     r8, [rsp+898h+var_860]; struct _GUID *
0x180011927  lea     rdx, ActivityStop; struct _EVENT_DESCRIPTOR *
0x18001192e  call    ?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z; EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)
0x180011933  cmp     cs:MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, rsi
0x18001193a  jz      short loc_180011990
0x18001193c  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x180011943  call    cs:__imp_EventUnregister
0x180011949  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011950  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, rsi
0x180011957  call    McGenEventUnregister_EventUnregister
0x18001195c  xorps   xmm0, xmm0
0x18001195f  mov     cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA, rsi; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180011966  movups  cs:?gCfgStoreTracingDesc@@3PAPEAU_EVENT_DESCRIPTOR@@A, xmm0; _EVENT_DESCRIPTOR * near * gCfgStoreTracingDesc
0x18001196d  mov     cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA, rsi; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180011974  movups  cs:xmmword_180071080, xmm0
0x18001197b  mov     cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA, rsi; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180011982  movups  cs:xmmword_180071090, xmm0
0x180011989  movups  cs:xmmword_1800710A0, xmm0
0x180011990  mov     rbx, cs:hRecipient
0x180011997  lea     rcx, ?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; void *
0x18001199e  xor     edx, edx; Val
0x1800119a0  mov     cs:?gbldwDIMComponentsLoaded@@3KA, esi; ulong gbldwDIMComponentsLoaded
0x1800119a6  mov     r8d, 0C0h; Size
0x1800119ac  mov     cs:?gblhEventDDMTerminated@@3PEAXEA, rsi; void * gblhEventDDMTerminated
0x1800119b3  mov     cs:?gblhEventDDMServiceState@@3PEAXEA, rsi; void * gblhEventDDMServiceState
0x1800119ba  mov     cs:?gblhEventTerminateDIM@@3PEAXEA, rsi; void * gblhEventTerminateDIM
0x1800119c1  mov     cs:?gblpSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rsi; _SVCHOST_GLOBAL_DATA * gblpSvchostSharedGlobals
0x1800119c8  call    memset_0
0x1800119cd  mov     eax, edi
0x1800119cf  mov     cs:hRecipient, rbx
0x1800119d6  neg     eax
0x1800119d8  mov     cs:dword_180070F20, 20h ; ' '
0x1800119e2  mov     cs:qword_180070F24, r15
0x1800119e9  sbb     ecx, ecx
0x1800119eb  mov     cs:qword_180070F34, rsi
0x1800119f2  and     ecx, 42Ah
0x1800119f8  mov     cs:dword_180070F30, edi
0x1800119fe  mov     cs:dword_180070F2C, ecx
0x180011a04  call    cs:__imp_UnInitializeRAS
0x180011a0a  or      cs:?gbldwDIMComponentsLoaded@@3KA, 20h; ulong gbldwDIMComponentsLoaded
0x180011a11  call    ?DimAnnounceServiceStatus@@YAXXZ; DimAnnounceServiceStatus(void)
0x180011a16  call    ?DeAllocateGlobals@@YAXXZ; DeAllocateGlobals(void)
0x180011a1b  call    TraceLoggingUnregister_EventUnregister
0x180011a20  mov     rcx, [rsp+898h+var_38]
0x180011a28  xor     rcx, rsp; StackCookie
0x180011a2b  call    __security_check_cookie
0x180011a30  add     rsp, 878h
0x180011a37  pop     r15
0x180011a39  pop     rdi
0x180011a3a  pop     rsi
0x180011a3b  pop     rbx
0x180011a3c  retn
```
