# DiscpCleanupService

- ea: `0x180012510`
- end: `0x180012a11`
- name: `DiscpCleanupService`
- size: `1281`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013ae0`
- `0x180013b24`

## callees

- `0x180007900`
- `0x18000bfc4`
- `0x180012510`
- `0x180016c48`
- `0x18001e010`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x1800126ff`
- `ISCSIUM!DiscpFreeMemory` at `0x1800127fb`
- `ISCSIUM!DiscpFreeMemory` at `0x18001289e`
- `ISCSIUM!DiscpFreeMemory` at `0x180012974`
- `ISCSIUM!DiscpFreeMemory` at `0x1800126ff`
- `ISCSIUM!DiscpFreeMemory` at `0x1800127fb`
- `ISCSIUM!DiscpFreeMemory` at `0x18001289e`
- `ISCSIUM!DiscpFreeMemory` at `0x180012974`
- `ISCSIUM!DiscpDisableEventlog` at `0x180012a0a`
- `ISCSIUM!DiscpRegisterHeap` at `0x1800129bc`
- `ISCSIUM!DiscpRegisterHeap` at `0x1800129bc`
- `ISCSIUM!DiscpDisableWinsock` at `0x1800128fd`
- `ISCSIUM!DiscpDisableWinsock` at `0x1800128fd`
- `ntdll!RtlDestroyHeap` at `0x1800129ad`
- `ntdll!RtlDestroyHeap` at `0x1800129ad`
- `ntdll!RtlDeleteCriticalSection` at `0x1800129ce`
- `ntdll!RtlDeleteCriticalSection` at `0x1800129e4`
- `ntdll!RtlDeleteCriticalSection` at `0x1800129fa`
- `ntdll!RtlDeleteCriticalSection` at `0x1800129ce`
- `ntdll!RtlDeleteCriticalSection` at `0x1800129e4`
- `ntdll!RtlDeleteCriticalSection` at `0x1800129fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180012587`
- `ntdll!RtlLeaveCriticalSection` at `0x1800127b4`
- `ntdll!RtlLeaveCriticalSection` at `0x180012906`
- `ntdll!RtlLeaveCriticalSection` at `0x180012988`
- `ntdll!RtlLeaveCriticalSection` at `0x180012587`
- `ntdll!RtlLeaveCriticalSection` at `0x1800127b4`
- `ntdll!RtlLeaveCriticalSection` at `0x180012906`
- `ntdll!RtlLeaveCriticalSection` at `0x180012988`
- `ntdll!RtlEnterCriticalSection` at `0x180012565`
- `ntdll!RtlEnterCriticalSection` at `0x18001273a`
- `ntdll!RtlEnterCriticalSection` at `0x1800128f7`
- `ntdll!RtlEnterCriticalSection` at `0x180012939`
- `ntdll!RtlEnterCriticalSection` at `0x180012565`
- `ntdll!RtlEnterCriticalSection` at `0x18001273a`
- `ntdll!RtlEnterCriticalSection` at `0x1800128f7`
- `ntdll!RtlEnterCriticalSection` at `0x180012939`
- `WMICLNT!WmiNotificationRegistrationW` at `0x180012927`
- `WMICLNT!WmiNotificationRegistrationW` at `0x180012927`
- `RPCRT4!RpcServerUnregisterIf` at `0x180012533`
- `RPCRT4!RpcServerUnregisterIf` at `0x180012533`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012545`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012545`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x18001260c`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012625`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x18001263e`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012657`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012670`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012689`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x1800126a2`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x1800126bb`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x1800126d4`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x18001260c`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012625`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x18001263e`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012657`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012670`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180012689`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x1800126a2`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x1800126bb`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x1800126d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800126ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001287c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800126ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001287c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012596`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125be`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012596`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125be`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001257a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001257a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012852`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180012852`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800128d7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800128d7`
- `fwpuclnt!FwpmEngineClose0` at `0x1800128b7`
- `fwpuclnt!FwpmEngineClose0` at `0x1800128b7`

## pseudocode

