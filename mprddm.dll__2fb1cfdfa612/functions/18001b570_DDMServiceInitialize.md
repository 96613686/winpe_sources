# DDMServiceInitialize

- ea: `0x18001b570`
- end: `0x18001d98b`
- name: `DDMServiceInitialize`
- size: `9243`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b7c`
- `0x18001533c`
- `0x18001561c`
- `0x1800157cc`
- `0x180015eec`
- `0x1800161f0`
- `0x180016bcc`
- `0x180017794`
- `0x180017cfc`
- `0x1800180d8`
- `0x18001aa88`
- `0x18001aaec`
- `0x18001afb8`
- `0x18001b570`
- `0x18001dadc`
- `0x18001f8e0`
- `0x180024668`
- `0x180024870`
- `0x180024bac`
- `0x1800259a0`
- `0x180026cc0`
- `0x1800275e0`
- `0x180028abc`
- `0x180028d10`
- `0x18003a9dc`
- `0x18003b8f4`
- `0x180046d6c`
- `0x1800511bc`
- `0x1800545a4`
- `0x180054fd4`
- `0x180055a2c`
- `0x180055d98`
- `0x180056d88`
- `0x180071cec`
- `0x18007d140`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001d855`
- `KERNEL32!SetEvent` at `0x18001d855`
- `KERNEL32!DeleteCriticalSection` at `0x18001d879`
- `KERNEL32!DeleteCriticalSection` at `0x18001d8a3`
- `KERNEL32!DeleteCriticalSection` at `0x18001d8b5`
- `KERNEL32!DeleteCriticalSection` at `0x18001d879`
- `KERNEL32!DeleteCriticalSection` at `0x18001d8a3`
- `KERNEL32!DeleteCriticalSection` at `0x18001d8b5`
- `KERNEL32!InitializeSRWLock` at `0x18001bb76`
- `KERNEL32!InitializeSRWLock` at `0x18001bb76`
- `KERNEL32!HeapCreate` at `0x18001b975`
- `KERNEL32!HeapCreate` at `0x18001b975`
- `KERNEL32!SetWaitableTimer` at `0x18001cc53`
- `KERNEL32!SetWaitableTimer` at `0x18001cc53`
- `KERNEL32!CreateWaitableTimerW` at `0x18001c59a`
- `KERNEL32!CreateWaitableTimerW` at `0x18001c59a`
- `KERNEL32!InitializeCriticalSection` at `0x18001b815`
- `KERNEL32!InitializeCriticalSection` at `0x18001b82a`
- `KERNEL32!InitializeCriticalSection` at `0x18001b83f`
- `KERNEL32!InitializeCriticalSection` at `0x18001b854`
- `KERNEL32!InitializeCriticalSection` at `0x18001d69b`
- `KERNEL32!InitializeCriticalSection` at `0x18001b815`
- `KERNEL32!InitializeCriticalSection` at `0x18001b82a`
- `KERNEL32!InitializeCriticalSection` at `0x18001b83f`
- `KERNEL32!InitializeCriticalSection` at `0x18001b854`
- `KERNEL32!InitializeCriticalSection` at `0x18001d69b`
- `KERNEL32!CreateThread` at `0x18001d595`
- `KERNEL32!CreateThread` at `0x18001d595`
- `KERNEL32!HeapAlloc` at `0x18001ba56`
- `KERNEL32!HeapAlloc` at `0x18001c48e`
- `KERNEL32!HeapAlloc` at `0x18001ba56`
- `KERNEL32!HeapAlloc` at `0x18001c48e`
- `KERNEL32!CloseHandle` at `0x18001d679`
- `KERNEL32!CloseHandle` at `0x18001d679`
- `KERNEL32!GetLastError` at `0x18001b98b`
- `KERNEL32!GetLastError` at `0x18001ba68`
- `KERNEL32!GetLastError` at `0x18001c4a5`
- `KERNEL32!GetLastError` at `0x18001cc5d`
- `KERNEL32!GetLastError` at `0x18001cf58`
- `KERNEL32!GetLastError` at `0x18001d5a3`
- `KERNEL32!GetLastError` at `0x18001b98b`
- `KERNEL32!GetLastError` at `0x18001ba68`
- `KERNEL32!GetLastError` at `0x18001c4a5`
- `KERNEL32!GetLastError` at `0x18001cc5d`
- `KERNEL32!GetLastError` at `0x18001cf58`
- `KERNEL32!GetLastError` at `0x18001d5a3`
- `KERNEL32!CreateEventW` at `0x18001c543`
- `KERNEL32!CreateEventW` at `0x18001c565`
- `KERNEL32!CreateEventW` at `0x18001c543`
- `KERNEL32!CreateEventW` at `0x18001c565`
- `ADVAPI32!EventRegister` at `0x18001b794`
- `ADVAPI32!EventRegister` at `0x18001b794`
- `ADVAPI32!EventSetInformation` at `0x18001b7b9`
- `ADVAPI32!EventSetInformation` at `0x18001b7b9`
- `ADVAPI32!RegOpenKeyW` at `0x18001be9e`
- `ADVAPI32!RegOpenKeyW` at `0x18001bfa0`
- `ADVAPI32!RegOpenKeyW` at `0x18001c027`
- `ADVAPI32!RegOpenKeyW` at `0x18001be9e`
- `ADVAPI32!RegOpenKeyW` at `0x18001bfa0`
- `ADVAPI32!RegOpenKeyW` at `0x18001c027`
- `rtutils!RouterLogEventW` at `0x18001bb47`
- `rtutils!RouterLogEventW` at `0x18001bb47`
- `rtutils!RouterLogRegisterW` at `0x18001cf46`
- `rtutils!RouterLogRegisterW` at `0x18001cf46`
- `rtutils!RouterLogEventStringW` at `0x18001bd3d`
- `rtutils!RouterLogEventStringW` at `0x18001d3cb`
- `rtutils!RouterLogEventStringW` at `0x18001bd3d`
- `rtutils!RouterLogEventStringW` at `0x18001d3cb`
- `rasman!RasGetKey` at `0x18001cd6e`
- `rasman!RasPortGetStatistics` at `0x18001cd50`
- `rasman!RasProtocolStarted` at `0x18001cdaa`
- `rasman!RasCompressionSetInfo` at `0x18001ce8b`
- `rasman!RasPortSetFramingEx` at `0x18001ce7c`
- `rasman!RasRegisterPnPHandler` at `0x18001d616`
- `rasman!RasRegisterPnPHandler` at `0x18001d616`
- `rasman!RasGetFramingCapabilities` at `0x18001ce6d`
- `rasman!RasSetConnectionUserData` at `0x18001cd9b`
- `rasman!RasActivateRoute` at `0x18001cdf5`
- `rasman!RasPortGetProtocolCompression` at `0x18001cea9`
- `rasman!RasGetTimeSinceLastActivity` at `0x18001cdb9`
- `rasman!RasCompressionGetInfo` at `0x18001ce9a`
- `rasman!RasGetInfo` at `0x18001ce4f`
- `rasman!RasPortCancelReceive` at `0x18001ce13`
- `rasman!RasPortSetProtocolCompression` at `0x18001cec7`
- `rasman!RasFreeBuffer` at `0x18001ce22`
- `rasman!RasGetConnectInfo` at `0x18001ce40`
- `rasman!RasAllocateRoute` at `0x18001cd5f`
- `rasman!RasDeAllocateRoute` at `0x18001cde6`
- `rasman!RasGetPortUserData` at `0x18001cd7d`
- `rasman!RasPortGetBundle` at `0x18001cd8c`
- `rasman!RasSendNotification` at `0x18001d74e`
- `rasman!RasSendNotification` at `0x18001d74e`
- `rasman!RasBundleGetPort` at `0x18001ce5e`
- `rasman!RasSetTunnelEndPoints` at `0x18001cdc8`
- `rasman!RasDeviceGetInfo` at `0x18001cd41`
- `rasman!RasReferenceRasman` at `0x18001bd4d`
- `rasman!RasReferenceRasman` at `0x18001bd4d`
- `rasman!RasInitialize` at `0x18001bc5d`
- `rasman!RasInitialize` at `0x18001bc5d`
- `rasman!RasGetBuffer` at `0x18001ceb8`
- `rasman!RasPortSend` at `0x18001ce31`
- `rasman!RasSendProtocolResultToRasman` at `0x18001cdd7`
- `rasman!RasUpdateDefaultRouteSettings` at `0x18001ce04`
- `sstpcfg!SetupSstpServerConfig` at `0x18001bb87`
- `sstpcfg!SetupSstpServerConfig` at `0x18001bb87`
- `eappprxy!EapHostPeerInitialize` at `0x18001c385`
- `eappprxy!EapHostPeerInitialize` at `0x18001c385`

