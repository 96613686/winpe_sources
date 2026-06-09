# pHandleDevicePolicyCheck

- ea: `0x180001da8`
- end: `0x180002bb1`
- name: `pHandleDevicePolicyCheck`
- size: `3593`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800031c0`

## callees

- `0x180001a78`
- `0x180001ad0`
- `0x180001c4c`
- `0x180001da8`
- `0x1800063bc`
- `0x180006ba4`
- `0x180007168`
- `0x180008d80`
- `0x18000973c`
- `0x180009bf0`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002467`
- `msvcrt!_wcsicmp` at `0x180002467`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001eef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000296d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000296d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a8a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180001e94`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180001e94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001ecd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001ecd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180001fdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000277d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180001fdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000277d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f70`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001f83`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001f83`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x180002536`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x1800029c4`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x180002536`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x1800029c4`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000255a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002642`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800029f0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000255a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002642`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800029f0`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x180002545`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x180002631`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x1800029d3`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x180002545`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x180002631`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x1800029d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001fe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002786`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002af3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001fe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002786`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002af3`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180001e2d`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180001e2d`
- `SETUPAPI!SetupWriteTextLog` at `0x180001e80`
- `SETUPAPI!SetupWriteTextLog` at `0x180001f1b`
- `SETUPAPI!SetupWriteTextLog` at `0x180001f3e`
- `SETUPAPI!SetupWriteTextLog` at `0x18000200a`
- `SETUPAPI!SetupWriteTextLog` at `0x180002234`
- `SETUPAPI!SetupWriteTextLog` at `0x180002297`
- `SETUPAPI!SetupWriteTextLog` at `0x180002344`
- `SETUPAPI!SetupWriteTextLog` at `0x1800023d8`
- `SETUPAPI!SetupWriteTextLog` at `0x1800023ff`
- `SETUPAPI!SetupWriteTextLog` at `0x1800024e6`
- `SETUPAPI!SetupWriteTextLog` at `0x18000250d`
- `SETUPAPI!SetupWriteTextLog` at `0x180002587`
- `SETUPAPI!SetupWriteTextLog` at `0x1800025f1`
- `SETUPAPI!SetupWriteTextLog` at `0x18000266f`
- `SETUPAPI!SetupWriteTextLog` at `0x1800026e8`
- `SETUPAPI!SetupWriteTextLog` at `0x180002717`
- `SETUPAPI!SetupWriteTextLog` at `0x180002774`
- `SETUPAPI!SetupWriteTextLog` at `0x1800027a7`
- `SETUPAPI!SetupWriteTextLog` at `0x180002894`
- `SETUPAPI!SetupWriteTextLog` at `0x18000299e`
- `SETUPAPI!SetupWriteTextLog` at `0x180002a1b`
- `SETUPAPI!SetupWriteTextLog` at `0x180002a51`
- `SETUPAPI!SetupWriteTextLog` at `0x180002ab8`
- `SETUPAPI!SetupWriteTextLog` at `0x180002ad7`
- `SETUPAPI!SetupWriteTextLog` at `0x180002b5f`
- `SETUPAPI!SetupWriteTextLog` at `0x180001e80`
- `SETUPAPI!SetupWriteTextLog` at `0x180001f1b`
- `SETUPAPI!SetupWriteTextLog` at `0x180001f3e`
- `SETUPAPI!SetupWriteTextLog` at `0x18000200a`
- `SETUPAPI!SetupWriteTextLog` at `0x180002234`
- `SETUPAPI!SetupWriteTextLog` at `0x180002297`
- `SETUPAPI!SetupWriteTextLog` at `0x180002344`
- `SETUPAPI!SetupWriteTextLog` at `0x1800023d8`
- `SETUPAPI!SetupWriteTextLog` at `0x1800023ff`
- `SETUPAPI!SetupWriteTextLog` at `0x1800024e6`
- `SETUPAPI!SetupWriteTextLog` at `0x18000250d`
- `SETUPAPI!SetupWriteTextLog` at `0x180002587`
- `SETUPAPI!SetupWriteTextLog` at `0x1800025f1`
- `SETUPAPI!SetupWriteTextLog` at `0x18000266f`
- `SETUPAPI!SetupWriteTextLog` at `0x1800026e8`
- `SETUPAPI!SetupWriteTextLog` at `0x180002717`
- `SETUPAPI!SetupWriteTextLog` at `0x180002774`
- `SETUPAPI!SetupWriteTextLog` at `0x1800027a7`
- `SETUPAPI!SetupWriteTextLog` at `0x180002894`
- `SETUPAPI!SetupWriteTextLog` at `0x18000299e`
- `SETUPAPI!SetupWriteTextLog` at `0x180002a1b`
- `SETUPAPI!SetupWriteTextLog` at `0x180002a51`
- `SETUPAPI!SetupWriteTextLog` at `0x180002ab8`
- `SETUPAPI!SetupWriteTextLog` at `0x180002ad7`
- `SETUPAPI!SetupWriteTextLog` at `0x180002b5f`
- `SETUPAPI!SetupSetThreadLogToken` at `0x180001e5f`
- `SETUPAPI!SetupSetThreadLogToken` at `0x180002b41`
- `SETUPAPI!SetupSetThreadLogToken` at `0x180001e5f`
- `SETUPAPI!SetupSetThreadLogToken` at `0x180002b41`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180001fa5`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180001fa5`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001fc1`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001fc1`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000202e`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000273f`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180002a7c`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000202e`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000273f`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180002a7c`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180002073`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800027cd`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180002073`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800027cd`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800020b4`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000210a`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180002440`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180002810`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800028fb`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800020b4`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000210a`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180002440`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180002810`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800028fb`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180002194`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180002699`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180002194`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180002699`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800021af`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800021af`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800021d1`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800021d1`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800021e6`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180002607`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800021e6`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180002607`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800024b1`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800024b1`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800025ba`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800025ba`
- `SETUPAPI!SetupDiRemoveDevice` at `0x180002619`
- `SETUPAPI!SetupDiRemoveDevice` at `0x180002619`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x18000285d`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180002963`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x18000285d`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180002963`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180002b02`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180002b28`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180002b02`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180002b28`
- `newdev!DiInstallDevice` at `0x1800028b8`
- `newdev!DiInstallDevice` at `0x1800028b8`
- `KERNEL32!HeapFree` at `0x180002b19`
- `KERNEL32!HeapFree` at `0x180002b19`

## string_xrefs

- `0x180001e47`: `Device Installation Restrictions Policy Check`
- `0x180001e67`: `{Device Installation Restrictions Policy Check}`
- `0x180001f00`: `Failed to acquire core device install mutex. Error = 0x%08X`
- `0x180001f29`: `Blocking Core Device Install`
- `0x180002284`: `Installation restriction exists but is not applied to existing device: %ws`
- `0x1800025ce`: `Unable to set remove params for blocked device: %ws. Error = 0x%08X`
- `0x18000278f`: `{Install NULL Drivers}`
- `0x180002a9f`: `Unable to enumerate next device to uninstall. Error = 0x%08X`
- `0x180002871`: `Unable to set up device %ws for NULL driver install. Error = 0x%08X`
- `0x180002984`: `Unable to reset device %ws state after NULL driver install. Error = 0x%08X`
- `0x180002abe`: `{Install NULL Drivers - exit(0x%08X)}`
- `0x180002b49`: `{Device Installation Restrictions Policy Check - exit(0x%08X)}`

## pseudocode

```c
__int64 pHandleDevicePolicyCheck()
{
  DWORD v0; // esi
  __int64 ClassDevsW; // r15
  WCHAR *v2; // r14
  __int64 DeviceInfoList; // r12
  SP_LOG_TOKEN ThreadLogToken; // rax
  __int64 v5; // rdx
  SP_LOG_TOKEN v6; // rdi
  int v7; // eax
  HANDLE v8; // r13
  DWORD LastError; // ebx
  DWORD v10; // eax
  DWORD v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  HANDLE CurrentProcess; // rax
  DWORD v15; // r13d
  int v16; // ebx
  BYTE v17; // al
  int v18; // r14d
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  CONFIGRET v23; // eax
  DEVINST DevInst; // ebx
  CONFIGRET v25; // eax
  DWORD v26; // esi
  DWORD i; // edx
  int v28; // eax
  DWORD v29; // ebx
  int v30; // eax
  BOOL v31; // eax
  int v32; // ebx
  CONFIGRET v33; // eax
  DWORD v34; // eax
  __int64 v35; // rcx
  __int64 v36; // r8
  DWORD PropertyBufferSize[2]; // [rsp+28h] [rbp-D8h]
  DWORD PropertyBufferSizea[2]; // [rsp+28h] [rbp-D8h]
  DWORD PropertyBufferSizeb[2]; // [rsp+28h] [rbp-D8h]
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v42[4]; // [rsp+44h] [rbp-BCh] BYREF
  WINBOOL NeedReboot; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v44[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE PropertyBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+54h] [rbp-ACh]
  int v47; // [rsp+58h] [rbp-A8h] BYREF
  int v48; // [rsp+5Ch] [rbp-A4h]
  SP_LOG_TOKEN LogToken; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+70h] [rbp-90h] BYREF
  struct _SP_DEVINFO_DATA v52; // [rsp+90h] [rbp-70h] BYREF
  _SP_CLASSINSTALL_HEADER ClassInstallParams[2]; // [rsp+B0h] [rbp-50h] BYREF
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+C0h] [rbp-40h] BYREF
  PCNZWCH lpString1[2]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v56[16]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR *v57; // [rsp+330h] [rbp+230h]
  int v58; // [rsp+338h] [rbp+238h]
  int v59; // [rsp+33Ch] [rbp+23Ch]
  HANDLE v60[2]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+350h] [rbp+250h] BYREF
  wchar_t v62[200]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v0 = 0;
  ClassDevsW = -1;
  v2 = 0;
  DeviceInfoList = -1;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  memset(&v52, 0, sizeof(v52));
  *(_OWORD *)&ClassInstallParams[0].cbSize = 0;
  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  PropertyType = 0;
  *(_DWORD *)v42 = 0;
  *(_DWORD *)PropertyBuffer = 0;
  v47 = 0;
  NeedReboot = 0;
  *(_DWORD *)v44 = 0;
  TokenHandle = 0;
  ThreadLogToken = SetupGetThreadLogToken();
  LogToken = ThreadLogToken;
  v6 = ThreadLogToken;
  if ( ThreadLogToken )
  {
    v48 = 0;
    SetupWriteTextLog(ThreadLogToken, 0x800000u, 0x30004u, "{Device Installation Restrictions Policy Check}");
  }
  else
  {
    v7 = pSetupCreateTextLogSectionW(0, v5, L"Device Installation Restrictions Policy Check", &LogToken);
    v6 = LogToken;
    v48 = v7;
    SetupSetThreadLogToken(LogToken);
  }
  v60[0] = CreateMutexW(0, 1, L"DrvInst.exe_mutex_{5B10AC83-4F13-4fde-8C0B-B85681BA8D73}");
  v8 = v60[0];
  if ( v60[0] )
  {
    LastError = 0;
    if ( GetLastError() == 183 )
    {
      v10 = WaitForSingleObjectEx(v8, 0xFFFFFFFF, 0);
      if ( v10 == -1 )
      {
        LastError = GetLastError();
        v0 = 0;
      }
      else
      {
        v0 = 0;
        if ( v10 )
          LastError = 13;
      }
    }
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  if ( !v8 )
  {
    v11 = GetLastError();
    SetupWriteTextLog(v6, 0x800000u, 0x10001u, "Failed to acquire core device install mutex. Error = 0x%08X", v11);
    goto LABEL_124;
  }
  SetupWriteTextLog(v6, 0x800000u, 0x10004u, "Blocking Core Device Install");
  RefreshDeviceConfigurationPolicies();
  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v12, ENTER_DEVICE_POLICY_CHECK, v13, 1, lpString1);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle)
    || (lpString1[0] = (PCNZWCH)DevUtilsGetCriticalDeviceIdList(), (v2 = (WCHAR *)lpString1[0]) == 0)
    || (DeviceInfoList = (__int64)SetupDiCreateDeviceInfoList(0, 0), DeviceInfoList == -1)
    || (ClassDevsW = (__int64)SetupDiGetClassDevsW(0, 0, 0, 4u), ClassDevsW == -1) )
  {
    v11 = GetLastError();
    ReleaseMutex(v8);
    CloseHandle(v8);
    goto LABEL_124;
  }
  v46 = 0;
  SetupWriteTextLog(v6, 0x800000u, 0x30004u, "{Policy Check}");
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  if ( SetupDiEnumDeviceInfo((HDEVINFO)ClassDevsW, 0, &DeviceInfoData) )
  {
    v15 = 0;
    while ( 1 )
    {
      ++v15;
      memset_0(DeviceInstanceId, 0, sizeof(DeviceInstanceId));
      if ( !SetupDiGetDeviceInstanceIdW((HDEVINFO)ClassDevsW, &DeviceInfoData, DeviceInstanceId, 0xC8u, 0) )
        goto LABEL_87;
      v16 = 0;
      if ( SetupDiGetDevicePropertyW(
             (HDEVINFO)ClassDevsW,
             &DeviceInfoData,
             &DEVPKEY_Device_ConfigFlags,
             &PropertyType,
             PropertyBuffer,
             4u,
             0,
             0)
        && PropertyType == 7 )
      {
        v17 = PropertyBuffer[0];
      }
      else
      {
        v17 = 0;
        *(_DWORD *)PropertyBuffer = 0;
      }
      if ( (v17 & 0x40) != 0 )
      {
        if ( SetupDiGetDevicePropertyW(
               (HDEVINFO)ClassDevsW,
               &DeviceInfoData,
               &DEVPKEY_Device_InstallError,
               &PropertyType,
               v44,
               4u,
               0,
               0) )
        {
          if ( PropertyType == 23 && *(_DWORD *)v44 == -536870328 )
          {
            v16 = 1;
            if ( !DeviceInfoData.ClassGuid.Data1
              && !*(_DWORD *)&DeviceInfoData.ClassGuid.Data2
              && !*(_DWORD *)DeviceInfoData.ClassGuid.Data4
              && !*(_DWORD *)&DeviceInfoData.ClassGuid.Data4[4] )
            {
              break;
            }
          }
        }
      }
LABEL_47:
      v18 = IsDeviceInstallAllowed(0, ClassDevsW, (unsigned int)&DeviceInfoData, 128, (__int64)&v47);
      if ( v16 )
      {
        if ( v18 )
        {
          SetupWriteTextLog(
            v6,
            0x800000u,
            4u,
            "Previously blocked device is now allowed by policy [%ws]",
            DeviceInstanceId);
LABEL_62:
          SetupWriteTextLog(
            v6,
            0x800000u,
            0x20004u,
            "{Device Removal Initiated by Policy Change [%ws]}",
            DeviceInstanceId);
          *(_DWORD *)v44 = 0;
          NeedReboot = 0;
          if ( SetupDiGetDevicePropertyW(
                 (HDEVINFO)ClassDevsW,
                 &DeviceInfoData,
                 &DEVPKEY_Device_EnumeratorName,
                 &PropertyType,
                 (PBYTE)v62,
                 0x190u,
                 0,
                 0)
            && PropertyType == 18
            && !_wcsicmp(v62, L"Root") )
          {
            if ( v16 || v18 )
            {
              DevUtilsMarkDeviceForReinstall(DeviceInfoData.DevInst);
              v23 = CM_Query_And_Remove_SubTreeW(DeviceInfoData.DevInst, 0, 0, 0, 2u);
              if ( v23 || (v23 = CM_Setup_DevNode(DeviceInfoData.DevInst, 0)) != 0 )
              {
                PropertyBufferSize[0] = CM_MapCrToWin32Err(v23, 0xDu);
                v0 = PropertyBufferSize[0];
                SetupWriteTextLog(
                  v6,
                  0x800000u,
                  2u,
                  "Unable to restart allowed device: %ws. Error = 0x%08X",
                  DeviceInstanceId,
                  *(_QWORD *)PropertyBufferSize);
              }
            }
            else
            {
              memset(&v52, 0, sizeof(v52));
              v52.cbSize = 32;
              if ( !SetupDiOpenDeviceInfoW((HDEVINFO)DeviceInfoList, DeviceInstanceId, 0, 0, &v52) )
              {
                PropertyBufferSize[0] = GetLastError();
                v0 = PropertyBufferSize[0];
                SetupWriteTextLog(
                  v6,
                  0x800000u,
                  2u,
                  "Unable to add blocked device %ws to removal list. Error = 0x%08X",
                  DeviceInstanceId,
                  *(_QWORD *)PropertyBufferSize);
              }
              SetupWriteTextLog(v6, 0x800000u, 4u, "Queuing device %ws for removal.", DeviceInstanceId);
            }
          }
          else
          {
            ClassInstallParams[0].cbSize = 8;
            ClassInstallParams[0].InstallFunction = 5;
            ClassInstallParams[1] = (_SP_CLASSINSTALL_HEADER)1LL;
            if ( !SetupDiSetClassInstallParamsW((HDEVINFO)ClassDevsW, &DeviceInfoData, ClassInstallParams, 0x10u) )
            {
              PropertyBufferSize[0] = GetLastError();
              v0 = PropertyBufferSize[0];
              SetupWriteTextLog(
                v6,
                0x800000u,
                2u,
                "Unable to set remove params for blocked device: %ws. Error = 0x%08X",
                DeviceInstanceId,
                *(_QWORD *)PropertyBufferSize);
            }
            DevInst = DeviceInfoData.DevInst;
            if ( !SetupDiCallClassInstaller(5u, (HDEVINFO)ClassDevsW, &DeviceInfoData)
              && !SetupDiRemoveDevice((HDEVINFO)ClassDevsW, &DeviceInfoData) )
            {
              *(_DWORD *)v44 = GetLastError();
            }
            v25 = CM_Setup_DevNode(DevInst, 0);
            if ( v25 )
            {
              PropertyBufferSize[0] = CM_MapCrToWin32Err(v25, 0xDu);
              v0 = PropertyBufferSize[0];
              SetupWriteTextLog(
                v6,
                0x800000u,
                2u,
                "Unable to re-enumerate blocked device: %ws. Error = 0x%08X",
                DeviceInstanceId,
                *(_QWORD *)PropertyBufferSize);
            }
            memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
            DeviceInstallParams.cbSize = 584;
            if ( SetupDiGetDeviceInstallParamsW((HDEVINFO)ClassDevsW, &DeviceInfoData, &DeviceInstallParams)
              && (DeviceInstallParams.Flags & 0x180) != 0 )
            {
              NeedReboot = 1;
            }
          }
          if ( NeedReboot && !v18 )
          {
            v46 = 1;
            SetupWriteTextLog(v6, 0x800000u, 2u, "Device required reboot: %ws", DeviceInstanceId);
          }
          PropertyBufferSize[0] = *(_DWORD *)v44;
          SetupWriteTextLog(
            v6,
            0x800000u,
            0x40004u,
            "{Device Removal Initiated by Policy Change [%ws] exit(0x%08X)}",
            DeviceInstanceId,
            *(_QWORD *)PropertyBufferSize);
        }
      }
      else if ( !v18 )
      {
        if ( v47 )
        {
          if ( !(unsigned int)pSetupMultiSzContainsString(lpString1[0], DeviceInstanceId) )
          {
            SetupWriteTextLog(
              v6,
              0x800000u,
              4u,
              "Previously allowed device is now blocked by policy [%ws]",
              DeviceInstanceId);
            if ( (Microsoft_Windows_UserPnpEnableBits & 2) != 0 )
            {
              v22 = -1;
              do
                ++v22;
              while ( DeviceInstanceId[v22] );
              v59 = 0;
              v58 = 2 * v22 + 2;
              v57 = DeviceInstanceId;
              McGenEventWrite_EventWriteTransfer(DeviceInstanceId, DM_POLICY_UNINSTALL, v21, 2, v56);
            }
            goto LABEL_62;
          }
          if ( (Microsoft_Windows_UserPnpEnableBits & 2) != 0 )
          {
            v20 = -1;
            do
              ++v20;
            while ( DeviceInstanceId[v20] );
            v59 = 0;
            v58 = 2 * v20 + 2;
            v57 = DeviceInstanceId;
            McGenEventWrite_EventWriteTransfer(DeviceInstanceId, DM_POLICY_UNINSTALL_EXEMPT, v19, 2, v56);
          }
        }
        else
        {
          SetupWriteTextLog(
            v6,
            0x800000u,
            2u,
            "Installation restriction exists but is not applied to existing device: %ws",
            DeviceInstanceId);
        }
      }
LABEL_87:
      memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
      DeviceInfoData.cbSize = 32;
      if ( !SetupDiEnumDeviceInfo((HDEVINFO)ClassDevsW, v15, &DeviceInfoData) )
      {
        v8 = v60[0];
        v2 = (WCHAR *)lpString1[0];
        goto LABEL_89;
      }
    }
    memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
    DeviceInstallParams.cbSize = 584;
    if ( !SetupDiGetDeviceInstallParamsW((HDEVINFO)ClassDevsW, &DeviceInfoData, &DeviceInstallParams)
      || (DeviceInstallParams.FlagsEx |= 0x80000000,
          !SetupDiSetDeviceInstallParamsW((HDEVINFO)ClassDevsW, &DeviceInfoData, &DeviceInstallParams)) )
    {
      v0 = GetLastError();
    }
    if ( !v0 )
    {
      if ( SetupDiBuildDriverInfoList((HDEVINFO)ClassDevsW, &DeviceInfoData, 2u)
        && SetupDiCallClassInstaller(0x17u, (HDEVINFO)ClassDevsW, &DeviceInfoData) )
      {
LABEL_46:
        v0 = 0;
        goto LABEL_47;
      }
      v0 = GetLastError();
    }
    if ( v0 == -536870360 )
    {
      SetupWriteTextLog(v6, 0x800000u, 4u, "No drivers available for blocked device: %ws", DeviceInstanceId);
    }
    else if ( v0 )
    {
      SetupWriteTextLog(
        v6,
        0x800000u,
        2u,
        "Unable to determine effective device class for blocked device: %ws",
        DeviceInstanceId);
    }
    goto LABEL_46;
  }
