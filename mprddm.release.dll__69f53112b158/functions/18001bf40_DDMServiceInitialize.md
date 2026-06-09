# DDMServiceInitialize

- ea: `0x18001bf40`
- end: `0x18001e4f1`
- name: `DDMServiceInitialize`
- size: `9649`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007c0c`
- `0x1800157a0`
- `0x180015a70`
- `0x180015c4c`
- `0x1800164b4`
- `0x1800167fc`
- `0x180017280`
- `0x180017fc8`
- `0x180018578`
- `0x180018998`
- `0x18001b3f4`
- `0x18001b458`
- `0x18001b924`
- `0x18001bf40`
- `0x18001e644`
- `0x1800205b0`
- `0x1800266b0`
- `0x1800268fc`
- `0x180026c7c`
- `0x180027b70`
- `0x180028f60`
- `0x1800298e4`
- `0x18002ad08`
- `0x18002aff8`
- `0x18003c2c8`
- `0x18003d278`
- `0x180047e94`
- `0x180052b74`
- `0x1800561f4`
- `0x180056dd0`
- `0x180057830`
- `0x180057bf4`
- `0x180058bd4`
- `0x1800755b8`
- `0x1800821e0`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001e2ed`
- `KERNEL32!SetEvent` at `0x18001e2ed`
- `KERNEL32!DeleteCriticalSection` at `0x18001e3cf`
- `KERNEL32!DeleteCriticalSection` at `0x18001e3ff`
- `KERNEL32!DeleteCriticalSection` at `0x18001e417`
- `KERNEL32!DeleteCriticalSection` at `0x18001e3cf`
- `KERNEL32!DeleteCriticalSection` at `0x18001e3ff`
- `KERNEL32!DeleteCriticalSection` at `0x18001e417`
- `KERNEL32!InitializeSRWLock` at `0x18001c583`
- `KERNEL32!InitializeSRWLock` at `0x18001c583`
- `KERNEL32!HeapCreate` at `0x18001c384`
- `KERNEL32!HeapCreate` at `0x18001c384`
- `KERNEL32!SetWaitableTimer` at `0x18001d778`
- `KERNEL32!SetWaitableTimer` at `0x18001d778`
- `KERNEL32!CreateWaitableTimerW` at `0x18001d053`
- `KERNEL32!CreateWaitableTimerW` at `0x18001d053`
- `KERNEL32!InitializeCriticalSection` at `0x18001c1fd`
- `KERNEL32!InitializeCriticalSection` at `0x18001c218`
- `KERNEL32!InitializeCriticalSection` at `0x18001c233`
- `KERNEL32!InitializeCriticalSection` at `0x18001c24e`
- `KERNEL32!InitializeCriticalSection` at `0x18001e184`
- `KERNEL32!InitializeCriticalSection` at `0x18001c1fd`
- `KERNEL32!InitializeCriticalSection` at `0x18001c218`
- `KERNEL32!InitializeCriticalSection` at `0x18001c233`
- `KERNEL32!InitializeCriticalSection` at `0x18001c24e`
- `KERNEL32!InitializeCriticalSection` at `0x18001e184`
- `KERNEL32!CreateThread` at `0x18001e067`
- `KERNEL32!CreateThread` at `0x18001e067`
- `KERNEL32!HeapAlloc` at `0x18001c459`
- `KERNEL32!HeapAlloc` at `0x18001cf07`
- `KERNEL32!HeapAlloc` at `0x18001c459`
- `KERNEL32!HeapAlloc` at `0x18001cf07`
- `KERNEL32!CloseHandle` at `0x18001e15c`
- `KERNEL32!CloseHandle` at `0x18001e15c`
- `KERNEL32!GetLastError` at `0x18001c3a0`
- `KERNEL32!GetLastError` at `0x18001c473`
- `KERNEL32!GetLastError` at `0x18001cf28`
- `KERNEL32!GetLastError` at `0x18001d788`
- `KERNEL32!GetLastError` at `0x18001da8e`
- `KERNEL32!GetLastError` at `0x18001e07b`
- `KERNEL32!GetLastError` at `0x18001c3a0`
- `KERNEL32!GetLastError` at `0x18001c473`
- `KERNEL32!GetLastError` at `0x18001cf28`
- `KERNEL32!GetLastError` at `0x18001d788`
- `KERNEL32!GetLastError` at `0x18001da8e`
- `KERNEL32!GetLastError` at `0x18001e07b`
- `KERNEL32!CreateEventW` at `0x18001d009`
- `KERNEL32!CreateEventW` at `0x18001d02c`
- `KERNEL32!CreateEventW` at `0x18001d009`
- `KERNEL32!CreateEventW` at `0x18001d02c`
- `ADVAPI32!EventRegister` at `0x18001c157`
- `ADVAPI32!EventRegister` at `0x18001c157`
- `ADVAPI32!EventSetInformation` at `0x18001c182`
- `ADVAPI32!EventSetInformation` at `0x18001c182`
- `ADVAPI32!RegOpenKeyW` at `0x18001c8ab`
- `ADVAPI32!RegOpenKeyW` at `0x18001c9ab`
- `ADVAPI32!RegOpenKeyW` at `0x18001ca34`
- `ADVAPI32!RegOpenKeyW` at `0x18001c8ab`
- `ADVAPI32!RegOpenKeyW` at `0x18001c9ab`
- `ADVAPI32!RegOpenKeyW` at `0x18001ca34`
- `rtutils!RouterLogEventW` at `0x18001c54e`
- `rtutils!RouterLogEventW` at `0x18001c54e`
- `rtutils!RouterLogRegisterW` at `0x18001da76`
- `rtutils!RouterLogRegisterW` at `0x18001da76`
- `rtutils!RouterLogEventStringW` at `0x18001c74a`
- `rtutils!RouterLogEventStringW` at `0x18001dec1`
- `rtutils!RouterLogEventStringW` at `0x18001c74a`
- `rtutils!RouterLogEventStringW` at `0x18001dec1`
- `rasman!RasGetKey` at `0x18001d89e`
- `rasman!RasPortGetStatistics` at `0x18001d880`
- `rasman!RasProtocolStarted` at `0x18001d8da`
- `rasman!RasCompressionSetInfo` at `0x18001d9bb`
- `rasman!RasPortSetFramingEx` at `0x18001d9ac`
- `rasman!RasRegisterPnPHandler` at `0x18001e0f3`
- `rasman!RasRegisterPnPHandler` at `0x18001e0f3`
- `rasman!RasGetFramingCapabilities` at `0x18001d99d`
- `rasman!RasSetConnectionUserData` at `0x18001d8cb`
- `rasman!RasActivateRoute` at `0x18001d925`
- `rasman!RasPortGetProtocolCompression` at `0x18001d9d9`
- `rasman!RasGetTimeSinceLastActivity` at `0x18001d8e9`
- `rasman!RasCompressionGetInfo` at `0x18001d9ca`
- `rasman!RasGetInfo` at `0x18001d97f`
- `rasman!RasPortCancelReceive` at `0x18001d943`
- `rasman!RasPortSetProtocolCompression` at `0x18001d9f7`
- `rasman!RasFreeBuffer` at `0x18001d952`
- `rasman!RasGetConnectInfo` at `0x18001d970`
- `rasman!RasAllocateRoute` at `0x18001d88f`
- `rasman!RasDeAllocateRoute` at `0x18001d916`
- `rasman!RasGetPortUserData` at `0x18001d8ad`
- `rasman!RasPortGetBundle` at `0x18001d8bc`
- `rasman!RasSendNotification` at `0x18001e34a`
- `rasman!RasSendNotification` at `0x18001e34a`
- `rasman!RasBundleGetPort` at `0x18001d98e`
- `rasman!RasSetTunnelEndPoints` at `0x18001d8f8`
- `rasman!RasDeviceGetInfo` at `0x18001d871`
- `rasman!RasReferenceRasman` at `0x18001c760`
- `rasman!RasReferenceRasman` at `0x18001c760`
- `rasman!RasInitialize` at `0x18001c66d`
- `rasman!RasInitialize` at `0x18001c66d`
- `rasman!RasGetBuffer` at `0x18001d9e8`
- `rasman!RasPortSend` at `0x18001d961`
- `rasman!RasSendProtocolResultToRasman` at `0x18001d907`
- `rasman!RasUpdateDefaultRouteSettings` at `0x18001d934`
- `sstpcfg!SetupSstpServerConfig` at `0x18001c59a`
- `sstpcfg!SetupSstpServerConfig` at `0x18001c59a`
- `eappprxy!EapHostPeerInitialize` at `0x18001cdb6`
- `eappprxy!EapHostPeerInitialize` at `0x18001cdb6`