## string_xrefs

- `0x18001cb38`: `RasIpv6SrvrStart completes with return code %d`
- `0x18001bbaf`: `DDMServiceInitialize: SetupSstpServerConfig failed. Error %d`
- `0x18001be90`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18001beae`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18001d8d5`: `DDMServiceInitialize: Resource initialization failed with error %d`
- `0x18001b88e`: `DDMServiceInitialize: InitGlobalThreadPool failed with error %d`
- `0x18001b935`: `DDMServiceInitialize: InitSerializedThreadPool failed with error %d`
- `0x18001b9b4`: `DDMServiceInitialize: Heap creation failed with error %d`
- `0x18001ba98`: `DDMServiceInitialize: Media object  creation failed with error %d`
- `0x18001bc1e`: `DDMServiceInitialize: WanDriver initialization failed with error %d`
- `0x18001bc89`: `DDMServiceInitialize: Rasman initialization failed with error %d`
- `0x18001bd71`: `DDMServiceInitialize: Rasman's reference count could not be incremented. Error %d`
- `0x18001bde4`: `DDMServiceInitialize: Failed to get the router phone book. Error %d`
- `0x18001be4a`: `DDMServiceInitialize: Failed to load resource strings. Error %d`
- `0x18001bed9`: `DDMServiceInitialize: Error %d while opening registry key %s.`
- `0x18001bfd3`: `DDMServiceInitialize: Error %d while opening registry key %s.`
- `0x18001bf92`: `System\CurrentControlSet\Services\RemoteAccess\Accounting`
- `0x18001bfac`: `System\CurrentControlSet\Services\RemoteAccess\Accounting`
- `0x18001c019`: `System\CurrentControlSet\Services\RemoteAccess\Authentication`
- `0x18001c033`: `System\CurrentControlSet\Services\RemoteAccess\Authentication`
- `0x18001c05e`: `DDMServiceInitialize: Error %d occured while opening registry key %s.`
- `0x18001c0e6`: `DDMServiceInitialize: Error %d occured while loading ddm parameters from registry `
- `0x18001c14c`: `DDMServiceInitialize: fIpAllowed = %d, fIpv6Allowed = %d`
- `0x18001c20b`: `DDMServiceInitialize: Error %d occured while loading third-party admin dll`
- `0x18001c278`: `DDMServiceInitialize: Error %d occured while loading third-party security dll`
- `0x18001c2e3`: `DDMServiceInitialize: Error %d occured while initializing Rasman interface`
- `0x18001c345`: `DDMServiceInitialize: InitializDeviceTable failed. Error %d`
- `0x18001c3aa`: `DDMServiceInitialize: EapHostPeerInitialize failed with error %d`
- `0x18001c402`: `DDMServiceInitialize: failed to create DdmNotificationHandler object`
- `0x18001c4c9`: `DDMServiceInitialize: Error %d occured while allocating memory for resources. #0`
- `0x18001c64d`: `DDMServiceInitialize: Error %d occured while registering device events with Rasman.`
- `0x18001c718`: `DDMServiceInitialize: Error %d occured while loading the configured Authentication provider`
- `0x18001c829`: `DDMServiceInitialize: Error %d occured while loading the configured Accounting provider`
- `0x18001c8e0`: `DDMServiceInitialize: Error %d occured while initalizing Ras Server`
- `0x18001ca2f`: `DDMServiceInitialize: Error %d occured while initializating ras server.`
- `0x18001cc7e`: `DDMServiceInitialize: Error %d occured while setting up the timer.`
- `0x18001ccdd`: `DDMServiceInitialize: Error %d occured while loading protocol engines.`
- `0x18001cefd`: `DDMServiceInitialize: RasInterfaceMgmtInit failed.`
- `0x18001cf3f`: `RemoteAccess`
- `0x18001cf79`: `DDMServiceInitialize: Error 0x%x occured while creating system event handle.`
- `0x18001d1ee`: `DDMServiceInitialize: Error %d occured while initializing client protocol engine [%ws].`
- `0x18001d317`: `DDMServiceInitialize: Error %d occured while initializing server protocol engine [%ws].`
- `0x18001d407`: `DDMServiceInitialize: protocol engine [%ws] does not support this configuration. dwServerFlags: 0x%.8x`
- `0x18001d51f`: `DDMServiceInitialize: All Engines are failed to load\n`
- `0x18001d5c4`: `DDMServiceInitialize: Error %d occured while creating worker thread.`
- `0x18001d63b`: `DDMServiceInitialize: Error %d occured while registering PnP notification handler with Rasman.`
- `0x18001d6cd`: `DDMServiceInitialize: Error %d occured while initializing address pool for IP addresses.`
- `0x18001d762`: `mprddm initialization is complete`
- `0x18001d7c4`: `DDMServiceInitialize: Error %d occured during mprddm initialization. Cleaning up...`

## pseudocode