LABEL_89:
  SetupWriteTextLog(v6, 0x800000u, 0x50004u, "{Policy Check - exit(0x%08X)}", v0);
  ReleaseMutex(v8);
  CloseHandle(v8);
  v26 = 0;
  SetupWriteTextLog(v6, 0x800000u, 0x30004u, "{Install NULL Drivers}");
  for ( i = 0; ; i = v26 )
  {
    NeedReboot = 0;
    memset(&v52, 0, sizeof(v52));
    v52.cbSize = 32;
    *(_DWORD *)v44 = 0;
    if ( !SetupDiEnumDeviceInfo((HDEVINFO)DeviceInfoList, i, &v52) )
      break;
    if ( !SetupDiGetDeviceInstanceIdW((HDEVINFO)DeviceInfoList, &v52, DeviceInstanceId, 0xC8u, 0) )
      DeviceInstanceId[0] = 0;
    ++v26;
    if ( !SetupDiGetDevicePropertyW(
            (HDEVINFO)DeviceInfoList,
            &v52,
            &DEVPKEY_Device_InstallFlags,
            &PropertyType,
            v42,
            4u,
            0,
            0)
      || (v28 = *(_DWORD *)v42, PropertyType != 7) )
    {
      v28 = 0;
    }
    *(_DWORD *)v42 = v28 | 4;
    v29 = 0;
    if ( !SetupDiSetDevicePropertyW((HDEVINFO)DeviceInfoList, &v52, &DEVPKEY_Device_InstallFlags, 7u, v42, 4u, 0) )
    {
      PropertyBufferSizea[0] = GetLastError();
      v29 = PropertyBufferSizea[0];
      SetupWriteTextLog(
        v6,
        0x800000u,
        2u,
        "Unable to set up device %ws for NULL driver install. Error = 0x%08X",
        DeviceInstanceId,
        *(_QWORD *)PropertyBufferSizea);
    }
    if ( !DiInstallDevice(0, (HDEVINFO)DeviceInfoList, &v52, 0, 4u, &NeedReboot) )
      *(_DWORD *)v44 = GetLastError();
    if ( SetupDiGetDevicePropertyW(
           (HDEVINFO)DeviceInfoList,
           &v52,
           &DEVPKEY_Device_InstallFlags,
           &PropertyType,
           v42,
           4u,
           0,
           0) )
    {
      if ( PropertyType == 7 )
      {
        v30 = *(_DWORD *)v42;
        if ( (v42[0] & 4) != 0 )
        {
          *(_DWORD *)v42 &= ~4u;
          if ( (v30 & 0xFFFFFFFB) != 0 )
            v31 = SetupDiSetDevicePropertyW(
                    (HDEVINFO)DeviceInfoList,
                    &v52,
                    &DEVPKEY_Device_InstallFlags,
                    7u,
                    v42,
                    4u,
                    0);
          else
            v31 = SetupDiSetDevicePropertyW((HDEVINFO)DeviceInfoList, &v52, &DEVPKEY_Device_InstallFlags, 0, 0, 0, 0);
          if ( !v31 )
            v29 = GetLastError();
          if ( v29 )
          {
            PropertyBufferSizeb[0] = v29;
            SetupWriteTextLog(
              v6,
              0x800000u,
              2u,
              "Unable to reset device %ws state after NULL driver install. Error = 0x%08X",
              DeviceInstanceId,
              *(_QWORD *)PropertyBufferSizeb);
          }
        }
      }
    }
    v32 = DevUtilsMarkDeviceForReinstall(v52.DevInst);
    v33 = CM_Query_And_Remove_SubTreeW(v52.DevInst, 0, 0, 0, 2u);
    if ( v33 || (v33 = CM_Setup_DevNode(v52.DevInst, 0)) != 0 )
    {
      if ( !v32 )
        NeedReboot = 1;
      PropertyBufferSizeb[0] = CM_MapCrToWin32Err(v33, 0xDu);
      SetupWriteTextLog(
        v6,
        0x800000u,
        2u,
        "Unable to restart blocked device: %ws. Error = 0x%08X",
        DeviceInstanceId,
        *(_QWORD *)PropertyBufferSizeb);
    }
    if ( NeedReboot )
    {
      v46 = 1;
      SetupWriteTextLog(v6, 0x800000u, 2u, "Device required reboot: %ws", DeviceInstanceId);
    }
  }
  v34 = GetLastError();
  v11 = 0;
  if ( v34 != 259 )
    v11 = v34;
  if ( v11 )
    SetupWriteTextLog(v6, 0x800000u, 2u, "Unable to enumerate next device to uninstall. Error = 0x%08X", v11);
  SetupWriteTextLog(v6, 0x800000u, 0x50004u, "{Install NULL Drivers - exit(0x%08X)}", v11);
  if ( v46 )
    RequestPolicyChangeReboot();
