# NCSI_INTERFACE_HARDWARE_ATTRIBUTES::GetInterfaceHardwareAttributes(NCSI_INTERFACE_ATTRIBUTES *)

- ea: `0x180025be0`
- end: `0x1800260b0`
- name: `?GetInterfaceHardwareAttributes@NCSI_INTERFACE_HARDWARE_ATTRIBUTES@@QEAAKPEAVNCSI_INTERFACE_ATTRIBUTES@@@Z`
- size: `1232`
- prototype: `unsigned int __fastcall(LPCOLESTR lpsz, struct NCSI_INTERFACE_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a950`
- `0x180059124`

## callees

- `0x180025be0`
- `0x1800260b8`
- `0x180047240`
- `0x180047f78`
- `0x180077b24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025ece`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025f8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025fb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025ff1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025ece`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025f8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025fb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025ff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002600b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002605c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002606f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002600b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002605c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002606f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026040`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e0c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180025e9c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180025e9c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180025d21`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180025d21`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180025d82`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180025dc8`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180025d82`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180025dc8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180025c2b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180025c2b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180025f42`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180025f42`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180025e02`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180025e02`
- `DEVOBJ!DevObjGetClassDevs` at `0x180025c5a`
- `DEVOBJ!DevObjGetClassDevs` at `0x180025c5a`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180025cda`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180025cda`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180025ca4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180025ca4`

## string_xrefs

