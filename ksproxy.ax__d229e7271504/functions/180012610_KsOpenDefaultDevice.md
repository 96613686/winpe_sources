# KsOpenDefaultDevice

- ea: `0x180012610`
- end: `0x18001278d`
- name: `KsOpenDefaultDevice`
- size: `381`
- prototype: `__int64 __fastcall(GUID *InterfaceClassGuid, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18001248c`
- `0x1800196f0`
- `0x1800402c4`

## callees

- `0x180012610`
- `0x18001f620`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001271a`
- `KERNEL32!GetLastError` at `0x18001274a`
- `KERNEL32!GetLastError` at `0x18001271a`
- `KERNEL32!GetLastError` at `0x18001274a`
- `KERNEL32!CreateFileW` at `0x1800126fe`
- `KERNEL32!CreateFileW` at `0x1800126fe`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180012738`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180012738`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800126c5`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800126c5`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180012645`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180012645`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180012690`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180012690`

## pseudocode

```c
__int64 __fastcall KsOpenDefaultDevice(GUID *InterfaceClassGuid, __int64 a2, _QWORD *a3)
{
  HDEVINFO ClassDevsW; // rdi
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+40h] [rbp-248h] BYREF
  _SP_DEVICE_INTERFACE_DETAIL_DATA_W DeviceInterfaceDetailData; // [rsp+60h] [rbp-228h] BYREF

  ClassDevsW = SetupDiGetClassDevsW(InterfaceClassGuid, 0, 0, 0x12u);
  if ( ClassDevsW != (HDEVINFO)-1LL )
  {
    DeviceInterfaceDetailData.cbSize = 8;
    memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
    DeviceInterfaceData.cbSize = 32;
    if ( SetupDiEnumDeviceInterfaces(ClassDevsW, 0, InterfaceClassGuid, 0, &DeviceInterfaceData)
      && SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, &DeviceInterfaceDetailData, 0x208u, 0, 0) )
    {
      FileW = CreateFileW(DeviceInterfaceDetailData.DevicePath, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
      *a3 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v8 = 0;
LABEL_8:
        SetupDiDestroyDeviceInfoList(ClassDevsW);
        return v8;
      }
      *a3 = 0;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  v9 = GetLastError();
  v8 = v9;
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return v8;
}

```

## disassembly

```asm
0x180012610  mov     [rsp+arg_8], rbx
0x180012615  mov     [rsp+arg_18], rsi
0x18001261a  push    rdi
0x18001261b  sub     rsp, 280h
0x180012622  mov     rax, cs:__security_cookie
0x180012629  xor     rax, rsp
0x18001262c  mov     [rsp+288h+var_18], rax
0x180012634  mov     rbx, r8
0x180012637  mov     r9d, 12h; Flags
0x18001263d  xor     r8d, r8d; hwndParent
0x180012640  xor     edx, edx; Enumerator
0x180012642  mov     rsi, rcx
0x180012645  call    cs:__imp_SetupDiGetClassDevsW
0x18001264c  nop     dword ptr [rax+rax+00h]
0x180012651  mov     rdi, rax
0x180012654  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012658  jz      loc_18001274A
0x18001265e  xorps   xmm0, xmm0
0x180012661  mov     [rsp+288h+DeviceInterfaceDetailData.cbSize], 8
0x180012669  lea     rax, [rsp+288h+var_248]
0x18001266e  xor     r9d, r9d; MemberIndex
0x180012671  movups  xmmword ptr [rsp+288h+var_248.cbSize], xmm0
0x180012676  mov     r8, rsi; InterfaceClassGuid
0x180012679  mov     [rsp+288h+var_248.cbSize], 20h ; ' '
0x180012681  xor     edx, edx; DeviceInfoData
0x180012683  mov     [rsp+288h+DeviceInterfaceData], rax; DeviceInterfaceData
0x180012688  mov     rcx, rdi; DeviceInfoSet
0x18001268b  movups  xmmword ptr [rsp+288h+var_248.InterfaceClassGuid.Data4+4], xmm0
0x180012690  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180012697  nop     dword ptr [rax+rax+00h]
0x18001269c  test    eax, eax
0x18001269e  jz      short loc_18001271A
0x1800126a0  mov     [rsp+288h+DeviceInfoData], 0; DeviceInfoData
0x1800126a9  lea     r8, [rsp+288h+DeviceInterfaceDetailData]; DeviceInterfaceDetailData
0x1800126ae  mov     r9d, 208h; DeviceInterfaceDetailDataSize
0x1800126b4  mov     [rsp+288h+DeviceInterfaceData], 0; RequiredSize
0x1800126bd  lea     rdx, [rsp+288h+var_248]; DeviceInterfaceData
0x1800126c2  mov     rcx, rdi; DeviceInfoSet
0x1800126c5  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800126cc  nop     dword ptr [rax+rax+00h]
0x1800126d1  test    eax, eax
0x1800126d3  jz      short loc_18001271A
0x1800126d5  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1800126de  lea     rcx, [rsp+288h+DeviceInterfaceDetailData.DevicePath]; lpFileName
0x1800126e3  mov     dword ptr [rsp+288h+DeviceInfoData], 40000080h; dwFlagsAndAttributes
0x1800126eb  xor     r9d, r9d; lpSecurityAttributes
0x1800126ee  xor     r8d, r8d; dwShareMode
0x1800126f1  mov     dword ptr [rsp+288h+DeviceInterfaceData], 3; dwCreationDisposition
0x1800126f9  mov     edx, 0C0000000h; dwDesiredAccess
0x1800126fe  call    cs:__imp_CreateFileW
0x180012705  nop     dword ptr [rax+rax+00h]
0x18001270a  mov     [rbx], rax
0x18001270d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012711  jnz     short loc_180012746
0x180012713  mov     qword ptr [rbx], 0
0x18001271a  call    cs:__imp_GetLastError
0x180012721  nop     dword ptr [rax+rax+00h]
0x180012726  mov     ebx, eax
0x180012728  test    eax, eax
0x18001272a  jle     short loc_180012735
0x18001272c  movzx   ebx, ax
0x18001272f  or      ebx, 80070000h
0x180012735  mov     rcx, rdi; DeviceInfoSet
0x180012738  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18001273f  nop     dword ptr [rax+rax+00h]
0x180012744  jmp     short loc_180012765
0x180012746  xor     ebx, ebx
0x180012748  jmp     short loc_180012735
0x18001274a  call    cs:__imp_GetLastError
0x180012751  nop     dword ptr [rax+rax+00h]
0x180012756  mov     ebx, eax
0x180012758  test    eax, eax
0x18001275a  jle     short loc_180012765
0x18001275c  movzx   ebx, ax
0x18001275f  or      ebx, 80070000h
0x180012765  mov     eax, ebx
0x180012767  mov     rcx, [rsp+288h+var_18]
0x18001276f  xor     rcx, rsp; StackCookie
0x180012772  call    __security_check_cookie
0x180012777  lea     r11, [rsp+288h+var_8]
0x18001277f  mov     rbx, [r11+18h]
0x180012783  mov     rsi, [r11+28h]
0x180012787  mov     rsp, r11
0x18001278a  pop     rdi
0x18001278b  retn
```
