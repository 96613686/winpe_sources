# ProcessDhcpRequestForever

- ea: `0x180023928`
- end: `0x180024481`
- name: `ProcessDhcpRequestForever`
- size: `2905`
- prototype: `__int64 __fastcall(int, __int64, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025350`

## callees

- `0x180005f28`
- `0x180007294`
- `0x180009038`
- `0x180009580`
- `0x18000a100`
- `0x18000eafc`
- `0x18001067c`
- `0x180011388`
- `0x1800147e4`
- `0x180014f80`
- `0x18001953c`
- `0x18001a92c`
- `0x18001b9b8`
- `0x18001cef0`
- `0x18001eb68`
- `0x18001f100`
- `0x180022fb0`
- `0x180023928`
- `0x1800249ec`
- `0x1800429cc`
- `0x180045ffc`
- `0x180046098`
- `0x180046794`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `ntdll!RtlxUnicodeStringToOemSize` at `0x180024165`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x180024165`
- `ntdll!RtlInitUnicodeString` at `0x180024157`
- `ntdll!RtlInitUnicodeString` at `0x180024157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002412a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002412a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023be2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023be2`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180023ec9`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180023ec9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180023fc7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180023fc7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023a34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023c95`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023a34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023c95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002446c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002446c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002443f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002443f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023e54`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800240f2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023e54`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800240f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002439c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002439c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023d50`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023d50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800242ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800242ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002410e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002410e`
- `RPCRT4!RpcBindingVectorFree` at `0x180023b0a`
- `RPCRT4!RpcBindingVectorFree` at `0x180023b0a`
- `RPCRT4!RpcServerInqBindings` at `0x180023ae6`
- `RPCRT4!RpcServerInqBindings` at `0x180023ae6`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180023b25`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180023b25`
- `RPCRT4!RpcEpUnregister` at `0x180023aff`
- `RPCRT4!RpcEpUnregister` at `0x180023aff`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180023c3b`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180023c3b`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180023b42`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180023b42`

## pseudocode

```c
__int64 __fastcall ProcessDhcpRequestForever(int a1, __int64 a2, int a3)
{
  RPC_BINDING_VECTOR *v3; // rsi
  __int64 v4; // rbx
  int v5; // r15d
  int v6; // r12d
  __int64 v7; // rcx
  unsigned int started; // edi
  unsigned int inited; // eax
  DWORD v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int v17; // eax
  DWORD LastError; // eax
  __int64 v19; // rcx
  DWORD v20; // edi
  __int64 v21; // rcx
  DWORD v22; // r13d
  DWORD v23; // esi
  unsigned int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // edi
  RPC_BINDING_VECTOR *v27; // r12
  DWORD v28; // eax
  DWORD v29; // edi
  __int64 v30; // rcx
  __int64 v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // edi
  DWORD v34; // eax
  __int64 v35; // rcx
  int v36; // r8d
  DWORD v37; // edi
  unsigned int v38; // r13d
  __int64 v39; // rdx
  __int64 v40; // r9
  char v41; // al
  DWORD v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  int v46; // r8d
  LPVOID *v47; // rdi
  int v48; // ebx
  LPVOID *v49; // rcx
  LPVOID *i; // rbx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v52; // [rsp+48h] [rbp-F0h]
  int v53; // [rsp+4Ch] [rbp-ECh]
  unsigned int v54; // [rsp+50h] [rbp-E8h]
  unsigned int v55; // [rsp+54h] [rbp-E4h]
  int v56; // [rsp+58h] [rbp-E0h]
  int v57; // [rsp+5Ch] [rbp-DCh]
  DWORD nSize; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v59; // [rsp+64h] [rbp-D4h] BYREF
  __int64 v60; // [rsp+6Ch] [rbp-CCh] BYREF
  int v61; // [rsp+74h] [rbp-C4h]
  int v62; // [rsp+78h] [rbp-C0h] BYREF
  NET_IF_COMPARTMENT_SCOPE CompartmentScope; // [rsp+7Ch] [rbp-BCh] BYREF
  __int64 v64; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+88h] [rbp-B0h] BYREF
  HANDLE NotificationHandle; // [rsp+90h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-A0h] BYREF
  HANDLE Handles[2]; // [rsp+A8h] [rbp-90h] BYREF
  __int128 v69; // [rsp+B8h] [rbp-80h]
  RPC_BINDING_VECTOR *v70; // [rsp+C8h] [rbp-70h]
  _BYTE v71[16]; // [rsp+D0h] [rbp-68h] BYREF
  _BYTE v72[16]; // [rsp+E0h] [rbp-58h] BYREF
  _BYTE v73[16]; // [rsp+F0h] [rbp-48h] BYREF

  v61 = 0;
  nSize = 0;
  v3 = 0;
  NotificationHandle = 0;
  v4 = 0;
  CompartmentScope = 0;
  *(_OWORD *)Handles = 0;
  v70 = 0;
  v5 = 0;
  v62 = 0;
  v6 = a1;
  v69 = 0;
  BindingVector = 0;
  v64 = 0;
  v59 = 0;
  v65 = 0;
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      a1,
      (unsigned int)ProcessDHCPRequestForever,
      a3,
      1,
      (__int64)&DestinationString);
  started = DhcpSetThreadCompartmentScopeAll(&CompartmentScope, &v62);
  if ( started )
    goto LABEL_15;
  inited = DhcpInitNSIMediaSense();
  started = inited;
  if ( inited )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 10, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, inited);
    if ( started == 50 )
    {
      v10 = WaitForSingleObject(DhcpGlobalServiceSyncEvent, 0xFFFFFFFF);
      started = v10;
      if ( v10 )
      {
        if ( (xmmword_1800616A0 & 2) == 0 )
          goto LABEL_19;
        v11 = 134;
        goto LABEL_11;
      }
      DhcpGlobalServiceStatus.dwCurrentState = 4;
      UpdateStatus();
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        WPP_SF_(1028, 135, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
        v5 = 0;
      }
      started = 1168;
    }
    goto LABEL_15;
  }
  v61 = 1;
  v17 = NotifyUnicastIpAddressChange(2u, DhcpUnicastAddressChangeCallback, 0, 0, &NotificationHandle);
  started = v17;
  if ( v17 )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
    {
LABEL_17:
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v7, ProcessDHCPRequestForeverFailed, started);
      goto LABEL_19;
    }
    WPP_SF_D(1025, 136, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v17);
