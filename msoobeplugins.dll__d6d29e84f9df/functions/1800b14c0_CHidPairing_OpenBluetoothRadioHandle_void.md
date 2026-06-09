# CHidPairing::_OpenBluetoothRadioHandle(void)

- ea: `0x1800b14c0`
- end: `0x1800b16d2`
- name: `?_OpenBluetoothRadioHandle@CHidPairing@@AEAAJXZ`
- size: `530`
- prototype: `__int64 __fastcall(CHidPairing *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b17c4`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x18000ac48`
- `0x18000bbb0`
- `0x1800b14c0`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b15ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b15ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b1669`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b1669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b169c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b169c`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800b16a5`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800b16a5`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800b1552`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800b1552`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800b14fc`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800b14fc`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800b15a2`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800b1637`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800b15a2`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800b1637`

## string_xrefs

- `0x1800b15bf`: `CHidPairing::_OpenBluetoothRadioHandle - Failed to get the required device interface detail size: hr=0x%08X`
- `0x1800b1564`: `CHidPairing::_OpenBluetoothRadioHandle - Failed to get the device interfaces: hr=0x%08X`
- `0x1800b167d`: `CHidPairing::_OpenBluetoothRadioHandle - Failed to get the device interface details: hr=0x%08X`
- `0x1800b1512`: `CHidPairing::_OpenBluetoothRadioHandle - Failed to get the class devices: hr=0x%08X`

## pseudocode

```c
__int64 __fastcall CHidPairing::_OpenBluetoothRadioHandle(CHidPairing *this)
{
  HDEVINFO ClassDevsW; // rsi
  __int64 Error; // rbx
  void *v4; // rcx
  PSP_DEVICE_INTERFACE_DETAIL_DATA_W v5; // r14
  HANDLE FileW; // rax
  DWORD RequiredSize; // [rsp+40h] [rbp-40h] BYREF
  PSP_DEVICE_INTERFACE_DETAIL_DATA_W DeviceInterfaceDetailData; // [rsp+48h] [rbp-38h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+50h] [rbp-30h] BYREF

  ClassDevsW = SetupDiGetClassDevsW(&GUID_BTHPORT_DEVICE_INTERFACE, 0, 0, 0x12u);
  if ( ClassDevsW )
  {
    memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
    DeviceInterfaceData.cbSize = 32;
    if ( SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_BTHPORT_DEVICE_INTERFACE, 0, &DeviceInterfaceData) )
    {
      RequiredSize = 0;
      if ( SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, 0, 0, &RequiredSize, 0)
        || GetLastError() == 122
        || (Error = (unsigned int)ResultFromKnownLastError(),
            UnattendLogW(
              1,
              L"CHidPairing::_OpenBluetoothRadioHandle - Failed to get the required device interface detail size: hr=0x%08X",
              Error),
            (int)Error >= 0) )
      {
        DeviceInterfaceDetailData = 0;
        LODWORD(Error) = CTCoAllocPolicy::Alloc(v4, 1u, RequiredSize, (void **)&DeviceInterfaceDetailData);
        if ( (int)Error >= 0 )
        {
          v5 = DeviceInterfaceDetailData;
          memset_0(DeviceInterfaceDetailData, 0, RequiredSize);
          v5->cbSize = 8;
          if ( SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, v5, RequiredSize, &RequiredSize, 0)
            && (FileW = CreateFileW(v5->DevicePath, 0xC0000000, 3u, 0, 3u, 0, 0), FileW != (HANDLE)-1LL) )
          {
            *((_QWORD *)this + 47) = FileW;
          }
          else
          {
            Error = (unsigned int)ResultFromKnownLastError();
            UnattendLogW(
              1,
              L"CHidPairing::_OpenBluetoothRadioHandle - Failed to get the device interface details: hr=0x%08X",
              Error);
          }
          CoTaskMemFree(v5);
        }
      }
    }
    else
    {
      Error = (unsigned int)ResultFromKnownLastError();
      UnattendLogW(1, L"CHidPairing::_OpenBluetoothRadioHandle - Failed to get the device interfaces: hr=0x%08X", Error);
    }
    SetupDiDestroyDeviceInfoList(ClassDevsW);
  }
  else
  {
    Error = (unsigned int)ResultFromKnownLastError();
    UnattendLogW(1, L"CHidPairing::_OpenBluetoothRadioHandle - Failed to get the class devices: hr=0x%08X", Error);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800b14c0  mov     [rsp-18h+arg_8], rbx
0x1800b14c5  mov     [rsp-18h+arg_10], rsi
0x1800b14ca  push    rbp
0x1800b14cb  push    r14
0x1800b14cd  push    r15
0x1800b14cf  mov     rbp, rsp
0x1800b14d2  sub     rsp, 80h
0x1800b14d9  mov     rax, cs:__security_cookie
0x1800b14e0  xor     rax, rsp
0x1800b14e3  mov     [rbp+var_10], rax
0x1800b14e7  mov     r15, rcx
0x1800b14ea  mov     r9d, 12h; Flags
0x1800b14f0  lea     rcx, GUID_BTHPORT_DEVICE_INTERFACE; ClassGuid
0x1800b14f7  xor     r8d, r8d; hwndParent
0x1800b14fa  xor     edx, edx; Enumerator
0x1800b14fc  call    cs:__imp_SetupDiGetClassDevsW
0x1800b1502  mov     rsi, rax
0x1800b1505  test    rax, rax
0x1800b1508  jnz     short loc_1800B1528
0x1800b150a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b150f  mov     r8d, eax
0x1800b1512  lea     rdx, aChidpairingOpe; "CHidPairing::_OpenBluetoothRadioHandle "...
0x1800b1519  lea     ecx, [rsi+1]
0x1800b151c  mov     ebx, eax
0x1800b151e  call    UnattendLogW
0x1800b1523  jmp     loc_1800B16AB
0x1800b1528  xorps   xmm0, xmm0
0x1800b152b  lea     rax, [rbp+var_30]
0x1800b152f  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x1800b1533  xor     r9d, r9d; MemberIndex
0x1800b1536  mov     [rbp+var_30.cbSize], 20h ; ' '
0x1800b153d  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE; InterfaceClassGuid
0x1800b1544  mov     [rsp+80h+DeviceInterfaceData], rax; DeviceInterfaceData
0x1800b1549  xor     edx, edx; DeviceInfoData
0x1800b154b  mov     rcx, rsi; DeviceInfoSet
0x1800b154e  movups  xmmword ptr [rbp+var_30.InterfaceClassGuid.Data4+4], xmm0
0x1800b1552  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x1800b1558  test    eax, eax
0x1800b155a  jnz     short loc_1800B157C
0x1800b155c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b1561  mov     r8d, eax
0x1800b1564  lea     rdx, aChidpairingOpe_1; "CHidPairing::_OpenBluetoothRadioHandle "...
0x1800b156b  mov     ecx, 1
0x1800b1570  mov     ebx, eax
0x1800b1572  call    UnattendLogW
0x1800b1577  jmp     loc_1800B16A2
0x1800b157c  lea     rax, [rbp+RequiredSize]
0x1800b1580  mov     [rsp+80h+DeviceInfoData], 0; DeviceInfoData
0x1800b1589  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x1800b158c  mov     [rsp+80h+DeviceInterfaceData], rax; RequiredSize
0x1800b1591  xor     r8d, r8d; DeviceInterfaceDetailData
0x1800b1594  mov     [rbp+RequiredSize], 0
0x1800b159b  lea     rdx, [rbp+var_30]; DeviceInterfaceData
0x1800b159f  mov     rcx, rsi; DeviceInfoSet
0x1800b15a2  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800b15a8  test    eax, eax
0x1800b15aa  jnz     short loc_1800B15DA
0x1800b15ac  call    cs:__imp_GetLastError
0x1800b15b2  cmp     eax, 7Ah ; 'z'
0x1800b15b5  jz      short loc_1800B15DA
0x1800b15b7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b15bc  mov     r8d, eax
0x1800b15bf  lea     rdx, aChidpairingOpe_2; "CHidPairing::_OpenBluetoothRadioHandle "...
0x1800b15c6  mov     ecx, 1
0x1800b15cb  mov     ebx, eax
0x1800b15cd  call    UnattendLogW
0x1800b15d2  test    ebx, ebx
0x1800b15d4  js      loc_1800B16A2
0x1800b15da  mov     r8d, [rbp+RequiredSize]; unsigned __int64
0x1800b15de  lea     r9, [rbp+DeviceInterfaceDetailData]; void **
0x1800b15e2  mov     edx, 1; unsigned int
0x1800b15e7  mov     [rbp+DeviceInterfaceDetailData], 0
0x1800b15ef  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800b15f4  mov     ebx, eax
0x1800b15f6  test    eax, eax
0x1800b15f8  js      loc_1800B16A2
0x1800b15fe  mov     r14, [rbp+DeviceInterfaceDetailData]
0x1800b1602  xor     edx, edx; Val
0x1800b1604  mov     r8d, [rbp+RequiredSize]; Size
0x1800b1608  mov     rcx, r14; void *
0x1800b160b  call    memset_0
0x1800b1610  lea     rax, [rbp+RequiredSize]
0x1800b1614  mov     dword ptr [r14], 8
0x1800b161b  mov     r9d, [rbp+RequiredSize]; DeviceInterfaceDetailDataSize
0x1800b161f  lea     rdx, [rbp+var_30]; DeviceInterfaceData
0x1800b1623  mov     [rsp+80h+DeviceInfoData], 0; DeviceInfoData
0x1800b162c  mov     r8, r14; DeviceInterfaceDetailData
0x1800b162f  mov     rcx, rsi; DeviceInfoSet
0x1800b1632  mov     [rsp+80h+DeviceInterfaceData], rax; RequiredSize
0x1800b1637  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800b163d  test    eax, eax
0x1800b163f  jz      short loc_1800B1675
0x1800b1641  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800b164a  lea     rcx, [r14+4]; lpFileName
0x1800b164e  mov     r8d, 3; dwShareMode
0x1800b1654  mov     dword ptr [rsp+80h+DeviceInfoData], 0; dwFlagsAndAttributes
0x1800b165c  xor     r9d, r9d; lpSecurityAttributes
0x1800b165f  mov     dword ptr [rsp+80h+DeviceInterfaceData], r8d; dwCreationDisposition
0x1800b1664  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b1669  call    cs:__imp_CreateFileW
0x1800b166f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b1673  jnz     short loc_1800B1692
0x1800b1675  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b167a  mov     r8d, eax
0x1800b167d  lea     rdx, aChidpairingOpe_0; "CHidPairing::_OpenBluetoothRadioHandle "...
0x1800b1684  mov     ecx, 1
0x1800b1689  mov     ebx, eax
0x1800b168b  call    UnattendLogW
0x1800b1690  jmp     short loc_1800B1699
0x1800b1692  mov     [r15+178h], rax
0x1800b1699  mov     rcx, r14; pv
0x1800b169c  call    cs:__imp_CoTaskMemFree
0x1800b16a2  mov     rcx, rsi; DeviceInfoSet
0x1800b16a5  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800b16ab  mov     eax, ebx
0x1800b16ad  mov     rcx, [rbp+var_10]
0x1800b16b1  xor     rcx, rsp; StackCookie
0x1800b16b4  call    __security_check_cookie
0x1800b16b9  lea     r11, [rsp+80h+var_s0]
0x1800b16c1  mov     rbx, [r11+28h]
0x1800b16c5  mov     rsi, [r11+30h]
0x1800b16c9  mov     rsp, r11
0x1800b16cc  pop     r15
0x1800b16ce  pop     r14
0x1800b16d0  pop     rbp
0x1800b16d1  retn
```