```c
__int64 __fastcall DDMServiceInitialize(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  __int64 v4; // r8
  unsigned int inited; // eax
  DWORD dwErrorCode; // ebx
  __int64 v7; // r8
  __int64 v8; // rdi
  unsigned int v10; // eax
  HANDLE v11; // rax
  DWORD LastError; // eax
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 *v20; // rdx
  DWORD v21; // eax
  unsigned int v22; // eax
  DWORD v23; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 *v26; // rdx
  DWORD v27; // r8d
  DWORD v28; // eax
  unsigned int RouterPhoneBook; // eax
  unsigned int Strings; // eax
  unsigned int v31; // eax
  __int64 v32; // r8
  __int64 v33; // rax
  unsigned int v34; // eax
  unsigned int v35; // eax
  DWORD DDMParameters; // eax
  __int64 v37; // r8
  __int64 v38; // rax
  DWORD SecurityModule; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  DWORD v42; // eax
  __int64 v43; // r8
  unsigned __int64 v44; // rax
  unsigned int v45; // r15d
  unsigned __int64 v46; // rax
  HANDLE *v47; // rdx
  DWORD v48; // eax
  unsigned int i; // ebx
  HANDLE v50; // rax
  HANDLE EventW; // rax
  HANDLE WaitableTimerW; // rax
  DdmDeviceTable *Instance; // rax
  unsigned int v54; // eax
  DWORD v55; // eax
  __int64 v56; // r8
  __int64 v57; // rax
  DWORD v58; // eax
  LONGLONG v59; // r15
  __int64 v60; // r8
  __int64 v61; // rax
  DWORD v62; // eax
  __int64 v63; // r8
  __int64 v64; // rax
  __int64 *v65; // rdx
  __int64 v66; // r8
  unsigned int v67; // ecx
  __int64 v68; // rdx
  __int64 v69; // r10
  __int64 v70; // r8
  __int64 v71; // rax
  DWORD v72; // eax
  DWORD v73; // eax
  DWORD ProtocolEngines; // eax
  __int64 v75; // r8
  __int64 (__fastcall *v76)(int); // rax
  DWORD v77; // eax
  DWORD v78; // eax
  unsigned int v79; // eax
  unsigned __int64 v80; // r15
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  int v85; // r15d
  HANDLE Thread; // rax
  void *v87; // rsi
  DWORD v88; // eax
  DWORD v89; // eax
  DWORD v90; // eax
  __int64 v91; // r8
  __int64 v92; // r8
  LPWSTR *plpszSubStringArray; // [rsp+20h] [rbp-1858h]
  unsigned int v94; // [rsp+60h] [rbp-1818h]
  LARGE_INTEGER DueTime; // [rsp+68h] [rbp-1810h] BYREF
  DWORD ThreadId[4]; // [rsp+70h] [rbp-1808h] BYREF
  __int64 (__fastcall *v97)(); // [rsp+80h] [rbp-17F8h] BYREF
  __int64 (__usercall *v98)@<rax>(int@<ecx>, __int64); // [rsp+88h] [rbp-17F0h]
  __int64 (__fastcall *v99)(int); // [rsp+90h] [rbp-17E8h]
  __int64 (__fastcall *v100)(int); // [rsp+98h] [rbp-17E0h]
  __int64 (__fastcall *v101)(int, int, int, void *); // [rsp+A0h] [rbp-17D8h]
  __int64 (__fastcall *v102)(int); // [rsp+A8h] [rbp-17D0h]
  void *v103; // [rsp+B0h] [rbp-17C8h]
  __int64 (__fastcall *v104)(); // [rsp+B8h] [rbp-17C0h]
  __int64 (__fastcall *v105)(int); // [rsp+C0h] [rbp-17B8h]
  __int64 (__fastcall *v106)(int); // [rsp+C8h] [rbp-17B0h]
  __int64 (__fastcall *v107)(int); // [rsp+D0h] [rbp-17A8h]
  __int64 (__fastcall *v108)(); // [rsp+D8h] [rbp-17A0h]
  __int64 (__fastcall *v109)(); // [rsp+E0h] [rbp-1798h]
  __int64 (__fastcall *v110)(int); // [rsp+E8h] [rbp-1790h]
  __int64 (__fastcall *v111)(); // [rsp+F0h] [rbp-1788h]
  __int64 (__fastcall *v112)(int); // [rsp+F8h] [rbp-1780h]
  __int64 (__fastcall *v113)(HLOCAL); // [rsp+100h] [rbp-1778h]
  __int64 (__fastcall *v114)(int); // [rsp+108h] [rbp-1770h]
  __int64 (__fastcall *v115)(int); // [rsp+110h] [rbp-1768h]
  void *v116; // [rsp+118h] [rbp-1760h]
  __int64 (__fastcall *v117)(); // [rsp+120h] [rbp-1758h]
  __int64 (__fastcall *v118)(int); // [rsp+128h] [rbp-1750h]
  __int64 (__fastcall *v119)(int); // [rsp+130h] [rbp-1748h]
  __int64 (__fastcall *v120)(int); // [rsp+138h] [rbp-1740h]
  __int64 (__fastcall *v121)(int); // [rsp+140h] [rbp-1738h]
  __int64 (__fastcall *v122)(int); // [rsp+148h] [rbp-1730h]
  __int64 (__fastcall *v123)(); // [rsp+150h] [rbp-1728h]
  __int64 (__fastcall *v124)(int); // [rsp+158h] [rbp-1720h]
  __int128 v125; // [rsp+160h] [rbp-1718h] BYREF
  __int128 v126; // [rsp+170h] [rbp-1708h] BYREF
  __int128 v127; // [rsp+180h] [rbp-16F8h] BYREF
  unsigned int (*v128)(void); // [rsp+190h] [rbp-16E8h]
  _DWORD v129[920]; // [rsp+1A0h] [rbp-16D8h] BYREF
  GUID ProviderId; // [rsp+1000h] [rbp-878h] BYREF
  struct _GUID Buf1; // [rsp+1010h] [rbp-868h] BYREF
  const wchar_t *v132; // [rsp+1020h] [rbp-858h]
  __int64 v133; // [rsp+1028h] [rbp-850h]
  int v134; // [rsp+1030h] [rbp-848h] BYREF
  char v135[2044]; // [rsp+1034h] [rbp-844h] BYREF

  ThreadId[0] = 0;
  DueTime.LowPart = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  memset_0(&v97, 0, 0xE0u);
  v134 = 0;
  memset_0(v135, 0, sizeof(v135));
  memset_0(&gblDDMConfigInfo, 0, 0x1F8u);
  g_pIDimInterfaceTable = *(_QWORD *)a1;
  qword_1800C84F8 = *(_QWORD *)(a1 + 8);
  dword_1800C8500 = *(_DWORD *)(a1 + 40);
  hLogHandle = *(HANDLE *)(a1 + 48);
  gblphEventDDMServiceState = *(_QWORD *)(a1 + 16);
  gblphEventDDMTerminated = *(_QWORD *)(a1 + 24);
  qword_1800C8558 = *(_QWORD *)(a1 + 32);
  qword_1800C8570 = *(_QWORD *)(a1 + 64);
  qword_1800C8698 = *(_QWORD *)(a1 + 72);
  qword_1800C86A0 = *(_QWORD *)(a1 + 80);
  qword_1800C86A8 = *(_QWORD *)(a1 + 88);
  qword_1800C86B0 = *(_QWORD *)(a1 + 96);
  dword_1800C8648 = 0;
  dword_1800C864C = *(_DWORD *)(a1 + 56);
  g_dhcpIpFailureEventRaised = 0;
  g_portExhaustedEventRaised = 0;
  *(_DWORD *)(a1 + 104) = 0;
  v3 = *(_QWORD *)(a1 + 128);
  if ( v3 )
  {
    qword_1800C8688 = *(_QWORD *)(v3 + 40);
    qword_1800C8690 = *(_QWORD *)(*(_QWORD *)(a1 + 128) + 56LL);
  }
  dword_1800C8650 = *(_DWORD *)(a1 + 108);
  dword_1800C8654 = *(_DWORD *)(a1 + 112);
  if ( (int)McGenEventRegister_EventRegister(
              MICROSOFT_WINDOWS_RRAS_PROVIDER,
              v2,
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context) >= 0 )
  {
    SetLibParams();
    SetLibParamsWithBuffer();
  }
  ProviderId = (GUID)*((_OWORD *)off_1800C7728 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_1800C7748 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_1800C7720, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_1800C7728, (unsigned __int16)*off_1800C7728);
  LOBYTE(ProviderId.Data1) = byte_1800C8404 & 0x10;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v132 = L"mprddm initialization is starting...";
    v133 = 74;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v4, 2, &Buf1);
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800C97D0 + 1));
  InitializeCriticalSection(&gblDeviceTable);
  InitializeCriticalSection(&stru_1800C8740);
  InitializeCriticalSection(&stru_1800C85A8);
  inited = InitGlobalThreadPool();
  dwErrorCode = inited;
  if ( inited )
  {
    if ( (byte_1800C8404 & 8) == 0 )
      return dwErrorCode;
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"DDMServiceInitialize: InitGlobalThreadPool failed with error %d", inited);
    if ( (byte_1800C8404 & 8) == 0 )
      return dwErrorCode;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v135[2 * v8 - 4] );
LABEL_16:
    v132 = (const wchar_t *)&v134;
    v133 = (unsigned int)(2 * v8 + 2);
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v7, 2, &Buf1);
    return dwErrorCode;
  }
  v10 = InitSerializedThreadPool();
  dwErrorCode = v10;
  if ( v10 )
  {
    if ( (byte_1800C8404 & 8) == 0 )
      return dwErrorCode;
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"DDMServiceInitialize: InitSerializedThreadPool failed with error %d", v10);
    if ( (byte_1800C8404 & 8) == 0 )
      return dwErrorCode;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v135[2 * v8 - 4] );
    goto LABEL_16;
  }
  v11 = HeapCreate(0, 0, 0);
  hHeap = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    dwErrorCode = LastError;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Heap creation failed with error %d", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
LABEL_29:
        v16 = RasDdmTraceError;
LABEL_30:
        v133 = (unsigned int)(2 * v15 + 2);
        v132 = (const wchar_t *)&v134;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v16, v13, 2, &Buf1);
        goto LABEL_335;
      }
    }
    goto LABEL_114;
  }
  DWORD1(gblMediaTable) = 5;
  *((_QWORD *)&gblMediaTable + 1) = HeapAlloc(v11, 8u, 0xC8u);
  if ( *((_QWORD *)&gblMediaTable + 1) )
    dwErrorCode = 0;
  else
    dwErrorCode = GetLastError();
  if ( dwErrorCode )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Media object  creation failed with error %d", dwErrorCode);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&v135[2 * v19 - 4] );
        v20 = RasDdmTraceError;
LABEL_40:
        v133 = (unsigned int)(2 * v19 + 2);
        v132 = (const wchar_t *)&v134;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v20, v18, 2, &Buf1);
        goto LABEL_42;
      }
    }
    v14 = -1;
    goto LABEL_42;
  }
  McGenEventRegister_EventRegister(MPRDDM_EVENT_SOURCE, v17, MPRDDM_EVENT_SOURCE_Context, MPRDDM_EVENT_SOURCE_Context);
  dword_1800C84E0 |= 0x10u;
  InitializeSRWLock(&SRWLock);
  if ( !*(_DWORD *)(a1 + 112) )
  {
    v23 = RasInitialize();
    dwErrorCode = v23;
    if ( v23 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(&v134, L"DDMServiceInitialize: Rasman initialization failed with error %d", v23);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v14 = -1;
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)&v135[2 * v25 - 4] );
          v26 = RasDdmTraceError;
LABEL_63:
          v133 = (unsigned int)(2 * v25 + 2);
          v132 = (const wchar_t *)&v134;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v26, v24, 2, &Buf1);
LABEL_65:
          if ( !dword_1800C84E4 )
            goto LABEL_335;
          v27 = 20054;
LABEL_67:
          RouterLogEventStringW(hLogHandle, 1u, v27, 0, 0, dwErrorCode, 0);
          goto LABEL_335;
        }
      }
    }
    else
    {
      v28 = RasReferenceRasman(1);
      dwErrorCode = v28;
      if ( !v28 )
      {
        dword_1800C8648 = 1;
        goto LABEL_75;
      }
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(
          &v134,
          L"DDMServiceInitialize: Rasman's reference count could not be incremented. Error %d",
          v28);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v14 = -1;
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)&v135[2 * v25 - 4] );
          v26 = RasDdmTraceInfo;
          goto LABEL_63;
        }
      }
    }
    v14 = -1;
    goto LABEL_65;
  }
  v21 = SetupSstpServerConfig();
  dwErrorCode = v21;
  if ( v21 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: SetupSstpServerConfig failed. Error %d", v21);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_29;
      }
    }
LABEL_114:
    v14 = -1;
    goto LABEL_335;
  }
  v22 = InitDdmDriverHelper(*(_DWORD *)(a1 + 120));
  dwErrorCode = v22;
  if ( v22 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: WanDriver initialization failed with error %d", v22);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_29;
      }
    }
    goto LABEL_114;
  }
LABEL_75:
  RouterPhoneBook = GetRouterPhoneBook();
  dwErrorCode = RouterPhoneBook;
  if ( RouterPhoneBook )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Failed to get the router phone book. Error %d",
        RouterPhoneBook);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_29;
      }
    }
    goto LABEL_114;
  }
  Strings = LoadStrings();
  dwErrorCode = Strings;
  if ( Strings )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Failed to load resource strings. Error %d", Strings);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_29;
      }
    }
    goto LABEL_114;
  }
  v31 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", &hKey);
  dwErrorCode = v31;
  if ( v31 )
  {
    *(_QWORD *)&ProviderId.Data1 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters";
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d while opening registry key %s.", v31);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v14 = -1;
        v33 = -1;
        do
          ++v33;
        while ( *(_WORD *)&v135[2 * v33 - 4] );
LABEL_92:
        v132 = (const wchar_t *)&v134;
        v133 = (unsigned int)(2 * v33 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v32, 2, &Buf1);
        goto LABEL_94;
      }
    }
    goto LABEL_93;
  }
  v34 = RegOpenKeyW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Accounting",
          &qword_1800C8548);
  dwErrorCode = v34;
  if ( v34 )
  {
    *(_QWORD *)&ProviderId.Data1 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Accounting";
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d while opening registry key %s.", v34);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v14 = -1;
        v33 = -1;
        do
          ++v33;
        while ( *(_WORD *)&v135[2 * v33 - 4] );
        goto LABEL_92;
      }
    }
LABEL_93:
    v14 = -1;
LABEL_94:
    if ( dword_1800C84E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, (LPWSTR *)&ProviderId, dwErrorCode);
    goto LABEL_335;
  }
  v35 = RegOpenKeyW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Authentication",
          &qword_1800C8550);
  dwErrorCode = v35;
  if ( v35 )
  {
    *(_QWORD *)&ProviderId.Data1 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Authentication";
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d occured while opening registry key %s.", v35);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v14 = -1;
        v33 = -1;
        do
          ++v33;
        while ( *(_WORD *)&v135[2 * v33 - 4] );
        goto LABEL_92;
      }
    }
    goto LABEL_93;
  }
  DDMParameters = LoadDDMParameters(hKey);
  dwErrorCode = DDMParameters;
  if ( DDMParameters )
  {
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_114;
    LOWORD(v134) = 0;
    FormatRRASErrorString(
      &v134,
      L"DDMServiceInitialize: Error %d occured while loading ddm parameters from registry ",
      DDMParameters);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_114;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v135[2 * v15 - 4] );
LABEL_113:
    v16 = RasDdmTraceInfo;
    goto LABEL_30;
  }
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"DDMServiceInitialize: fIpAllowed = %d, fIpv6Allowed = %d", 0, DueTime.LowPart);
    v14 = -1;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v38 = -1;
      do
        ++v38;
      while ( *(_WORD *)&v135[2 * v38 - 4] );
      v132 = (const wchar_t *)&v134;
      v133 = (unsigned int)(2 * v38 + 2);
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v37, 2, &Buf1);
    }
  }
  else
  {
    v14 = -1;
  }
  if ( dword_1800C84EC < 0 )
    *(_DWORD *)(a1 + 116) = 1;
  dwErrorCode = LoadAdminModule();
  if ( dwErrorCode )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured while loading third-party admin dll",
        dwErrorCode);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_113;
      }
    }
LABEL_339:
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
    v41 = InitializDeviceTable();
    dwErrorCode = v41;
    if ( v41 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(&v134, L"DDMServiceInitialize: InitializDeviceTable failed. Error %d", v41);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v135[2 * v15 - 4] );
          goto LABEL_29;
        }
      }
      goto LABEL_335;
    }
    InitializeRasIpsec();
    v42 = EapHostPeerInitialize();
    dwErrorCode = v42;
    if ( v42 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(&v134, L"DDMServiceInitialize: EapHostPeerInitialize failed with error %d", v42);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v135[2 * v15 - 4] );
          goto LABEL_29;
        }
      }
      goto LABEL_335;
    }
    dword_1800C8668 = 1;
  }
  else
  {
    SecurityModule = LoadSecurityModule();
    dwErrorCode = SecurityModule;
    if ( SecurityModule )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(
          &v134,
          L"DDMServiceInitialize: Error %d occured while loading third-party security dll",
          SecurityModule);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v135[2 * v15 - 4] );
          goto LABEL_113;
        }
      }
      goto LABEL_339;
    }
    v40 = RmInit((int *)(a1 + 104));
    dwErrorCode = v40;
    if ( v40 )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d occured while initializing Rasman interface", v40);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v135[2 * v15 - 4] );
          goto LABEL_113;
        }
      }
      goto LABEL_339;
    }
  }
  if ( !DdmNotificationHandler::GetInstance() )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v132 = L"DDMServiceInitialize: failed to create DdmNotificationHandler object";
      v133 = 138;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v43, 2, &Buf1);
    }
    dwErrorCode = 8;
    goto LABEL_335;
  }
  v44 = 3LL * *(unsigned int *)DdmDeviceTable::GetInstance(0x11u);
  if ( v44 > 0xFFFFFFFF || (v45 = v44 + 6, (int)v44 + 6 < (unsigned int)v44) || (v46 = 8LL * v45, v46 > 0xFFFFFFFF) )
  {
    dwErrorCode = 534;
    goto LABEL_335;
  }
  v47 = (HANDLE *)HeapAlloc(hHeap, 8u, (unsigned int)v46);
  gblSupervisorEvents = v47;
  if ( !v47 )
  {
    v48 = GetLastError();
    dwErrorCode = v48;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured while allocating memory for resources. #0",
        v48);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&v135[2 * v19 - 4] );
        v20 = RasDdmTraceInfo;
        goto LABEL_40;
      }
    }
LABEL_42:
    if ( dword_1800C84E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, dwErrorCode);
    goto LABEL_335;
  }
  for ( i = 0; i < v45; ++i )
  {
    if ( i )
    {
      if ( i == 1 )
      {
        v47[1] = *(HANDLE *)gblphEventDDMTerminated;
      }
      else if ( i == 2 )
      {
        WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
        v47 = gblSupervisorEvents;
        gblSupervisorEvents[2] = WaitableTimerW;
        qword_1800C86E8 = (__int64)TimerHandler;
      }
      else if ( i == 3 || i - 4 < 2 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v47 = gblSupervisorEvents;
        gblSupervisorEvents[i] = EventW;
        qword_1800C86C8[2 * i] = (__int64)ChangeNotificationEventHandler;
      }
      else
      {
        v50 = CreateEventW(0, 0, 0, 0);
        v47 = gblSupervisorEvents;
        gblSupervisorEvents[i] = v50;
      }
    }
    else
    {
      *v47 = *(HANDLE *)gblphEventDDMServiceState;
      qword_1800C86C8[0] = (__int64)SvcEventHandler;
    }
  }
  if ( !*(_DWORD *)(a1 + 112) )
  {
    *(_QWORD *)&ProviderId.Data1 = &DeviceRequestNotification::`vftable';
    Instance = DdmDeviceTable::GetInstance(0x11u);
    v54 = DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&ProviderId, 1, 0);
    dwErrorCode = v54;
    if ( v54 )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(
          &v134,
          L"DDMServiceInitialize: Error %d occured while registering device events with Rasman.",
          v54);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v135[2 * v15 - 4] );
          goto LABEL_113;
        }
      }
      goto LABEL_339;
    }
  }
  ProviderId.Data1 = 0;
  v55 = LoadAndInitAuthOrAcctProvider(
          1,
          0,
          0,
          (unsigned int)&v125,
          (__int64)&v125 + 8,
          (__int64)&qword_1800C85A0,
          0,
          0,
          0,
          0,
          0);
  dwErrorCode = v55;
  if ( v55 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured while loading the configured Authentication provider",
        v55);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v57 = -1;
        do
          ++v57;
        while ( *(_WORD *)&v135[2 * v57 - 4] );
        v132 = (const wchar_t *)&v134;
        v133 = (unsigned int)(2 * v57 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v56, 2, &Buf1);
      }
    }
    if ( !dword_1800C84E4 )
      goto LABEL_335;
    v27 = 20152;
    goto LABEL_67;
  }
  v58 = LoadAndInitAuthOrAcctProvider(
          0,
          0,
          (unsigned int)&Data,
          0,
          0,
          0,
          (__int64)&v126,
          (__int64)&v126 + 8,
          (__int64)&v127,
          (__int64)&v127 + 8,
          (__int64)&qword_1800C8598);
  dwErrorCode = v58;
  v59 = 0;
  if ( v58 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured while loading the configured Accounting provider",
        v58);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v61 = -1;
        do
          ++v61;
        while ( *(_WORD *)&v135[2 * v61 - 4] );
        v132 = (const wchar_t *)&v134;
        v133 = (unsigned int)(2 * v61 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v60, 2, &Buf1);
      }
    }
    if ( !dword_1800C84E4 )
      goto LABEL_335;
    v27 = 20153;
    goto LABEL_67;
  }
  v62 = RasSrvrInitialize();
  dwErrorCode = v62;
  if ( v62 )
  {
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_210;
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d occured while initalizing Ras Server", v62);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_210;
    v64 = -1;
    do
      ++v64;
    while ( *(_WORD *)&v135[2 * v64 - 4] );
    v65 = RasDdmTraceInfo;
LABEL_209:
    v133 = (unsigned int)(2 * v64 + 2);
    v132 = (const wchar_t *)&v134;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v65, v63, 2, &Buf1);