LABEL_15:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 161, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, started);
    goto LABEL_17;
  }
  v5 = 1;
  v57 = 1;
  started = DhcpStartRPCServer();
  if ( started )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_15;
  }
  v10 = WaitForSingleObject(DhcpGlobalServiceSyncEvent, 0xFFFFFFFF);
  started = v10;
  if ( v10 )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_19;
    v11 = 137;
LABEL_11:
    WPP_SF_D(1025, v11, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v10);
    goto LABEL_19;
  }
  v54 = 0;
  v52 = 0;
  DhcpGlobalServiceStatus.dwCurrentState = 4;
  UpdateStatus();
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 138, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  Handles[1] = DhcpGlobalRecomputeTimerEvent;
  Handles[0] = DhcpGlobalTerminateEvent;
  *(_QWORD *)&v69 = DhcpGlobalRefreshEvent;
  *((_QWORD *)&v69 + 1) = DhcpLsaDnsDomChangeNotifyHandle;
  v56 = 0;
  v55 = 0;
  v53 = 0;
  if ( (unsigned int)CheckIfSystemSupportsAOAC() )
  {
    BindingVector = (RPC_BINDING_VECTOR *)CreateEventW(0, 1, 0, 0);
    v3 = BindingVector;
    if ( !BindingVector )
    {
      LastError = GetLastError();
      v20 = LastError;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_d(1025, 139, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError);
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v19, CreateRenewalSignalHandleFailed, v20);
    }
  }
  while ( 1 )
  {
    v21 = v52;
    if ( v3 )
      v21 = 1;
    v52 = v21;
    v22 = 4;
    if ( v6 == -1 )
    {
      v23 = -1;
    }
    else
    {
      v23 = 1000 * v6;
      if ( 1000 * v6 / 0x3E8u != v6 )
        v23 = -2;
    }
    if ( !(_DWORD)v21 )
    {
      v26 = 0;
LABEL_70:
      v27 = BindingVector;
      goto LABEL_79;
    }
    if ( v64 )
    {
      v24 = DeleteRenewTimer(&v64);
      v25 = v24;
      if ( v24 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_d(1025, 140, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v24);
        if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v21, DeleteRenewTimerFailed, v25);
        v26 = 0;
        v52 = 0;
        goto LABEL_70;
      }
    }
    v27 = BindingVector;
    if ( ResetEvent(BindingVector) )
    {
      v26 = v52;
    }
    else
    {
      v28 = GetLastError();
      v29 = v28;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_d(1025, 141, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v28);
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v21, ResetRenewalSignalHandleFailed, v29);
      v26 = 0;
      v52 = 0;
    }