## string_xrefs

- `0x18001d656`: `RasIpv6SrvrStart completes with return code %d`
- `0x18001c5c8`: `DDMServiceInitialize: SetupSstpServerConfig failed. Error %d`
- `0x18001c89d`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18001c8c1`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18001e43d`: `DDMServiceInitialize: Resource initialization failed with error %d`
- `0x18001c292`: `DDMServiceInitialize: InitGlobalThreadPool failed with error %d`
- `0x18001c339`: `DDMServiceInitialize: InitSerializedThreadPool failed with error %d`
- `0x18001c3cf`: `DDMServiceInitialize: Heap creation failed with error %d`
- `0x18001c4a9`: `DDMServiceInitialize: Media object  creation failed with error %d`
- `0x18001c632`: `DDMServiceInitialize: WanDriver initialization failed with error %d`
- `0x18001c69f`: `DDMServiceInitialize: Rasman initialization failed with error %d`
- `0x18001c78a`: `DDMServiceInitialize: Rasman's reference count could not be incremented. Error %d`
- `0x18001c7f9`: `DDMServiceInitialize: Failed to get the router phone book. Error %d`
- `0x18001c85b`: `DDMServiceInitialize: Failed to load resource strings. Error %d`
- `0x18001c8ec`: `DDMServiceInitialize: Error %d while opening registry key %s.`
- `0x18001c9e4`: `DDMServiceInitialize: Error %d while opening registry key %s.`
- `0x18001c99d`: `System\CurrentControlSet\Services\RemoteAccess\Accounting`
- `0x18001c9bd`: `System\CurrentControlSet\Services\RemoteAccess\Accounting`
- `0x18001ca26`: `System\CurrentControlSet\Services\RemoteAccess\Authentication`
- `0x18001ca48`: `System\CurrentControlSet\Services\RemoteAccess\Authentication`
- `0x18001ca73`: `DDMServiceInitialize: Error %d occured while opening registry key %s.`
- `0x18001cafb`: `DDMServiceInitialize: Error %d occured while loading ddm parameters from registry `
- `0x18001cb5a`: `DDMServiceInitialize: fIpAllowed = %d, fIpv6Allowed = %d`
- `0x18001cc0c`: `DDMServiceInitialize: Error %d occured while loading third-party admin dll`
- `0x18001cc78`: `DDMServiceInitialize: Error %d occured while loading third-party security dll`
- `0x18001cce2`: `DDMServiceInitialize: Error %d occured while initializing Rasman interface`
- `0x18001cd48`: `DDMServiceInitialize: InitializDeviceTable failed. Error %d`
- `0x18001cde1`: `DDMServiceInitialize: EapHostPeerInitialize failed with error %d`
- `0x18001ce39`: `DDMServiceInitialize: failed to create DdmNotificationHandler object`
- `0x18001cf52`: `DDMServiceInitialize: Error %d occured while allocating memory for resources. #0`
- `0x18001d118`: `DDMServiceInitialize: Error %d occured while registering device events with Rasman.`
- `0x18001d1d7`: `DDMServiceInitialize: Error %d occured while loading the configured Authentication provider`
- `0x18001d2eb`: `DDMServiceInitialize: Error %d occured while loading the configured Accounting provider`
- `0x18001d3a6`: `DDMServiceInitialize: Error %d occured while initalizing Ras Server`
- `0x18001d4fe`: `DDMServiceInitialize: Error %d occured while initializating ras server.`
- `0x18001d7af`: `DDMServiceInitialize: Error %d occured while setting up the timer.`
- `0x18001d80e`: `DDMServiceInitialize: Error %d occured while loading protocol engines.`
- `0x18001da2d`: `DDMServiceInitialize: RasInterfaceMgmtInit failed.`
- `0x18001da6f`: `RemoteAccess`
- `0x18001dab5`: `DDMServiceInitialize: Error 0x%x occured while creating system event handle.`
- `0x18001dd01`: `DDMServiceInitialize: Error %d occured while initializing client protocol engine [%ws].`
- `0x18001de03`: `DDMServiceInitialize: Error %d occured while initializing server protocol engine [%ws].`
- `0x18001def7`: `DDMServiceInitialize: protocol engine [%ws] does not support this configuration. dwServerFlags: 0x%.8x`
- `0x18001dfdd`: `DDMServiceInitialize: All Engines are failed to load\n`
- `0x18001e0a2`: `DDMServiceInitialize: Error %d occured while creating worker thread.`
- `0x18001e11e`: `DDMServiceInitialize: Error %d occured while registering PnP notification handler with Rasman.`
- `0x18001e1c0`: `DDMServiceInitialize: Error %d occured while initializing address pool for IP addresses.`
- `0x18001e364`: `mprddm initialization is complete`
- `0x18001e258`: `DDMServiceInitialize: Error %d occured during mprddm initialization. Cleaning up...`

## pseudocode