LABEL_210:
    if ( !dword_1800C84E4 )
      goto LABEL_335;
    v27 = 20145;
    goto LABEL_67;
  }
  if ( DueTime.LowPart )
  {
    v66 = 0;
    v67 = 0;
    if ( dword_1800C8568 )
    {
      while ( 1 )
      {
        v68 = 168LL * v67;
        v69 = *(_QWORD *)((char *)qword_1800C8560 + v68 + 32);
        if ( v69 )
        {
          if ( *(_QWORD *)((char *)qword_1800C8560 + v68 + 40) )
            break;
        }
        if ( ++v67 >= dword_1800C8568 )
          goto LABEL_221;
      }
      dwErrorCode = RasSrvrIpv6Initialize(
                      v69,
                      *(_QWORD *)((char *)qword_1800C8560 + v68 + 40),
                      *((unsigned __int8 *)qword_1800C8560 + v68 + 8));
      if ( !dwErrorCode )
      {
        Buf1 = GUID_NULL;
        dwErrorCode = RasIpv6SrvrStart(&Buf1);
      }
      v66 = 1;
    }
LABEL_221:
    if ( !(_DWORD)v66 )
    {
      dwErrorCode = RasSrvrIpv6Initialize(0, 0, v66);
      if ( !dwErrorCode )
      {
        Buf1 = GUID_NULL;
        dwErrorCode = RasIpv6SrvrStart(&Buf1);
      }
    }
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"RasIpv6SrvrStart completes with return code %d", dwErrorCode);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v71 = -1;
        do
          ++v71;
        while ( *(_WORD *)&v135[2 * v71 - 4] );
        v132 = (const wchar_t *)&v134;
        v133 = (unsigned int)(2 * v71 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v70, 2, &Buf1);
      }
    }
    if ( dwErrorCode )
      goto LABEL_210;
    dword_1800C851C = 1;
  }
  v72 = RasSrvrInitializeIpAddrMgmtFunctions();
  dwErrorCode = v72;
  if ( v72 )
  {
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_210;
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"RasSrvrInitializeIpAddrMgmtFunctions failed with return code %d", v72);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_210;
    v64 = -1;
    do
      ++v64;
    while ( *(_WORD *)&v135[2 * v64 - 4] );
    v65 = RasDdmTraceError;
    goto LABEL_209;
  }
  DueTime.QuadPart = -10000000;
  if ( !SetWaitableTimer(gblSupervisorEvents[2], &DueTime, 1000, 0, 0, 0) )
  {
    v73 = GetLastError();
    dwErrorCode = v73;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d occured while setting up the timer.", v73);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_113;
      }
    }
    goto LABEL_339;
  }
  ProtocolEngines = LoadProtocolEngines();
  dwErrorCode = ProtocolEngines;
  if ( ProtocolEngines )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured while loading protocol engines.",
        ProtocolEngines);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_113;
      }
    }
    goto LABEL_339;
  }
  v128 = GetNextAccountingSessionId;
  v97 = DDMRouterTypeLookupForRoutingDomain;
  if ( !*(_DWORD *)(a1 + 112) )
  {
    v98 = (__int64 (__usercall *)@<rax>(int@<ecx>, __int64))RasDeviceGetInfo;
    v99 = (__int64 (__fastcall *)(int))RasPortGetStatistics;
    v100 = (__int64 (__fastcall *)(int))RasAllocateRoute;
    v101 = (__int64 (__fastcall *)(int, int, int, void *))RasGetKey;
    v102 = (__int64 (__fastcall *)(int))RasGetPortUserData;
    v103 = (void *)RasPortGetBundle;
    v104 = (__int64 (__fastcall *)())RasSetConnectionUserData;
    v105 = (__int64 (__fastcall *)(int))RasProtocolStarted;
    v106 = (__int64 (__fastcall *)(int))RasGetTimeSinceLastActivity;
    v107 = (__int64 (__fastcall *)(int))RasSetTunnelEndPoints;
    v108 = (__int64 (__fastcall *)())RasSendProtocolResultToRasman;
    v109 = (__int64 (__fastcall *)())RasDeAllocateRoute;
    v110 = (__int64 (__fastcall *)(int))RasActivateRoute;
    v111 = (__int64 (__fastcall *)())RasUpdateDefaultRouteSettings;
    v112 = (__int64 (__fastcall *)(int))RasPortCancelReceive;
    v113 = (__int64 (__fastcall *)(HLOCAL))RasFreeBuffer;
    v114 = (__int64 (__fastcall *)(int))RasPortSend;
    v115 = (__int64 (__fastcall *)(int))RasGetConnectInfo;
    v116 = (void *)RasGetInfo;
    v117 = (__int64 (__fastcall *)())RasBundleGetPort;
    v118 = (__int64 (__fastcall *)(int))RasGetFramingCapabilities;
    v119 = (__int64 (__fastcall *)(int))RasPortSetFramingEx;
    v120 = (__int64 (__fastcall *)(int))RasCompressionSetInfo;
    v121 = (__int64 (__fastcall *)(int))RasCompressionGetInfo;
    v122 = (__int64 (__fastcall *)(int))RasPortGetProtocolCompression;
    v123 = (__int64 (__fastcall *)())RasGetBuffer;
    v76 = (__int64 (__fastcall *)(int))RasPortSetProtocolCompression;
    goto LABEL_264;
  }
  v77 = RasInterfaceMgmtInit((unsigned int)dword_1800C8500);
  dwErrorCode = v77;
  if ( v77 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: RasInterfaceMgmtInit failed.", v77);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_29;
      }
    }