- `0x180026039`: `ImagePath`
- `0x180025f03`: `Service`
- `0x180025f7c`: `System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall NCSI_INTERFACE_HARDWARE_ATTRIBUTES::GetInterfaceHardwareAttributes(
        unsigned int *lpsz,
        struct NCSI_INTERFACE_ATTRIBUTES *a2)
{
  unsigned int BinaryVersion; // ebx
  __int64 DeviceInfoList; // rax
  __int64 v6; // r15
  __int64 v7; // rdx
  HKEY v8; // rdi
  __int64 v9; // rax
  HKEY v11; // rcx
  size_t Size; // [rsp+40h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-51h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-49h] BYREF
  GUID iid; // [rsp+68h] [rbp-41h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-31h] BYREF
  _OWORD v19[3]; // [rsp+88h] [rbp-21h] BYREF

  lpsz[20] = 0;
  BinaryVersion = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  v6 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
    return BinaryVersion;
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 10, 0, 0) )
    goto LABEL_30;
  phkResult = 0;
  memset(v19, 0, sizeof(v19));
  LODWORD(v19[0]) = 48;
  v7 = 0;
  hKey = 0;
  cbData = 0;
  iid = 0;
  *(_QWORD *)Data = 0;
  SystemTime = 0;
  for ( lpsz[20] = 0; ; v7 = lpsz[20] )
  {
    if ( !(unsigned int)DevObjEnumDeviceInfo(v6, v7, v19) || lpsz[20] == -1 )
      goto LABEL_30;
    v8 = (HKEY)DevObjOpenDevRegKey(v6, v19, 1);
    if ( v8 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      break;
LABEL_13:
    ++lpsz[20];
  }
  cbData = 78;
  BinaryVersion = RegQueryValueExW(v8, L"NetCfgInstanceId", 0, 0, (LPBYTE)lpsz, &cbData);
  if ( BinaryVersion )
    goto LABEL_12;
  BinaryVersion = IIDFromString((LPCOLESTR)lpsz, &iid);
  if ( BinaryVersion )
    goto LABEL_12;
  v9 = *(_QWORD *)&iid.Data1 - *((_QWORD *)a2 + 1);
  if ( *(_QWORD *)&iid.Data1 == *((_QWORD *)a2 + 1) )
    v9 = *(_QWORD *)iid.Data4 - *((_QWORD *)a2 + 2);
  if ( v9 )
  {
LABEL_12:
    RegCloseKey(v8);
    goto LABEL_13;
  }
  cbData = 512;
  if ( !(unsigned int)DevObjGetDeviceRegistryProperty(v6, v19, 0, 0, lpsz + 21, 512, 0) )
  {
    GetLastError();
    memset_0(lpsz + 21, 0, cbData);
  }
  cbData = 512;
  if ( !(unsigned int)DevObjGetDeviceRegistryProperty(v6, v19, 11, 0, lpsz + 149, 512, 0) )
  {
    GetLastError();
    memset_0(lpsz + 149, 0, cbData);
  }
  if ( !(unsigned int)DevObjGetDeviceInstanceId(v6, v19, lpsz + 277, 256, 0) )
  {
    GetLastError();
    memset_0(lpsz + 277, 0, cbData);
  }
  cbData = 512;
  if ( RegQueryValueExW(v8, L"DriverVersion", 0, 0, (LPBYTE)lpsz + 2132, &cbData) )
    memset_0(lpsz + 533, 0, cbData);
  cbData = 8;
  if ( !RegQueryValueExW(v8, L"DriverDateData", 0, 0, Data, &cbData)
    && FileTimeToSystemTime((const FILETIME *)Data, &SystemTime) )
  {
    *(_SYSTEMTIME *)(lpsz + 661) = SystemTime;
  }
  BinaryVersion = RegOpenKeyExW(v8, L"Ndi", 0, 0x20019u, &phkResult);
  if ( BinaryVersion || phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    goto LABEL_29;
  cbData = 512;
  BinaryVersion = RegQueryValueExW(phkResult, L"Service", 0, 0, (LPBYTE)lpsz + 2660, &cbData);
  RegCloseKey(phkResult);
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( BinaryVersion )
  {
    memset_0(lpsz + 665, 0, cbData);
LABEL_29:
    RegCloseKey(v8);
    goto LABEL_30;
  }
  BinaryVersion = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services", 0, 0x20019u, &phkResult);
  if ( BinaryVersion || phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    goto LABEL_29;
  BinaryVersion = RegOpenKeyExW(phkResult, (LPCWSTR)lpsz + 1330, 0, 0x20019u, &hKey);
  if ( BinaryVersion )
  {
    if ( wcscmp_0(L"QCWLAN", (const wchar_t *)lpsz + 1330)
      || (BinaryVersion = RegOpenKeyExW(phkResult, L"QcaWlan", 0, 0x20019u, &hKey)) != 0
      || (v11 = hKey, hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL) )
    {
      RegCloseKey(phkResult);
      goto LABEL_29;
    }
  }
  else
  {
    v11 = hKey;
  }
  cbData = 512;
  if ( RegQueryValueExW(v11, L"ImagePath", 0, 0, (LPBYTE)lpsz + 3172, &cbData) )
    memset_0(lpsz + 793, 0, cbData);
  RegCloseKey(hKey);
  RegCloseKey(phkResult);
  RegCloseKey(v8);
  LODWORD(Size) = 512;
  BinaryVersion = details::GetBinaryVersion(
                    (unsigned __int16 *)lpsz + 1586,
                    cbData,
                    (unsigned __int16 *)lpsz + 810,
                    (unsigned int *)&Size);
  if ( BinaryVersion )
    memset_0(lpsz + 405, 0, (unsigned int)Size);
LABEL_30:
  DevObjDestroyDeviceInfoList(v6);
  return BinaryVersion;
}

```

## disassembly