```c
__int64 __fastcall DDMServiceInitialize(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  __int64 v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rax
  unsigned int inited; // eax
  unsigned int dwErrorCode; // ebx
  __int64 v9; // r8
  unsigned int v11; // eax
  HANDLE v12; // rax
  DWORD LastError; // eax
  __int64 v14; // r8
  __int64 v15; // rax
  GUID *p_ProviderId; // rax
  __int64 *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  GUID *v21; // rax
  __int64 *v22; // rdx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 *v28; // rdx
  DWORD v29; // r8d
  unsigned int v30; // eax
  unsigned int RouterPhoneBook; // eax
  unsigned int Strings; // eax
  unsigned int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int DDMParameters; // eax
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  unsigned int SecurityModule; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  __int64 v45; // rax
  DWORD v46; // eax
  __int64 v47; // r8
  __int64 v48; // rax
  unsigned __int64 v49; // rdx
  bool v50; // cf
  unsigned int v51; // r12d
  unsigned __int64 v52; // rax
  HANDLE *v53; // rdx
  DWORD v54; // eax
  __int64 v55; // rax
  unsigned int v56; // eax
  __int64 v57; // rbx
  __int64 *v58; // r15
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  HANDLE v62; // rax
  HANDLE EventW; // rax
  void (__fastcall *v64)(unsigned int); // rax
  HANDLE WaitableTimerW; // rax
  unsigned int v66; // r12d
  DdmDeviceTable *Instance; // rax
  unsigned int v68; // eax
  unsigned int v69; // eax
  __int64 v70; // r8
  __int64 v71; // rax
  unsigned int v72; // eax
  __int64 v73; // r8
  __int64 v74; // rax
  unsigned int v75; // eax
  __int64 v76; // r8
  __int64 v77; // rax
  unsigned int v78; // eax
  __int64 v79; // r8
  __int64 v80; // rax
  DWORD v81; // eax
  unsigned int ProtocolEngines; // eax
  __int64 v83; // r8
  __int64 (__fastcall *v84)(); // rax
  unsigned int v85; // eax
  DWORD v86; // eax
  wchar_t **v87; // r15
  __int64 v88; // rdx
  unsigned int v89; // eax
  __int64 v90; // rax
  unsigned int v91; // eax
  __int64 v92; // rax
  __int64 v93; // rax
  unsigned int v94; // r15d
  int *v95; // rax
  __int64 v96; // rax
  HANDLE Thread; // rax
  void *v98; // rsi
  DWORD v99; // eax
  unsigned int v100; // eax
  unsigned int v101; // eax
  __int64 v102; // r8
  __int64 v103; // r8
  DWORD ThreadId[4]; // [rsp+70h] [rbp-1818h] BYREF
  __int64 (__fastcall *v105)(); // [rsp+80h] [rbp-1808h] BYREF
  __int64 (__fastcall *v106)(int, int, int, int, __int64); // [rsp+88h] [rbp-1800h]
  __int64 (__fastcall *v107)(); // [rsp+90h] [rbp-17F8h]
  __int64 (__fastcall *v108)(); // [rsp+98h] [rbp-17F0h]
  __int64 (__fastcall *v109)(int, int, int, void *); // [rsp+A0h] [rbp-17E8h]
  __int64 (__fastcall *v110)(); // [rsp+A8h] [rbp-17E0h]
  __int64 (__fastcall *v111)(); // [rsp+B0h] [rbp-17D8h]
  __int64 (__fastcall *v112)(); // [rsp+B8h] [rbp-17D0h]
  __int64 (__fastcall *v113)(); // [rsp+C0h] [rbp-17C8h]
  __int64 (__fastcall *v114)(); // [rsp+C8h] [rbp-17C0h]
  __int64 (__fastcall *v115)(__int64, unsigned int, __int128 *, __int128 *); // [rsp+D0h] [rbp-17B8h]
  __int64 (__fastcall *v116)(); // [rsp+D8h] [rbp-17B0h]
  __int64 (__fastcall *v117)(); // [rsp+E0h] [rbp-17A8h]
  __int64 (__fastcall *v118)(); // [rsp+E8h] [rbp-17A0h]
  __int64 (__fastcall *v119)(); // [rsp+F0h] [rbp-1798h]
  __int64 (__fastcall *v120)(); // [rsp+F8h] [rbp-1790h]
  __int64 (__fastcall *v121)(HLOCAL); // [rsp+100h] [rbp-1788h]
  __int64 (__fastcall *v122)(); // [rsp+108h] [rbp-1780h]
  __int64 (__fastcall *v123)(); // [rsp+110h] [rbp-1778h]
  __int64 (__fastcall *v124)(); // [rsp+118h] [rbp-1770h]
  __int64 (__fastcall *v125)(); // [rsp+120h] [rbp-1768h]
  __int64 (__fastcall *v126)(); // [rsp+128h] [rbp-1760h]
  __int64 (__fastcall *v127)(); // [rsp+130h] [rbp-1758h]
  __int64 (__fastcall *v128)(); // [rsp+138h] [rbp-1750h]
  __int64 (__fastcall *v129)(); // [rsp+140h] [rbp-1748h]
  __int64 (__fastcall *v130)(); // [rsp+148h] [rbp-1740h]
  __int64 (__fastcall *v131)(); // [rsp+150h] [rbp-1738h]
  __int64 (__fastcall *v132)(); // [rsp+158h] [rbp-1730h]
  __int128 v133; // [rsp+160h] [rbp-1728h] BYREF
  __int128 v134; // [rsp+170h] [rbp-1718h] BYREF
  __int128 v135; // [rsp+180h] [rbp-1708h] BYREF
  unsigned int (*v136)(void); // [rsp+190h] [rbp-16F8h]
  _DWORD v137[920]; // [rsp+1A0h] [rbp-16E8h] BYREF
  _BYTE v138[16]; // [rsp+1000h] [rbp-888h] BYREF
  const wchar_t *v139; // [rsp+1010h] [rbp-878h]
  int v140; // [rsp+1018h] [rbp-870h]
  int v141; // [rsp+101Ch] [rbp-86Ch]
  GUID ProviderId; // [rsp+1020h] [rbp-868h] BYREF
  const wchar_t *v143; // [rsp+1030h] [rbp-858h]
  int v144; // [rsp+1038h] [rbp-850h]
  int v145; // [rsp+103Ch] [rbp-84Ch]
  int v146; // [rsp+1040h] [rbp-848h] BYREF
  char v147[2044]; // [rsp+1044h] [rbp-844h] BYREF

  ThreadId[0] = 0;
  v133 = 0;
  v134 = 0;
  v135 = 0;
  v136 = 0;
  memset_0(&v105, 0, 0xE0u);
  v146 = 0;
  memset_0(v147, 0, sizeof(v147));
  memset_0(&gblDDMConfigInfo, 0, 0x1F8u);
  g_pIDimInterfaceTable = *(_QWORD *)a1;
  qword_1800CF4F8 = *(_QWORD *)(a1 + 8);
  dword_1800CF500 = *(_DWORD *)(a1 + 40);
  hLogHandle = *(HANDLE *)(a1 + 48);
  gblphEventDDMServiceState = *(_QWORD *)(a1 + 16);
  gblphEventDDMTerminated = *(_QWORD *)(a1 + 24);
  qword_1800CF558 = *(_QWORD *)(a1 + 32);
  qword_1800CF570 = *(_QWORD *)(a1 + 64);
  qword_1800CF698 = *(_QWORD *)(a1 + 72);
  qword_1800CF6A0 = *(_QWORD *)(a1 + 80);
  qword_1800CF6A8 = *(_QWORD *)(a1 + 88);
  qword_1800CF6B0 = *(_QWORD *)(a1 + 96);
  dword_1800CF648 = 0;
  dword_1800CF64C = *(_DWORD *)(a1 + 56);
  g_dhcpIpFailureEventRaised = 0;
  g_portExhaustedEventRaised = 0;
  *(_DWORD *)(a1 + 104) = 0;
  v3 = *(_QWORD *)(a1 + 128);
  if ( v3 )
  {
    qword_1800CF688 = *(_QWORD *)(v3 + 40);
    qword_1800CF690 = *(_QWORD *)(*(_QWORD *)(a1 + 128) + 56LL);
  }
  dword_1800CF650 = *(_DWORD *)(a1 + 108);
  dword_1800CF654 = *(_DWORD *)(a1 + 112);
  if ( (int)McGenEventRegister_EventRegister(
              MICROSOFT_WINDOWS_RRAS_PROVIDER,
              v2,
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context) >= 0 )
  {
    SetLibParams();
    SetLibParamsWithBuffer();
  }
  ProviderId = (GUID)*((_OWORD *)off_1800CE728 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_1800CE748 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_1800CE720, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_1800CE728, (unsigned __int16)*off_1800CE728);
  v5 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( aMprddmInitiali[v6] );
    v143 = L"mprddm initialization is starting...";
    v144 = 2 * v6 + 2;
    v145 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v4, 2, &ProviderId);
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800D07D0 + 1));
  InitializeCriticalSection(&gblDeviceTable);
  InitializeCriticalSection(&stru_1800CF740);
  InitializeCriticalSection(&stru_1800CF5A8);
  inited = InitGlobalThreadPool();
  dwErrorCode = inited;
  if ( inited )
  {
    if ( (byte_1800CF404 & 8) == 0 )
      return dwErrorCode;
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: InitGlobalThreadPool failed with error %d", inited);
    if ( (byte_1800CF404 & 8) == 0 )
      return dwErrorCode;
    do
      ++v5;
    while ( *(_WORD *)&v147[2 * v5 - 4] );
    v143 = (const wchar_t *)&v146;
LABEL_18:
    v144 = 2 * v5 + 2;
    v145 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v9, 2, &ProviderId);
    return dwErrorCode;
  }
  v11 = InitSerializedThreadPool();
  dwErrorCode = v11;
  if ( v11 )
  {
    if ( (byte_1800CF404 & 8) == 0 )
      return dwErrorCode;
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: InitSerializedThreadPool failed with error %d", v11);
    if ( (byte_1800CF404 & 8) == 0 )
      return dwErrorCode;
    do
      ++v5;
    while ( *(_WORD *)&v147[2 * v5 - 4] );
    v143 = (const wchar_t *)&v146;
    goto LABEL_18;
  }
  v12 = HeapCreate(0, 0, 0);
  hHeap = v12;
  if ( !v12 )
  {
    LastError = GetLastError();
    dwErrorCode = LastError;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Heap creation failed with error %d", LastError);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v147[2 * v15 - 4] );
LABEL_30:
        v143 = (const wchar_t *)&v146;
        v144 = 2 * v15 + 2;
        v145 = 0;
        p_ProviderId = &ProviderId;
LABEL_31:
        v17 = RasDdmTraceError;
LABEL_317:
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v17, v14, 2, p_ProviderId);
        goto LABEL_318;
      }
    }
    goto LABEL_318;
  }
  DWORD1(gblMediaTable) = 5;
  *((_QWORD *)&gblMediaTable + 1) = HeapAlloc(v12, 8u, 0xC8u);
  if ( *((_QWORD *)&gblMediaTable + 1) )
    dwErrorCode = 0;
  else
    dwErrorCode = GetLastError();
  if ( dwErrorCode )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Media object  creation failed with error %d", dwErrorCode);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)&v147[2 * v20 - 4] );
        v143 = (const wchar_t *)&v146;
        v144 = 2 * v20 + 2;
        v145 = 0;
        v21 = &ProviderId;
        v22 = RasDdmTraceError;
LABEL_41:
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v22, v19, 2, v21);
        goto LABEL_42;
      }
    }
    goto LABEL_42;
  }
  McGenEventRegister_EventRegister(MPRDDM_EVENT_SOURCE, v18, MPRDDM_EVENT_SOURCE_Context, MPRDDM_EVENT_SOURCE_Context);
  dword_1800CF4E0 |= 0x10u;
  InitializeSRWLock(&SRWLock);
  if ( !*(_DWORD *)(a1 + 112) )
  {
    v25 = RasInitialize();
    dwErrorCode = v25;
    if ( v25 )
    {
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_64;
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Rasman initialization failed with error %d", v25);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_64;
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)&v147[2 * v27 - 4] );
      v28 = RasDdmTraceError;
    }
    else
    {
      v30 = RasReferenceRasman(1);
      dwErrorCode = v30;
      if ( !v30 )
      {
        dword_1800CF648 = 1;
        goto LABEL_74;
      }
      if ( (byte_1800CF404 & 0x10) == 0
        || (LOWORD(v146) = 0,
            FormatRRASErrorString(
              &v146,
              L"DDMServiceInitialize: Rasman's reference count could not be incremented. Error %d",
              v30),
            (byte_1800CF404 & 0x10) == 0) )
      {
LABEL_64:
        if ( !dword_1800CF4E4 )
          goto LABEL_318;
        v29 = 20054;
LABEL_66:
        RouterLogEventStringW(hLogHandle, 1u, v29, 0, 0, dwErrorCode, 0);
        goto LABEL_318;
      }
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)&v147[2 * v27 - 4] );
      v28 = RasDdmTraceInfo;
    }
    v144 = 2 * v27 + 2;
    v145 = 0;
    v143 = (const wchar_t *)&v146;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v28, v26, 2, &ProviderId);
    goto LABEL_64;
  }
  v23 = SetupSstpServerConfig();
  dwErrorCode = v23;
  if ( v23 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: SetupSstpServerConfig failed. Error %d", v23);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v147[2 * v15 - 4] );
        goto LABEL_30;
      }
    }
LABEL_318:
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured during mprddm initialization. Cleaning up...",
        dwErrorCode);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        do
          ++v5;
        while ( *(_WORD *)&v147[2 * v5 - 4] );
        v139 = (const wchar_t *)&v146;
        v140 = 2 * v5 + 2;
        v141 = 0;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v102, 2, v138);
      }
    }
    goto LABEL_322;
  }
  v24 = InitDdmDriverHelper(*(_DWORD *)(a1 + 120));
  dwErrorCode = v24;
  if ( v24 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: WanDriver initialization failed with error %d", v24);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v147[2 * v15 - 4] );
        goto LABEL_30;
      }
    }
    goto LABEL_318;
  }
LABEL_74:
  RouterPhoneBook = GetRouterPhoneBook();
  dwErrorCode = RouterPhoneBook;
  if ( RouterPhoneBook )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Failed to get the router phone book. Error %d",
        RouterPhoneBook);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v147[2 * v15 - 4] );
        goto LABEL_30;
      }
    }
    goto LABEL_318;
  }
  Strings = LoadStrings();
  dwErrorCode = Strings;
  if ( Strings )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Failed to load resource strings. Error %d", Strings);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v147[2 * v15 - 4] );
        goto LABEL_30;
      }
    }
    goto LABEL_318;
  }
  v33 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", &hKey);
  dwErrorCode = v33;
  if ( v33 )
  {
    *(_QWORD *)&ProviderId.Data1 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters";
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d while opening registry key %s.", v33);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)&v147[2 * v35 - 4] );
LABEL_91:
        v139 = (const wchar_t *)&v146;
        v140 = 2 * v35 + 2;
        v141 = 0;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v34, 2, v138);
        goto LABEL_92;
      }
    }
    goto LABEL_92;
  }
  v36 = RegOpenKeyW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Accounting",
          &qword_1800CF548);
  dwErrorCode = v36;
  if ( v36 )
  {
    *(_QWORD *)&ProviderId.Data1 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Accounting";
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d while opening registry key %s.", v36);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)&v147[2 * v35 - 4] );
        goto LABEL_91;
      }
    }
LABEL_92:
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, (LPWSTR *)&ProviderId, dwErrorCode);
    goto LABEL_318;
  }
  v37 = RegOpenKeyW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Authentication",
          &qword_1800CF550);
  dwErrorCode = v37;
  if ( v37 )
  {
    *(_QWORD *)&ProviderId.Data1 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Authentication";
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d occured while opening registry key %s.", v37);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)&v147[2 * v35 - 4] );
        goto LABEL_91;
      }
    }
    goto LABEL_92;
  }
  DDMParameters = LoadDDMParameters(hKey);
  dwErrorCode = DDMParameters;
  if ( DDMParameters )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while loading ddm parameters from registry ",
        DDMParameters);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)&v147[2 * v39 - 4] );
LABEL_111:
        v17 = RasDdmTraceInfo;
LABEL_316:
        v140 = 2 * v39 + 2;
        v139 = (const wchar_t *)&v146;
        v141 = 0;
        p_ProviderId = (GUID *)v138;
        goto LABEL_317;
      }
    }
    goto LABEL_322;
  }
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: fIpAllowed = %d, fIpv6Allowed = %d", 0, 0);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v41 = -1;
      do
        ++v41;
      while ( *(_WORD *)&v147[2 * v41 - 4] );
      v139 = (const wchar_t *)&v146;
      v140 = 2 * v41 + 2;
      v141 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v40, 2, v138);
    }
  }
  if ( dword_1800CF4EC < 0 )
    *(_DWORD *)(a1 + 116) = 1;
  dwErrorCode = LoadAdminModule();
  if ( dwErrorCode )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while loading third-party admin dll",
        dwErrorCode);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)&v147[2 * v39 - 4] );
        goto LABEL_111;
      }
    }
LABEL_322:
    DDMCleanUp();
    if ( dwErrorCode )
      DDMPostCleanup();
    if ( gblphEventDDMTerminated )
      SetEvent(*(HANDLE *)gblphEventDDMTerminated);
    gblphEventDDMTerminated = 0;
    return dwErrorCode;
  }
  if ( *(_DWORD *)(a1 + 112) )
  {
    v44 = InitializDeviceTable();
    dwErrorCode = v44;
    if ( v44 )
    {
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_318;
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: InitializDeviceTable failed. Error %d", v44);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_318;
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)&v147[2 * v45 - 4] );
    }
    else
    {
      InitializeRasIpsec();
      v46 = EapHostPeerInitialize();
      dwErrorCode = v46;
      if ( !v46 )
      {
        dword_1800CF668 = 1;
        goto LABEL_151;
      }
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_318;
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: EapHostPeerInitialize failed with error %d", v46);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_318;
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)&v147[2 * v45 - 4] );
    }
LABEL_143:
    v139 = (const wchar_t *)&v146;
    v140 = 2 * v45 + 2;
    v141 = 0;
    p_ProviderId = (GUID *)v138;
    goto LABEL_31;
  }
  SecurityModule = LoadSecurityModule();
  dwErrorCode = SecurityModule;
  if ( SecurityModule )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while loading third-party security dll",
        SecurityModule);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)&v147[2 * v39 - 4] );
        goto LABEL_111;
      }
    }
    goto LABEL_322;
  }
  v43 = RmInit((int *)(a1 + 104));
  dwErrorCode = v43;
  if ( v43 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d occured while initializing Rasman interface", v43);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)&v147[2 * v39 - 4] );
        goto LABEL_111;
      }
    }
    goto LABEL_322;
  }
LABEL_151:
  if ( !DdmNotificationHandler::GetInstance() )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v48 = -1;
      do
        ++v48;
      while ( aDdmserviceinit_10[v48] );
      v139 = L"DDMServiceInitialize: failed to create DdmNotificationHandler object";
      v140 = 2 * v48 + 2;
      v141 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v47, 2, v138);
    }
    dwErrorCode = 8;
    goto LABEL_318;
  }
  v49 = 3LL * *(unsigned int *)DdmDeviceTable::GetInstance(0x11u);
  if ( v49 > 0xFFFFFFFF )
  {
    dwErrorCode = v49 > 0xFFFFFFFF ? 0x216 : 0;
    goto LABEL_318;
  }
  v50 = (int)v49 + 6 < (unsigned int)v49;
  if ( (int)v49 + 6 < (unsigned int)v49 )
  {
LABEL_161:
    dwErrorCode = v50 ? 0x216 : 0;
    goto LABEL_318;
  }
  v51 = v49 + 6;
  v52 = 8LL * (unsigned int)(v49 + 6);
  if ( v52 > 0xFFFFFFFF )
  {
    v50 = 1;
    goto LABEL_161;
  }
  v53 = (HANDLE *)HeapAlloc(hHeap, 8u, (unsigned int)v52);
  gblSupervisorEvents = v53;
  if ( !v53 )
  {
    v54 = GetLastError();
    dwErrorCode = v54;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while allocating memory for resources. #0",
        v54);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v55 = -1;
        do
          ++v55;
        while ( *(_WORD *)&v147[2 * v55 - 4] );
        v139 = (const wchar_t *)&v146;
        v140 = 2 * v55 + 2;
        v141 = 0;
        v21 = (GUID *)v138;
        v22 = RasDdmTraceInfo;
        goto LABEL_41;
      }
    }
LABEL_42:
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, dwErrorCode);
    goto LABEL_318;
  }
  v56 = 0;
  ProviderId.Data1 = 0;
  if ( v51 )
  {
    v57 = 0;
    v58 = qword_1800CF6C8;
    do
    {
      if ( !v56 )
      {
        v53[v57] = *(HANDLE *)gblphEventDDMServiceState;
        v64 = SvcEventHandler;
        goto LABEL_182;
      }
      v59 = v56 - 1;
      if ( v59 )
      {
        v60 = v59 - 1;
        if ( !v60 )
        {
          WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
          v53 = gblSupervisorEvents;
          gblSupervisorEvents[v57] = WaitableTimerW;
          v64 = TimerHandler;
          goto LABEL_182;
        }
        v61 = v60 - 1;
        if ( !v61 || v61 - 1 < 2 )
        {
          EventW = CreateEventW(0, 0, 0, 0);
          v53 = gblSupervisorEvents;
          gblSupervisorEvents[v57] = EventW;
          v64 = ChangeNotificationEventHandler;
LABEL_182:
          *v58 = (__int64)v64;
          goto LABEL_183;
        }
        v62 = CreateEventW(0, 0, 0, 0);
        v53 = gblSupervisorEvents;
        gblSupervisorEvents[v57] = v62;
      }
      else
      {
        v53[v57] = *(HANDLE *)gblphEventDDMTerminated;
      }
LABEL_183:
      v56 = ProviderId.Data1 + 1;
      ProviderId.Data1 = v56;
      ++v57;
      v58 += 2;
    }
    while ( v56 < v51 );
  }
  v66 = 0;
  if ( !*(_DWORD *)(a1 + 112) )
  {
    *(_QWORD *)&ProviderId.Data1 = &DeviceRequestNotification::`vftable';
    Instance = DdmDeviceTable::GetInstance(0x11u);
    v68 = DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&ProviderId, 1, 0);
    dwErrorCode = v68;
    if ( v68 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_322;
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while registering device events with Rasman.",
        v68);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_322;
      v39 = -1;
      do
        ++v39;
      while ( *(_WORD *)&v147[2 * v39 - 4] );