LABEL_335:
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured during mprddm initialization. Cleaning up...",
        dwErrorCode);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v135[2 * v14 - 4] );
        v132 = (const wchar_t *)&v134;
        v133 = (unsigned int)(2 * v14 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v92, 2, &Buf1);
      }
    }
    goto LABEL_339;
  }
  dword_1800C84E0 |= 0x20u;
  qword_1800C8660 = (__int64)RouterLogRegisterW(L"RemoteAccess");
  if ( !qword_1800C8660 )
  {
    v78 = GetLastError();
    dwErrorCode = v78;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error 0x%x occured while creating system event handle.", v78);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_113;
      }
    }
    goto LABEL_339;
  }
  v98 = DdmDeviceGetInfo;
  v99 = DdmPortGetStatistics;
  v100 = DdmAllocateRoute;
  v101 = DdmGetKey;
  v102 = DdmGetPortUserData;
  v103 = &DdmPortGetBundle;
  v104 = DdmSetConnectionUserData;
  v105 = DdmProtocolStarted;
  v106 = DdmGetTimeSinceLastActivity;
  v107 = DdmSetTunnelEndPoints;
  v108 = DdmSendProtocolResultToDdm;
  v109 = DdmDeAllocateRoute;
  v110 = DdmActivateRoute;
  v111 = DdmUpdateDefaultRouteSettings;
  v112 = DdmPortCancelReceive;
  v113 = DdmFreeBuffer;
  v114 = DdmPortSend;
  v115 = DdmGetConnectInfo;
  v116 = &DdmGetInfo;
  v117 = DdmBundleGetPort;
  v118 = DdmGetFramingCapabilities;
  v119 = DdmPortSetFramingEx;
  v120 = DdmCompressionSetInfo;
  v121 = DdmCompressionGetInfo;
  v122 = DdmPortGetProtocolCompression;
  v123 = DdmGetBuffer;
  v76 = DdmPortSetProtocolCompression;