```asm
0x180025be0  push    rbp
0x180025be2  push    rbx
0x180025be3  push    rsi
0x180025be4  push    rdi
0x180025be5  push    r12
0x180025be7  push    r13
0x180025be9  push    r14
0x180025beb  push    r15
0x180025bed  lea     rbp, [rsp-1Fh]
0x180025bf2  sub     rsp, 0C8h
0x180025bf9  mov     rax, cs:__security_cookie
0x180025c00  xor     rax, rsp
0x180025c03  mov     [rbp+57h+var_48], rax
0x180025c07  xor     r12d, r12d
0x180025c0a  mov     r14, rdx
0x180025c0d  mov     [rcx+50h], r12d
0x180025c11  mov     rsi, rcx
0x180025c14  lea     rcx, GUID_DEVCLASS_NET
0x180025c1b  mov     [rsp+100h+lpData], r12
0x180025c20  xor     r9d, r9d
0x180025c23  xor     r8d, r8d
0x180025c26  xor     edx, edx
0x180025c28  mov     ebx, r12d
0x180025c2b  call    cs:__imp_DevObjCreateDeviceInfoList
0x180025c31  mov     r15, rax
0x180025c34  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025c38  jz      loc_180025F48
0x180025c3e  mov     [rsp+100h+lpcbData], r12
0x180025c43  lea     r9d, [r12+0Ah]
0x180025c48  xor     r8d, r8d
0x180025c4b  mov     [rsp+100h+lpData], r12
0x180025c50  lea     rdx, GUID_DEVCLASS_NET
0x180025c57  mov     rcx, rax
0x180025c5a  call    cs:__imp_DevObjGetClassDevs
0x180025c60  test    eax, eax
0x180025c62  jz      loc_180025F3F
0x180025c68  xorps   xmm0, xmm0
0x180025c6b  mov     [rbp+57h+phkResult], r12
0x180025c6f  movups  [rbp+57h+var_78], xmm0
0x180025c73  mov     dword ptr [rbp+57h+var_78], 30h ; '0'
0x180025c7a  mov     edx, r12d
0x180025c7d  movups  [rbp+57h+var_68], xmm0
0x180025c81  mov     [rbp+57h+hKey], r12
0x180025c85  movups  [rbp+57h+var_58], xmm0
0x180025c89  mov     [rbp+57h+cbData], r12d
0x180025c8d  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x180025c91  mov     qword ptr [rbp+57h+Data], r12
0x180025c95  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180025c99  mov     [rsi+50h], r12d
0x180025c9d  lea     r8, [rbp+57h+var_78]
0x180025ca1  mov     rcx, r15
0x180025ca4  call    cs:__imp_DevObjEnumDeviceInfo
0x180025caa  test    eax, eax
0x180025cac  jz      loc_180025F3F
0x180025cb2  cmp     dword ptr [rsi+50h], 0FFFFFFFFh
0x180025cb6  jnb     loc_180025F3F
0x180025cbc  xor     r9d, r9d
0x180025cbf  mov     dword ptr [rsp+100h+lpcbData], 20019h
0x180025cc7  lea     rdx, [rbp+57h+var_78]
0x180025ccb  mov     dword ptr [rsp+100h+lpData], 2
0x180025cd3  mov     rcx, r15
0x180025cd6  lea     r8d, [r9+1]
0x180025cda  call    cs:__imp_DevObjOpenDevRegKey
0x180025ce0  mov     rdi, rax
0x180025ce3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025ce7  jz      short loc_180025D4D
0x180025ce9  lea     rax, [rbp+57h+cbData]
0x180025ced  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x180025cf4  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180025cf9  lea     rdx, ValueName; "NetCfgInstanceId"
0x180025d00  xor     r9d, r9d; lpType
0x180025d03  mov     [rsp+100h+lpData], rsi; lpData
0x180025d08  xor     r8d, r8d; lpReserved
0x180025d0b  mov     rcx, rdi; hKey
0x180025d0e  call    cs:__imp_RegQueryValueExW
0x180025d14  mov     ebx, eax
0x180025d16  test    eax, eax
0x180025d18  jnz     short loc_180025D44
0x180025d1a  lea     rdx, [rbp+57h+iid]; lpiid
0x180025d1e  mov     rcx, rsi; lpsz
0x180025d21  call    cs:__imp_IIDFromString
0x180025d27  mov     ebx, eax
0x180025d29  test    eax, eax
0x180025d2b  jnz     short loc_180025D44
0x180025d2d  mov     rax, qword ptr [rbp+57h+iid.Data1]
0x180025d31  sub     rax, [r14+8]
0x180025d35  jnz     short loc_180025D3F
0x180025d37  mov     rax, qword ptr [rbp+57h+iid.Data4]
0x180025d3b  sub     rax, [r14+10h]
0x180025d3f  test    rax, rax
0x180025d42  jz      short loc_180025D58
0x180025d44  mov     rcx, rdi; hKey
0x180025d47  call    cs:__imp_RegCloseKey
0x180025d4d  inc     dword ptr [rsi+50h]
0x180025d50  mov     edx, [rsi+50h]
0x180025d53  jmp     loc_180025C9D
0x180025d58  mov     r13d, 200h
0x180025d5e  mov     [rsp+100h+var_D0], r12
0x180025d63  lea     rbx, [rsi+54h]
0x180025d67  mov     dword ptr [rsp+100h+lpcbData], r13d
0x180025d6c  xor     r9d, r9d
0x180025d6f  mov     [rsp+100h+lpData], rbx
0x180025d74  xor     r8d, r8d
0x180025d77  mov     [rbp+57h+cbData], r13d
0x180025d7b  lea     rdx, [rbp+57h+var_78]
0x180025d7f  mov     rcx, r15
0x180025d82  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180025d88  test    eax, eax
0x180025d8a  jnz     short loc_180025DA0
0x180025d8c  call    cs:__imp_GetLastError
0x180025d92  mov     r8d, [rbp+57h+cbData]; Size
0x180025d96  xor     edx, edx; Val
0x180025d98  mov     rcx, rbx; void *
0x180025d9b  call    memset_0
0x180025da0  xor     r9d, r9d
0x180025da3  mov     [rsp+100h+var_D0], r12
0x180025da8  lea     rbx, [rsi+254h]
0x180025daf  mov     dword ptr [rsp+100h+lpcbData], r13d
0x180025db4  lea     rdx, [rbp+57h+var_78]
0x180025db8  mov     [rbp+57h+cbData], r13d
0x180025dbc  mov     rcx, r15
0x180025dbf  mov     [rsp+100h+lpData], rbx
0x180025dc4  lea     r8d, [r9+0Bh]
0x180025dc8  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180025dce  test    eax, eax
0x180025dd0  jnz     short loc_180025DE6
0x180025dd2  call    cs:__imp_GetLastError
0x180025dd8  mov     r8d, [rbp+57h+cbData]; Size
0x180025ddc  xor     edx, edx; Val
0x180025dde  mov     rcx, rbx; void *
0x180025de1  call    memset_0
0x180025de6  lea     rbx, [rsi+454h]
0x180025ded  mov     [rsp+100h+lpData], r12
0x180025df2  mov     r8, rbx
0x180025df5  lea     rdx, [rbp+57h+var_78]
0x180025df9  mov     r9d, 100h
0x180025dff  mov     rcx, r15
0x180025e02  call    cs:__imp_DevObjGetDeviceInstanceId
0x180025e08  test    eax, eax
0x180025e0a  jnz     short loc_180025E20
0x180025e0c  call    cs:__imp_GetLastError
0x180025e12  mov     r8d, [rbp+57h+cbData]; Size
0x180025e16  xor     edx, edx; Val
0x180025e18  mov     rcx, rbx; void *
0x180025e1b  call    memset_0
0x180025e20  lea     rax, [rbp+57h+cbData]
0x180025e24  mov     [rbp+57h+cbData], r13d
0x180025e28  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180025e2d  lea     rbx, [rsi+854h]
0x180025e34  xor     r9d, r9d; lpType
0x180025e37  mov     [rsp+100h+lpData], rbx; lpData
0x180025e3c  xor     r8d, r8d; lpReserved
0x180025e3f  lea     rdx, aDriverversion; "DriverVersion"
0x180025e46  mov     rcx, rdi; hKey
0x180025e49  call    cs:__imp_RegQueryValueExW
0x180025e4f  test    eax, eax
0x180025e51  jz      short loc_180025E61
0x180025e53  mov     r8d, [rbp+57h+cbData]; Size
0x180025e57  xor     edx, edx; Val
0x180025e59  mov     rcx, rbx; void *
0x180025e5c  call    memset_0
0x180025e61  lea     rax, [rbp+57h+cbData]
0x180025e65  mov     [rbp+57h+cbData], 8
0x180025e6c  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180025e71  lea     rdx, aDriverdatedata; "DriverDateData"
0x180025e78  lea     rax, [rbp+57h+Data]
0x180025e7c  xor     r9d, r9d; lpType
0x180025e7f  xor     r8d, r8d; lpReserved
0x180025e82  mov     [rsp+100h+lpData], rax; lpData
0x180025e87  mov     rcx, rdi; hKey
0x180025e8a  call    cs:__imp_RegQueryValueExW
0x180025e90  test    eax, eax
0x180025e92  jnz     short loc_180025EB2
0x180025e94  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180025e98  lea     rcx, [rbp+57h+Data]; lpFileTime
0x180025e9c  call    cs:__imp_FileTimeToSystemTime
0x180025ea2  test    eax, eax
0x180025ea4  jz      short loc_180025EB2
0x180025ea6  movups  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x180025eaa  movdqu  xmmword ptr [rsi+0A54h], xmm0
0x180025eb2  lea     rax, [rbp+57h+phkResult]
0x180025eb6  mov     r9d, 20019h; samDesired
0x180025ebc  xor     r8d, r8d; ulOptions
0x180025ebf  mov     [rsp+100h+lpData], rax; phkResult
0x180025ec4  lea     rdx, SubKey; "Ndi"
0x180025ecb  mov     rcx, rdi; hKey
0x180025ece  call    cs:__imp_RegOpenKeyExW
0x180025ed4  mov     ebx, eax
0x180025ed6  test    eax, eax
0x180025ed8  jnz     short loc_180025F36
0x180025eda  mov     rcx, [rbp+57h+phkResult]; hKey
0x180025ede  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025ee2  jz      short loc_180025F36
0x180025ee4  lea     rax, [rbp+57h+cbData]
0x180025ee8  mov     [rbp+57h+cbData], r13d
0x180025eec  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180025ef1  lea     r14, [rsi+0A64h]
0x180025ef8  xor     r9d, r9d; lpType
0x180025efb  mov     [rsp+100h+lpData], r14; lpData
0x180025f00  xor     r8d, r8d; lpReserved
0x180025f03  lea     rdx, aService; "Service"
0x180025f0a  call    cs:__imp_RegQueryValueExW
0x180025f10  mov     rcx, [rbp+57h+phkResult]; hKey
0x180025f14  mov     ebx, eax
0x180025f16  call    cs:__imp_RegCloseKey
0x180025f1c  mov     [rbp+57h+phkResult], 0FFFFFFFFFFFFFFFFh
0x180025f24  test    ebx, ebx
0x180025f26  jz      short loc_180025F6A
0x180025f28  mov     r8d, [rbp+57h+cbData]; Size
0x180025f2c  xor     edx, edx; Val
0x180025f2e  mov     rcx, r14; void *
0x180025f31  call    memset_0
0x180025f36  mov     rcx, rdi; hKey
0x180025f39  call    cs:__imp_RegCloseKey
0x180025f3f  mov     rcx, r15
0x180025f42  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180025f48  mov     eax, ebx
0x180025f4a  mov     rcx, [rbp+57h+var_48]
0x180025f4e  xor     rcx, rsp; StackCookie
0x180025f51  call    __security_check_cookie
0x180025f56  add     rsp, 0C8h
0x180025f5d  pop     r15
0x180025f5f  pop     r14
0x180025f61  pop     r13
0x180025f63  pop     r12
0x180025f65  pop     rdi
0x180025f66  pop     rsi
0x180025f67  pop     rbx
0x180025f68  pop     rbp
0x180025f69  retn
0x180025f6a  lea     rax, [rbp+57h+phkResult]
0x180025f6e  mov     r9d, 20019h; samDesired
0x180025f74  xor     r8d, r8d; ulOptions
0x180025f77  mov     [rsp+100h+lpData], rax; phkResult
0x180025f7c  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services"
0x180025f83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025f8a  call    cs:__imp_RegOpenKeyExW
0x180025f90  mov     ebx, eax
0x180025f92  test    eax, eax
0x180025f94  jnz     short loc_180025F36
0x180025f96  mov     rcx, [rbp+57h+phkResult]; hKey
0x180025f9a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025f9e  jz      short loc_180025F36
0x180025fa0  lea     rax, [rbp+57h+hKey]
0x180025fa4  mov     r9d, 20019h; samDesired
0x180025faa  xor     r8d, r8d; ulOptions
0x180025fad  mov     [rsp+100h+lpData], rax; phkResult
0x180025fb2  mov     rdx, r14; lpSubKey
0x180025fb5  call    cs:__imp_RegOpenKeyExW
0x180025fbb  mov     ebx, eax
0x180025fbd  test    eax, eax
0x180025fbf  jz      short loc_180026016
0x180025fc1  mov     rdx, r14; String2
0x180025fc4  lea     rcx, aQcwlan; "QCWLAN"
0x180025fcb  call    wcscmp_0
0x180025fd0  test    eax, eax
0x180025fd2  jnz     short loc_180026007
0x180025fd4  mov     rcx, [rbp+57h+phkResult]; hKey
0x180025fd8  lea     rax, [rbp+57h+hKey]
0x180025fdc  mov     r9d, 20019h; samDesired
0x180025fe2  mov     [rsp+100h+lpData], rax; phkResult
0x180025fe7  xor     r8d, r8d; ulOptions
0x180025fea  lea     rdx, aQcawlan; "QcaWlan"
0x180025ff1  call    cs:__imp_RegOpenKeyExW
0x180025ff7  mov     ebx, eax
0x180025ff9  test    eax, eax
0x180025ffb  jnz     short loc_180026007
0x180025ffd  mov     rcx, [rbp+57h+hKey]
0x180026001  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026005  jnz     short loc_18002601A
0x180026007  mov     rcx, [rbp+57h+phkResult]; hKey
0x18002600b  call    cs:__imp_RegCloseKey
0x180026011  jmp     loc_180025F36
0x180026016  mov     rcx, [rbp+57h+hKey]; hKey
0x18002601a  lea     rax, [rbp+57h+cbData]
0x18002601e  mov     [rbp+57h+cbData], r13d
0x180026022  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180026027  lea     rbx, [rsi+0C64h]
0x18002602e  xor     r9d, r9d; lpType
0x180026031  mov     [rsp+100h+lpData], rbx; lpData
0x180026036  xor     r8d, r8d; lpReserved
0x180026039  lea     rdx, aImagepath; "ImagePath"
0x180026040  call    cs:__imp_RegQueryValueExW
0x180026046  test    eax, eax
0x180026048  jz      short loc_180026058
0x18002604a  mov     r8d, [rbp+57h+cbData]; Size
0x18002604e  xor     edx, edx; Val
0x180026050  mov     rcx, rbx; void *
0x180026053  call    memset_0
0x180026058  mov     rcx, [rbp+57h+hKey]; hKey
0x18002605c  call    cs:__imp_RegCloseKey
0x180026062  mov     rcx, [rbp+57h+phkResult]; hKey
0x180026066  call    cs:__imp_RegCloseKey
0x18002606c  mov     rcx, rdi; hKey
0x18002606f  call    cs:__imp_RegCloseKey
0x180026075  mov     edx, [rbp+57h+cbData]; unsigned int
0x180026078  lea     r9, [rbp+57h+Size]; unsigned int *
0x18002607c  lea     r8, [rsi+654h]; unsigned __int16 *
0x180026083  mov     dword ptr [rbp+57h+Size], r13d
0x180026087  mov     rcx, rbx; unsigned __int16 *
  ... truncated ...
```