LABEL_79:
    if ( v55 == -1 )
      CancelWaitableTimer(DhcpGlobalWaitableTimerHandle);
    else
      DhcpStartWaitableTimer(v21, v55);
    if ( g_fVelocityDhcpv4InformNegativeCacheFix )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_d(1028, 142, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v23);
    }
    else if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_d(1028, 143, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v23);
    }
    if ( v26 )
    {
      v32 = CreateRenewTimer(v23, v27, v31, &v64);
      v33 = v32;
      if ( v32 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_d(1025, 144, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v32);
        if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v30, CreateRenewTimerFailed, v33);
        v52 = 0;
      }
      else
      {
        v23 = -1;
        v70 = v27;
        v22 = 5;
      }
    }
    if ( g_fVelocityDhcpMainThreadSleepTracing )
    {
      SetPreSleepMainThreadInfo(v30, v23, v54, &v65);
      v4 = v65;
    }
    v34 = WaitForMultipleObjectsEx(v22, Handles, 0, v23, 0);
    v37 = v34;
    if ( g_fVelocityDhcpMainThreadSleepTracing )
    {
      SetPostSleepMainThreadInfo(v35, v4, v34);
      v38 = 0;
      v54 = 0;
    }
    else
    {
      v38 = v54;
    }
    v6 = 0;
    if ( !v37 )
      break;
    switch ( v37 )
    {
      case 1u:
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          v45 = 149;
          goto LABEL_136;
        }