LABEL_264:
  v124 = v76;
  v79 = 0;
  v94 = 0;
  DueTime.QuadPart = 0;
  do
  {
    v80 = 80 * v59;
    if ( !*(_DWORD *)&byte_1800C7498[v80] )
    {
      if ( *(_DWORD *)(a1 + 112)
        && (v79
          ? (v79 != 1
           ? (v81 = (unsigned int)dword_1800C95FC)
           : (v81 = (unsigned int)dword_1800C94C4))
          : (v81 = (unsigned int)dword_1800C938C),
            (dwErrorCode = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))qword_1800C74A0[v80 / 8 + 1])(
                             qword_1800C8660,
                             v81,
                             0)) != 0) )
      {
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v134) = 0;
          FormatRRASErrorString(
            &v134,
            L"DDMServiceInitialize: Error %d occured while initializing client protocol engine [%ws].",
            dwErrorCode,
            off_1800C7488[v80 / 8]);
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v82 = -1;
            do
              ++v82;
            while ( *(_WORD *)&v135[2 * v82 - 4] );
            v132 = (const wchar_t *)&v134;
            v133 = (unsigned int)(2 * v82 + 2);
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v75, 2, &Buf1);
          }
        }
      }
      else
      {
        LODWORD(plpszSubStringArray) = dword_1800C84E0 & 1;
        dwErrorCode = ((__int64 (__fastcall *)(__int64 (__fastcall *)(), _QWORD, _QWORD, _QWORD, LPWSTR *, __int128 *, void *, __int64 (__fastcall **)()))qword_1800C74A0[v80 / 8 + 3])(
                        SendProtocolMessageToDDM,
                        (unsigned int)dword_1800C84EC,
                        (unsigned int)dword_1800C84E4,
                        ProviderId.Data1,
                        plpszSubStringArray,
                        &v125,
                        &g_IPAddressMgmtFunctions,
                        &v97);
        if ( dwErrorCode )
        {
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            LOWORD(v134) = 0;
            FormatRRASErrorString(
              &v134,
              L"DDMServiceInitialize: Error %d occured while initializing server protocol engine [%ws].",
              dwErrorCode,
              off_1800C7488[v80 / 8]);
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              v83 = -1;
              do
                ++v83;
              while ( *(_WORD *)&v135[2 * v83 - 4] );
              v132 = (const wchar_t *)&v134;
              v133 = (unsigned int)(2 * v83 + 2);
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceInfo,
                v75,
                2,
                &Buf1);
            }
          }
          if ( dword_1800C84E4 )
            RouterLogEventStringW(hLogHandle, 1u, 0x4E5Fu, 1u, &off_1800C7488[v80 / 8], dwErrorCode, 0);
          if ( dwErrorCode == 50 )
          {
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              LOWORD(v134) = 0;
              FormatRRASErrorString(
                &v134,
                L"DDMServiceInitialize: protocol engine [%ws] does not support this configuration. dwServerFlags: 0x%.8x",
                off_1800C7488[v80 / 8],
                (unsigned int)dword_1800C84EC);
              if ( (byte_1800C8404 & 0x10) != 0 )
              {
                v84 = -1;
                do
                  ++v84;
                while ( *(_WORD *)&v135[2 * v84 - 4] );
                v132 = (const wchar_t *)&v134;
                v133 = (unsigned int)(2 * v84 + 2);
                McGenEventWrite_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasDdmTraceInfo,
                  v75,
                  2,
                  &Buf1);
              }
            }
            dwErrorCode = 0;
          }
          if ( *(_DWORD *)(a1 + 112) )
            ((void (__fastcall *)(_QWORD))qword_1800C74A0[v80 / 8 + 2])(0);
          dword_1800C749C[v80 / 4] = 0;
        }
        else
        {
          dword_1800C749C[v80 / 4] = 1;
        }
      }
      v79 = v94;
    }
    v94 = ++v79;
    v59 = ++DueTime.QuadPart;
  }
  while ( v79 < 3 );
  v85 = 0;
  while ( dword_1800C749C[20 * v85] != 1 )
  {
    if ( (unsigned int)++v85 >= 3 )
      goto LABEL_305;
  }
  DdmSetProtocolEvent();
LABEL_305:
  if ( v85 == 3 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v132 = L"DDMServiceInitialize: All Engines are failed to load\n";
      v133 = 108;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v75, 2, &Buf1);
    }
    if ( !dword_1800C84E4 )
      goto LABEL_335;
    v27 = 20064;
    goto LABEL_67;
  }
  Thread = CreateThread(0, 0, EventDispatcher, 0, 0, ThreadId);
  v87 = Thread;
  if ( !Thread )
  {
    v88 = GetLastError();
    dwErrorCode = v88;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMServiceInitialize: Error %d occured while creating worker thread.", v88);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_113;
      }
    }
    goto LABEL_339;
  }
  if ( !*(_DWORD *)(a1 + 112) )
  {
    v89 = RasRegisterPnPHandler(DdmDevicePnpHandler, Thread, 1);
    dwErrorCode = v89;
    if ( v89 )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(
          &v134,
          L"DDMServiceInitialize: Error %d occured while registering PnP notification handler with Rasman.",
          v89);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&v135[2 * v15 - 4] );
          goto LABEL_113;
        }
      }
      goto LABEL_339;
    }
  }
  CloseHandle(v87);
  qword_1800C85F8 = (__int64)&lpMem;
  lpMem = &lpMem;
  InitializeCriticalSection(&CriticalSection);
  dword_1800C84E0 |= 0x80u;
  v90 = AddressPoolInit();
  dwErrorCode = v90;
  if ( v90 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v134) = 0;
      FormatRRASErrorString(
        &v134,
        L"DDMServiceInitialize: Error %d occured while initializing address pool for IP addresses.",
        v90);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v135[2 * v15 - 4] );
        goto LABEL_113;
      }
    }
    goto LABEL_339;
  }
  dword_1800C8628 = 0;
  if ( !*(_DWORD *)(a1 + 112) )
  {
    memset_0(v129, 0, sizeof(v129));
    v129[0] = 0x20000;
    v129[2] = 0;
    v129[3] = 2;
    RasSendNotification(v129);
  }
  DDMInitializePerformanceCounters();
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v132 = L"mprddm initialization is complete";
    v133 = 68;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v91, 2, &Buf1);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b570  mov     [rsp+arg_8], rbx