LABEL_315:
      v17 = RasDdmTraceInfo;
      goto LABEL_316;
    }
  }
  v69 = LoadAndInitAuthOrAcctProvider(
          1,
          0,
          0,
          (unsigned int)&v133,
          (__int64)&v133 + 8,
          (__int64)&qword_1800CF5A0,
          0,
          0,
          0,
          0,
          0);
  dwErrorCode = v69;
  if ( v69 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while loading the configured Authentication provider",
        v69);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v71 = -1;
        do
          ++v71;
        while ( *(_WORD *)&v147[2 * v71 - 4] );
        v139 = (const wchar_t *)&v146;
        v140 = 2 * v71 + 2;
        v141 = 0;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v70, 2, v138);
      }
    }
    if ( !dword_1800CF4E4 )
      goto LABEL_318;
    v29 = 20152;
    goto LABEL_66;
  }
  v72 = LoadAndInitAuthOrAcctProvider(
          0,
          0,
          (unsigned int)&Data,
          0,
          0,
          0,
          (__int64)&v134,
          (__int64)&v134 + 8,
          (__int64)&v135,
          (__int64)&v135 + 8,
          (__int64)&qword_1800CF598);
  dwErrorCode = v72;
  if ( v72 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while loading the configured Accounting provider",
        v72);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v74 = -1;
        do
          ++v74;
        while ( *(_WORD *)&v147[2 * v74 - 4] );
        v139 = (const wchar_t *)&v146;
        v140 = 2 * v74 + 2;
        v141 = 0;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v73, 2, v138);
      }
    }
    if ( !dword_1800CF4E4 )
      goto LABEL_318;
    v29 = 20153;
    goto LABEL_66;
  }
  v75 = RasSrvrInitialize();
  dwErrorCode = v75;
  if ( v75 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d occured while initalizing Ras Server", v75);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v77 = -1;
        do
          ++v77;
        while ( *(_WORD *)&v147[2 * v77 - 4] );
        v139 = (const wchar_t *)&v146;
        v140 = 2 * v77 + 2;
        v141 = 0;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v76, 2, v138);
      }
    }
    if ( !dword_1800CF4E4 )
      goto LABEL_318;
    v29 = 20145;
    goto LABEL_66;
  }
  v78 = RasSrvrInitializeIpAddrMgmtFunctions();
  dwErrorCode = v78;
  if ( v78 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v146) = 0;
      FormatRRASErrorString(&v146, L"RasSrvrInitializeIpAddrMgmtFunctions failed with return code %d", v78);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v80 = -1;
        do
          ++v80;
        while ( *(_WORD *)&v147[2 * v80 - 4] );
        v140 = 2 * v80 + 2;
        v141 = 0;
        v139 = (const wchar_t *)&v146;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v79, 2, v138);
      }
    }
    if ( !dword_1800CF4E4 )
      goto LABEL_318;
    v29 = 20145;
    goto LABEL_66;
  }
  *(_QWORD *)&ProviderId.Data1 = -10000000;
  if ( !SetWaitableTimer(gblSupervisorEvents[2], (const LARGE_INTEGER *)&ProviderId, 1000, 0, 0, 0) )
  {
    v81 = GetLastError();
    dwErrorCode = v81;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d occured while setting up the timer.", v81);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)&v147[2 * v39 - 4] );
    goto LABEL_315;
  }
  ProtocolEngines = LoadProtocolEngines();
  dwErrorCode = ProtocolEngines;
  if ( ProtocolEngines )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    LOWORD(v146) = 0;
    FormatRRASErrorString(
      &v146,
      L"DDMServiceInitialize: Error %d occured while loading protocol engines.",
      ProtocolEngines);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)&v147[2 * v39 - 4] );
    goto LABEL_315;
  }
  v136 = GetNextAccountingSessionId;
  v105 = DDMRouterTypeLookupForRoutingDomain;
  if ( !*(_DWORD *)(a1 + 112) )
  {
    v106 = (__int64 (__fastcall *)(int, int, int, int, __int64))RasDeviceGetInfo;
    v107 = (__int64 (__fastcall *)())RasPortGetStatistics;
    v108 = (__int64 (__fastcall *)())RasAllocateRoute;
    v109 = (__int64 (__fastcall *)(int, int, int, void *))RasGetKey;
    v110 = (__int64 (__fastcall *)())RasGetPortUserData;
    v111 = (__int64 (__fastcall *)())RasPortGetBundle;
    v112 = (__int64 (__fastcall *)())RasSetConnectionUserData;
    v113 = (__int64 (__fastcall *)())RasProtocolStarted;
    v114 = (__int64 (__fastcall *)())RasGetTimeSinceLastActivity;
    v115 = (__int64 (__fastcall *)(__int64, unsigned int, __int128 *, __int128 *))RasSetTunnelEndPoints;
    v116 = (__int64 (__fastcall *)())RasSendProtocolResultToRasman;
    v117 = (__int64 (__fastcall *)())RasDeAllocateRoute;
    v118 = (__int64 (__fastcall *)())RasActivateRoute;
    v119 = (__int64 (__fastcall *)())RasUpdateDefaultRouteSettings;
    v120 = (__int64 (__fastcall *)())RasPortCancelReceive;
    v121 = (__int64 (__fastcall *)(HLOCAL))RasFreeBuffer;
    v122 = (__int64 (__fastcall *)())RasPortSend;
    v123 = (__int64 (__fastcall *)())RasGetConnectInfo;
    v124 = (__int64 (__fastcall *)())RasGetInfo;
    v125 = (__int64 (__fastcall *)())RasBundleGetPort;
    v126 = (__int64 (__fastcall *)())RasGetFramingCapabilities;
    v127 = (__int64 (__fastcall *)())RasPortSetFramingEx;
    v128 = (__int64 (__fastcall *)())RasCompressionSetInfo;
    v129 = (__int64 (__fastcall *)())RasCompressionGetInfo;
    v130 = (__int64 (__fastcall *)())RasPortGetProtocolCompression;
    v131 = (__int64 (__fastcall *)())RasGetBuffer;
    v84 = (__int64 (__fastcall *)())RasPortSetProtocolCompression;
    goto LABEL_251;
  }
  v85 = RasInterfaceMgmtInit((unsigned int)dword_1800CF500);
  dwErrorCode = v85;
  if ( v85 )
  {
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_318;
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: RasInterfaceMgmtInit failed.", v85);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_318;
    v45 = -1;
    do
      ++v45;
    while ( *(_WORD *)&v147[2 * v45 - 4] );
    goto LABEL_143;
  }
  dword_1800CF4E0 |= 0x20u;
  qword_1800CF660 = (__int64)RouterLogRegisterW(L"RemoteAccess");
  if ( !qword_1800CF660 )
  {
    v86 = GetLastError();
    dwErrorCode = v86;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error 0x%x occured while creating system event handle.", v86);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)&v147[2 * v39 - 4] );
    goto LABEL_315;
  }
  v106 = DdmDeviceGetInfo;
  v107 = DdmPortGetStatistics;
  v108 = DdmAllocateRoute;
  v109 = DdmGetKey;
  v110 = DdmGetPortUserData;
  v111 = DdmPortGetBundle;
  v112 = DdmSetConnectionUserData;
  v113 = DdmProtocolStarted;
  v114 = DdmGetTimeSinceLastActivity;
  v115 = DdmSetTunnelEndPoints;
  v116 = DdmSendProtocolResultToDdm;
  v117 = DdmDeAllocateRoute;
  v118 = DdmActivateRoute;
  v119 = DdmUpdateDefaultRouteSettings;
  v120 = DdmPortCancelReceive;
  v121 = DdmFreeBuffer;
  v122 = DdmPortSend;
  v123 = DdmGetConnectInfo;
  v124 = DdmGetInfo;
  v125 = DdmBundleGetPort;
  v126 = DdmGetFramingCapabilities;
  v127 = DdmPortSetFramingEx;
  v128 = DdmCompressionSetInfo;
  v129 = DdmCompressionGetInfo;
  v130 = DdmPortGetProtocolCompression;
  v131 = DdmGetBuffer;
  v84 = DdmPortSetProtocolCompression;
