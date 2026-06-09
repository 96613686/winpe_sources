# ProcessDevicesToRemove

- ea: `0x180004e74`
- end: `0x1800057de`
- name: `ProcessDevicesToRemove`
- size: `2410`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180003d70`
- `0x180004c14`

## callees

- `0x180004460`
- `0x1800045b8`
- `0x180004a04`
- `0x180004e0c`
- `0x180004e74`
- `0x1800088d8`
- `0x180008990`
- `0x180008a30`
- `0x180008dfe`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x18000503e`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800050ba`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180005133`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18000503e`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800050ba`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180005133`
- `KERNEL32!FileTimeToSystemTime` at `0x180005054`
- `KERNEL32!FileTimeToSystemTime` at `0x1800050cd`
- `KERNEL32!FileTimeToSystemTime` at `0x180005146`
- `KERNEL32!FileTimeToSystemTime` at `0x180005054`
- `KERNEL32!FileTimeToSystemTime` at `0x1800050cd`
- `KERNEL32!FileTimeToSystemTime` at `0x180005146`
- `KERNEL32!CompareFileTime` at `0x1800053cb`
- `KERNEL32!CompareFileTime` at `0x1800053ef`
- `KERNEL32!CompareFileTime` at `0x1800053cb`
- `KERNEL32!CompareFileTime` at `0x1800053ef`
- `KERNEL32!GetLastError` at `0x180005211`
- `KERNEL32!GetLastError` at `0x180005337`
- `KERNEL32!GetLastError` at `0x180005673`
- `KERNEL32!GetLastError` at `0x18000568d`
- `KERNEL32!GetLastError` at `0x1800057c5`
- `KERNEL32!GetLastError` at `0x180005211`
- `KERNEL32!GetLastError` at `0x180005337`
- `KERNEL32!GetLastError` at `0x180005673`
- `KERNEL32!GetLastError` at `0x18000568d`
- `KERNEL32!GetLastError` at `0x1800057c5`
- `KERNEL32!CompareStringOrdinal` at `0x1800052dc`
- `KERNEL32!CompareStringOrdinal` at `0x1800052dc`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005771`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005771`
- `SETUPAPI!SetupDiRemoveDevice` at `0x180005683`
- `SETUPAPI!SetupDiRemoveDevice` at `0x180005683`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180005669`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180005669`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000532d`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000539f`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800054b6`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800055fb`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000532d`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000539f`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800054b6`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800055fb`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180005202`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180005202`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180005256`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180005256`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x18000527c`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x18000527c`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800052a8`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800052a8`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18000563e`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18000563e`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180005654`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180005654`

## string_xrefs

- `0x18000558e`: `Device %ws %ws be removed.`
- `0x1800056b8`: `Device %ws was removed.`
- `0x1800056e3`: `Device was last used with alternate Hardware Configuration (%d), setting re-specialize.`
- `0x1800057a1`: `Failed to remove device %ws, Err = 0x%lx`
- `0x180005753`: `Failed to determine devices to remove, Err = 0x%lx`

## pseudocode

```c
__int64 __fastcall ProcessDevicesToRemove(__int64 a1)
{
  unsigned __int64 v1; // r12
  unsigned int SystemTimeOfDayInfo; // r14d
  FILETIME v4; // rbx
  FILETIME v5; // r15
  int v6; // ecx
  __int64 v7; // rax
  unsigned __int64 v8; // r13
  FILETIME v9; // rdi
  __int64 v10; // r15
  int v11; // eax
  HDEVINFO ClassDevs; // r12
  DWORD v13; // r13d
  int v14; // eax
  FILETIME v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // r13d
  unsigned __int64 DeviceRemovalTimeoutPolicyPeriod; // rax
  unsigned __int64 v21; // rcx
  const wchar_t *v22; // rcx
  DWORD v23; // eax
  int v24; // edx
  __int64 v25; // rcx
  unsigned int v26; // eax
  int v27; // ecx
  DWORD LastError; // eax
  HDEVINFO DeviceInfoSet; // [rsp+20h] [rbp-E0h]
  HDEVINFO DeviceInfoSeta; // [rsp+20h] [rbp-E0h]
  PCWSTR MachineName; // [rsp+28h] [rbp-D8h]
  PCWSTR MachineNamea; // [rsp+28h] [rbp-D8h]
  PVOID Reserved; // [rsp+30h] [rbp-D0h]
  __int64 Flags; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h]
  BYTE v38[4]; // [rsp+60h] [rbp-A0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD RequiredSize; // [rsp+68h] [rbp-98h] BYREF
  BYTE v41[4]; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v42; // [rsp+70h] [rbp-90h]
  struct _FILETIME LocalFileTime; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v44; // [rsp+80h] [rbp-80h]
  unsigned __int64 v45; // [rsp+88h] [rbp-78h]
  FILETIME FileTime; // [rsp+90h] [rbp-70h] BYREF
  FILETIME FileTime2; // [rsp+98h] [rbp-68h] BYREF
  ULONG pulProblemNumber; // [rsp+A0h] [rbp-60h] BYREF
  ULONG pulStatus; // [rsp+A4h] [rbp-5Ch] BYREF
  FILETIME v50; // [rsp+A8h] [rbp-58h] BYREF
  BYTE v51[8]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE PropertyBuffer[8]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v53; // [rsp+C0h] [rbp-40h]
  _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp-38h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+D8h] [rbp-28h] BYREF
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[40]; // [rsp+350h] [rbp+250h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v1 = 0;
  pulStatus = 0;
  pulProblemNumber = 0;
  *(_DWORD *)v41 = 0;
  PropertyType = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v38[0] = 0;
  RequiredSize = 0;
  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  FileTime = 0;
  v50 = 0;
  FileTime2 = 0;
  *(_QWORD *)PropertyBuffer = 0;
  *(_QWORD *)v51 = 0;
  LocalFileTime = 0;
  SystemTime = 0;
  if ( !a1 )
    return 87;
  if ( !(unsigned int)PnpCleanDevicesNotifyCallback(a1) )
    return 1223;
  v53 = 864000000000LL * *(unsigned int *)(a1 + 76);
  (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
    *(_QWORD *)(a1 + 56),
    3,
    0,
    "Default missing device timeout period is %d days.",
    v53 / 0x989680 / 0x3C / 0x3C / 0x18);
  SystemTimeOfDayInfo = pUtilGetSystemTimeOfDayInfo(&FileTime2, &v50);
  if ( SystemTimeOfDayInfo )
    goto LABEL_6;
  v4 = FileTime2;
  v5 = v50;
  if ( *(_QWORD *)&FileTime2 < *(unsigned __int64 *)&v50 )
  {
    v7 = -1;
    v6 = -1073741675;
  }
  else
  {
    v6 = 0;
    v7 = *(_QWORD *)&FileTime2 - *(_QWORD *)&v50;
  }
  v8 = 0;
  if ( v6 >= 0 )
    v8 = v7;
  SystemTimeOfDayInfo = pUtilGetSystemLastShutdownTime((LPBYTE)&FileTime);
  if ( SystemTimeOfDayInfo )
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD, __int64))(a1 + 48))(*(_QWORD *)(a1 + 56), 1);
    return SystemTimeOfDayInfo;
  }
  v9 = FileTime;
  if ( *(_QWORD *)&v5 < *(unsigned __int64 *)&FileTime )
  {
    v10 = -1;
    v11 = -1073741675;
  }
  else
  {
    v10 = *(_QWORD *)&v5 - *(_QWORD *)&FileTime;
    v11 = 0;
  }
  if ( v11 >= 0 )
    v1 = v10;
  if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    LODWORD(DeviceInfoSet) = SystemTime.wMonth;
    (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
      *(_QWORD *)(a1 + 56),
      4,
      0,
      "Last System Shutdown Time: %02d/%02d/%04d, %02d:%02d:%02d",
      DeviceInfoSet,
      SystemTime.wDay,
      SystemTime.wYear,
      SystemTime.wHour,
      SystemTime.wMinute,
      SystemTime.wSecond);
  }
  if ( FileTimeToLocalFileTime(&v50, &LocalFileTime) && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    LODWORD(v37) = SystemTime.wSecond;
    LODWORD(v36) = SystemTime.wMinute;
    LODWORD(Flags) = SystemTime.wHour;
    LODWORD(Reserved) = SystemTime.wYear;
    LODWORD(MachineName) = SystemTime.wDay;
    LODWORD(DeviceInfoSet) = SystemTime.wMonth;
    (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
      *(_QWORD *)(a1 + 56),
      4,
      0,
      "Boot Time: %02d/%02d/%04d, %02d:%02d:%02d",
      DeviceInfoSet,
      MachineName,
      Reserved,
      Flags,
      v36,
      v37);
  }
  if ( FileTimeToLocalFileTime(&FileTime2, &LocalFileTime) && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    LODWORD(v37) = SystemTime.wSecond;
    LODWORD(v36) = SystemTime.wMinute;
    LODWORD(Flags) = SystemTime.wHour;
    LODWORD(Reserved) = SystemTime.wYear;
    LODWORD(MachineName) = SystemTime.wDay;
    LODWORD(DeviceInfoSet) = SystemTime.wMonth;
    (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
      *(_QWORD *)(a1 + 56),
      4,
      0,
      "Current Time: %02d/%02d/%04d, %02d:%02d:%02d",
      DeviceInfoSet,
      MachineName,
      Reserved,
      Flags,
      v36,
      v37);
  }
  (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
    *(_QWORD *)(a1 + 56),
    4,
    0,
    "System was previously in shutdown state for %d seconds",
    v1 / 0x989680);
  if ( v1 <= v53 || v8 >= v53 )
  {
    ClassDevs = SetupDiGetClassDevsExW(0, 0, 0, 4u, 0, 0, 0);
    if ( ClassDevs == (HDEVINFO)-1LL )
      return GetLastError();
    v42 = 0;
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    v13 = 0;
    v14 = PnpCleanDevicesNotifyCallback(a1);
    while ( 1 )
    {
      if ( !v14 )
      {
        SystemTimeOfDayInfo = 1223;
LABEL_86:
        LODWORD(DeviceInfoSeta) = SystemTimeOfDayInfo;
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
          *(_QWORD *)(a1 + 56),
          1,
          0,
          "Failed to determine devices to remove, Err = 0x%lx",
          DeviceInfoSeta);
        goto LABEL_87;
      }
      if ( !SetupDiEnumDeviceInfo(ClassDevs, v13, &DeviceInfoData) )
      {
        LastError = GetLastError();
        if ( LastError != 259 )
        {
          SystemTimeOfDayInfo = LastError;
          if ( LastError )
            goto LABEL_86;
        }
LABEL_87:
        SetupDiDestroyDeviceInfoList(ClassDevs);
        return SystemTimeOfDayInfo;
      }
      if ( CM_Get_DevNode_Status_Ex(&pulStatus, &pulProblemNumber, DeviceInfoData.DevInst, 0, 0) != 13 )
        goto LABEL_83;
      if ( !SetupDiGetDeviceInstanceIdW(ClassDevs, &DeviceInfoData, DeviceInstanceId, 0xC8u, 0) )
        goto LABEL_83;
      DeviceInstanceId[199] = 0;
      if ( CompareStringOrdinal(DeviceInstanceId, -1, L"HTREE\\ROOT\\0", -1, 1) == 2
        || (unsigned int)pUtilIsRootEnumeratedDevice(DeviceInfoData.DevInst) )
      {
        goto LABEL_83;
      }
      if ( SetupDiGetDevicePropertyW(
             ClassDevs,
             &DeviceInfoData,
             &DEVPKEY_Device_LastRemovalDate,
             &PropertyType,
             PropertyBuffer,
             8u,
             &RequiredSize,
             0) )
      {
        if ( PropertyType != 16 || RequiredSize != 8 )
          goto LABEL_83;
        v15 = *(FILETIME *)PropertyBuffer;
        if ( *(_QWORD *)PropertyBuffer )
          goto LABEL_48;
      }
      else if ( GetLastError() != 1168 )
      {
        goto LABEL_83;
      }
      if ( !SetupDiGetDevicePropertyW(
              ClassDevs,
              &DeviceInfoData,
              &DEVPKEY_Device_LastArrivalDate,
              &PropertyType,
              v51,
              8u,
              &RequiredSize,
              0)
        || PropertyType != 16
        || RequiredSize != 8 )
      {
        goto LABEL_83;
      }
      if ( CompareFileTime((const FILETIME *)v51, &FileTime) > 0 )
      {
        if ( CompareFileTime((const FILETIME *)v51, &FileTime2) >= 0 )
          goto LABEL_83;
        v15 = v4;
LABEL_49:
        v16 = *(_QWORD *)&v4 - *(_QWORD *)&v15;
        v17 = 0;
        goto LABEL_53;
      }
      v15 = v9;
LABEL_48:
      if ( *(_QWORD *)&v4 >= *(unsigned __int64 *)&v15 )
        goto LABEL_49;
      v16 = -1;
      v17 = -1073741675;
LABEL_53:
      v18 = 0;
      if ( v17 >= 0 )
        v18 = v16;
      v44 = v18;
      (*(void (__fastcall **)(_QWORD, __int64))(a1 + 48))(*(_QWORD *)(a1 + 56), 6);
      v19 = SetupDiGetDevicePropertyW(
              ClassDevs,
              &DeviceInfoData,
              &DEVPKEY_Device_InLocalMachineContainer,
              &PropertyType,
              v38,
              1u,
              &RequiredSize,
              0)
         && PropertyType == 17
         && RequiredSize == 1
         && v38[0] == 0xFF;
      DeviceRemovalTimeoutPolicyPeriod = GetDeviceRemovalTimeoutPolicyPeriod(
                                           a1,
                                           ClassDevs,
                                           (__int64)&DeviceInfoData,
                                           v19);
      v21 = DeviceRemovalTimeoutPolicyPeriod;
      v45 = DeviceRemovalTimeoutPolicyPeriod;
      if ( DeviceRemovalTimeoutPolicyPeriod != v53 )
      {
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
          *(_QWORD *)(a1 + 56),
          3,
          0,
          "Device %ws uses timeout period of %d days.",
          DeviceInstanceId,
          DeviceRemovalTimeoutPolicyPeriod / 0x989680 / 0x3C / 0x3C / 0x18);
        v21 = v45;
      }
      if ( v44 >= v21 )
      {
        v22 = L"will";
        if ( !*(_DWORD *)(a1 + 64) )
          v22 = L"may";
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
          *(_QWORD *)(a1 + 56),
          3,
          0,
          "Device %ws %ws be removed.",
          DeviceInstanceId,
          v22);
        if ( *(_DWORD *)(a1 + 64) )
        {
          if ( !SetupDiGetDevicePropertyW(
                  ClassDevs,
                  &DeviceInfoData,
                  &DEVPKEY_Device_HardwareConfigurationIndex,
                  &PropertyType,
                  v41,
                  4u,
                  &RequiredSize,
                  0)
            || PropertyType != 7
            || RequiredSize != 4 )
          {
            *(_DWORD *)v41 = -1;
          }
          memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
          DeviceInstallParams.cbSize = 584;
          SetupDiGetDeviceInstallParamsW(ClassDevs, &DeviceInfoData, &DeviceInstallParams);
          DeviceInstallParams.Flags |= 0x20000u;
          SetupDiSetDeviceInstallParamsW(ClassDevs, &DeviceInfoData, &DeviceInstallParams);
          LODWORD(v44) = 0;
          if ( SetupDiCallClassInstaller(5u, ClassDevs, &DeviceInfoData)
            || (LODWORD(v44) = GetLastError(), SetupDiRemoveDevice(ClassDevs, &DeviceInfoData)) )
          {
            v23 = v44;
            v24 = 1;
          }
          else
          {
            v23 = GetLastError();
            v24 = 0;
          }
          v25 = *(_QWORD *)(a1 + 56);
          if ( !v24 )
          {
            LODWORD(MachineNamea) = v23;
            (*(void (**)(__int64, __int64, _QWORD, const char *, ...))(a1 + 48))(
              v25,
              1,
              0,
              "Failed to remove device %ws, Err = 0x%lx",
              DeviceInstanceId,
              MachineNamea);
            goto LABEL_83;
          }
          (*(void (**)(__int64, __int64, _QWORD, const char *, ...))(a1 + 48))(
            v25,
            3,
            0,
            "Device %ws was removed.",
            DeviceInstanceId);
          if ( v19 )
          {
            if ( *(_DWORD *)v41 != *(_DWORD *)(a1 + 24) && *(_DWORD *)v41 != -1 )
            {
              LODWORD(DeviceInfoSeta) = *(_DWORD *)v41;
              (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 48))(
                *(_QWORD *)(a1 + 56),
                3,
                0,
                "Device was last used with alternate Hardware Configuration (%d), setting re-specialize.",
                DeviceInfoSeta);
              if ( !(unsigned int)HwCfgIndexToGuid(*(int *)v41, SubKey) )
                HwCfgConfigurationNeedsRespecialize(SubKey);
            }
          }
        }
        v26 = *(_DWORD *)(a1 + 72);
        v27 = -1;
        if ( v26 + 1 >= v26 )
          v27 = v26 + 1;
        *(_DWORD *)(a1 + 72) = v27;
      }