```c
__int64 DiscpCleanupService()
{
  __int128 v0; // rax
  __int64 v1; // rax
  _QWORD *v2; // rbx
  _OWORD *v3; // rdi
  _OWORD *v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  int v7; // eax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rdi
  _OWORD v11[3]; // [rsp+30h] [rbp-38h] BYREF

  if ( DiscpRpcServerInitialized )
    RpcServerUnregisterIf(qword_18001FA80, 0, 1u);
  if ( DiscpAdministratorsGroup )
  {
    FreeSid(DiscpAdministratorsGroup);
    DiscpAdministratorsGroup = 0;
  }
  if ( DiscpInitiatorArrivalTimersCleared )
  {
    RtlEnterCriticalSection(&DiscpShutdownCritSection);
    if ( !DiscpInitiatorArrivalTimersActiveCount )
      SetEvent(DiscpInitiatorArrivalTimersCleared);
    RtlLeaveCriticalSection(&DiscpShutdownCritSection);
    WaitForSingleObject(DiscpInitiatorArrivalTimersCleared, 0xFFFFFFFF);
    CloseHandle(DiscpInitiatorArrivalTimersCleared);
    DiscpInitiatorArrivalTimersCleared = 0;
  }
  if ( DiscoveryThreadHandle )
  {
    WaitForSingleObject(DiscoveryThreadHandle, 0xFFFFFFFF);
    CloseHandle(DiscoveryThreadHandle);
    DiscoveryThreadHandle = 0;
  }
  if ( GPThreadHandle )
  {
    WaitForSingleObject(GPThreadHandle, 0xFFFFFFFF);
    CloseHandle(GPThreadHandle);
    GPThreadHandle = 0;
  }
  if ( DiscpHBANotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpHBANotificationHandle = 0;
  }
  if ( DiscpVolumeNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpVolumeNotificationHandle = 0;
  }
  if ( DiscpDiskNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpDiskNotificationHandle = 0;
  }
  if ( DiscpTapeNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpTapeNotificationHandle = 0;
  }
  if ( DiscpCDChangerNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpCDChangerNotificationHandle = 0;
  }
  if ( DiscpMediumChangerNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpMediumChangerNotificationHandle = 0;
  }
  if ( DiscpCDRomNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpCDRomNotificationHandle = 0;
  }
  if ( DiscpFloppyNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpFloppyNotificationHandle = 0;
  }
  if ( DiscpWriteOnceDiskNotificationHandle )
  {
    I_ScUnregisterDeviceNotification();
    DiscpWriteOnceDiskNotificationHandle = 0;
  }
  if ( DiscpVolumeArrivalEventHandle )
    CloseHandle(DiscpVolumeArrivalEventHandle);
  if ( DiscpPersistentVolumeList )
    DiscpFreeMemory(DiscpPersistentVolumeList);
  if ( DiscpServerStopEvent )
  {
    CloseHandle(DiscpServerStopEvent);
    DiscpServerStopEvent = 0;
  }
  v11[0] = 0;
  if ( DiscpDiscoveryCritSectionInited )
  {
    RtlEnterCriticalSection(&DiscpDiscoveryCritSection);
    *(_QWORD *)&v0 = iSNSServerInfoList;
    *((_QWORD *)&v0 + 1) = &iSNSServerInfoList;
    if ( *(__int64 **)(iSNSServerInfoList + 8) != &iSNSServerInfoList )
      goto LABEL_69;
    v11[0] = v0;
    *(_QWORD *)(v0 + 8) = v11;
    iSNSServerInfoList = (__int64)v11;
    if ( *((__int64 **)&v11[0] + 1) != &iSNSServerInfoList )
      goto LABEL_69;
    v1 = qword_180027678;
    if ( *(__int64 **)qword_180027678 != &iSNSServerInfoList )
      goto LABEL_69;
    *(_QWORD *)qword_180027678 = v11;
    *((_QWORD *)&v11[0] + 1) = v1;
    qword_180027678 = (__int64)&iSNSServerInfoList;
    iSNSServerInfoList = (__int64)&iSNSServerInfoList;
    RtlLeaveCriticalSection(&DiscpDiscoveryCritSection);
    v2 = *(_QWORD **)&v11[0];
    if ( *(_OWORD **)&v11[0] != v11 )
    {
      while ( 1 )
      {
        v3 = (_OWORD *)*v2;
        DiscpDeregisterWithiSNSServer(v2);
        v4 = (_OWORD *)*v2;
        if ( *(_QWORD **)(*v2 + 8LL) != v2 )
          break;
        v5 = (_QWORD *)v2[1];
        if ( (_QWORD *)*v5 != v2 )
          break;
        v6 = v2;
        *v5 = v4;
        v2 = v3;
        *((_QWORD *)v4 + 1) = v5;
        DiscpFreeMemory(v6);
        if ( v3 == v11 )
          goto LABEL_45;
      }
LABEL_69:
      __fastfail(3u);
    }
  }
LABEL_45:
  if ( SCNAndESIMutex )
  {
    CloseHandle(SCNAndESIMutex);
    SCNAndESIMutex = 0;
  }
  if ( !iSNSFirewallEnabled )
  {
    v7 = WindowsFirewall_EnableiSCSI(0);
    if ( v7 >= 0 && v7 != 1 )
      iSNSFirewallEnabled = -1;
  }
  if ( DiscpGPNotificationWait )
    UnregisterWaitEx(DiscpGPNotificationWait, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( DiscpGPNotificationEvent )
  {
    if ( xmmword_180027870 )
    {
      xmmword_180027870();
      CloseHandle(DiscpGPNotificationEvent);
    }
    DiscpGPNotificationEvent = 0;
  }
  if ( DiscpIsIpsecEnabled )
  {
    if ( DiscpMMPolicyTemplate )
    {
      DiscpFreeMemory(DiscpMMPolicyTemplate);
      DiscpMMPolicyTemplate = 0;
    }
    if ( DiscpEngineHandle )
    {
      FwpmEngineClose0(DiscpEngineHandle);
      DiscpEngineHandle = 0;
    }
    DiscpIsIpsecEnabled = 0;
  }
  if ( DiscpEDModule )
  {
    FreeLibrary(DiscpEDModule);
    DiscpEDModule = 0;
  }
  if ( DiscpCritSectionInited )
  {
    RtlEnterCriticalSection(&DiscpCritSection);
    DiscpDisableWinsock();
    RtlLeaveCriticalSection(&DiscpCritSection);
  }
  WmiNotificationRegistrationW(MSiSCSI_AdapterEvent_GUID, 0, DiscpAdapterEventRoutine, 0, 4);
  if ( DiscpCritSectionInited )
  {
    RtlEnterCriticalSection(&DiscpCritSection);
    v8 = (volatile signed __int32 *)DiscpInitiatorInstanceList;
    while ( v8 != (volatile signed __int32 *)&DiscpInitiatorInstanceList )
    {
      v9 = v8;
      v8 = *(volatile signed __int32 **)v8;
      DiscpRemoveInitiatorInstance(v9);
      if ( _InterlockedExchangeAdd(v9 + 4, 0xFFFFFFFF) == 1 )
        DiscpFreeMemory(v9);
    }
    DiscpInitiatorInstanceCount = 0;
    RtlLeaveCriticalSection(&DiscpCritSection);
  }
  if ( DiscpProcessHeap && DiscpProcessHeap != NtCurrentPeb()->ProcessHeap )
  {
    RtlDestroyHeap(DiscpProcessHeap);
    DiscpProcessHeap = 0;
    DiscpRegisterHeap(0);
  }
  if ( DiscpCritSectionInited )
    RtlDeleteCriticalSection(&DiscpCritSection);
  if ( DiscpDiscoveryCritSectionInited )
    RtlDeleteCriticalSection(&DiscpDiscoveryCritSection);
  if ( DiscpShutdownCritSectionInited )
    RtlDeleteCriticalSection(&DiscpShutdownCritSection);
  return DiscpDisableEventlog();
}

```