LABEL_137:
        v6 = -1;
        v55 = -1;
        v60 = -1;
        if ( (unsigned int)DhcpIsFSEGuestSystem() )
        {
          v3 = BindingVector;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
          {
            v43 = 152;
LABEL_140:
            v44 = 1028;
LABEL_141:
            WPP_SF_(v44, v43, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
          }
        }
        else if ( DhcpGlobalDsFeatureEnabled || !(unsigned int)DhcpIsMachineInDs() )
        {
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_(1028, 154, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
          if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(
              1,
              (unsigned int)ProcessDHCPRequestForeverWaitTimeout,
              v46,
              1,
              (__int64)v72);
          if ( v53 )
          {
            HandleFailedRenewals();
            v53 = 0;
          }
          GetTickCount64();
          EnterCriticalSection(&DhcpGlobalNicListCritSect);
          v47 = (LPVOID *)DhcpGlobalConnectedNICList;
          if ( DhcpGlobalConnectedNICList != &DhcpGlobalConnectedNICList )
          {
            v48 = v53;
            do
            {
              v49 = v47;
              v47 = (LPVOID *)*v47;
              if ( g_fVelocityDhcpMainThreadSleepTracing )
                ++v38;
              ProcessSingleContext(v49, (__int64)&v60, (__int64)&v59, (__int64)&v59 + 4);
              if ( (_DWORD)v59 )
                v48 = 1;
              if ( HIDWORD(v59) )
                SetEvent(DhcpGlobalRecomputeTimerEvent);
            }
            while ( v47 != &DhcpGlobalConnectedNICList );
            v6 = v60;
            v53 = v48;
            v4 = v65;
            v55 = HIDWORD(v60);
            v54 = v38;
          }
          v56 = 0;
          LeaveCriticalSection(&DhcpGlobalNicListCritSect);
          v3 = BindingVector;
        }
        else
        {
          v3 = BindingVector;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
          {
            v43 = 153;
            goto LABEL_140;
          }
        }
        break;
      case 2u:
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_(1028, 145, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
        ResetEvent(DhcpGlobalRefreshEvent);
        nSize = 64;
        if ( GetComputerNameExW(ComputerNameNetBIOS, &DhcpGlobalHostNameW, &nSize) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, &DhcpGlobalHostNameW);
          if ( (unsigned __int16)RtlxUnicodeStringToOemSize(&DestinationString) < 0x80u )
          {
            DhcpUnicodeToOem(&DhcpGlobalHostNameW);
LABEL_126:
            if ( Microsoft_Windows_Dhcp_ClientEnableBits < 0 )
              McGenEventWrite_EtwEventWriteTransfer(v35, (unsigned int)DomainChangeNotification, v36, 1, (__int64)v71);
            v56 = 1;
            goto LABEL_137;
          }
          v3 = BindingVector;
          if ( (xmmword_1800616A0 & 2) != 0 )
          {
            v43 = 147;
            v44 = 1025;
            goto LABEL_141;
          }
        }
        else
        {
          v3 = BindingVector;
          if ( (xmmword_1800616A0 & 2) != 0 )
          {
            v42 = GetLastError();
            v39 = 146;
            goto LABEL_121;
          }
        }
        break;
      case 3u:
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_(1028, 148, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
        goto LABEL_126;
      case 4u:
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_(1028, 150, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
        goto LABEL_137;
      case 0x102u:
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          v45 = 151;
LABEL_136:
          WPP_SF_(1028, v45, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
          goto LABEL_137;
        }
        goto LABEL_137;
      case 0xFFFFFFFF:
        v41 = xmmword_1800616A0;
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          WPP_SF_(1028, 156, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
          v41 = xmmword_1800616A0;
        }
        v3 = BindingVector;
        if ( (v41 & 2) != 0 )
        {
          v42 = GetLastError();
          v39 = 157;
LABEL_121:
          v40 = v42;
LABEL_109:
          WPP_SF_D(1025, v39, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v40);
        }
        break;
      default:
        v3 = BindingVector;
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v39 = 158;
          v40 = v37;
          goto LABEL_109;
        }
        break;
    }
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 155, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v35, (unsigned int)ServiceSetsTerminateEvent, v36, 1, (__int64)v73);
  started = 0;
  EnterCriticalSection(&DhcpGlobalNicListCritSect);
  for ( i = (LPVOID *)DhcpGlobalConnectedNICList; i != &DhcpGlobalConnectedNICList; i = (LPVOID *)*i )
    CancelRenew(i);
  LeaveCriticalSection(&DhcpGlobalNicListCritSect);
  v3 = BindingVector;
  v5 = v57;
LABEL_19:
  if ( DhcpGlobalRpcServUp )
  {
    BindingVector = 0;
    if ( !RpcServerInqBindings(&BindingVector) )
    {
      RpcEpUnregister(qword_180052910, BindingVector, 0);
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
    RpcServerUnregisterIfEx(qword_180052910, 0, 0);
    DhcpGlobalRpcServUp = 0;
  }
  if ( v5 )
  {
    v12 = CancelMibChangeNotify2(NotificationHandle);
    if ( v12 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 159, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v12);
    }
  }
  if ( v61 )
    DhcpDeInitNSIMediaSense();
  if ( v62 )
    DhcpRevertThreadCompartmentScope(CompartmentScope);
  if ( v64 )
  {
    v13 = DeleteRenewTimer(&v64);
    v15 = v13;
    if ( v13 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_d(1025, 160, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v13);
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v14, DeleteRenewTimerFailed, v15);
    }
  }
  if ( v3 )
    CloseHandle(v3);
  return started;
}