LABEL_83:
      ++v42;
      v14 = PnpCleanDevicesNotifyCallback(a1);
      v13 = v42;
    }
  }
  return SystemTimeOfDayInfo;
}

```

## disassembly

```asm
0x180004e74  push    rbp
0x180004e76  push    rbx
0x180004e77  push    rsi
0x180004e78  push    rdi
0x180004e79  push    r12
0x180004e7b  push    r13
0x180004e7d  push    r14
0x180004e7f  push    r15
0x180004e81  lea     rbp, [rsp-448h]
0x180004e89  sub     rsp, 548h
0x180004e90  mov     rax, cs:__security_cookie
0x180004e97  xor     rax, rsp
0x180004e9a  mov     [rbp+480h+var_50], rax
0x180004ea1  xor     r12d, r12d
0x180004ea4  xorps   xmm0, xmm0
0x180004ea7  mov     rsi, rcx
0x180004eaa  mov     [rbp+480h+pulStatus], r12d
0x180004eae  lea     rcx, [rbp+480h+DeviceInstallParams]; void *
0x180004eb2  mov     [rbp+480h+pulProblemNumber], r12d
0x180004eb6  xor     edx, edx; Val
0x180004eb8  mov     dword ptr [rsp+580h+var_514], r12d
0x180004ebd  mov     r8d, 248h; Size
0x180004ec3  mov     [rsp+580h+PropertyType], r12d
0x180004ec8  movups  xmmword ptr [rbp+480h+DeviceInfoData.cbSize], xmm0
0x180004ecc  mov     [rsp+580h+var_520], r12b
0x180004ed1  movups  xmmword ptr [rbp+480h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180004ed5  mov     [rsp+580h+RequiredSize], r12d
0x180004eda  call    memset_0
0x180004edf  mov     qword ptr [rbp+480h+FileTime.dwLowDateTime], r12
0x180004ee3  xorps   xmm0, xmm0
0x180004ee6  mov     qword ptr [rbp+480h+var_4D8.dwLowDateTime], r12
0x180004eea  mov     qword ptr [rbp+480h+FileTime2.dwLowDateTime], r12
0x180004eee  mov     qword ptr [rbp+480h+PropertyBuffer], r12
0x180004ef2  mov     qword ptr [rbp+480h+var_4D0], r12
0x180004ef6  mov     qword ptr [rsp+580h+LocalFileTime.dwLowDateTime], r12
0x180004efb  movups  xmmword ptr [rbp+480h+SystemTime.wYear], xmm0
0x180004eff  test    rsi, rsi
0x180004f02  jnz     short loc_180004F0E
0x180004f04  lea     r14d, [r12+57h]
0x180004f09  jmp     loc_180005777
0x180004f0e  mov     rcx, rsi
0x180004f11  call    PnpCleanDevicesNotifyCallback
0x180004f16  test    eax, eax
0x180004f18  jnz     short loc_180004F25
0x180004f1a  mov     r14d, 4C7h
0x180004f20  jmp     loc_180005777
0x180004f25  mov     ecx, [rsi+4Ch]
0x180004f28  lea     r9, aDefaultMissing; "Default missing device timeout period i"...
0x180004f2f  mov     rax, 0C92A69C000h
0x180004f39  xor     r8d, r8d
0x180004f3c  imul    rcx, rax
0x180004f40  mov     rax, 0D6BF94D5E57A42BDh
0x180004f4a  mul     rcx
0x180004f4d  mov     [rbp+480h+var_4C0], rcx
0x180004f51  mov     rcx, 8888888888888889h
0x180004f5b  shr     rdx, 17h
0x180004f5f  mov     rax, rcx
0x180004f62  mul     rdx
0x180004f65  mov     rax, rcx
0x180004f68  mov     rcx, [rsi+38h]
0x180004f6c  shr     rdx, 5
0x180004f70  mul     rdx
0x180004f73  mov     rax, 0AAAAAAAAAAAAAAABh
0x180004f7d  shr     rdx, 5
0x180004f81  mul     rdx
0x180004f84  mov     rax, [rsi+30h]
0x180004f88  shr     rdx, 4
0x180004f8c  mov     [rsp+580h+DeviceInfoSet], rdx
0x180004f91  lea     edx, [r8+3]
0x180004f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9a  lea     rdx, [rbp+480h+var_4D8]
0x180004f9e  lea     rcx, [rbp+480h+FileTime2]
0x180004fa2  call    pUtilGetSystemTimeOfDayInfo
0x180004fa7  mov     r14d, eax
0x180004faa  test    eax, eax
0x180004fac  jz      short loc_180004FD2
0x180004fae  lea     r9, aPutilgetsystem; "pUtilGetSystemTimeOfDayInfo failed, Err"...
0x180004fb5  mov     rcx, [rsi+38h]
0x180004fb9  xor     r8d, r8d
0x180004fbc  mov     dword ptr [rsp+580h+DeviceInfoSet], eax
0x180004fc0  mov     rax, [rsi+30h]
0x180004fc4  lea     edx, [r8+1]
0x180004fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fcd  jmp     loc_180005777
0x180004fd2  mov     rbx, qword ptr [rbp+480h+FileTime2.dwLowDateTime]
0x180004fd6  mov     r15, qword ptr [rbp+480h+var_4D8.dwLowDateTime]
0x180004fda  cmp     rbx, r15
0x180004fdd  jb      short loc_180004FEA
0x180004fdf  mov     rax, rbx
0x180004fe2  mov     ecx, r12d
0x180004fe5  sub     rax, r15
0x180004fe8  jmp     short loc_180004FF3
0x180004fea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004fee  mov     ecx, 0C0000095h
0x180004ff3  test    ecx, ecx
0x180004ff5  mov     r13, r12
0x180004ff8  lea     rcx, [rbp+480h+FileTime]; lpData
0x180004ffc  cmovns  r13, rax
0x180005000  call    pUtilGetSystemLastShutdownTime
0x180005005  mov     r14d, eax
0x180005008  test    eax, eax
0x18000500a  jz      short loc_180005015
0x18000500c  lea     r9, aPnpgetsystemla; "PnpGetSystemLastShutdownTime failed, Er"...
0x180005013  jmp     short loc_180004FB5
0x180005015  mov     rdi, qword ptr [rbp+480h+FileTime.dwLowDateTime]
0x180005019  cmp     r15, rdi
0x18000501c  jb      short loc_180005026
0x18000501e  sub     r15, rdi
0x180005021  mov     eax, r12d
0x180005024  jmp     short loc_18000502F
0x180005026  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000502a  mov     eax, 0C0000095h
0x18000502f  test    eax, eax
0x180005031  lea     rdx, [rsp+580h+LocalFileTime]; lpLocalFileTime
0x180005036  lea     rcx, [rbp+480h+FileTime]; lpFileTime
0x18000503a  cmovns  r12, r15
0x18000503e  call    cs:__imp_FileTimeToLocalFileTime
0x180005044  xor     r15d, r15d
0x180005047  test    eax, eax
0x180005049  jz      short loc_1800050B1
0x18000504b  lea     rdx, [rbp+480h+SystemTime]; lpSystemTime
0x18000504f  lea     rcx, [rsp+580h+LocalFileTime]; lpFileTime
0x180005054  call    cs:__imp_FileTimeToSystemTime
0x18000505a  test    eax, eax
0x18000505c  jz      short loc_1800050B1
0x18000505e  movzx   ecx, [rbp+480h+SystemTime.wSecond]
0x180005062  movzx   edx, [rbp+480h+SystemTime.wMinute]
0x180005066  movzx   r8d, [rbp+480h+SystemTime.wHour]
0x18000506b  movzx   r9d, [rbp+480h+SystemTime.wYear]
0x180005070  movzx   r10d, [rbp+480h+SystemTime.wDay]
0x180005075  movzx   r11d, [rbp+480h+SystemTime.wMonth]
0x18000507a  mov     rax, [rsi+30h]
0x18000507e  mov     dword ptr [rsp+580h+var_538], ecx
0x180005082  mov     rcx, [rsi+38h]
0x180005086  mov     dword ptr [rsp+580h+var_540], edx
0x18000508a  lea     edx, [r15+4]
0x18000508e  mov     dword ptr [rsp+580h+Flags], r8d
0x180005093  xor     r8d, r8d
0x180005096  mov     dword ptr [rsp+580h+Reserved], r9d
0x18000509b  lea     r9, aLastSystemShut; "Last System Shutdown Time: %02d/%02d/%0"...
0x1800050a2  mov     dword ptr [rsp+580h+MachineName], r10d
0x1800050a7  mov     dword ptr [rsp+580h+DeviceInfoSet], r11d
0x1800050ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b1  lea     rdx, [rsp+580h+LocalFileTime]; lpLocalFileTime
0x1800050b6  lea     rcx, [rbp+480h+var_4D8]; lpFileTime
0x1800050ba  call    cs:__imp_FileTimeToLocalFileTime
0x1800050c0  test    eax, eax
0x1800050c2  jz      short loc_18000512A
0x1800050c4  lea     rdx, [rbp+480h+SystemTime]; lpSystemTime
0x1800050c8  lea     rcx, [rsp+580h+LocalFileTime]; lpFileTime
0x1800050cd  call    cs:__imp_FileTimeToSystemTime
0x1800050d3  test    eax, eax
0x1800050d5  jz      short loc_18000512A
0x1800050d7  movzx   ecx, [rbp+480h+SystemTime.wSecond]
0x1800050db  movzx   edx, [rbp+480h+SystemTime.wMinute]
0x1800050df  movzx   r8d, [rbp+480h+SystemTime.wHour]
0x1800050e4  movzx   r9d, [rbp+480h+SystemTime.wYear]
0x1800050e9  movzx   r10d, [rbp+480h+SystemTime.wDay]
0x1800050ee  movzx   r11d, [rbp+480h+SystemTime.wMonth]
0x1800050f3  mov     rax, [rsi+30h]
0x1800050f7  mov     dword ptr [rsp+580h+var_538], ecx
0x1800050fb  mov     rcx, [rsi+38h]
0x1800050ff  mov     dword ptr [rsp+580h+var_540], edx
0x180005103  mov     dword ptr [rsp+580h+Flags], r8d
0x180005108  xor     r8d, r8d
0x18000510b  mov     dword ptr [rsp+580h+Reserved], r9d
0x180005110  lea     r9, aBootTime02d02d; "Boot Time: %02d/%02d/%04d, %02d:%02d:%0"...
0x180005117  mov     dword ptr [rsp+580h+MachineName], r10d
0x18000511c  mov     dword ptr [rsp+580h+DeviceInfoSet], r11d
0x180005121  lea     edx, [r8+4]
0x180005125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000512a  lea     rdx, [rsp+580h+LocalFileTime]; lpLocalFileTime
0x18000512f  lea     rcx, [rbp+480h+FileTime2]; lpFileTime
0x180005133  call    cs:__imp_FileTimeToLocalFileTime
0x180005139  test    eax, eax
0x18000513b  jz      short loc_1800051A3
0x18000513d  lea     rdx, [rbp+480h+SystemTime]; lpSystemTime
0x180005141  lea     rcx, [rsp+580h+LocalFileTime]; lpFileTime
0x180005146  call    cs:__imp_FileTimeToSystemTime
0x18000514c  test    eax, eax
0x18000514e  jz      short loc_1800051A3
0x180005150  movzx   ecx, [rbp+480h+SystemTime.wSecond]
0x180005154  movzx   edx, [rbp+480h+SystemTime.wMinute]
0x180005158  movzx   r8d, [rbp+480h+SystemTime.wHour]
0x18000515d  movzx   r9d, [rbp+480h+SystemTime.wYear]
0x180005162  movzx   r10d, [rbp+480h+SystemTime.wDay]
0x180005167  movzx   r11d, [rbp+480h+SystemTime.wMonth]
0x18000516c  mov     rax, [rsi+30h]
0x180005170  mov     dword ptr [rsp+580h+var_538], ecx
0x180005174  mov     rcx, [rsi+38h]
0x180005178  mov     dword ptr [rsp+580h+var_540], edx
0x18000517c  mov     dword ptr [rsp+580h+Flags], r8d
0x180005181  xor     r8d, r8d
0x180005184  mov     dword ptr [rsp+580h+Reserved], r9d
0x180005189  lea     r9, aCurrentTime02d; "Current Time: %02d/%02d/%04d, %02d:%02d"...
0x180005190  mov     dword ptr [rsp+580h+MachineName], r10d
0x180005195  mov     dword ptr [rsp+580h+DeviceInfoSet], r11d
0x18000519a  lea     edx, [r8+4]
0x18000519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a3  mov     rcx, [rsi+38h]
0x1800051a7  lea     r9, aSystemWasPrevi; "System was previously in shutdown state"...
0x1800051ae  xor     r8d, r8d
0x1800051b1  mov     rax, 0D6BF94D5E57A42BDh
0x1800051bb  mul     r12
0x1800051be  mov     rax, [rsi+30h]
0x1800051c2  shr     rdx, 17h
0x1800051c6  mov     [rsp+580h+DeviceInfoSet], rdx
0x1800051cb  lea     edx, [r8+4]
0x1800051cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d4  mov     rax, [rbp+480h+var_4C0]
0x1800051d8  cmp     r12, rax
0x1800051db  jbe     short loc_1800051E6
0x1800051dd  cmp     r13, rax
0x1800051e0  jb      loc_180005777
0x1800051e6  mov     [rsp+580h+Reserved], r15; Reserved
0x1800051eb  mov     r9d, 4; Flags
0x1800051f1  mov     [rsp+580h+MachineName], r15; MachineName
0x1800051f6  xor     r8d, r8d; hwndParent
0x1800051f9  xor     edx, edx; Enumerator
0x1800051fb  mov     [rsp+580h+DeviceInfoSet], r15; DeviceInfoSet
0x180005200  xor     ecx, ecx; ClassGuid
0x180005202  call    cs:__imp_SetupDiGetClassDevsExW
0x180005208  mov     r12, rax
0x18000520b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000520f  jnz     short loc_18000521F
0x180005211  call    cs:__imp_GetLastError
0x180005217  mov     r14d, eax
0x18000521a  jmp     loc_180005777
0x18000521f  xorps   xmm0, xmm0
0x180005222  mov     [rsp+580h+var_510], r15d
0x180005227  movups  xmmword ptr [rbp+480h+DeviceInfoData.cbSize], xmm0
0x18000522b  mov     rcx, rsi
0x18000522e  mov     [rbp+480h+DeviceInfoData.cbSize], 20h ; ' '
0x180005235  movups  xmmword ptr [rbp+480h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180005239  mov     r13d, r15d
0x18000523c  call    PnpCleanDevicesNotifyCallback
0x180005241  mov     r15d, 1
0x180005247  jmp     loc_180005741
0x18000524c  lea     r8, [rbp+480h+DeviceInfoData]; DeviceInfoData
0x180005250  mov     edx, r13d; MemberIndex
0x180005253  mov     rcx, r12; DeviceInfoSet
0x180005256  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000525c  test    eax, eax
0x18000525e  jz      loc_1800057C5
0x180005264  mov     r8d, [rbp+480h+DeviceInfoData.DevInst]; dnDevInst
0x180005268  lea     rdx, [rbp+480h+pulProblemNumber]; pulProblemNumber
0x18000526c  xor     r9d, r9d; ulFlags
0x18000526f  mov     [rsp+580h+DeviceInfoSet], 0; hMachine
0x180005278  lea     rcx, [rbp+480h+pulStatus]; pulStatus
0x18000527c  call    cs:__imp_CM_Get_DevNode_Status_Ex
0x180005282  cmp     eax, 0Dh
0x180005285  jnz     loc_18000572F
0x18000528b  mov     r9d, 0C8h; DeviceInstanceIdSize
0x180005291  mov     [rsp+580h+DeviceInfoSet], 0; RequiredSize
0x18000529a  lea     r8, [rbp+480h+DeviceInstanceId]; DeviceInstanceId
0x1800052a1  mov     rcx, r12; DeviceInfoSet
0x1800052a4  lea     rdx, [rbp+480h+DeviceInfoData]; DeviceInfoData
0x1800052a8  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x1800052ae  test    eax, eax
0x1800052b0  jz      loc_18000572F
0x1800052b6  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800052ba  mov     dword ptr [rsp+580h+DeviceInfoSet], r15d; bIgnoreCase
0x1800052bf  xor     eax, eax
0x1800052c1  lea     r8, aHtreeRoot0; "HTREE\\ROOT\\0"
0x1800052c8  mov     r9d, r13d; cchCount2
0x1800052cb  mov     [rbp+480h+var_52], ax
0x1800052d2  mov     edx, r13d; cchCount1
0x1800052d5  lea     rcx, [rbp+480h+DeviceInstanceId]; lpString1
0x1800052dc  call    cs:__imp_CompareStringOrdinal
0x1800052e2  cmp     eax, 2
0x1800052e5  jz      loc_18000572F
0x1800052eb  mov     ecx, [rbp+480h+DeviceInfoData.DevInst]
0x1800052ee  call    pUtilIsRootEnumeratedDevice
0x1800052f3  test    eax, eax
0x1800052f5  jnz     loc_18000572F
0x1800052fb  mov     dword ptr [rsp+580h+Flags], eax; Flags
0x1800052ff  lea     r9, [rsp+580h+PropertyType]; PropertyType
0x180005304  lea     rax, [rsp+580h+RequiredSize]
0x180005309  mov     rcx, r12; DeviceInfoSet
0x18000530c  mov     [rsp+580h+Reserved], rax; RequiredSize
0x180005311  lea     r8, DEVPKEY_Device_LastRemovalDate; PropertyKey
0x180005318  lea     rax, [rbp+480h+PropertyBuffer]
0x18000531c  mov     dword ptr [rsp+580h+MachineName], 8; PropertyBufferSize
0x180005324  lea     rdx, [rbp+480h+DeviceInfoData]; DeviceInfoData
0x180005328  mov     [rsp+580h+DeviceInfoSet], rax; PropertyBuffer
0x18000532d  call    cs:__imp_SetupDiGetDevicePropertyW
0x180005333  test    eax, eax
0x180005335  jnz     short loc_18000534A
0x180005337  call    cs:__imp_GetLastError
0x18000533d  cmp     eax, 490h
0x180005342  jnz     loc_18000572F
0x180005348  jmp     short loc_180005369
0x18000534a  cmp     [rsp+580h+PropertyType], 10h
0x18000534f  jnz     loc_18000572F
0x180005355  cmp     [rsp+580h+RequiredSize], 8
0x18000535a  jnz     loc_18000572F
0x180005360  mov     rax, qword ptr [rbp+480h+PropertyBuffer]
0x180005364  test    rax, rax
0x180005367  jnz     short loc_1800053D8
0x180005369  mov     dword ptr [rsp+580h+Flags], 0; Flags
  ... truncated ...
```
