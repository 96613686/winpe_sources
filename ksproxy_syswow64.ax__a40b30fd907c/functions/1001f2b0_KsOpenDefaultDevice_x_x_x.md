# KsOpenDefaultDevice(x,x,x)

- ea: `0x1001f2b0`
- end: `0x1001f39b`
- name: `_KsOpenDefaultDevice@12`
- size: `235`
- prototype: `int __stdcall(GUID *ClassGuid, int, _DWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1000cf60`
- `0x10034a30`
- `0x10034f5a`

## callees

- `0x1001f2b0`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001f357`
- `KERNEL32!GetLastError` at `0x1001f374`
- `KERNEL32!GetLastError` at `0x1001f357`
- `KERNEL32!GetLastError` at `0x1001f374`
- `KERNEL32!CreateFileW` at `0x1001f348`
- `KERNEL32!CreateFileW` at `0x1001f348`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1001f36c`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1001f36c`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1001f328`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1001f328`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1001f2d5`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1001f2d5`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1001f308`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1001f308`

## pseudocode

```c
int __stdcall KsOpenDefaultDevice(GUID *ClassGuid, int a2, _DWORD *a3)
{
  HDEVINFO ClassDevsW; // edi
  unsigned int v4; // esi
  HANDLE FileW; // eax
  signed int LastError; // eax
  signed int v7; // eax
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [esp+Ch] [ebp-228h] BYREF
  _SP_DEVICE_INTERFACE_DETAIL_DATA_W DeviceInterfaceDetailData; // [esp+28h] [ebp-20Ch] BYREF

  ClassDevsW = SetupDiGetClassDevsW(ClassGuid, 0, 0, 0x12u);
  if ( ClassDevsW != (HDEVINFO)-1 )
  {
    DeviceInterfaceData.cbSize = 28;
    v4 = 0;
    DeviceInterfaceDetailData.cbSize = 6;
    if ( SetupDiEnumDeviceInterfaces(ClassDevsW, 0, ClassGuid, 0, &DeviceInterfaceData)
      && SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, &DeviceInterfaceDetailData, 0x206u, 0, 0) )
    {
      FileW = CreateFileW(DeviceInterfaceDetailData.DevicePath, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
      *a3 = FileW;
      if ( FileW != (HANDLE)-1 )
      {
LABEL_8:
        SetupDiDestroyDeviceInfoList(ClassDevsW);
        return v4;
      }
      *a3 = 0;
    }
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
    goto LABEL_8;
  }
  v7 = GetLastError();
  v4 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    return v7;
  return v4;
}

```

## disassembly

```asm
0x1001f2b0  mov     edi, edi
0x1001f2b2  push    ebp
0x1001f2b3  mov     ebp, esp
0x1001f2b5  sub     esp, 228h
0x1001f2bb  mov     eax, ___security_cookie
0x1001f2c0  xor     eax, ebp
0x1001f2c2  mov     [ebp+var_4], eax
0x1001f2c5  push    ebx
0x1001f2c6  mov     ebx, [ebp+arg_8]
0x1001f2c9  push    esi
0x1001f2ca  mov     esi, [ebp+ClassGuid]
0x1001f2cd  push    edi
0x1001f2ce  push    12h; Flags
0x1001f2d0  push    0; hwndParent
0x1001f2d2  push    0; Enumerator
0x1001f2d4  push    esi; ClassGuid
0x1001f2d5  call    ds:__imp__SetupDiGetClassDevsW@16; SetupDiGetClassDevsW(x,x,x,x)
0x1001f2db  mov     edi, eax
0x1001f2dd  cmp     edi, 0FFFFFFFFh
0x1001f2e0  jz      loc_1001F374
0x1001f2e6  lea     eax, [ebp+DeviceInterfaceData]
0x1001f2ec  mov     [ebp+DeviceInterfaceData.cbSize], 1Ch
0x1001f2f6  push    eax; DeviceInterfaceData
0x1001f2f7  push    0; MemberIndex
0x1001f2f9  push    esi; InterfaceClassGuid
0x1001f2fa  xor     esi, esi
0x1001f2fc  mov     [ebp+DeviceInterfaceDetailData.cbSize], 6
0x1001f306  push    esi; DeviceInfoData
0x1001f307  push    edi; DeviceInfoSet
0x1001f308  call    ds:__imp__SetupDiEnumDeviceInterfaces@20; SetupDiEnumDeviceInterfaces(x,x,x,x,x)
0x1001f30e  test    eax, eax
0x1001f310  jz      short loc_1001F357
0x1001f312  push    esi; DeviceInfoData
0x1001f313  push    esi; RequiredSize
0x1001f314  push    206h; DeviceInterfaceDetailDataSize
0x1001f319  lea     eax, [ebp+DeviceInterfaceDetailData]
0x1001f31f  push    eax; DeviceInterfaceDetailData
0x1001f320  lea     eax, [ebp+DeviceInterfaceData]
0x1001f326  push    eax; DeviceInterfaceData
0x1001f327  push    edi; DeviceInfoSet
0x1001f328  call    ds:__imp__SetupDiGetDeviceInterfaceDetailW@24; SetupDiGetDeviceInterfaceDetailW(x,x,x,x,x,x)
0x1001f32e  test    eax, eax
0x1001f330  jz      short loc_1001F357
0x1001f332  push    esi; hTemplateFile
0x1001f333  push    40000080h; dwFlagsAndAttributes
0x1001f338  push    3; dwCreationDisposition
0x1001f33a  push    esi; lpSecurityAttributes
0x1001f33b  push    esi; dwShareMode
0x1001f33c  push    0C0000000h; dwDesiredAccess
0x1001f341  lea     eax, [ebp+DeviceInterfaceDetailData.DevicePath]
0x1001f347  push    eax; lpFileName
0x1001f348  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x1001f34e  mov     [ebx], eax
0x1001f350  cmp     eax, 0FFFFFFFFh
0x1001f353  jnz     short loc_1001F36B
0x1001f355  mov     [ebx], esi
0x1001f357  call    ds:__imp__GetLastError@0; GetLastError()
0x1001f35d  movzx   esi, ax
0x1001f360  or      esi, 80070000h
0x1001f366  test    eax, eax
0x1001f368  cmovle  esi, eax
0x1001f36b  push    edi; DeviceInfoSet
0x1001f36c  call    ds:__imp__SetupDiDestroyDeviceInfoList@4; SetupDiDestroyDeviceInfoList(x)
0x1001f372  jmp     short loc_1001F388
0x1001f374  call    ds:__imp__GetLastError@0; GetLastError()
0x1001f37a  movzx   esi, ax
0x1001f37d  or      esi, 80070000h
0x1001f383  test    eax, eax
0x1001f385  cmovle  esi, eax
0x1001f388  mov     ecx, [ebp+var_4]
0x1001f38b  mov     eax, esi
0x1001f38d  pop     edi
0x1001f38e  pop     esi
0x1001f38f  xor     ecx, ebp; StackCookie
0x1001f391  pop     ebx
0x1001f392  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001f397  leave
0x1001f398  retn    0Ch
```