```

## disassembly

```asm
0x180023928  mov     r11, rsp
0x18002392b  mov     [r11+10h], rbx
0x18002392f  mov     [r11+18h], rsi
0x180023933  push    rdi
0x180023934  push    r12
0x180023936  push    r13
0x180023938  push    r14
0x18002393a  push    r15
0x18002393c  sub     rsp, 110h
0x180023943  mov     rax, cs:__security_cookie
0x18002394a  xor     rax, rsp
0x18002394d  mov     [rsp+138h+var_38], rax
0x180023955  xor     eax, eax
0x180023957  mov     [rsp+138h+var_C4], 0
0x18002395f  xorps   xmm0, xmm0
0x180023962  mov     [rsp+138h+nSize], eax
0x180023966  xor     esi, esi
0x180023968  mov     [r11-0A8h], rax
0x18002396f  xor     ebx, ebx
0x180023971  mov     [rsp+138h+CompartmentScope], eax
0x180023975  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18002397d  lea     r14d, [rax+1]
0x180023981  mov     [r11-70h], rax
0x180023985  xor     r15d, r15d
0x180023988  mov     [rsp+138h+var_C0], eax
0x18002398c  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, r14b
0x180023993  mov     r12d, ecx
0x180023996  movups  xmmword ptr [r11-80h], xmm0
0x18002399b  mov     [rsp+138h+BindingVector], rsi
0x1800239a0  mov     [r11-0B8h], rax
0x1800239a7  mov     dword ptr [rsp+138h+var_D4], eax
0x1800239ab  mov     dword ptr [rsp+138h+var_D4+4], eax
0x1800239af  mov     [rsp+138h+var_B0], rbx
0x1800239b7  jz      short loc_1800239D4
0x1800239b9  lea     rax, [r11-0A0h]
0x1800239c0  mov     r9d, r14d
0x1800239c3  lea     rdx, ProcessDHCPRequestForever
0x1800239ca  mov     qword ptr [rsp+138h+bAlertable], rax
0x1800239cf  call    McGenEventWrite_EtwEventWriteTransfer
0x1800239d4  lea     rdx, [rsp+138h+var_C0]
0x1800239d9  lea     rcx, [rsp+138h+CompartmentScope]
0x1800239de  call    DhcpSetThreadCompartmentScopeAll
0x1800239e3  lea     r13, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800239ea  mov     edi, eax
0x1800239ec  test    eax, eax
0x1800239ee  jnz     loc_180023A99
0x1800239f4  call    DhcpInitNSIMediaSense
0x1800239f9  mov     edi, eax
0x1800239fb  test    eax, eax
0x1800239fd  jz      loc_180023C17
0x180023a03  test    byte ptr cs:xmmword_1800616A0, 2
0x180023a0a  jz      short loc_180023A25
0x180023a0c  mov     edx, 0Ah
0x180023a11  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180023a18  mov     ecx, 401h
0x180023a1d  mov     r9d, eax
0x180023a20  call    WPP_SF_D
0x180023a25  cmp     edi, 32h ; '2'
0x180023a28  jnz     short loc_180023A99
0x180023a2a  mov     rcx, cs:DhcpGlobalServiceSyncEvent; hHandle
0x180023a31  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023a34  call    cs:__imp_WaitForSingleObject
0x180023a3a  mov     edi, eax
0x180023a3c  test    eax, eax
0x180023a3e  jz      short loc_180023A64
0x180023a40  test    byte ptr cs:xmmword_1800616A0, 2
0x180023a47  jz      loc_180023ACF
0x180023a4d  mov     edx, 86h
0x180023a52  mov     ecx, 401h
0x180023a57  mov     r9d, eax
0x180023a5a  mov     r8, r13
0x180023a5d  call    WPP_SF_D
0x180023a62  jmp     short loc_180023ACF
0x180023a64  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 4
0x180023a6e  call    UpdateStatus
0x180023a73  mov     r14b, 10h
0x180023a76  test    byte ptr cs:xmmword_1800616A0, r14b
0x180023a7d  jz      short loc_180023A94
0x180023a7f  mov     edx, 87h
0x180023a84  mov     ecx, 404h
0x180023a89  mov     r8, r13
0x180023a8c  call    WPP_SF_
0x180023a91  mov     r15d, ebx
0x180023a94  mov     edi, 490h
0x180023a99  test    byte ptr cs:xmmword_1800616A0, 2
0x180023aa0  jz      short loc_180023AB7
0x180023aa2  mov     edx, 0A1h
0x180023aa7  mov     ecx, 401h
0x180023aac  mov     r9d, edi
0x180023aaf  mov     r8, r13
0x180023ab2  call    WPP_SF_D
0x180023ab7  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 4
0x180023abe  jz      short loc_180023ACF
0x180023ac0  mov     r8d, edi
0x180023ac3  lea     rdx, ProcessDHCPRequestForeverFailed
0x180023aca  call    McTemplateU0q_EtwEventWriteTransfer
0x180023acf  cmp     cs:DhcpGlobalRpcServUp, 0
0x180023ad6  jz      short loc_180023B35
0x180023ad8  lea     rcx, [rsp+138h+BindingVector]; BindingVector
0x180023add  mov     [rsp+138h+BindingVector], 0
0x180023ae6  call    cs:__imp_RpcServerInqBindings
0x180023aec  test    eax, eax
0x180023aee  jnz     short loc_180023B19
0x180023af0  mov     rdx, [rsp+138h+BindingVector]; BindingVector
0x180023af5  lea     rcx, qword_180052910; IfSpec
0x180023afc  xor     r8d, r8d; UuidVector
0x180023aff  call    cs:__imp_RpcEpUnregister
0x180023b05  lea     rcx, [rsp+138h+BindingVector]; BindingVector
0x180023b0a  call    cs:__imp_RpcBindingVectorFree
0x180023b10  mov     [rsp+138h+BindingVector], 0
0x180023b19  xor     r8d, r8d; RundownContextHandles
0x180023b1c  lea     rcx, qword_180052910; IfSpec
0x180023b23  xor     edx, edx; MgrTypeUuid
0x180023b25  call    cs:__imp_RpcServerUnregisterIfEx
0x180023b2b  mov     cs:DhcpGlobalRpcServUp, 0
0x180023b35  test    r15d, r15d
0x180023b38  jz      short loc_180023B6A
0x180023b3a  mov     rcx, [rsp+138h+NotificationHandle]; NotificationHandle
0x180023b42  call    cs:__imp_CancelMibChangeNotify2
0x180023b48  test    eax, eax
0x180023b4a  jz      short loc_180023B6A
0x180023b4c  test    byte ptr cs:xmmword_1800616A0, 2
0x180023b53  jz      short loc_180023B6A
0x180023b55  mov     edx, 9Fh
0x180023b5a  mov     ecx, 401h
0x180023b5f  mov     r9d, eax
0x180023b62  mov     r8, r13
0x180023b65  call    WPP_SF_D
0x180023b6a  cmp     [rsp+138h+var_C4], 0
0x180023b6f  jz      short loc_180023B76
0x180023b71  call    DhcpDeInitNSIMediaSense
0x180023b76  cmp     [rsp+138h+var_C0], 0
0x180023b7b  jz      short loc_180023B86
0x180023b7d  mov     ecx, [rsp+138h+CompartmentScope]; CompartmentScope
0x180023b81  call    DhcpRevertThreadCompartmentScope
0x180023b86  cmp     [rsp+138h+var_B8], 0
0x180023b8f  jz      short loc_180023BDA
0x180023b91  lea     rcx, [rsp+138h+var_B8]
0x180023b99  call    DeleteRenewTimer
0x180023b9e  mov     ebx, eax
0x180023ba0  test    eax, eax
0x180023ba2  jz      short loc_180023BDA
0x180023ba4  test    byte ptr cs:xmmword_1800616A0, 2
0x180023bab  jz      short loc_180023BC2
0x180023bad  mov     edx, 0A0h
0x180023bb2  mov     ecx, 401h
0x180023bb7  mov     r9d, eax
0x180023bba  mov     r8, r13
0x180023bbd  call    WPP_SF_d
0x180023bc2  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 4
0x180023bc9  jz      short loc_180023BDA
0x180023bcb  mov     r8d, ebx
0x180023bce  lea     rdx, DeleteRenewTimerFailed
0x180023bd5  call    McTemplateU0q_EtwEventWriteTransfer
0x180023bda  test    rsi, rsi
0x180023bdd  jz      short loc_180023BE8
0x180023bdf  mov     rcx, rsi; hObject
0x180023be2  call    cs:__imp_CloseHandle
0x180023be8  mov     eax, edi
0x180023bea  mov     rcx, [rsp+138h+var_38]
0x180023bf2  xor     rcx, rsp; StackCookie
0x180023bf5  call    __security_check_cookie
0x180023bfa  lea     r11, [rsp+138h+var_28]
0x180023c02  mov     rbx, [r11+38h]
0x180023c06  mov     rsi, [r11+40h]
0x180023c0a  mov     rsp, r11
0x180023c0d  pop     r15
0x180023c0f  pop     r14
0x180023c11  pop     r13
0x180023c13  pop     r12
0x180023c15  pop     rdi
0x180023c16  retn
0x180023c17  lea     rax, [rsp+138h+NotificationHandle]
0x180023c1f  mov     [rsp+138h+var_C4], r14d
0x180023c24  mov     ecx, 2; Family
0x180023c29  mov     qword ptr [rsp+138h+bAlertable], rax; NotificationHandle
0x180023c2e  xor     r9d, r9d; InitialNotification
0x180023c31  lea     rdx, DhcpUnicastAddressChangeCallback; Callback
0x180023c38  xor     r8d, r8d; CallerContext
0x180023c3b  call    cs:__imp_NotifyUnicastIpAddressChange
0x180023c41  mov     edi, eax
0x180023c43  test    eax, eax
0x180023c45  jz      short loc_180023C6E
0x180023c47  test    byte ptr cs:xmmword_1800616A0, 2
0x180023c4e  jz      loc_180023AB7
0x180023c54  mov     edx, 88h
0x180023c59  mov     ecx, 401h
0x180023c5e  mov     r9d, eax
0x180023c61  mov     r8, r13
0x180023c64  call    WPP_SF_D
0x180023c69  jmp     loc_180023A99
0x180023c6e  mov     r15d, r14d
0x180023c71  mov     [rsp+138h+var_DC], r14d
0x180023c76  call    DhcpStartRPCServer
0x180023c7b  mov     edi, eax
0x180023c7d  test    eax, eax
0x180023c7f  jz      short loc_180023C8B
0x180023c81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023c86  jmp     loc_180023A99
0x180023c8b  mov     rcx, cs:DhcpGlobalServiceSyncEvent; hHandle
0x180023c92  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023c95  call    cs:__imp_WaitForSingleObject
0x180023c9b  mov     edi, eax
0x180023c9d  test    eax, eax
0x180023c9f  jz      short loc_180023CB8
0x180023ca1  test    byte ptr cs:xmmword_1800616A0, 2
0x180023ca8  jz      loc_180023ACF
0x180023cae  mov     edx, 89h
0x180023cb3  jmp     loc_180023A52
0x180023cb8  xor     edi, edi
0x180023cba  mov     [rsp+138h+var_E8], ebx
0x180023cbe  mov     [rsp+138h+var_F0], edi
0x180023cc2  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 4
0x180023ccc  call    UpdateStatus
0x180023cd1  mov     r14b, 10h
0x180023cd4  mov     r15d, 404h
0x180023cda  test    byte ptr cs:xmmword_1800616A0, r14b
0x180023ce1  jz      short loc_180023CF3
0x180023ce3  mov     edx, 8Ah
0x180023ce8  mov     ecx, r15d
0x180023ceb  mov     r8, r13
0x180023cee  call    WPP_SF_
0x180023cf3  mov     rax, cs:DhcpGlobalRecomputeTimerEvent
0x180023cfa  mov     [rsp+138h+Handles+8], rax
0x180023d02  mov     rax, cs:DhcpGlobalTerminateEvent
0x180023d09  mov     [rsp+138h+Handles], rax
0x180023d11  mov     rax, cs:DhcpGlobalRefreshEvent
0x180023d18  mov     [rsp+138h+var_80], rax
0x180023d20  mov     rax, cs:DhcpLsaDnsDomChangeNotifyHandle
0x180023d27  mov     [rsp+138h+var_78], rax
0x180023d2f  mov     [rsp+138h+var_E0], ebx
0x180023d33  mov     [rsp+138h+var_E4], ebx
0x180023d37  mov     [rsp+138h+var_EC], ebx
0x180023d3b  call    CheckIfSystemSupportsAOAC
0x180023d40  test    eax, eax
0x180023d42  jz      short loc_180023DA1
0x180023d44  xor     r9d, r9d; lpName
0x180023d47  xor     r8d, r8d; bInitialState
0x180023d4a  xor     ecx, ecx; lpEventAttributes
0x180023d4c  lea     edx, [r9+1]; bManualReset
0x180023d50  call    cs:__imp_CreateEventW
0x180023d56  mov     [rsp+138h+BindingVector], rax
0x180023d5b  mov     rsi, rax
0x180023d5e  test    rax, rax
0x180023d61  jnz     short loc_180023DA1
0x180023d63  call    cs:__imp_GetLastError
0x180023d69  mov     edi, eax
0x180023d6b  test    byte ptr cs:xmmword_1800616A0, 2
0x180023d72  jz      short loc_180023D89
0x180023d74  mov     edx, 8Bh
0x180023d79  mov     ecx, 401h
0x180023d7e  mov     r9d, eax
0x180023d81  mov     r8, r13
0x180023d84  call    WPP_SF_d
0x180023d89  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 4
0x180023d90  jz      short loc_180023DA1
0x180023d92  mov     r8d, edi
0x180023d95  lea     rdx, CreateRenewalSignalHandleFailed
0x180023d9c  call    McTemplateU0q_EtwEventWriteTransfer
0x180023da1  mov     ecx, [rsp+138h+var_F0]
0x180023da5  test    rsi, rsi
0x180023da8  mov     eax, 1
0x180023dad  cmovnz  ecx, eax
0x180023db0  mov     [rsp+138h+var_F0], ecx
0x180023db4  lea     r13d, [rax+3]
0x180023db8  cmp     r12d, 0FFFFFFFFh
0x180023dbc  jnz     short loc_180023DC3
0x180023dbe  or      esi, r12d
0x180023dc1  jmp     short loc_180023DDF
0x180023dc3  imul    esi, r12d, 3E8h
0x180023dca  mov     eax, 10624DD3h
0x180023dcf  mul     esi
0x180023dd1  mov     eax, 0FFFFFFFEh
0x180023dd6  shr     edx, 6
0x180023dd9  cmp     edx, r12d
0x180023ddc  cmovnz  esi, eax
0x180023ddf  test    ecx, ecx
0x180023de1  jz      loc_180023EA8
0x180023de7  cmp     [rsp+138h+var_B8], 0
0x180023df0  jz      short loc_180023E4C
0x180023df2  lea     rcx, [rsp+138h+var_B8]
0x180023dfa  call    DeleteRenewTimer
0x180023dff  mov     edi, eax
0x180023e01  test    eax, eax
0x180023e03  jz      short loc_180023E4C
0x180023e05  test    byte ptr cs:xmmword_1800616A0, 2
0x180023e0c  jz      short loc_180023E27
0x180023e0e  mov     edx, 8Ch
0x180023e13  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180023e1a  mov     ecx, 401h
0x180023e1f  mov     r9d, eax
0x180023e22  call    WPP_SF_d
0x180023e27  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, r13b
0x180023e2e  jz      short loc_180023E3F
0x180023e30  mov     r8d, edi
0x180023e33  lea     rdx, DeleteRenewTimerFailed
0x180023e3a  call    McTemplateU0q_EtwEventWriteTransfer
0x180023e3f  xor     edi, edi
0x180023e41  mov     [rsp+138h+var_F0], edi
0x180023e45  mov     r12, [rsp+138h+BindingVector]
  ... truncated ...
```
