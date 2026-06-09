# NotifyDevicesNeedReboot(int)

- ea: `0x18000b868`
- end: `0x18000bd48`
- name: `?NotifyDevicesNeedReboot@@YAJH@Z`
- size: `1248`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bd50`
- `0x18000c350`

## callees

- `0x18000b710`
- `0x18000b868`
- `0x18000bde4`
- `0x18000ccc6`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b9c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bc80`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b9c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bc80`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000bba0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000bbb3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000bba0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000bbb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd1d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000b952`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000b952`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bcd0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bcd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b91c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b986`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b91c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b986`
- `ntdll!NtQuerySystemInformation` at `0x18000b9a0`
- `ntdll!NtQuerySystemInformation` at `0x18000b9a0`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000baab`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000bb31`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000baab`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000bb31`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x18000baf0`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x18000bca3`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x18000baf0`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x18000bca3`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000bcef`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000bcfe`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000bcef`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000bcfe`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000ba6c`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bbe9`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bc05`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bc66`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bce2`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000ba6c`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bbe9`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bc05`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bc66`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000bce2`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000ba04`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000ba04`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x18000bbcf`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x18000bbcf`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000ba26`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000ba26`

## pseudocode

```c
__int64 __fastcall NotifyDevicesNeedReboot(int a1)
{
  signed int LastError; // eax
  signed int v3; // ebx
  bool v4; // cc
  HDEVINFO ClassDevsW; // r14
  HDEVINFO DeviceInfoList; // rdi
  signed int v7; // eax
  unsigned int v8; // esi
  int v9; // r15d
  DWORD v10; // edx
  int v11; // eax
  int v12; // esi
  DWORD i; // edx
  DWORD v14; // edx
  int v15; // esi
  BYTE PropertyBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+54h] [rbp-ACh] BYREF
  DWORD RequiredSize; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  BYTE v26[8]; // [rsp+88h] [rbp-78h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+90h] [rbp-70h] BYREF
  _OWORD SystemInformation[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v29; // [rsp+D0h] [rbp-30h]
  WCHAR DeviceInstanceId[200]; // [rsp+E0h] [rbp-20h] BYREF

  hKey = 0;
  PropertyType = 1;
  phkResult = 0;
  SystemTimeAsFileTime = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  PropertyBuffer[0] = 0;
  *(_QWORD *)v26 = 0;
  v29 = 0;
  RequiredSize = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  *(_QWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  LastError = RegCreateKeyExW(HKEY_CURRENT_USER, L"System\\CurrentControlSet\\Control", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( LastError )
    goto LABEL_2;
  if ( a1 )
    RegDeleteKeyExW(hKey, L"NotifyDeviceReboot", 0, 0);
  LastError = RegCreateKeyExW(hKey, L"NotifyDeviceReboot", 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( LastError )
    goto LABEL_2;
  if ( NtQuerySystemInformation(SystemTimeOfDayInformation, SystemInformation, 0x30u, 0) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)&SystemTimeAsFileTime -= 864000000000LL;
    *(struct _FILETIME *)&SystemInformation[0] = SystemTimeAsFileTime;
  }
  else
  {
    *(_QWORD *)&SystemInformation[0] -= v29;
    SystemTimeAsFileTime = *(struct _FILETIME *)&SystemInformation[0];
  }
  ClassDevsW = SetupDiGetClassDevsW(0, 0, 0, 6u);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = LastError <= 0;
LABEL_2:
    if ( !v4 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_51;
  }
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_49;
  }
  DeviceInfoData.cbSize = 32;
  v3 = 0;
  v8 = 0;
  v9 = 1;
  if ( SetupDiEnumDeviceInfo(ClassDevsW, 0, &DeviceInfoData) )
  {
    do
    {
      if ( SetupDiGetDevicePropertyW(
             ClassDevsW,
             &DeviceInfoData,
             &DEVPKEY_Device_IsRebootRequired,
             &PropertyType,
             PropertyBuffer,
             1u,
             &RequiredSize,
             0)
        && PropertyType == 17
        && RequiredSize == 1
        && PropertyBuffer[0]
        && SetupDiGetDeviceInstanceIdW(ClassDevsW, &DeviceInfoData, DeviceInstanceId, 0xC8u, 0) )
      {
        if ( !SetupDiGetDevicePropertyW(
                ClassDevsW,
                &DeviceInfoData,
                &DEVPKEY_Device_InstallDate,
                &PropertyType,
                v26,
                8u,
                &RequiredSize,
                0)
          || PropertyType != 16
          || RequiredSize != 8 )
        {
          *(struct _FILETIME *)v26 = SystemTimeAsFileTime;
        }
        cbData = 8;
        if ( (RegQueryValueExW(phkResult, DeviceInstanceId, 0, &Type, Data, &cbData)
           || Type != 11
           || cbData != 8
           || CompareFileTime((const FILETIME *)Data, &SystemTimeAsFileTime) <= 0
           || CompareFileTime((const FILETIME *)Data, (const FILETIME *)v26) <= 0)
          && SetupDiOpenDeviceInfoW(DeviceInfoList, DeviceInstanceId, 0, 0, 0) )
        {
          ++v8;
        }
      }
      v10 = v9++;
    }
    while ( SetupDiEnumDeviceInfo(ClassDevsW, v10, &DeviceInfoData) );
    if ( v8 == 1 )
    {
      if ( SetupDiEnumDeviceInfo(DeviceInfoList, 0, &DeviceInfoData) )
      {
        v11 = NotifyDeviceNeedsReboot(DeviceInfoList, &DeviceInfoData);
LABEL_43:
        v3 = v11;
        if ( v11 >= 0 )
        {
LABEL_44:
          GetSystemTimeAsFileTime((LPFILETIME)Data);
          v14 = 0;
          v15 = 1;
          while ( SetupDiEnumDeviceInfo(DeviceInfoList, v14, &DeviceInfoData) )
          {
            if ( SetupDiGetDeviceInstanceIdW(DeviceInfoList, &DeviceInfoData, DeviceInstanceId, 0xC8u, 0) )
              RegSetValueExW(phkResult, DeviceInstanceId, 0, 0xBu, Data, 8u);
            v14 = v15++;
          }
        }
      }
    }
    else if ( v8 > 1 )
    {
      v12 = 1;
      for ( i = 0; SetupDiEnumDeviceInfo(DeviceInfoList, i, &DeviceInfoData); i = v12++ )
      {
        if ( !memcmp_0(&DeviceInfoData.ClassGuid, &GUID_DEVCLASS_DISPLAY, 0x10u) )
        {
          v3 = NotifyDeviceNeedsReboot(DeviceInfoList, &DeviceInfoData);
          if ( v3 >= 0 )
            goto LABEL_44;
        }
      }
      v11 = NotifyMultipleDevicesNeedReboot();
      goto LABEL_43;
    }
  }
LABEL_49:
  SetupDiDestroyDeviceInfoList(ClassDevsW);
  if ( DeviceInfoList != (HDEVINFO)-1LL )
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
LABEL_51:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b868  push    rbp
0x18000b86a  push    rbx
0x18000b86b  push    rsi
0x18000b86c  push    rdi
0x18000b86d  push    r12
0x18000b86f  push    r13
0x18000b871  push    r14
0x18000b873  push    r15
0x18000b875  lea     rbp, [rsp-188h]
0x18000b87d  sub     rsp, 288h
0x18000b884  mov     rax, cs:__security_cookie
0x18000b88b  xor     rax, rsp
0x18000b88e  mov     [rbp+1C0h+var_50], rax
0x18000b895  xor     r12d, r12d
0x18000b898  lea     rax, [rsp+2C0h+hKey]
0x18000b89d  xorps   xmm0, xmm0
0x18000b8a0  mov     [rsp+2C0h+lpdwDisposition], r12; lpdwDisposition
0x18000b8a5  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000b8aa  lea     rdx, SubKey; "System\\CurrentControlSet\\Control"
0x18000b8b1  mov     edi, ecx
0x18000b8b3  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000b8b8  mov     esi, 2001Fh
0x18000b8bd  mov     [rsp+2C0h+hKey], r12
0x18000b8c2  lea     r13d, [r12+1]
0x18000b8c7  mov     [rsp+2C0h+samDesired], esi; samDesired
0x18000b8cb  xor     r9d, r9d; lpClass
0x18000b8ce  mov     [rsp+2C0h+PropertyType], r13d
0x18000b8d3  xor     r8d, r8d; Reserved
0x18000b8d6  mov     [rbp+1C0h+var_240], r12
0x18000b8da  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000b8e1  mov     qword ptr [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18000b8e6  movups  [rbp+1C0h+SystemInformation], xmm0
0x18000b8ea  mov     [rsp+2C0h+PropertyBuffer], r12b
0x18000b8ef  movups  [rbp+1C0h+var_200], xmm0
0x18000b8f3  mov     qword ptr [rbp+1C0h+var_238], r12
0x18000b8f7  movups  [rbp+1C0h+var_1F0], xmm0
0x18000b8fb  mov     [rsp+2C0h+RequiredSize], r12d
0x18000b900  movups  xmmword ptr [rbp+1C0h+DeviceInfoData.cbSize], xmm0
0x18000b904  mov     qword ptr [rsp+2C0h+Data], r12
0x18000b909  movups  xmmword ptr [rbp+1C0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18000b90d  mov     [rsp+2C0h+Type], r12d
0x18000b912  mov     [rsp+2C0h+cbData], r12d
0x18000b917  mov     [rsp+2C0h+dwOptions], r12d; dwOptions
0x18000b91c  call    cs:__imp_RegCreateKeyExW
0x18000b922  mov     ebx, eax
0x18000b924  test    eax, eax
0x18000b926  jz      short loc_18000B93C
0x18000b928  jle     loc_18000BD04
0x18000b92e  movzx   ebx, ax
0x18000b931  or      ebx, 80070000h
0x18000b937  jmp     loc_18000BD04
0x18000b93c  test    edi, edi
0x18000b93e  jz      short loc_18000B958
0x18000b940  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000b945  lea     rdx, aNotifydevicere; "NotifyDeviceReboot"
0x18000b94c  xor     r9d, r9d; Reserved
0x18000b94f  xor     r8d, r8d; samDesired
0x18000b952  call    cs:__imp_RegDeleteKeyExW
0x18000b958  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000b95d  lea     rax, [rbp+1C0h+var_240]
0x18000b961  mov     [rsp+2C0h+lpdwDisposition], r12; lpdwDisposition
0x18000b966  lea     rdx, aNotifydevicere; "NotifyDeviceReboot"
0x18000b96d  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000b972  xor     r9d, r9d; lpClass
0x18000b975  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000b97a  xor     r8d, r8d; Reserved
0x18000b97d  mov     [rsp+2C0h+samDesired], esi; samDesired
0x18000b981  mov     [rsp+2C0h+dwOptions], r13d; dwOptions
0x18000b986  call    cs:__imp_RegCreateKeyExW
0x18000b98c  mov     ebx, eax
0x18000b98e  test    eax, eax
0x18000b990  jnz     short loc_18000B928
0x18000b992  xor     r9d, r9d; ReturnLength
0x18000b995  lea     r8d, [rax+30h]; SystemInformationLength
0x18000b999  lea     rdx, [rbp+1C0h+SystemInformation]; SystemInformation
0x18000b99d  lea     ecx, [rax+3]; SystemInformationClass
0x18000b9a0  call    cs:__imp_NtQuerySystemInformation
0x18000b9a6  test    eax, eax
0x18000b9a8  jnz     short loc_18000B9BD
0x18000b9aa  mov     rax, qword ptr [rbp+1C0h+SystemInformation]
0x18000b9ae  sub     rax, qword ptr [rbp+1C0h+var_1F0]
0x18000b9b2  mov     qword ptr [rbp+1C0h+SystemInformation], rax
0x18000b9b6  mov     qword ptr [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000b9bb  jmp     short loc_18000B9F7
0x18000b9bd  lea     rcx, [rsp+2C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000b9c2  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b9c8  mov     eax, [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime]
0x18000b9cc  mov     dword ptr [rbp+1C0h+SystemInformation], eax
0x18000b9cf  mov     eax, [rsp+2C0h+SystemTimeAsFileTime.dwHighDateTime]
0x18000b9d3  mov     dword ptr [rbp+1C0h+SystemInformation+4], eax
0x18000b9d6  mov     rax, 0C92A69C000h
0x18000b9e0  mov     rcx, qword ptr [rbp+1C0h+SystemInformation]
0x18000b9e4  sub     rcx, rax
0x18000b9e7  mov     qword ptr [rbp+1C0h+SystemInformation], rcx
0x18000b9eb  mov     [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x18000b9ef  sar     rcx, 20h
0x18000b9f3  mov     [rsp+2C0h+SystemTimeAsFileTime.dwHighDateTime], ecx
0x18000b9f7  mov     r9d, 6; Flags
0x18000b9fd  xor     r8d, r8d; hwndParent
0x18000ba00  xor     edx, edx; Enumerator
0x18000ba02  xor     ecx, ecx; ClassGuid
0x18000ba04  call    cs:__imp_SetupDiGetClassDevsW
0x18000ba0a  mov     r14, rax
0x18000ba0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba11  jnz     short loc_18000BA22
0x18000ba13  call    cs:__imp_GetLastError
0x18000ba19  mov     ebx, eax
0x18000ba1b  test    eax, eax
0x18000ba1d  jmp     loc_18000B928
0x18000ba22  xor     edx, edx; hwndParent
0x18000ba24  xor     ecx, ecx; ClassGuid
0x18000ba26  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18000ba2c  mov     rdi, rax
0x18000ba2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba33  jnz     short loc_18000BA53
0x18000ba35  call    cs:__imp_GetLastError
0x18000ba3b  mov     ebx, eax
0x18000ba3d  test    eax, eax
0x18000ba3f  jle     loc_18000BCEC
0x18000ba45  movzx   ebx, ax
0x18000ba48  or      ebx, 80070000h
0x18000ba4e  jmp     loc_18000BCEC
0x18000ba53  lea     r8, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000ba57  mov     [rbp+1C0h+DeviceInfoData.cbSize], 20h ; ' '
0x18000ba5e  xor     edx, edx; MemberIndex
0x18000ba60  mov     rcx, r14; DeviceInfoSet
0x18000ba63  mov     ebx, r12d
0x18000ba66  mov     esi, r12d
0x18000ba69  mov     r15d, r13d
0x18000ba6c  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000ba72  test    eax, eax
0x18000ba74  jz      loc_18000BCEC
0x18000ba7a  mov     dword ptr [rsp+2C0h+phkResult], r12d; Flags
0x18000ba7f  lea     rax, [rsp+2C0h+RequiredSize]
0x18000ba84  mov     [rsp+2C0h+lpSecurityAttributes], rax; RequiredSize
0x18000ba89  lea     r9, [rsp+2C0h+PropertyType]; PropertyType
0x18000ba8e  lea     rax, [rsp+2C0h+PropertyBuffer]
0x18000ba93  mov     [rsp+2C0h+samDesired], r13d; PropertyBufferSize
0x18000ba98  lea     r8, DEVPKEY_Device_IsRebootRequired; PropertyKey
0x18000ba9f  mov     qword ptr [rsp+2C0h+dwOptions], rax; PropertyBuffer
0x18000baa4  lea     rdx, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000baa8  mov     rcx, r14; DeviceInfoSet
0x18000baab  call    cs:__imp_SetupDiGetDevicePropertyW
0x18000bab1  test    eax, eax
0x18000bab3  jz      loc_18000BBDC
0x18000bab9  cmp     [rsp+2C0h+PropertyType], 11h
0x18000babe  jnz     loc_18000BBDC
0x18000bac4  cmp     [rsp+2C0h+RequiredSize], r13d
0x18000bac9  jnz     loc_18000BBDC
0x18000bacf  cmp     [rsp+2C0h+PropertyBuffer], r12b
0x18000bad4  jz      loc_18000BBDC
0x18000bada  mov     r9d, 0C8h; DeviceInstanceIdSize
0x18000bae0  mov     qword ptr [rsp+2C0h+dwOptions], r12; RequiredSize
0x18000bae5  lea     r8, [rbp+1C0h+DeviceInstanceId]; DeviceInstanceId
0x18000bae9  mov     rcx, r14; DeviceInfoSet
0x18000baec  lea     rdx, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000baf0  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x18000baf6  test    eax, eax
0x18000baf8  jz      loc_18000BBDC
0x18000bafe  mov     dword ptr [rsp+2C0h+phkResult], r12d; Flags
0x18000bb03  lea     rax, [rsp+2C0h+RequiredSize]
0x18000bb08  mov     [rsp+2C0h+lpSecurityAttributes], rax; RequiredSize
0x18000bb0d  lea     r9, [rsp+2C0h+PropertyType]; PropertyType
0x18000bb12  lea     rax, [rbp+1C0h+var_238]
0x18000bb16  mov     [rsp+2C0h+samDesired], 8; PropertyBufferSize
0x18000bb1e  lea     r8, DEVPKEY_Device_InstallDate; PropertyKey
0x18000bb25  mov     qword ptr [rsp+2C0h+dwOptions], rax; PropertyBuffer
0x18000bb2a  lea     rdx, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bb2e  mov     rcx, r14; DeviceInfoSet
0x18000bb31  call    cs:__imp_SetupDiGetDevicePropertyW
0x18000bb37  test    eax, eax
0x18000bb39  jz      short loc_18000BB49
0x18000bb3b  cmp     [rsp+2C0h+PropertyType], 10h
0x18000bb40  jnz     short loc_18000BB49
0x18000bb42  cmp     [rsp+2C0h+RequiredSize], 8
0x18000bb47  jz      short loc_18000BB52
0x18000bb49  mov     rax, qword ptr [rsp+2C0h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bb4e  mov     qword ptr [rbp+1C0h+var_238], rax
0x18000bb52  mov     rcx, [rbp+1C0h+var_240]; hKey
0x18000bb56  lea     rax, [rsp+2C0h+cbData]
0x18000bb5b  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000bb60  lea     r9, [rsp+2C0h+Type]; lpType
0x18000bb65  lea     rax, [rsp+2C0h+Data]
0x18000bb6a  mov     [rsp+2C0h+cbData], 8
0x18000bb72  xor     r8d, r8d; lpReserved
0x18000bb75  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000bb7a  lea     rdx, [rbp+1C0h+DeviceInstanceId]; lpValueName
0x18000bb7e  call    cs:__imp_RegQueryValueExW
0x18000bb84  test    eax, eax
0x18000bb86  jnz     short loc_18000BBBD
0x18000bb88  cmp     [rsp+2C0h+Type], 0Bh
0x18000bb8d  jnz     short loc_18000BBBD
0x18000bb8f  cmp     [rsp+2C0h+cbData], 8
0x18000bb94  jnz     short loc_18000BBBD
0x18000bb96  lea     rdx, [rsp+2C0h+SystemTimeAsFileTime]; lpFileTime2
0x18000bb9b  lea     rcx, [rsp+2C0h+Data]; lpFileTime1
0x18000bba0  call    cs:__imp_CompareFileTime
0x18000bba6  test    eax, eax
0x18000bba8  jle     short loc_18000BBBD
0x18000bbaa  lea     rdx, [rbp+1C0h+var_238]; lpFileTime2
0x18000bbae  lea     rcx, [rsp+2C0h+Data]; lpFileTime1
0x18000bbb3  call    cs:__imp_CompareFileTime
0x18000bbb9  test    eax, eax
0x18000bbbb  jg      short loc_18000BBDC
0x18000bbbd  xor     r9d, r9d; OpenFlags
0x18000bbc0  mov     qword ptr [rsp+2C0h+dwOptions], r12; DeviceInfoData
0x18000bbc5  xor     r8d, r8d; hwndParent
0x18000bbc8  lea     rdx, [rbp+1C0h+DeviceInstanceId]; DeviceInstanceId
0x18000bbcc  mov     rcx, rdi; DeviceInfoSet
0x18000bbcf  call    cs:__imp_SetupDiOpenDeviceInfoW
0x18000bbd5  test    eax, eax
0x18000bbd7  jz      short loc_18000BBDC
0x18000bbd9  add     esi, r13d
0x18000bbdc  mov     edx, r15d; MemberIndex
0x18000bbdf  lea     r8, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bbe3  mov     rcx, r14; DeviceInfoSet
0x18000bbe6  add     r15d, r13d
0x18000bbe9  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000bbef  test    eax, eax
0x18000bbf1  jnz     loc_18000BA7A
0x18000bbf7  cmp     esi, r13d
0x18000bbfa  jnz     short loc_18000BC21
0x18000bbfc  lea     r8, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bc00  xor     edx, edx; MemberIndex
0x18000bc02  mov     rcx, rdi; DeviceInfoSet
0x18000bc05  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000bc0b  test    eax, eax
0x18000bc0d  jz      loc_18000BCEC
0x18000bc13  lea     rdx, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bc17  mov     rcx, rdi; DeviceInfoSet
0x18000bc1a  call    ?NotifyDeviceNeedsReboot@@YAJPEAXPEAU_SP_DEVINFO_DATA@@@Z; NotifyDeviceNeedsReboot(void *,_SP_DEVINFO_DATA *)
0x18000bc1f  jmp     short loc_18000BC75
0x18000bc21  jbe     loc_18000BCEC
0x18000bc27  mov     esi, r13d
0x18000bc2a  xor     edx, edx
0x18000bc2c  jmp     short loc_18000BC5F
0x18000bc2e  mov     r8d, 10h; Size
0x18000bc34  lea     rdx, GUID_DEVCLASS_DISPLAY; Buf2
0x18000bc3b  lea     rcx, [rbp+1C0h+DeviceInfoData.ClassGuid]; Buf1
0x18000bc3f  call    memcmp_0
0x18000bc44  test    eax, eax
0x18000bc46  jnz     short loc_18000BC5A
0x18000bc48  lea     rdx, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bc4c  mov     rcx, rdi; DeviceInfoSet
0x18000bc4f  call    ?NotifyDeviceNeedsReboot@@YAJPEAXPEAU_SP_DEVINFO_DATA@@@Z; NotifyDeviceNeedsReboot(void *,_SP_DEVINFO_DATA *)
0x18000bc54  mov     ebx, eax
0x18000bc56  test    eax, eax
0x18000bc58  jns     short loc_18000BC7B
0x18000bc5a  mov     edx, esi; MemberIndex
0x18000bc5c  add     esi, r13d
0x18000bc5f  lea     r8, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bc63  mov     rcx, rdi; DeviceInfoSet
0x18000bc66  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000bc6c  test    eax, eax
0x18000bc6e  jnz     short loc_18000BC2E
0x18000bc70  call    ?NotifyMultipleDevicesNeedReboot@@YAJXZ; NotifyMultipleDevicesNeedReboot(void)
0x18000bc75  mov     ebx, eax
0x18000bc77  test    eax, eax
0x18000bc79  js      short loc_18000BCEC
0x18000bc7b  lea     rcx, [rsp+2C0h+Data]; lpSystemTimeAsFileTime
0x18000bc80  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bc86  xor     edx, edx
0x18000bc88  mov     esi, r13d
0x18000bc8b  jmp     short loc_18000BCDB
0x18000bc8d  mov     r9d, 0C8h; DeviceInstanceIdSize
0x18000bc93  mov     qword ptr [rsp+2C0h+dwOptions], r12; RequiredSize
0x18000bc98  lea     r8, [rbp+1C0h+DeviceInstanceId]; DeviceInstanceId
0x18000bc9c  mov     rcx, rdi; DeviceInfoSet
0x18000bc9f  lea     rdx, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bca3  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x18000bca9  test    eax, eax
0x18000bcab  jz      short loc_18000BCD6
0x18000bcad  mov     rcx, [rbp+1C0h+var_240]; hKey
0x18000bcb1  lea     rax, [rsp+2C0h+Data]
0x18000bcb6  mov     [rsp+2C0h+samDesired], 8; cbData
0x18000bcbe  lea     rdx, [rbp+1C0h+DeviceInstanceId]; lpValueName
0x18000bcc2  mov     r9d, 0Bh; dwType
0x18000bcc8  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000bccd  xor     r8d, r8d; Reserved
0x18000bcd0  call    cs:__imp_RegSetValueExW
0x18000bcd6  mov     edx, esi; MemberIndex
0x18000bcd8  add     esi, r13d
0x18000bcdb  lea     r8, [rbp+1C0h+DeviceInfoData]; DeviceInfoData
0x18000bcdf  mov     rcx, rdi; DeviceInfoSet
0x18000bce2  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000bce8  test    eax, eax
0x18000bcea  jnz     short loc_18000BC8D
0x18000bcec  mov     rcx, r14; DeviceInfoSet
0x18000bcef  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000bcf5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000bcf9  jz      short loc_18000BD04
0x18000bcfb  mov     rcx, rdi; DeviceInfoSet
0x18000bcfe  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000bd04  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000bd09  test    rcx, rcx
0x18000bd0c  jz      short loc_18000BD14
0x18000bd0e  call    cs:__imp_RegCloseKey
0x18000bd14  mov     rcx, [rbp+1C0h+var_240]; hKey
0x18000bd18  test    rcx, rcx
0x18000bd1b  jz      short loc_18000BD23
  ... truncated ...
```