## disassembly

```asm
0x180012510  push    rbx
0x180012512  push    rbp
0x180012513  push    rsi
0x180012514  push    rdi
0x180012515  push    r15
0x180012517  sub     rsp, 40h
0x18001251b  xor     esi, esi
0x18001251d  cmp     cs:DiscpRpcServerInitialized, sil
0x180012524  jz      short loc_180012539
0x180012526  xor     edx, edx; MgrTypeUuid
0x180012528  lea     r8d, [rsi+1]; WaitForCallsToComplete
0x18001252c  lea     rcx, qword_18001FA80; IfSpec
0x180012533  call    cs:__imp_RpcServerUnregisterIf
0x180012539  mov     rcx, cs:DiscpAdministratorsGroup; pSid
0x180012540  test    rcx, rcx
0x180012543  jz      short loc_180012552
0x180012545  call    cs:__imp_FreeSid
0x18001254b  mov     cs:DiscpAdministratorsGroup, rsi
0x180012552  or      ebp, 0FFFFFFFFh
0x180012555  cmp     cs:DiscpInitiatorArrivalTimersCleared, rsi
0x18001255c  jz      short loc_1800125B0
0x18001255e  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x180012565  call    cs:__imp_RtlEnterCriticalSection
0x18001256b  cmp     cs:DiscpInitiatorArrivalTimersActiveCount, esi
0x180012571  jnz     short loc_180012580
0x180012573  mov     rcx, cs:DiscpInitiatorArrivalTimersCleared; hEvent
0x18001257a  call    cs:__imp_SetEvent
0x180012580  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x180012587  call    cs:__imp_RtlLeaveCriticalSection
0x18001258d  mov     rcx, cs:DiscpInitiatorArrivalTimersCleared; hHandle
0x180012594  mov     edx, ebp; dwMilliseconds
0x180012596  call    cs:__imp_WaitForSingleObject
0x18001259c  mov     rcx, cs:DiscpInitiatorArrivalTimersCleared; hObject
0x1800125a3  call    cs:__imp_CloseHandle
0x1800125a9  mov     cs:DiscpInitiatorArrivalTimersCleared, rsi
0x1800125b0  mov     rcx, cs:DiscoveryThreadHandle; hHandle
0x1800125b7  test    rcx, rcx
0x1800125ba  jz      short loc_1800125D8
0x1800125bc  mov     edx, ebp; dwMilliseconds
0x1800125be  call    cs:__imp_WaitForSingleObject
0x1800125c4  mov     rcx, cs:DiscoveryThreadHandle; hObject
0x1800125cb  call    cs:__imp_CloseHandle
0x1800125d1  mov     cs:DiscoveryThreadHandle, rsi
0x1800125d8  mov     rcx, cs:GPThreadHandle; hHandle
0x1800125df  test    rcx, rcx
0x1800125e2  jz      short loc_180012600
0x1800125e4  mov     edx, ebp; dwMilliseconds
0x1800125e6  call    cs:__imp_WaitForSingleObject
0x1800125ec  mov     rcx, cs:GPThreadHandle; hObject
0x1800125f3  call    cs:__imp_CloseHandle
0x1800125f9  mov     cs:GPThreadHandle, rsi
0x180012600  mov     rcx, cs:DiscpHBANotificationHandle
0x180012607  test    rcx, rcx
0x18001260a  jz      short loc_180012619
0x18001260c  call    cs:__imp_I_ScUnregisterDeviceNotification
0x180012612  mov     cs:DiscpHBANotificationHandle, rsi
0x180012619  mov     rcx, cs:DiscpVolumeNotificationHandle
0x180012620  test    rcx, rcx
0x180012623  jz      short loc_180012632
0x180012625  call    cs:__imp_I_ScUnregisterDeviceNotification
0x18001262b  mov     cs:DiscpVolumeNotificationHandle, rsi
0x180012632  mov     rcx, cs:DiscpDiskNotificationHandle
0x180012639  test    rcx, rcx
0x18001263c  jz      short loc_18001264B
0x18001263e  call    cs:__imp_I_ScUnregisterDeviceNotification
0x180012644  mov     cs:DiscpDiskNotificationHandle, rsi
0x18001264b  mov     rcx, cs:DiscpTapeNotificationHandle
0x180012652  test    rcx, rcx
0x180012655  jz      short loc_180012664
0x180012657  call    cs:__imp_I_ScUnregisterDeviceNotification
0x18001265d  mov     cs:DiscpTapeNotificationHandle, rsi
0x180012664  mov     rcx, cs:DiscpCDChangerNotificationHandle
0x18001266b  test    rcx, rcx
0x18001266e  jz      short loc_18001267D
0x180012670  call    cs:__imp_I_ScUnregisterDeviceNotification
0x180012676  mov     cs:DiscpCDChangerNotificationHandle, rsi
0x18001267d  mov     rcx, cs:DiscpMediumChangerNotificationHandle
0x180012684  test    rcx, rcx
0x180012687  jz      short loc_180012696
0x180012689  call    cs:__imp_I_ScUnregisterDeviceNotification
0x18001268f  mov     cs:DiscpMediumChangerNotificationHandle, rsi
0x180012696  mov     rcx, cs:DiscpCDRomNotificationHandle
0x18001269d  test    rcx, rcx
0x1800126a0  jz      short loc_1800126AF
0x1800126a2  call    cs:__imp_I_ScUnregisterDeviceNotification
0x1800126a8  mov     cs:DiscpCDRomNotificationHandle, rsi
0x1800126af  mov     rcx, cs:DiscpFloppyNotificationHandle
0x1800126b6  test    rcx, rcx
0x1800126b9  jz      short loc_1800126C8
0x1800126bb  call    cs:__imp_I_ScUnregisterDeviceNotification
0x1800126c1  mov     cs:DiscpFloppyNotificationHandle, rsi
0x1800126c8  mov     rcx, cs:DiscpWriteOnceDiskNotificationHandle
0x1800126cf  test    rcx, rcx
0x1800126d2  jz      short loc_1800126E1
0x1800126d4  call    cs:__imp_I_ScUnregisterDeviceNotification
0x1800126da  mov     cs:DiscpWriteOnceDiskNotificationHandle, rsi
0x1800126e1  mov     rcx, cs:DiscpVolumeArrivalEventHandle; hObject
0x1800126e8  test    rcx, rcx
0x1800126eb  jz      short loc_1800126F3
0x1800126ed  call    cs:__imp_CloseHandle
0x1800126f3  mov     rcx, cs:DiscpPersistentVolumeList
0x1800126fa  test    rcx, rcx
0x1800126fd  jz      short loc_180012705
0x1800126ff  call    cs:__imp_DiscpFreeMemory
0x180012705  mov     rcx, cs:DiscpServerStopEvent; hObject
0x18001270c  test    rcx, rcx
0x18001270f  jz      short loc_18001271E
0x180012711  call    cs:__imp_CloseHandle
0x180012717  mov     cs:DiscpServerStopEvent, rsi
0x18001271e  cmp     cs:DiscpDiscoveryCritSectionInited, sil
0x180012725  xorps   xmm0, xmm0
0x180012728  movups  [rsp+68h+var_38], xmm0
0x18001272d  jz      loc_18001280B
0x180012733  lea     rcx, DiscpDiscoveryCritSection; CriticalSection
0x18001273a  call    cs:__imp_RtlEnterCriticalSection
0x180012740  mov     rax, cs:iSNSServerInfoList
0x180012747  lea     rdx, iSNSServerInfoList
0x18001274e  cmp     [rax+8], rdx
0x180012752  jnz     loc_18001294F
0x180012758  mov     qword ptr [rsp+68h+var_38], rax
0x18001275d  lea     rcx, [rsp+68h+var_38]
0x180012762  mov     qword ptr [rsp+68h+var_38+8], rdx
0x180012767  mov     [rax+8], rcx
0x18001276b  lea     rax, [rsp+68h+var_38]
0x180012770  mov     cs:iSNSServerInfoList, rax
0x180012777  cmp     qword ptr [rsp+68h+var_38+8], rdx
0x18001277c  jnz     loc_18001294F
0x180012782  mov     rax, cs:qword_180027678
0x180012789  cmp     [rax], rdx
0x18001278c  jnz     loc_18001294F
0x180012792  lea     rcx, [rsp+68h+var_38]
0x180012797  mov     [rax], rcx
0x18001279a  lea     rcx, DiscpDiscoveryCritSection; CriticalSection
0x1800127a1  mov     qword ptr [rsp+68h+var_38+8], rax
0x1800127a6  mov     cs:qword_180027678, rdx
0x1800127ad  mov     cs:iSNSServerInfoList, rdx
0x1800127b4  call    cs:__imp_RtlLeaveCriticalSection
0x1800127ba  mov     rbx, qword ptr [rsp+68h+var_38]
0x1800127bf  lea     rax, [rsp+68h+var_38]
0x1800127c4  cmp     rbx, rax
0x1800127c7  jz      short loc_18001280B
0x1800127c9  mov     rdi, [rbx]
0x1800127cc  mov     rcx, rbx
0x1800127cf  call    DiscpDeregisterWithiSNSServer
0x1800127d4  mov     rdx, [rbx]
0x1800127d7  cmp     [rdx+8], rbx
0x1800127db  jnz     loc_18001294F
0x1800127e1  mov     rax, [rbx+8]
0x1800127e5  cmp     [rax], rbx
0x1800127e8  jnz     loc_18001294F
0x1800127ee  mov     rcx, rbx
0x1800127f1  mov     [rax], rdx
0x1800127f4  mov     rbx, rdi
0x1800127f7  mov     [rdx+8], rax
0x1800127fb  call    cs:__imp_DiscpFreeMemory
0x180012801  lea     rax, [rsp+68h+var_38]
0x180012806  cmp     rdi, rax
0x180012809  jnz     short loc_1800127C9
0x18001280b  mov     rcx, cs:SCNAndESIMutex; hObject
0x180012812  test    rcx, rcx
0x180012815  jz      short loc_180012824
0x180012817  call    cs:__imp_CloseHandle
0x18001281d  mov     cs:SCNAndESIMutex, rsi
0x180012824  cmp     cs:iSNSFirewallEnabled, esi
0x18001282a  jnz     short loc_180012842
0x18001282c  xor     ecx, ecx
0x18001282e  call    WindowsFirewall_EnableiSCSI
0x180012833  test    eax, eax
0x180012835  js      short loc_180012842
0x180012837  cmp     eax, 1
0x18001283a  jz      short loc_180012842
0x18001283c  mov     cs:iSNSFirewallEnabled, ebp
0x180012842  mov     rcx, cs:DiscpGPNotificationWait; WaitHandle
0x180012849  test    rcx, rcx
0x18001284c  jz      short loc_180012858
0x18001284e  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180012852  call    cs:__imp_UnregisterWaitEx
0x180012858  mov     rcx, cs:DiscpGPNotificationEvent
0x18001285f  test    rcx, rcx
0x180012862  jz      short loc_180012889
0x180012864  mov     rax, qword ptr cs:xmmword_180027870
0x18001286b  test    rax, rax
0x18001286e  jz      short loc_180012882
0x180012870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012875  mov     rcx, cs:DiscpGPNotificationEvent; hObject
0x18001287c  call    cs:__imp_CloseHandle
0x180012882  mov     cs:DiscpGPNotificationEvent, rsi
0x180012889  cmp     cs:DiscpIsIpsecEnabled, sil
0x180012890  jz      short loc_1800128CB
0x180012892  mov     rcx, cs:DiscpMMPolicyTemplate
0x180012899  test    rcx, rcx
0x18001289c  jz      short loc_1800128AB
0x18001289e  call    cs:__imp_DiscpFreeMemory
0x1800128a4  mov     cs:DiscpMMPolicyTemplate, rsi
0x1800128ab  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x1800128b2  test    rcx, rcx
0x1800128b5  jz      short loc_1800128C4
0x1800128b7  call    cs:__imp_FwpmEngineClose0
0x1800128bd  mov     cs:DiscpEngineHandle, rsi
0x1800128c4  mov     cs:DiscpIsIpsecEnabled, sil
0x1800128cb  mov     rcx, cs:DiscpEDModule; hLibModule
0x1800128d2  test    rcx, rcx
0x1800128d5  jz      short loc_1800128E4
0x1800128d7  call    cs:__imp_FreeLibrary
0x1800128dd  mov     cs:DiscpEDModule, rsi
0x1800128e4  cmp     cs:DiscpCritSectionInited, sil
0x1800128eb  lea     rbp, DiscpCritSection
0x1800128f2  jz      short loc_18001290C
0x1800128f4  mov     rcx, rbp; CriticalSection
0x1800128f7  call    cs:__imp_RtlEnterCriticalSection
0x1800128fd  call    cs:__imp_DiscpDisableWinsock
0x180012903  mov     rcx, rbp; CriticalSection
0x180012906  call    cs:__imp_RtlLeaveCriticalSection
0x18001290c  xor     r9d, r9d
0x18001290f  mov     [rsp+68h+var_48], 4
0x180012917  lea     r8, DiscpAdapterEventRoutine
0x18001291e  xor     edx, edx
0x180012920  lea     rcx, MSiSCSI_AdapterEvent_GUID
0x180012927  call    cs:__imp_WmiNotificationRegistrationW
0x18001292d  cmp     cs:DiscpCritSectionInited, sil
0x180012934  jz      short loc_18001298E
0x180012936  mov     rcx, rbp; CriticalSection
0x180012939  call    cs:__imp_RtlEnterCriticalSection
0x18001293f  mov     rbx, cs:DiscpInitiatorInstanceList
0x180012946  lea     r15, DiscpInitiatorInstanceList
0x18001294d  jmp     short loc_18001297A
0x18001294f  mov     ecx, 3
0x180012954  int     29h; Win8: RtlFailFast(ecx)
0x180012956  mov     rdi, rbx
0x180012959  mov     rbx, [rbx]
0x18001295c  mov     rcx, rdi
0x18001295f  call    DiscpRemoveInitiatorInstance
0x180012964  or      eax, 0FFFFFFFFh
0x180012967  lock xadd [rdi+10h], eax
0x18001296c  cmp     eax, 1
0x18001296f  jnz     short loc_18001297A
0x180012971  mov     rcx, rdi
0x180012974  call    cs:__imp_DiscpFreeMemory
0x18001297a  cmp     rbx, r15
0x18001297d  jnz     short loc_180012956
0x18001297f  mov     rcx, rbp; CriticalSection
0x180012982  mov     cs:DiscpInitiatorInstanceCount, esi
0x180012988  call    cs:__imp_RtlLeaveCriticalSection
0x18001298e  cmp     cs:DiscpProcessHeap, rsi
0x180012995  jz      short loc_1800129C2
0x180012997  mov     rax, gs:60h
0x1800129a0  mov     rcx, cs:DiscpProcessHeap; Heap
0x1800129a7  cmp     rcx, [rax+30h]
0x1800129ab  jz      short loc_1800129C2
0x1800129ad  call    cs:__imp_RtlDestroyHeap
0x1800129b3  xor     ecx, ecx
0x1800129b5  mov     cs:DiscpProcessHeap, rsi
0x1800129bc  call    cs:__imp_DiscpRegisterHeap
0x1800129c2  cmp     cs:DiscpCritSectionInited, sil
0x1800129c9  jz      short loc_1800129D4
0x1800129cb  mov     rcx, rbp; CriticalSection
0x1800129ce  call    cs:__imp_RtlDeleteCriticalSection
0x1800129d4  cmp     cs:DiscpDiscoveryCritSectionInited, sil
0x1800129db  jz      short loc_1800129EA
0x1800129dd  lea     rcx, DiscpDiscoveryCritSection; CriticalSection
0x1800129e4  call    cs:__imp_RtlDeleteCriticalSection
0x1800129ea  cmp     cs:DiscpShutdownCritSectionInited, sil
0x1800129f1  jz      short loc_180012A00
0x1800129f3  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x1800129fa  call    cs:__imp_RtlDeleteCriticalSection
0x180012a00  add     rsp, 40h
0x180012a04  pop     r15
0x180012a06  pop     rdi
0x180012a07  pop     rsi
0x180012a08  pop     rbp
0x180012a09  pop     rbx
0x180012a0a  jmp     cs:__imp_DiscpDisableEventlog
```