0x18001b575  mov     [rsp+arg_10], rsi
0x18001b57a  push    rdi
0x18001b57b  push    r12
0x18001b57d  push    r13
0x18001b57f  push    r14
0x18001b581  push    r15
0x18001b583  mov     eax, 1850h
0x18001b588  call    _alloca_probe
0x18001b58d  sub     rsp, rax
0x18001b590  movaps  [rsp+1878h+var_38], xmm6
0x18001b598  mov     rax, cs:__security_cookie
0x18001b59f  xor     rax, rsp
0x18001b5a2  mov     [rsp+1878h+var_48], rax
0x18001b5aa  mov     r12, rcx
0x18001b5ad  xor     edi, edi
0x18001b5af  mov     [rsp+1878h+ThreadId], edi
0x18001b5b3  mov     [rsp+1878h+var_1818], edi
0x18001b5b7  mov     dword ptr [rsp+1878h+DueTime], edi
0x18001b5bb  xorps   xmm0, xmm0
0x18001b5be  xor     eax, eax
0x18001b5c0  movups  [rsp+1878h+var_1718], xmm0
0x18001b5c8  movups  [rsp+1878h+var_1708], xmm0
0x18001b5d0  movups  [rsp+1878h+var_16F8], xmm0
0x18001b5d8  mov     [rsp+1878h+var_16E8], rax
0x18001b5e0  xor     edx, edx; Val
0x18001b5e2  mov     r8d, 0E0h; Size
0x18001b5e8  lea     rcx, [rsp+1878h+var_17F8]; void *
0x18001b5f0  call    memset_0
0x18001b5f5  mov     [rsp+1878h+var_1814], edi
0x18001b5f9  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18001b600  mov     [rsp+1878h+var_848], edi
0x18001b607  xor     edx, edx; Val
0x18001b609  mov     r8d, 7FCh; Size
0x18001b60f  lea     rcx, [rsp+1878h+var_844]; void *
0x18001b617  call    memset_0
0x18001b61c  xor     edx, edx; Val
0x18001b61e  mov     r8d, 1F8h; Size
0x18001b624  lea     rcx, gblDDMConfigInfo; void *
0x18001b62b  call    memset_0
0x18001b630  mov     rax, [r12]
0x18001b634  mov     cs:g_pIDimInterfaceTable, rax
0x18001b63b  mov     rax, [r12+8]
0x18001b640  mov     cs:qword_1800C84F8, rax
0x18001b647  mov     eax, [r12+28h]
0x18001b64c  mov     cs:dword_1800C8500, eax
0x18001b652  mov     rax, [r12+30h]
0x18001b657  mov     cs:hLogHandle, rax
0x18001b65e  mov     rax, [r12+10h]
0x18001b663  mov     cs:gblphEventDDMServiceState, rax
0x18001b66a  mov     rax, [r12+18h]
0x18001b66f  mov     cs:gblphEventDDMTerminated, rax
0x18001b676  mov     rax, [r12+20h]
0x18001b67b  mov     cs:qword_1800C8558, rax
0x18001b682  mov     rax, [r12+40h]
0x18001b687  mov     cs:qword_1800C8570, rax
0x18001b68e  mov     rax, [r12+48h]
0x18001b693  mov     cs:qword_1800C8698, rax
0x18001b69a  mov     rax, [r12+50h]
0x18001b69f  mov     cs:qword_1800C86A0, rax
0x18001b6a6  mov     rax, [r12+58h]
0x18001b6ab  mov     cs:qword_1800C86A8, rax
0x18001b6b2  mov     rax, [r12+60h]
0x18001b6b7  mov     cs:qword_1800C86B0, rax
0x18001b6be  mov     cs:dword_1800C8648, edi
0x18001b6c4  mov     eax, [r12+38h]
0x18001b6c9  mov     cs:dword_1800C864C, eax
0x18001b6cf  mov     cs:g_dhcpIpFailureEventRaised, edi
0x18001b6d5  mov     cs:g_portExhaustedEventRaised, edi
0x18001b6db  mov     [r12+68h], edi
0x18001b6e0  mov     rax, [r12+80h]
0x18001b6e8  test    rax, rax
0x18001b6eb  jz      short loc_18001B70B
0x18001b6ed  mov     rax, [rax+28h]
0x18001b6f1  mov     cs:qword_1800C8688, rax
0x18001b6f8  mov     rax, [r12+80h]
0x18001b700  mov     rcx, [rax+38h]
0x18001b704  mov     cs:qword_1800C8690, rcx
0x18001b70b  mov     eax, [r12+6Ch]
0x18001b710  mov     cs:dword_1800C8650, eax
0x18001b716  mov     eax, [r12+70h]
0x18001b71b  mov     cs:dword_1800C8654, eax
0x18001b721  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b728  mov     r9, rbx
0x18001b72b  mov     r8, rbx
0x18001b72e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER
0x18001b735  call    McGenEventRegister_EventRegister
0x18001b73a  test    eax, eax
0x18001b73c  js      short loc_18001B748
0x18001b73e  call    ?SetLibParams@@YAXXZ; SetLibParams(void)
0x18001b743  call    ?SetLibParamsWithBuffer@@YAXXZ; SetLibParamsWithBuffer(void)
0x18001b748  mov     rax, cs:off_1800C7728
0x18001b74f  movups  xmm0, xmmword ptr [rax-10h]
0x18001b753  movdqu  xmmword ptr [rsp+1878h+ProviderId.Data1], xmm0
0x18001b75c  cmp     cs:RegHandle, rdi
0x18001b763  jz      short loc_18001B76C
0x18001b765  mov     ecx, 5
0x18001b76a  int     29h; Win8: RtlFailFast(ecx)
0x18001b76c  xorps   xmm0, xmm0
0x18001b76f  movdqu  cs:xmmword_1800C7748, xmm0
0x18001b777  lea     r9, RegHandle; RegHandle
0x18001b77e  lea     r8, dword_1800C7720; CallbackContext
0x18001b785  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001b78c  lea     rcx, [rsp+1878h+ProviderId]; ProviderId
0x18001b794  call    cs:__imp_EventRegister
0x18001b79a  mov     r14d, 2
0x18001b7a0  test    eax, eax
0x18001b7a2  jnz     short loc_18001B7BF
0x18001b7a4  mov     r8, cs:off_1800C7728
0x18001b7ab  movzx   r9d, word ptr [r8]
0x18001b7af  mov     edx, r14d
0x18001b7b2  mov     rcx, cs:RegHandle
0x18001b7b9  call    cs:__imp_EventSetInformation
0x18001b7bf  mov     al, cs:byte_1800C8404
0x18001b7c5  and     al, 10h
0x18001b7c7  mov     byte ptr [rsp+1878h+ProviderId.Data1], al
0x18001b7ce  lea     r13, RasDdmTraceInfo
0x18001b7d5  jz      short loc_18001B80E
0x18001b7d7  lea     rax, aMprddmInitiali; "mprddm initialization is starting..."
0x18001b7de  mov     [rsp+1878h+var_858], rax
0x18001b7e6  mov     [rsp+1878h+var_850], 4Ah ; 'J'
0x18001b7f2  lea     rax, [rsp+1878h+Buf1]
0x18001b7fa  mov     [rsp+1878h+plpszSubStringArray], rax
0x18001b7ff  mov     r9d, r14d
0x18001b802  mov     rdx, r13
0x18001b805  mov     rcx, rbx
0x18001b808  call    McGenEventWrite_EventWriteTransfer
0x18001b80d  nop
0x18001b80e  lea     rcx, xmmword_1800C97D0+8; lpCriticalSection
0x18001b815  call    cs:__imp_InitializeCriticalSection
0x18001b81b  mov     [rsp+1878h+var_1814], 1
0x18001b823  lea     rcx, gblDeviceTable; lpCriticalSection
0x18001b82a  call    cs:__imp_InitializeCriticalSection
0x18001b830  mov     [rsp+1878h+var_1814], 3
0x18001b838  lea     rcx, stru_1800C8740; lpCriticalSection
0x18001b83f  call    cs:__imp_InitializeCriticalSection
0x18001b845  mov     [rsp+1878h+var_1814], 0Bh
0x18001b84d  lea     rcx, stru_1800C85A8; lpCriticalSection
0x18001b854  call    cs:__imp_InitializeCriticalSection
0x18001b85a  mov     [rsp+1878h+var_1814], 0Fh
0x18001b862  call    ?InitGlobalThreadPool@@YAKXZ; InitGlobalThreadPool(void)
0x18001b867  mov     ebx, eax
0x18001b869  test    eax, eax
0x18001b86b  jz      loc_18001B911
0x18001b871  mov     esi, 8
0x18001b876  test    cs:byte_1800C8404, sil
0x18001b87d  jz      loc_18001B90A
0x18001b883  mov     word ptr [rsp+1878h+var_848], di
0x18001b88b  mov     r8d, eax
0x18001b88e  lea     rdx, aDdmserviceinit_30; "DDMServiceInitialize: InitGlobalThreadP"...
0x18001b895  lea     rcx, [rsp+1878h+var_848]
0x18001b89d  call    FormatRRASErrorString
0x18001b8a2  test    cs:byte_1800C8404, sil
0x18001b8a9  jz      short loc_18001B90A
0x18001b8ab  lea     rax, [rsp+1878h+var_848]
0x18001b8b3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b8b7  xor     edx, edx
0x18001b8b9  inc     rdi
0x18001b8bc  cmp     [rax+rdi*2], dx
0x18001b8c0  jnz     short loc_18001B8B9
0x18001b8c2  lea     rax, [rsp+1878h+var_848]
0x18001b8ca  mov     [rsp+1878h+var_858], rax
0x18001b8d2  lea     eax, ds:2[rdi*2]
0x18001b8d9  mov     dword ptr [rsp+1878h+var_850], eax
0x18001b8e0  mov     dword ptr [rsp+1878h+var_850+4], edx
0x18001b8e7  lea     rax, [rsp+1878h+Buf1]
0x18001b8ef  mov     [rsp+1878h+plpszSubStringArray], rax
0x18001b8f4  mov     r9d, r14d
0x18001b8f7  lea     rdx, RasDdmTraceError
0x18001b8fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b905  call    McGenEventWrite_EventWriteTransfer
0x18001b90a  mov     eax, ebx
0x18001b90c  jmp     loc_18001D959
0x18001b911  call    ?InitSerializedThreadPool@@YAKXZ; InitSerializedThreadPool(void)
0x18001b916  mov     ebx, eax
0x18001b918  test    eax, eax
0x18001b91a  jz      short loc_18001B96E
0x18001b91c  mov     esi, 8
0x18001b921  test    cs:byte_1800C8404, sil
0x18001b928  jz      short loc_18001B90A
0x18001b92a  mov     word ptr [rsp+1878h+var_848], di
0x18001b932  mov     r8d, eax
0x18001b935  lea     rdx, aDdmserviceinit_20; "DDMServiceInitialize: InitSerializedThr"...
0x18001b93c  lea     rcx, [rsp+1878h+var_848]
0x18001b944  call    FormatRRASErrorString
0x18001b949  test    cs:byte_1800C8404, sil
0x18001b950  jz      short loc_18001B90A
0x18001b952  lea     rax, [rsp+1878h+var_848]
0x18001b95a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b95e  xor     edx, edx
0x18001b960  inc     rdi
0x18001b963  cmp     [rax+rdi*2], dx
0x18001b967  jnz     short loc_18001B960
0x18001b969  jmp     loc_18001B8C2
0x18001b96e  xor     r8d, r8d; dwMaximumSize
0x18001b971  xor     edx, edx; dwInitialSize
0x18001b973  xor     ecx, ecx; flOptions
0x18001b975  call    cs:__imp_HeapCreate
0x18001b97b  mov     cs:hHeap, rax
0x18001b982  test    rax, rax
0x18001b985  jnz     loc_18001BA3C
0x18001b98b  call    cs:__imp_GetLastError
0x18001b991  mov     ebx, eax
0x18001b993  mov     esi, 8
0x18001b998  xor     r15d, r15d
0x18001b99b  test    cs:byte_1800C8404, sil
0x18001b9a2  jz      loc_18001C124
0x18001b9a8  mov     word ptr [rsp+1878h+var_848], r15w
0x18001b9b1  mov     r8d, eax
0x18001b9b4  lea     rdx, aDdmserviceinit_9; "DDMServiceInitialize: Heap creation fai"...
0x18001b9bb  lea     rcx, [rsp+1878h+var_848]
0x18001b9c3  call    FormatRRASErrorString
0x18001b9c8  test    cs:byte_1800C8404, sil
0x18001b9cf  jz      loc_18001C124
0x18001b9d5  lea     rcx, [rsp+1878h+var_848]
0x18001b9dd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b9e1  mov     rax, rdi
0x18001b9e4  inc     rax
0x18001b9e7  cmp     [rcx+rax*2], r15w
0x18001b9ec  jnz     short loc_18001B9E4
0x18001b9ee  lea     rdx, RasDdmTraceError
0x18001b9f5  lea     eax, ds:2[rax*2]
0x18001b9fc  mov     dword ptr [rsp+1878h+var_850], eax
0x18001ba03  lea     rax, [rsp+1878h+Buf1]
0x18001ba0b  lea     rcx, [rsp+1878h+var_848]
0x18001ba13  mov     r9d, r14d
0x18001ba16  mov     [rsp+1878h+plpszSubStringArray], rax
0x18001ba1b  mov     dword ptr [rsp+1878h+var_850+4], r15d
0x18001ba23  mov     [rsp+1878h+var_858], rcx
0x18001ba2b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ba32  call    McGenEventWrite_EventWriteTransfer
0x18001ba37  jmp     loc_18001D7AB
0x18001ba3c  mov     dword ptr cs:gblMediaTable+4, 5
0x18001ba46  mov     esi, 8
0x18001ba4b  mov     r8d, 0C8h; dwBytes
0x18001ba51  mov     edx, esi; dwFlags
0x18001ba53  mov     rcx, rax; hHeap
0x18001ba56  call    cs:__imp_HeapAlloc
0x18001ba5c  mov     qword ptr cs:gblMediaTable+8, rax
0x18001ba63  test    rax, rax
0x18001ba66  jnz     short loc_18001BA72
0x18001ba68  call    cs:__imp_GetLastError
0x18001ba6e  mov     ebx, eax
0x18001ba70  jmp     short loc_18001BA74
0x18001ba72  mov     ebx, edi
0x18001ba74  test    ebx, ebx
0x18001ba76  jz      loc_18001BB52
0x18001ba7c  xor     r15d, r15d
0x18001ba7f  test    cs:byte_1800C8404, sil
0x18001ba86  jz      loc_18001BB19
0x18001ba8c  mov     word ptr [rsp+1878h+var_848], r15w
0x18001ba95  mov     r8d, ebx
0x18001ba98  lea     rdx, aDdmserviceinit_5; "DDMServiceInitialize: Media object  cre"...
0x18001ba9f  lea     rcx, [rsp+1878h+var_848]
0x18001baa7  call    FormatRRASErrorString
0x18001baac  test    cs:byte_1800C8404, sil
0x18001bab3  jz      short loc_18001BB19
0x18001bab5  lea     rcx, [rsp+1878h+var_848]
0x18001babd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bac1  mov     rax, rdi
0x18001bac4  inc     rax
0x18001bac7  cmp     [rcx+rax*2], r15w
0x18001bacc  jnz     short loc_18001BAC4
0x18001bace  lea     rdx, RasDdmTraceError
0x18001bad5  lea     eax, ds:2[rax*2]
0x18001badc  mov     dword ptr [rsp+1878h+var_850], eax
0x18001bae3  lea     rax, [rsp+1878h+Buf1]
0x18001baeb  lea     rcx, [rsp+1878h+var_848]
0x18001baf3  mov     r9d, r14d
0x18001baf6  mov     [rsp+1878h+plpszSubStringArray], rax
0x18001bafb  mov     dword ptr [rsp+1878h+var_850+4], r15d
0x18001bb03  mov     [rsp+1878h+var_858], rcx
0x18001bb0b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001bb12  call    McGenEventWrite_EventWriteTransfer
0x18001bb17  jmp     short loc_18001BB1D
0x18001bb19  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bb1d  cmp     cs:dword_1800C84E4, r15d
0x18001bb24  jbe     loc_18001D7AB
0x18001bb2a  mov     [rsp+1878h+dwErrorCode], ebx; dwErrorCode
0x18001bb2e  mov     [rsp+1878h+plpszSubStringArray], r15; plpszSubStringArray
0x18001bb33  xor     r9d, r9d; dwSubStringCount
0x18001bb36  lea     edx, [r9+1]; dwEventType
0x18001bb3a  mov     r8d, 4E88h; dwMessageId
0x18001bb40  mov     rcx, cs:hLogHandle; hLogHandle
0x18001bb47  call    cs:__imp_RouterLogEventW
0x18001bb4d  jmp     loc_18001D7AB
0x18001bb52  lea     r8, MPRDDM_EVENT_SOURCE_Context
0x18001bb59  mov     r9, r8
0x18001bb5c  lea     rcx, MPRDDM_EVENT_SOURCE
0x18001bb63  call    McGenEventRegister_EventRegister
0x18001bb68  or      cs:dword_1800C84E0, 10h
0x18001bb6f  lea     rcx, SRWLock; SRWLock
0x18001bb76  call    cs:__imp_InitializeSRWLock
0x18001bb7c  cmp     [r12+70h], edi
0x18001bb81  jz      loc_18001BC5D
0x18001bb87  call    cs:__imp_SetupSstpServerConfig
0x18001bb8d  mov     ebx, eax
0x18001bb8f  test    eax, eax
0x18001bb91  jz      short loc_18001BBEE
0x18001bb93  xor     r15d, r15d
  ... truncated ...
```