LABEL_251:
  v132 = v84;
  v87 = off_1800CE488;
  do
  {
    if ( !*((_DWORD *)v87 + 4) )
    {
      if ( *(_DWORD *)(a1 + 112)
        && (v66
          ? (v66 != 1
           ? (v88 = (unsigned int)dword_1800D05FC)
           : (v88 = (unsigned int)dword_1800D04C4))
          : (v88 = (unsigned int)dword_1800D038C),
            v89 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))v87[4])(qword_1800CF660, v88, 0),
            (dwErrorCode = v89) != 0) )
      {
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v146) = 0;
          FormatRRASErrorString(
            &v146,
            L"DDMServiceInitialize: Error %d occured while initializing client protocol engine [%ws].",
            v89,
            *v87);
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            v90 = -1;
            do
              ++v90;
            while ( *(_WORD *)&v147[2 * v90 - 4] );
            v139 = (const wchar_t *)&v146;
            v140 = 2 * v90 + 2;
            v141 = 0;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v83, 2, v138);
          }
        }
      }
      else
      {
        v91 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(_QWORD), _QWORD, _QWORD, _QWORD, int, __int128 *, void *, __int64 (__fastcall **)()))v87[6])(
                SendProtocolMessageToDDM,
                (unsigned int)dword_1800CF4EC,
                (unsigned int)dword_1800CF4E4,
                0,
                dword_1800CF4E0 & 1,
                &v133,
                &g_IPAddressMgmtFunctions,
                &v105);
        dwErrorCode = v91;
        if ( v91 )
        {
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            LOWORD(v146) = 0;
            FormatRRASErrorString(
              &v146,
              L"DDMServiceInitialize: Error %d occured while initializing server protocol engine [%ws].",
              v91,
              *v87);
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              v92 = -1;
              do
                ++v92;
              while ( *(_WORD *)&v147[2 * v92 - 4] );
              v139 = (const wchar_t *)&v146;
              v140 = 2 * v92 + 2;
              v141 = 0;
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceInfo,
                v83,
                2,
                v138);
            }
          }
          if ( dword_1800CF4E4 )
            RouterLogEventStringW(hLogHandle, 1u, 0x4E5Fu, 1u, &off_1800CE488[10 * v66], dwErrorCode, 0);
          if ( dwErrorCode == 50 )
          {
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              LOWORD(v146) = 0;
              FormatRRASErrorString(
                &v146,
                L"DDMServiceInitialize: protocol engine [%ws] does not support this configuration. dwServerFlags: 0x%.8x",
                *v87,
                (unsigned int)dword_1800CF4EC);
              if ( (byte_1800CF404 & 0x10) != 0 )
              {
                v93 = -1;
                do
                  ++v93;
                while ( *(_WORD *)&v147[2 * v93 - 4] );
                v139 = (const wchar_t *)&v146;
                v140 = 2 * v93 + 2;
                v141 = 0;
                McGenEventWrite_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasDdmTraceInfo,
                  v83,
                  2,
                  v138);
              }
            }
            dwErrorCode = 0;
          }
          if ( *(_DWORD *)(a1 + 112) )
            ((void (__fastcall *)(_QWORD, _QWORD))v87[5])(0, 0);
          *((_DWORD *)v87 + 5) = 0;
        }
        else
        {
          *((_DWORD *)v87 + 5) = 1;
        }
      }
    }
    ++v66;
    v87 += 10;
  }
  while ( v66 < 3 );
  v94 = 0;
  v95 = &dword_1800CE49C;
  while ( *v95 != 1 )
  {
    ++v94;
    v95 += 20;
    if ( v94 >= 3 )
      goto LABEL_290;
  }
  DdmSetProtocolEvent();