LABEL_124:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ClassDevsW != -1 )
    SetupDiDestroyDeviceInfoList((HDEVINFO)ClassDevsW);
  if ( v2 )
    HeapFree(hHeap, 0, v2);
  if ( DeviceInfoList != -1 )
    SetupDiDestroyDeviceInfoList((HDEVINFO)DeviceInfoList);
  if ( v48 )
  {
    pSetupCloseTextLogSection(v6, v11);
    SetupSetThreadLogToken(0);
  }
  else
  {
    SetupWriteTextLog(v6, 0x800000u, 0x50004u, "{Device Installation Restrictions Policy Check - exit(0x%08X)}", v11);
  }
  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v35, EXIT_DEVICE_POLICY_CHECK, v36, 1, v60);
  return v11;
}

```

## disassembly

```asm
0x180001da8  push    rbp
0x180001daa  push    rbx
0x180001dab  push    rsi
0x180001dac  push    rdi
0x180001dad  push    r12
0x180001daf  push    r13
0x180001db1  push    r14
0x180001db3  push    r15
0x180001db5  lea     rbp, [rsp-588h]
0x180001dbd  sub     rsp, 688h
0x180001dc4  mov     rax, cs:__security_cookie
0x180001dcb  xor     rax, rsp
0x180001dce  mov     [rbp+5C0h+var_50], rax
0x180001dd5  xorps   xmm0, xmm0
0x180001dd8  lea     rcx, [rbp+5C0h+DeviceInstallParams]; void *
0x180001ddc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001de0  xorps   xmm1, xmm1
0x180001de3  xor     esi, esi
0x180001de5  xor     edx, edx; Val
0x180001de7  mov     r8d, 248h; Size
0x180001ded  mov     r15, rax
0x180001df0  mov     r14d, esi
0x180001df3  mov     r12, rax
0x180001df6  movups  xmmword ptr [rsp+6C0h+DeviceInfoData.cbSize], xmm0
0x180001dfb  movups  xmmword ptr [rbp+5C0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180001dff  movups  xmmword ptr [rbp+5C0h+var_630.cbSize], xmm1
0x180001e03  movups  xmmword ptr [rbp+5C0h+var_630.ClassGuid.Data4+4], xmm1
0x180001e07  movups  xmmword ptr [rbp+5C0h+ClassInstallParams.cbSize], xmm0
0x180001e0b  call    memset_0
0x180001e10  mov     [rsp+6C0h+PropertyType], esi
0x180001e14  mov     dword ptr [rsp+6C0h+var_67C], esi
0x180001e18  mov     dword ptr [rsp+6C0h+PropertyBuffer], esi
0x180001e1c  mov     [rsp+6C0h+var_668], esi
0x180001e20  mov     [rsp+6C0h+NeedReboot], esi
0x180001e24  mov     dword ptr [rsp+6C0h+var_674], esi
0x180001e28  mov     [rsp+6C0h+TokenHandle], rsi
0x180001e2d  call    cs:__imp_SetupGetThreadLogToken
0x180001e33  mov     [rsp+6C0h+LogToken], rax
0x180001e38  mov     rdi, rax
0x180001e3b  test    rax, rax
0x180001e3e  jnz     short loc_180001E67
0x180001e40  lea     r9, [rsp+6C0h+LogToken]
0x180001e45  xor     ecx, ecx
0x180001e47  lea     r8, aDeviceInstalla_1; "Device Installation Restrictions Policy"...
0x180001e4e  call    pSetupCreateTextLogSectionW
0x180001e53  mov     rdi, [rsp+6C0h+LogToken]
0x180001e58  mov     rcx, rdi; LogToken
0x180001e5b  mov     [rsp+6C0h+var_664], eax
0x180001e5f  call    cs:__imp_SetupSetThreadLogToken
0x180001e65  jmp     short loc_180001E86
0x180001e67  lea     r9, aDeviceInstalla_4; "{Device Installation Restrictions Polic"...
0x180001e6e  mov     [rsp+6C0h+var_664], esi
0x180001e72  mov     edx, 800000h; Category
0x180001e77  mov     r8d, 30004h; Flags
0x180001e7d  mov     rcx, rax; LogToken
0x180001e80  call    cs:__imp_SetupWriteTextLog
0x180001e86  lea     r8, Name; "DrvInst.exe_mutex_{5B10AC83-4F13-4fde-8"...
0x180001e8d  mov     edx, 1; bInitialOwner
0x180001e92  xor     ecx, ecx; lpMutexAttributes
0x180001e94  call    cs:__imp_CreateMutexW
0x180001e9a  mov     [rbp+5C0h+var_380], rax
0x180001ea1  mov     r13, rax
0x180001ea4  test    rax, rax
0x180001ea7  jnz     short loc_180001EB3
0x180001ea9  call    cs:__imp_GetLastError
0x180001eaf  mov     ebx, eax
0x180001eb1  jmp     short loc_180001EED
0x180001eb3  mov     ebx, esi
0x180001eb5  call    cs:__imp_GetLastError
0x180001ebb  cmp     eax, 0B7h
0x180001ec0  jnz     short loc_180001EED
0x180001ec2  or      esi, 0FFFFFFFFh
0x180001ec5  xor     r8d, r8d; bAlertable
0x180001ec8  mov     edx, esi; dwMilliseconds
0x180001eca  mov     rcx, r13; hHandle
0x180001ecd  call    cs:__imp_WaitForSingleObjectEx
0x180001ed3  cmp     eax, esi
0x180001ed5  jnz     short loc_180001EE3
0x180001ed7  call    cs:__imp_GetLastError
0x180001edd  mov     ebx, eax
0x180001edf  xor     esi, esi
0x180001ee1  jmp     short loc_180001EED
0x180001ee3  xor     esi, esi
0x180001ee5  test    eax, eax
0x180001ee7  lea     eax, [rsi+0Dh]
0x180001eea  cmovnz  ebx, eax
0x180001eed  mov     ecx, ebx; dwErrCode
0x180001eef  call    cs:__imp_SetLastError
0x180001ef5  test    r13, r13
0x180001ef8  jnz     short loc_180001F29
0x180001efa  call    cs:__imp_GetLastError
0x180001f00  lea     r9, aFailedToAcquir; "Failed to acquire core device install m"...
0x180001f07  mov     edx, 800000h; Category
0x180001f0c  mov     r8d, 10001h; Flags
0x180001f12  mov     dword ptr [rsp+6C0h+RequiredSize], eax
0x180001f16  mov     rcx, rdi; LogToken
0x180001f19  mov     ebx, eax
0x180001f1b  call    cs:__imp_SetupWriteTextLog
0x180001f21  xor     r13d, r13d
0x180001f24  jmp     loc_180002AE9
0x180001f29  lea     r9, aBlockingCoreDe; "Blocking Core Device Install"
0x180001f30  mov     edx, 800000h; Category
0x180001f35  mov     r8d, 10004h; Flags
0x180001f3b  mov     rcx, rdi; LogToken
0x180001f3e  call    cs:__imp_SetupWriteTextLog
0x180001f44  call    RefreshDeviceConfigurationPolicies
0x180001f49  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x180001f50  jz      short loc_180001F70
0x180001f52  lea     rax, [rbp+5C0h+lpString1]
0x180001f59  mov     r9d, 1
0x180001f5f  lea     rdx, ENTER_DEVICE_POLICY_CHECK
0x180001f66  mov     [rsp+6C0h+RequiredSize], rax
0x180001f6b  call    McGenEventWrite_EventWriteTransfer
0x180001f70  call    cs:__imp_GetCurrentProcess
0x180001f76  lea     r8, [rsp+6C0h+TokenHandle]; TokenHandle
0x180001f7b  mov     edx, 2000000h; DesiredAccess
0x180001f80  mov     rcx, rax; ProcessHandle
0x180001f83  call    cs:__imp_OpenProcessToken
0x180001f89  test    eax, eax
0x180001f8b  jz      short loc_180001FD0
0x180001f8d  call    DevUtilsGetCriticalDeviceIdList
0x180001f92  mov     [rbp+5C0h+lpString1], rax
0x180001f99  mov     r14, rax
0x180001f9c  test    rax, rax
0x180001f9f  jz      short loc_180001FD0
0x180001fa1  xor     edx, edx; hwndParent
0x180001fa3  xor     ecx, ecx; ClassGuid
0x180001fa5  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180001fab  mov     r12, rax
0x180001fae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001fb2  jz      short loc_180001FD0
0x180001fb4  mov     r9d, 4; Flags
0x180001fba  xor     r8d, r8d; hwndParent
0x180001fbd  xor     edx, edx; Enumerator
0x180001fbf  xor     ecx, ecx; ClassGuid
0x180001fc1  call    cs:__imp_SetupDiGetClassDevsW
0x180001fc7  mov     r15, rax
0x180001fca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001fce  jnz     short loc_180001FEF
0x180001fd0  call    cs:__imp_GetLastError
0x180001fd6  mov     rcx, r13; hMutex
0x180001fd9  mov     ebx, eax
0x180001fdb  call    cs:__imp_ReleaseMutex
0x180001fe1  mov     rcx, r13; hObject
0x180001fe4  call    cs:__imp_CloseHandle
0x180001fea  jmp     loc_180001F21
0x180001fef  xor     ebx, ebx
0x180001ff1  lea     r9, aPolicyCheck; "{Policy Check}"
0x180001ff8  mov     edx, 800000h; Category
0x180001ffd  mov     [rsp+6C0h+var_66C], ebx
0x180002001  mov     r8d, 30004h; Flags
0x180002007  mov     rcx, rdi; LogToken
0x18000200a  call    cs:__imp_SetupWriteTextLog
0x180002010  xorps   xmm0, xmm0
0x180002013  lea     r8, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x180002018  movups  xmmword ptr [rsp+6C0h+DeviceInfoData.cbSize], xmm0
0x18000201d  xor     edx, edx; MemberIndex
0x18000201f  mov     [rsp+6C0h+DeviceInfoData.cbSize], 20h ; ' '
0x180002027  mov     rcx, r15; DeviceInfoSet
0x18000202a  movups  xmmword ptr [rbp+5C0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18000202e  call    cs:__imp_SetupDiEnumDeviceInfo
0x180002034  test    eax, eax
0x180002036  jz      loc_18000275B
0x18000203c  mov     r13d, ebx
0x18000203f  xor     r14d, r14d
0x180002042  xor     edx, edx; Val
0x180002044  lea     rcx, [rbp+5C0h+DeviceInstanceId]; void *
0x18000204b  mov     r8d, 190h; Size
0x180002051  inc     r13d
0x180002054  call    memset_0
0x180002059  mov     r9d, 0C8h; DeviceInstanceIdSize
0x18000205f  mov     [rsp+6C0h+RequiredSize], r14; RequiredSize
0x180002064  lea     r8, [rbp+5C0h+DeviceInstanceId]; DeviceInstanceId
0x18000206b  mov     rcx, r15; DeviceInfoSet
0x18000206e  lea     rdx, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x180002073  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180002079  test    eax, eax
0x18000207b  jz      loc_180002720
0x180002081  mov     [rsp+6C0h+Flags], r14d; Flags
0x180002086  lea     rax, [rsp+6C0h+PropertyBuffer]
0x18000208b  mov     [rsp+6C0h+var_690], r14; RequiredSize
0x180002090  lea     r9, [rsp+6C0h+PropertyType]; PropertyType
0x180002095  mov     [rsp+6C0h+PropertyBufferSize], 4; PropertyBufferSize
0x18000209d  lea     r8, DEVPKEY_Device_ConfigFlags; PropertyKey
0x1800020a4  lea     rdx, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x1800020a9  mov     [rsp+6C0h+RequiredSize], rax; PropertyBuffer
0x1800020ae  mov     rcx, r15; DeviceInfoSet
0x1800020b1  mov     ebx, r14d
0x1800020b4  call    cs:__imp_SetupDiGetDevicePropertyW
0x1800020ba  test    eax, eax
0x1800020bc  jz      short loc_1800020CB
0x1800020be  cmp     [rsp+6C0h+PropertyType], 7
0x1800020c3  jnz     short loc_1800020CB
0x1800020c5  mov     eax, dword ptr [rsp+6C0h+PropertyBuffer]
0x1800020c9  jmp     short loc_1800020D2
0x1800020cb  mov     eax, r14d
0x1800020ce  mov     dword ptr [rsp+6C0h+PropertyBuffer], eax
0x1800020d2  test    al, 40h
0x1800020d4  jz      loc_18000223D
0x1800020da  mov     [rsp+6C0h+Flags], r14d; Flags
0x1800020df  lea     rax, [rsp+6C0h+var_674]
0x1800020e4  mov     [rsp+6C0h+var_690], r14; RequiredSize
0x1800020e9  lea     r9, [rsp+6C0h+PropertyType]; PropertyType
0x1800020ee  mov     [rsp+6C0h+PropertyBufferSize], 4; PropertyBufferSize
0x1800020f6  lea     r8, DEVPKEY_Device_InstallError; PropertyKey
0x1800020fd  lea     rdx, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x180002102  mov     [rsp+6C0h+RequiredSize], rax; PropertyBuffer
0x180002107  mov     rcx, r15; DeviceInfoSet
0x18000210a  call    cs:__imp_SetupDiGetDevicePropertyW
0x180002110  test    eax, eax
0x180002112  jz      loc_18000223D
0x180002118  cmp     [rsp+6C0h+PropertyType], 17h
0x18000211d  jnz     loc_18000223D
0x180002123  cmp     dword ptr [rsp+6C0h+var_674], 0E0000248h
0x18000212b  jnz     loc_18000223D
0x180002131  mov     ebx, 1
0x180002136  cmp     [rsp+6C0h+DeviceInfoData.ClassGuid.Data1], r14d
0x18000213b  jnz     loc_18000223D
0x180002141  mov     eax, cs:dword_18000D9C4
0x180002147  cmp     dword ptr [rsp+6C0h+DeviceInfoData.ClassGuid.Data2], eax
0x18000214b  jnz     loc_18000223D
0x180002151  mov     eax, cs:dword_18000D9C8
0x180002157  cmp     dword ptr [rsp+6C0h+DeviceInfoData.ClassGuid.Data4], eax
0x18000215b  jnz     loc_18000223D
0x180002161  mov     eax, cs:dword_18000D9CC
0x180002167  cmp     dword ptr [rbp+5C0h+DeviceInfoData.ClassGuid.Data4+4], eax
0x18000216a  jnz     loc_18000223D
0x180002170  xor     edx, edx; Val
0x180002172  lea     rcx, [rbp+5C0h+DeviceInstallParams.Flags]; void *
0x180002176  mov     r8d, 244h; Size
0x18000217c  call    memset_0
0x180002181  lea     r8, [rbp+5C0h+DeviceInstallParams]; DeviceInstallParams
0x180002185  mov     [rbp+5C0h+DeviceInstallParams.cbSize], 248h
0x18000218c  lea     rdx, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x180002191  mov     rcx, r15; DeviceInfoSet
0x180002194  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18000219a  test    eax, eax
0x18000219c  jz      short loc_1800021B9
0x18000219e  bts     [rbp+5C0h+DeviceInstallParams.FlagsEx], 1Fh
0x1800021a3  lea     r8, [rbp+5C0h+DeviceInstallParams]; DeviceInstallParams
0x1800021a7  lea     rdx, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x1800021ac  mov     rcx, r15; DeviceInfoSet
0x1800021af  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x1800021b5  test    eax, eax
0x1800021b7  jnz     short loc_1800021C1
0x1800021b9  call    cs:__imp_GetLastError
0x1800021bf  mov     esi, eax
0x1800021c1  test    esi, esi
0x1800021c3  jnz     short loc_1800021F8
0x1800021c5  lea     r8d, [rsi+2]; DriverType
0x1800021c9  mov     rcx, r15; DeviceInfoSet
0x1800021cc  lea     rdx, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x1800021d1  call    cs:__imp_SetupDiBuildDriverInfoList
0x1800021d7  test    eax, eax
0x1800021d9  jz      short loc_1800021F0
0x1800021db  lea     r8, [rsp+6C0h+DeviceInfoData]; DeviceInfoData
0x1800021e0  mov     rdx, r15; DeviceInfoSet
0x1800021e3  lea     ecx, [rsi+17h]; InstallFunction
0x1800021e6  call    cs:__imp_SetupDiCallClassInstaller
0x1800021ec  test    eax, eax
0x1800021ee  jnz     short loc_18000223A
0x1800021f0  call    cs:__imp_GetLastError
0x1800021f6  mov     esi, eax
0x1800021f8  cmp     esi, 0E0000228h
0x1800021fe  jnz     short loc_18000220F
0x180002200  lea     r9, aNoDriversAvail; "No drivers available for blocked device"...
0x180002207  mov     r8d, 4
0x18000220d  jmp     short loc_180002220
0x18000220f  test    esi, esi
0x180002211  jz      short loc_18000223A
0x180002213  lea     r9, aUnableToDeterm; "Unable to determine effective device cl"...
0x18000221a  mov     r8d, 2; Flags
0x180002220  lea     rax, [rbp+5C0h+DeviceInstanceId]
0x180002227  mov     edx, 800000h; Category
0x18000222c  mov     rcx, rdi; LogToken
0x18000222f  mov     [rsp+6C0h+RequiredSize], rax
0x180002234  call    cs:__imp_SetupWriteTextLog
0x18000223a  mov     esi, r14d
0x18000223d  lea     rax, [rsp+6C0h+var_668]
0x180002242  mov     r9d, 80h
0x180002248  lea     r8, [rsp+6C0h+DeviceInfoData]
0x18000224d  mov     [rsp+6C0h+RequiredSize], rax
0x180002252  mov     rdx, r15
0x180002255  xor     ecx, ecx
0x180002257  call    IsDeviceInstallAllowed
0x18000225c  mov     r14d, eax
0x18000225f  xor     eax, eax
0x180002261  test    ebx, ebx
0x180002263  jnz     loc_1800023AE
0x180002269  test    r14d, r14d
0x18000226c  jnz     loc_18000271D
0x180002272  cmp     [rsp+6C0h+var_668], eax
0x180002276  jnz     short loc_1800022A2
0x180002278  lea     rax, [rbp+5C0h+DeviceInstanceId]
0x18000227f  mov     edx, 800000h; Category
0x180002284  lea     r9, aInstallationRe; "Installation restriction exists but is "...
0x18000228b  mov     [rsp+6C0h+RequiredSize], rax
0x180002290  lea     r8d, [rbx+2]; Flags
0x180002294  mov     rcx, rdi; LogToken
0x180002297  call    cs:__imp_SetupWriteTextLog
  ... truncated ...
```
