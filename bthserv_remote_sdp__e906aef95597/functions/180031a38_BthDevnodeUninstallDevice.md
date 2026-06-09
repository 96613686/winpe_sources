# BthDevnodeUninstallDevice

- ea: `0x180031a38`
- end: `0x180031bc0`
- name: `BthDevnodeUninstallDevice`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180031788`

## callees

- `0x1800017a0`
- `0x180031a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b75`
- `DEVOBJ!DevObjUninstallDevice` at `0x180031b61`
- `DEVOBJ!DevObjUninstallDevice` at `0x180031b61`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180031a9e`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180031a9e`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x180031b45`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x180031b45`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x180031ae3`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x180031ae3`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x180031a69`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x180031a69`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x180031b10`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x180031b10`

## pseudocode

```c
__int64 __fastcall BthDevnodeUninstallDevice(__int64 a1, __int64 a2)
{
  BOOL v4; // esi
  HDEVINFO DeviceInfoList; // rdi
  signed int v6; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  WINBOOL NeedReboot; // [rsp+30h] [rbp-278h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+38h] [rbp-270h] BYREF
  WCHAR DeviceInstanceId[264]; // [rsp+60h] [rbp-248h] BYREF

  v4 = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
    goto LABEL_19;
  if ( (unsigned int)DevObjGetDeviceInstanceId(a1, a2, DeviceInstanceId, 260, 0) )
  {
    DeviceInfoData.cbSize = 32;
    v6 = 0;
    memset(&DeviceInfoData.ClassGuid, 0, 28);
    if ( SetupDiOpenDeviceInfoW(DeviceInfoList, DeviceInstanceId, 0, 0, &DeviceInfoData) )
    {
      NeedReboot = 0;
      v4 = DiUninstallDevice(HWND_MESSAGE|0x2LL, DeviceInfoList, &DeviceInfoData, 0, &NeedReboot);
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
  }
  SetupDiDestroyDeviceInfoList(DeviceInfoList);
  if ( !v4 )
  {
LABEL_19:
    if ( (unsigned int)DevObjUninstallDevice(a1, a2, 0, 0) )
    {
      return 0;
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180031a38  mov     [rsp+arg_10], rbx
0x180031a3d  push    rbp
0x180031a3e  push    rsi
0x180031a3f  push    rdi
0x180031a40  push    r14
0x180031a42  push    r15
0x180031a44  sub     rsp, 280h
0x180031a4b  mov     rax, cs:__security_cookie
0x180031a52  xor     rax, rsp
0x180031a55  mov     [rsp+2A8h+var_38], rax
0x180031a5d  mov     r14, rdx
0x180031a60  mov     rbp, rcx
0x180031a63  xor     edx, edx; hwndParent
0x180031a65  xor     ecx, ecx; ClassGuid
0x180031a67  xor     esi, esi
0x180031a69  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180031a70  nop     dword ptr [rax+rax+00h]
0x180031a75  mov     rdi, rax
0x180031a78  mov     r15d, 80004005h
0x180031a7e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031a82  jz      loc_180031B55
0x180031a88  and     [rsp+2A8h+DeviceInfoData], rsi
0x180031a8d  lea     r8, [rsp+2A8h+DeviceInstanceId]
0x180031a92  mov     r9d, 104h
0x180031a98  mov     rdx, r14
0x180031a9b  mov     rcx, rbp
0x180031a9e  call    cs:__imp_DevObjGetDeviceInstanceId
0x180031aa5  nop     dword ptr [rax+rax+00h]
0x180031aaa  test    eax, eax
0x180031aac  jz      short loc_180031B20
0x180031aae  xor     eax, eax
0x180031ab0  mov     [rsp+2A8h+var_270.cbSize], 20h ; ' '
0x180031ab8  mov     qword ptr [rsp+2A8h+var_270.DevInst], rax
0x180031abd  lea     rdx, [rsp+2A8h+DeviceInstanceId]; DeviceInstanceId
0x180031ac2  mov     dword ptr [rsp+2A8h+var_270.Reserved+4], eax
0x180031ac6  xorps   xmm0, xmm0
0x180031ac9  lea     rax, [rsp+2A8h+var_270]
0x180031ace  xor     r9d, r9d; OpenFlags
0x180031ad1  xor     r8d, r8d; hwndParent
0x180031ad4  mov     [rsp+2A8h+DeviceInfoData], rax; DeviceInfoData
0x180031ad9  mov     rcx, rdi; DeviceInfoSet
0x180031adc  xor     ebx, ebx
0x180031ade  movups  xmmword ptr [rsp+2A8h+var_270.ClassGuid.Data1], xmm0
0x180031ae3  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180031aea  nop     dword ptr [rax+rax+00h]
0x180031aef  test    eax, eax
0x180031af1  jz      short loc_180031B42
0x180031af3  and     [rsp+2A8h+NeedReboot], ebx
0x180031af7  lea     rax, [rsp+2A8h+NeedReboot]
0x180031afc  xor     r9d, r9d; Flags
0x180031aff  mov     [rsp+2A8h+DeviceInfoData], rax; NeedReboot
0x180031b04  lea     r8, [rsp+2A8h+var_270]; DeviceInfoData
0x180031b09  mov     rdx, rdi; DeviceInfoSet
0x180031b0c  or      rcx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x180031b10  call    cs:__imp_DiUninstallDevice
0x180031b17  nop     dword ptr [rax+rax+00h]
0x180031b1c  mov     esi, eax
0x180031b1e  jmp     short loc_180031B42
0x180031b20  call    cs:__imp_GetLastError
0x180031b27  nop     dword ptr [rax+rax+00h]
0x180031b2c  mov     ebx, eax
0x180031b2e  test    eax, eax
0x180031b30  jle     short loc_180031B3B
0x180031b32  movzx   ebx, ax
0x180031b35  or      ebx, 80070000h
0x180031b3b  test    ebx, ebx
0x180031b3d  js      short loc_180031B42
0x180031b3f  mov     ebx, r15d
0x180031b42  mov     rcx, rdi; DeviceInfoSet
0x180031b45  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180031b4c  nop     dword ptr [rax+rax+00h]
0x180031b51  test    esi, esi
0x180031b53  jnz     short loc_180031B96
0x180031b55  xor     r9d, r9d
0x180031b58  xor     r8d, r8d
0x180031b5b  mov     rdx, r14
0x180031b5e  mov     rcx, rbp
0x180031b61  call    cs:__imp_DevObjUninstallDevice
0x180031b68  nop     dword ptr [rax+rax+00h]
0x180031b6d  test    eax, eax
0x180031b6f  jz      short loc_180031B75
0x180031b71  xor     ebx, ebx
0x180031b73  jmp     short loc_180031B96
0x180031b75  call    cs:__imp_GetLastError
0x180031b7c  nop     dword ptr [rax+rax+00h]
0x180031b81  mov     ebx, eax
0x180031b83  test    eax, eax
0x180031b85  jle     short loc_180031B90
0x180031b87  movzx   ebx, ax
0x180031b8a  or      ebx, 80070000h
0x180031b90  test    ebx, ebx
0x180031b92  cmovns  ebx, r15d
0x180031b96  mov     eax, ebx
0x180031b98  mov     rcx, [rsp+2A8h+var_38]
0x180031ba0  xor     rcx, rsp; StackCookie
0x180031ba3  call    __security_check_cookie
0x180031ba8  mov     rbx, [rsp+2A8h+arg_10]
0x180031bb0  add     rsp, 280h
0x180031bb7  pop     r15
0x180031bb9  pop     r14
0x180031bbb  pop     rdi
0x180031bbc  pop     rsi
0x180031bbd  pop     rbp
0x180031bbe  retn
```