LABEL_290:
  if ( v94 == 3 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v96 = -1;
      do
        ++v96;
      while ( aDdmserviceinit_0[v96] );
      v139 = L"DDMServiceInitialize: All Engines are failed to load\n";
      v140 = 2 * v96 + 2;
      v141 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v83, 2, v138);
    }
    if ( !dword_1800CF4E4 )
      goto LABEL_318;
    v29 = 20064;
    goto LABEL_66;
  }
  Thread = CreateThread(0, 0, EventDispatcher, 0, 0, ThreadId);
  v98 = Thread;
  if ( !Thread )
  {
    v99 = GetLastError();
    dwErrorCode = v99;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    LOWORD(v146) = 0;
    FormatRRASErrorString(&v146, L"DDMServiceInitialize: Error %d occured while creating worker thread.", v99);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)&v147[2 * v39 - 4] );
    goto LABEL_315;
  }
  if ( !*(_DWORD *)(a1 + 112) )
  {
    v100 = RasRegisterPnPHandler(DdmDevicePnpHandler, Thread, 1);
    dwErrorCode = v100;
    if ( v100 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_322;
      LOWORD(v146) = 0;
      FormatRRASErrorString(
        &v146,
        L"DDMServiceInitialize: Error %d occured while registering PnP notification handler with Rasman.",
        v100);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_322;
      v39 = -1;
      do
        ++v39;
      while ( *(_WORD *)&v147[2 * v39 - 4] );
      goto LABEL_315;
    }
  }
  CloseHandle(v98);
  qword_1800CF5F8 = (__int64)&lpMem;
  lpMem = &lpMem;
  InitializeCriticalSection(&stru_1800CF600);
  dword_1800CF4E0 |= 0x80u;
  v101 = AddressPoolInit();
  dwErrorCode = v101;
  if ( v101 )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    LOWORD(v146) = 0;
    FormatRRASErrorString(
      &v146,
      L"DDMServiceInitialize: Error %d occured while initializing address pool for IP addresses.",
      v101);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_322;
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)&v147[2 * v39 - 4] );
    goto LABEL_315;
  }
  dword_1800CF628 = 0;
  if ( !*(_DWORD *)(a1 + 112) )
  {
    memset_0(v137, 0, sizeof(v137));
    v137[0] = 0x20000;
    v137[2] = 0;
    v137[3] = 2;
    RasSendNotification(v137);
  }
  DDMInitializePerformanceCounters();
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    do
      ++v5;
    while ( aMprddmInitiali_0[v5] );
    v139 = L"mprddm initialization is complete";
    v140 = 2 * v5 + 2;
    v141 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v103, 2, v138);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bf40  mov     [rsp+arg_8], rbx
0x18001bf45  mov     [rsp+arg_10], rsi
0x18001bf4a  push    rdi
0x18001bf4b  push    r12
0x18001bf4d  push    r13
0x18001bf4f  push    r14
0x18001bf51  push    r15
0x18001bf53  mov     eax, 1860h
0x18001bf58  call    _alloca_probe
0x18001bf5d  sub     rsp, rax
0x18001bf60  movaps  [rsp+1888h+var_38], xmm6
0x18001bf68  mov     rax, cs:__security_cookie
0x18001bf6f  xor     rax, rsp
0x18001bf72  mov     [rsp+1888h+var_48], rax
0x18001bf7a  mov     r13, rcx
0x18001bf7d  xor     esi, esi
0x18001bf7f  mov     [rsp+1888h+ThreadId], esi
0x18001bf83  mov     [rsp+1888h+var_1824], esi
0x18001bf87  mov     [rsp+1888h+var_1820], esi
0x18001bf8b  xorps   xmm0, xmm0
0x18001bf8e  xor     eax, eax
0x18001bf90  movups  [rsp+1888h+var_1728], xmm0
0x18001bf98  movups  [rsp+1888h+var_1718], xmm0
0x18001bfa0  movups  [rsp+1888h+var_1708], xmm0
0x18001bfa8  mov     [rsp+1888h+var_16F8], rax
0x18001bfb0  xor     edx, edx; Val
0x18001bfb2  mov     r8d, 0E0h; Size
0x18001bfb8  lea     rcx, [rsp+1888h+var_1808]; void *
0x18001bfc0  call    memset_0
0x18001bfc5  mov     [rsp+1888h+var_181C], esi
0x18001bfc9  mov     [rsp+1888h+var_1828], esi
0x18001bfcd  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18001bfd4  mov     [rsp+1888h+var_848], esi
0x18001bfdb  xor     edx, edx; Val
0x18001bfdd  mov     r8d, 7FCh; Size
0x18001bfe3  lea     rcx, [rsp+1888h+var_844]; void *
0x18001bfeb  call    memset_0
0x18001bff0  xor     edx, edx; Val
0x18001bff2  mov     r8d, 1F8h; Size
0x18001bff8  lea     rcx, gblDDMConfigInfo; void *
0x18001bfff  call    memset_0
0x18001c004  mov     rax, [r13+0]
0x18001c008  mov     cs:g_pIDimInterfaceTable, rax
0x18001c00f  mov     rax, [r13+8]
0x18001c013  mov     cs:qword_1800CF4F8, rax
0x18001c01a  mov     eax, [r13+28h]
0x18001c01e  mov     cs:dword_1800CF500, eax
0x18001c024  mov     rax, [r13+30h]
0x18001c028  mov     cs:hLogHandle, rax
0x18001c02f  mov     rax, [r13+10h]
0x18001c033  mov     cs:gblphEventDDMServiceState, rax
0x18001c03a  mov     rax, [r13+18h]
0x18001c03e  mov     cs:gblphEventDDMTerminated, rax
0x18001c045  mov     rax, [r13+20h]
0x18001c049  mov     cs:qword_1800CF558, rax
0x18001c050  mov     rax, [r13+40h]
0x18001c054  mov     cs:qword_1800CF570, rax
0x18001c05b  mov     rax, [r13+48h]
0x18001c05f  mov     cs:qword_1800CF698, rax
0x18001c066  mov     rax, [r13+50h]
0x18001c06a  mov     cs:qword_1800CF6A0, rax
0x18001c071  mov     rax, [r13+58h]
0x18001c075  mov     cs:qword_1800CF6A8, rax
0x18001c07c  mov     rax, [r13+60h]
0x18001c080  mov     cs:qword_1800CF6B0, rax
0x18001c087  mov     cs:dword_1800CF648, esi
0x18001c08d  mov     eax, [r13+38h]
0x18001c091  mov     cs:dword_1800CF64C, eax
0x18001c097  mov     cs:g_dhcpIpFailureEventRaised, esi
0x18001c09d  mov     cs:g_portExhaustedEventRaised, esi
0x18001c0a3  mov     [r13+68h], esi
0x18001c0a7  mov     rax, [r13+80h]
0x18001c0ae  test    rax, rax
0x18001c0b1  jz      short loc_18001C0D0
0x18001c0b3  mov     rax, [rax+28h]
0x18001c0b7  mov     cs:qword_1800CF688, rax
0x18001c0be  mov     rax, [r13+80h]
0x18001c0c5  mov     rcx, [rax+38h]
0x18001c0c9  mov     cs:qword_1800CF690, rcx
0x18001c0d0  mov     eax, [r13+6Ch]
0x18001c0d4  mov     cs:dword_1800CF650, eax
0x18001c0da  mov     eax, [r13+70h]
0x18001c0de  mov     cs:dword_1800CF654, eax
0x18001c0e4  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c0eb  mov     r9, rbx
0x18001c0ee  mov     r8, rbx
0x18001c0f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER
0x18001c0f8  call    McGenEventRegister_EventRegister
0x18001c0fd  test    eax, eax
0x18001c0ff  js      short loc_18001C10B
0x18001c101  call    ?SetLibParams@@YAXXZ; SetLibParams(void)
0x18001c106  call    ?SetLibParamsWithBuffer@@YAXXZ; SetLibParamsWithBuffer(void)
0x18001c10b  mov     rax, cs:off_1800CE728
0x18001c112  movups  xmm0, xmmword ptr [rax-10h]
0x18001c116  movdqu  xmmword ptr [rsp+1888h+ProviderId.Data1], xmm0
0x18001c11f  cmp     cs:RegHandle, rsi
0x18001c126  jz      short loc_18001C12F
0x18001c128  mov     ecx, 5
0x18001c12d  int     29h; Win8: RtlFailFast(ecx)
0x18001c12f  xorps   xmm0, xmm0
0x18001c132  movdqu  cs:xmmword_1800CE748, xmm0
0x18001c13a  lea     r9, RegHandle; RegHandle
0x18001c141  lea     r8, dword_1800CE720; CallbackContext
0x18001c148  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001c14f  lea     rcx, [rsp+1888h+ProviderId]; ProviderId
0x18001c157  call    cs:__imp_EventRegister
0x18001c15e  nop     dword ptr [rax+rax+00h]
0x18001c163  mov     r14d, 2
0x18001c169  test    eax, eax
0x18001c16b  jnz     short loc_18001C18E
0x18001c16d  mov     r8, cs:off_1800CE728
0x18001c174  movzx   r9d, word ptr [r8]
0x18001c178  mov     edx, r14d
0x18001c17b  mov     rcx, cs:RegHandle
0x18001c182  call    cs:__imp_EventSetInformation
0x18001c189  nop     dword ptr [rax+rax+00h]
0x18001c18e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c192  test    cs:byte_1800CF404, 10h
0x18001c199  jz      short loc_18001C1EF
0x18001c19b  lea     rcx, aMprddmInitiali; "mprddm initialization is starting..."
0x18001c1a2  mov     rax, rdi
0x18001c1a5  inc     rax
0x18001c1a8  cmp     [rcx+rax*2], si
0x18001c1ac  jnz     short loc_18001C1A5
0x18001c1ae  lea     eax, ds:2[rax*2]
0x18001c1b5  mov     [rsp+1888h+var_858], rcx
0x18001c1bd  mov     [rsp+1888h+var_850], eax
0x18001c1c4  mov     [rsp+1888h+var_84C], esi
0x18001c1cb  lea     rax, [rsp+1888h+ProviderId]
0x18001c1d3  mov     [rsp+1888h+plpszSubStringArray], rax
0x18001c1d8  mov     r9d, r14d
0x18001c1db  lea     r15, RasDdmTraceInfo
0x18001c1e2  mov     rdx, r15
0x18001c1e5  mov     rcx, rbx
0x18001c1e8  call    McGenEventWrite_EventWriteTransfer
0x18001c1ed  jmp     short loc_18001C1F6
0x18001c1ef  lea     r15, RasDdmTraceInfo
0x18001c1f6  lea     rcx, xmmword_1800D07D0+8; lpCriticalSection
0x18001c1fd  call    cs:__imp_InitializeCriticalSection
0x18001c204  nop     dword ptr [rax+rax+00h]
0x18001c209  mov     [rsp+1888h+var_1828], 1
0x18001c211  lea     rcx, gblDeviceTable; lpCriticalSection
0x18001c218  call    cs:__imp_InitializeCriticalSection
0x18001c21f  nop     dword ptr [rax+rax+00h]
0x18001c224  mov     [rsp+1888h+var_1828], 3
0x18001c22c  lea     rcx, stru_1800CF740; lpCriticalSection
0x18001c233  call    cs:__imp_InitializeCriticalSection
0x18001c23a  nop     dword ptr [rax+rax+00h]
0x18001c23f  mov     [rsp+1888h+var_1828], 0Bh
0x18001c247  lea     rcx, stru_1800CF5A8; lpCriticalSection
0x18001c24e  call    cs:__imp_InitializeCriticalSection
0x18001c255  nop     dword ptr [rax+rax+00h]
0x18001c25a  mov     [rsp+1888h+var_1828], 0Fh
0x18001c262  call    ?InitGlobalThreadPool@@YAKXZ; InitGlobalThreadPool(void)
0x18001c267  mov     ebx, eax
0x18001c269  test    eax, eax
0x18001c26b  jz      loc_18001C311
0x18001c271  mov     esi, 8
0x18001c276  test    cs:byte_1800CF404, sil
0x18001c27d  jz      loc_18001C30A
0x18001c283  xor     r15d, r15d
0x18001c286  mov     word ptr [rsp+1888h+var_848], r15w
0x18001c28f  mov     r8d, eax
0x18001c292  lea     rdx, aDdmserviceinit_30; "DDMServiceInitialize: InitGlobalThreadP"...
0x18001c299  lea     rcx, [rsp+1888h+var_848]
0x18001c2a1  call    FormatRRASErrorString
0x18001c2a6  test    cs:byte_1800CF404, sil
0x18001c2ad  jz      short loc_18001C30A
0x18001c2af  lea     rax, [rsp+1888h+var_848]
0x18001c2b7  inc     rdi
0x18001c2ba  cmp     [rax+rdi*2], r15w
0x18001c2bf  jnz     short loc_18001C2B7
0x18001c2c1  lea     rdx, [rsp+1888h+var_848]
0x18001c2c9  mov     [rsp+1888h+var_858], rdx
0x18001c2d1  lea     eax, ds:2[rdi*2]
0x18001c2d8  mov     [rsp+1888h+var_850], eax
0x18001c2df  mov     [rsp+1888h+var_84C], r15d
0x18001c2e7  lea     rax, [rsp+1888h+ProviderId]
0x18001c2ef  mov     [rsp+1888h+plpszSubStringArray], rax
0x18001c2f4  mov     r9d, r14d
0x18001c2f7  lea     rdx, RasDdmTraceError
0x18001c2fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c305  call    McGenEventWrite_EventWriteTransfer
0x18001c30a  mov     eax, ebx
0x18001c30c  jmp     loc_18001E4BE
0x18001c311  call    ?InitSerializedThreadPool@@YAKXZ; InitSerializedThreadPool(void)
0x18001c316  mov     ebx, eax
0x18001c318  test    eax, eax
0x18001c31a  jz      short loc_18001C37D
0x18001c31c  mov     esi, 8
0x18001c321  test    cs:byte_1800CF404, sil
0x18001c328  jz      short loc_18001C30A
0x18001c32a  xor     r15d, r15d
0x18001c32d  mov     word ptr [rsp+1888h+var_848], r15w
0x18001c336  mov     r8d, eax
0x18001c339  lea     rdx, aDdmserviceinit_20; "DDMServiceInitialize: InitSerializedThr"...
0x18001c340  lea     rcx, [rsp+1888h+var_848]
0x18001c348  call    FormatRRASErrorString
0x18001c34d  test    cs:byte_1800CF404, sil
0x18001c354  jz      short loc_18001C30A
0x18001c356  lea     rax, [rsp+1888h+var_848]
0x18001c35e  inc     rdi
0x18001c361  cmp     [rax+rdi*2], r15w
0x18001c366  jnz     short loc_18001C35E
0x18001c368  lea     rcx, [rsp+1888h+var_848]
0x18001c370  mov     [rsp+1888h+var_858], rcx
0x18001c378  jmp     loc_18001C2D1
0x18001c37d  xor     r8d, r8d; dwMaximumSize
0x18001c380  xor     edx, edx; dwInitialSize
0x18001c382  xor     ecx, ecx; flOptions
0x18001c384  call    cs:__imp_HeapCreate
0x18001c38b  nop     dword ptr [rax+rax+00h]
0x18001c390  mov     cs:hHeap, rax
0x18001c397  test    rax, rax
0x18001c39a  jnz     loc_18001C43F
0x18001c3a0  call    cs:__imp_GetLastError
0x18001c3a7  nop     dword ptr [rax+rax+00h]
0x18001c3ac  mov     ebx, eax
0x18001c3ae  mov     esi, 8
0x18001c3b3  xor     r12d, r12d
0x18001c3b6  test    cs:byte_1800CF404, sil
0x18001c3bd  jz      loc_18001E23F
0x18001c3c3  mov     word ptr [rsp+1888h+var_848], r12w
0x18001c3cc  mov     r8d, eax
0x18001c3cf  lea     rdx, aDdmserviceinit_9; "DDMServiceInitialize: Heap creation fai"...
0x18001c3d6  lea     rcx, [rsp+1888h+var_848]
0x18001c3de  call    FormatRRASErrorString
0x18001c3e3  test    cs:byte_1800CF404, sil
0x18001c3ea  jz      loc_18001E23F
0x18001c3f0  lea     rcx, [rsp+1888h+var_848]
0x18001c3f8  mov     rax, rdi
0x18001c3fb  inc     rax
0x18001c3fe  cmp     [rcx+rax*2], r12w
0x18001c403  jnz     short loc_18001C3FB
0x18001c405  lea     eax, ds:2[rax*2]
0x18001c40c  lea     rcx, [rsp+1888h+var_848]
0x18001c414  mov     [rsp+1888h+var_858], rcx
0x18001c41c  mov     [rsp+1888h+var_850], eax
0x18001c423  mov     [rsp+1888h+var_84C], r12d
0x18001c42b  lea     rax, [rsp+1888h+ProviderId]
0x18001c433  lea     rdx, RasDdmTraceError
0x18001c43a  jmp     loc_18001E22B
0x18001c43f  mov     dword ptr cs:gblMediaTable+4, 5
0x18001c449  mov     esi, 8
0x18001c44e  mov     r8d, 0C8h; dwBytes
0x18001c454  mov     edx, esi; dwFlags
0x18001c456  mov     rcx, rax; hHeap
0x18001c459  call    cs:__imp_HeapAlloc
0x18001c460  nop     dword ptr [rax+rax+00h]
0x18001c465  mov     qword ptr cs:gblMediaTable+8, rax
0x18001c46c  xor     ecx, ecx
0x18001c46e  test    rax, rax
0x18001c471  jnz     short loc_18001C483
0x18001c473  call    cs:__imp_GetLastError
0x18001c47a  nop     dword ptr [rax+rax+00h]
0x18001c47f  mov     ebx, eax
0x18001c481  jmp     short loc_18001C485
0x18001c483  mov     ebx, ecx
0x18001c485  test    ebx, ebx
0x18001c487  jz      loc_18001C55F
0x18001c48d  xor     r12d, r12d
0x18001c490  test    cs:byte_1800CF404, sil
0x18001c497  jz      loc_18001C524
0x18001c49d  mov     word ptr [rsp+1888h+var_848], r12w
0x18001c4a6  mov     r8d, ebx
0x18001c4a9  lea     rdx, aDdmserviceinit_5; "DDMServiceInitialize: Media object  cre"...
0x18001c4b0  lea     rcx, [rsp+1888h+var_848]
0x18001c4b8  call    FormatRRASErrorString
0x18001c4bd  test    cs:byte_1800CF404, sil
0x18001c4c4  jz      short loc_18001C524
0x18001c4c6  lea     rcx, [rsp+1888h+var_848]
0x18001c4ce  mov     rax, rdi
0x18001c4d1  inc     rax
0x18001c4d4  cmp     [rcx+rax*2], r12w
0x18001c4d9  jnz     short loc_18001C4D1
0x18001c4db  lea     eax, ds:2[rax*2]
0x18001c4e2  lea     rcx, [rsp+1888h+var_848]
0x18001c4ea  mov     [rsp+1888h+var_858], rcx
0x18001c4f2  mov     [rsp+1888h+var_850], eax
0x18001c4f9  mov     [rsp+1888h+var_84C], r12d
0x18001c501  lea     rax, [rsp+1888h+ProviderId]
0x18001c509  lea     rdx, RasDdmTraceError
0x18001c510  mov     r9d, r14d
0x18001c513  mov     [rsp+1888h+plpszSubStringArray], rax
0x18001c518  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c51f  call    McGenEventWrite_EventWriteTransfer
0x18001c524  cmp     cs:dword_1800CF4E4, r12d
0x18001c52b  jbe     loc_18001E23F
0x18001c531  mov     [rsp+1888h+dwErrorCode], ebx; dwErrorCode
0x18001c535  mov     [rsp+1888h+plpszSubStringArray], r12; plpszSubStringArray
0x18001c53a  xor     r9d, r9d; dwSubStringCount
0x18001c53d  lea     edx, [r9+1]; dwEventType
0x18001c541  mov     r8d, 4E88h; dwMessageId
0x18001c547  mov     rcx, cs:hLogHandle; hLogHandle
0x18001c54e  call    cs:__imp_RouterLogEventW
0x18001c555  nop     dword ptr [rax+rax+00h]
0x18001c55a  jmp     loc_18001E23F
0x18001c55f  lea     r8, MPRDDM_EVENT_SOURCE_Context
0x18001c566  mov     r9, r8
0x18001c569  lea     rcx, MPRDDM_EVENT_SOURCE
  ... truncated ...
```
