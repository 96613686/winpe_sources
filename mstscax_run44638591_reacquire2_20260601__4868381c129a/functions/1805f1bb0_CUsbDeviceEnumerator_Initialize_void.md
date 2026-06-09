# CUsbDeviceEnumerator::Initialize(void)

- ea: `0x1805f1bb0`
- end: `0x1805f2394`
- name: `?Initialize@CUsbDeviceEnumerator@@EEAAJXZ`
- size: `2020`
- prototype: `__int64 __fastcall(CUsbDeviceEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1805ee75c`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18012966c`
- `0x1805ee3f0`
- `0x1805f05c4`
- `0x1805f1bb0`
- `0x1805f9b08`
- `0x1805f9fbc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1805f1e1c`
- `KERNEL32!CloseHandle` at `0x1805f1e1c`
- `KERNEL32!DeviceIoControl` at `0x1805f1d66`
- `KERNEL32!DeviceIoControl` at `0x1805f1e98`
- `KERNEL32!DeviceIoControl` at `0x1805f1d66`
- `KERNEL32!DeviceIoControl` at `0x1805f1e98`
- `KERNEL32!GetLastError` at `0x1805f1c6c`
- `KERNEL32!GetLastError` at `0x1805f1d74`
- `KERNEL32!GetLastError` at `0x1805f1ea2`
- `KERNEL32!GetLastError` at `0x1805f1c6c`
- `KERNEL32!GetLastError` at `0x1805f1d74`
- `KERNEL32!GetLastError` at `0x1805f1ea2`
- `KERNEL32!CreateFileW` at `0x1805f1c4f`
- `KERNEL32!CreateFileW` at `0x1805f1c4f`
- `ADVAPI32!RegOpenKeyExW` at `0x1805f1f74`
- `ADVAPI32!RegOpenKeyExW` at `0x1805f1f74`
- `ADVAPI32!RegCloseKey` at `0x1805f1e4d`
- `ADVAPI32!RegCloseKey` at `0x1805f1e4d`
- `OLE32!CLSIDFromString` at `0x1805f20ce`
- `OLE32!CLSIDFromString` at `0x1805f22b5`
- `OLE32!CLSIDFromString` at `0x1805f20ce`
- `OLE32!CLSIDFromString` at `0x1805f22b5`

## string_xrefs

- `0x1805f1f4d`: `Software\Policies\Microsoft\Windows NT\Terminal Services\Client`
- `0x1805f1d12`: `CreateFile failed`
- `0x1805f1c15`: `\\.\TerminalServicesUSBFilterDriverControlObject`

## pseudocode

```c
__int64 __fastcall CUsbDeviceEnumerator::Initialize(const unsigned __int16 ***this)
{
  unsigned __int16 *v1; // r14
  unsigned __int16 *v2; // rdi
  unsigned __int16 *v4; // r15
  signed int LastError; // eax
  int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  DWORD v11; // eax
  bool v12; // sf
  unsigned int v13; // eax
  signed int v15; // eax
  unsigned int v16; // eax
  LSTATUS v17; // r14d
  unsigned int v18; // eax
  unsigned int v19; // r14d
  GUID *v20; // r12
  unsigned int v21; // eax
  _QWORD *v22; // r15
  _DWORD *v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r15d
  GUID *v27; // r12
  unsigned int v28; // eax
  __int64 v29; // r14
  unsigned int v30; // eax
  unsigned __int16 *v31; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-41h]
  unsigned __int16 *v33; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v34[2]; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v36[3]; // [rsp+64h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  void *Block; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 **v39; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v40; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int64 v41; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp+Fh] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+17h]
  DWORD BytesReturned; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v45; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v46; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = 0;
  BytesReturned = 0;
  v2 = 0;
  v45 = 0;
  v4 = 0;
  v40 = 0;
  v36[1] = 0;
  v42 = 0;
  hKey = 0;
  v46 = 0;
  v33 = 0;
  v34[0] = 0;
  Block = 0;
  v34[1] = 0;
  v41 = 0;
  v35 = 0;
  v31 = 0;
  v36[0] = 0;
  v39 = 0;
  hObject = CreateFileW(L"\\\\.\\TerminalServicesUSBFilterDriverControlObject", 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( hObject == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    else
      v6 = LastError;
    if ( LastError == 2 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      goto LABEL_29;
    }
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 16;
      v10 = "CreateFile failed";
      goto LABEL_15;
    }
  }
  if ( DeviceIoControl(hObject, 0x224410u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    v6 = -2147024865;
LABEL_96:
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 17;
    v10 = "IOCTL_TSUSB_FILTER_QUERY_DISALLOW_DEVICE_LIST failed";
LABEL_15:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
      v8,
      (__int64)v10,
      v6);
LABEL_29:
    v2 = v31;
    goto LABEL_30;
  }
  v11 = GetLastError();
  v6 = 0;
  if ( v11 != 234 )
    v6 = v11;
  v12 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v12 = v6 < 0;
  }
  if ( v12 )
    goto LABEL_96;
  v32 = (unsigned __int16 *)operator new(BytesReturned);
  if ( !v32 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
        v13,
        (__int64)"IOCTL_TSUSB_FILTER_QUERY_DISALLOW_DEVICE_LIST_OUTPUT");
    }
    v6 = -2147024882;
LABEL_28:
    v1 = v32;
    goto LABEL_29;
  }
  if ( !DeviceIoControl(hObject, 0x224410u, 0, 0, v32, BytesReturned, &BytesReturned, 0) )
  {
    v15 = GetLastError();
    v6 = v15;
    if ( v15 > 0 )
      v6 = (unsigned __int16)v15 | 0x80070000;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
          v16,
          (__int64)"DeviceIoControl failed",
          v6);
      }
      goto LABEL_28;
    }
  }
  v1 = v32;
  if ( (int)ValidateMultiStrings(v32, BytesReturned, &v45, &v40, this + 5) < 0 )
  {
    v6 = -2147024883;
    goto LABEL_30;
  }
  *((_DWORD *)this + 12) = v45;
  v32 = 0;
  v17 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Client",
          0,
          0x20019u,
          &hKey);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v18, v17);
    }
    v1 = 0;
    goto LABEL_29;
  }
  RegQueryGuids(hKey, L"fEnableUsbSelectDeviceByInterface", L"UsbSelectDeviceByInterfaces", &v46, &v33, v34);
  if ( !v46 )
  {
    v23 = this + 8;
    v22 = this + 7;
    goto LABEL_68;
  }
  v4 = v33;
  if ( (int)ValidateMultiStrings(v33, v34[0], &v34[1], &v41, (const unsigned __int16 ***)&Block) >= 0 )
  {
    v19 = v34[1];
    v20 = (GUID *)operator new(saturated_mul(v34[1], 0x10u));
    if ( !v20 )
    {
      v6 = -2147024888;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v21);
      }
      goto LABEL_28;
    }
    if ( v19 )
    {
      while ( 1 )
      {
        v6 = CLSIDFromString(*((LPCOLESTR *)Block + (_QWORD)v2), &v20[(unsigned int)v2]);
        if ( v6 < 0 )
          break;
        v2 = (unsigned __int16 *)(unsigned int)((_DWORD)v2 + 1);
        if ( (unsigned int)v2 >= v19 )
          goto LABEL_62;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v24, v6);
      }
      goto LABEL_28;
    }
LABEL_62:
    v22 = this + 7;
    v23 = this + 8;
    this[7] = (const unsigned __int16 **)v20;
    *((_DWORD *)this + 16) = v19;
LABEL_68:
    if ( *((_DWORD *)this + 29) )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v25);
      }
      CUsbDeviceEnumerator::AppendUsbDiskInterfaceGuid((CUsbDeviceEnumerator *)(this - 2));
    }
    if ( *v23 )
      CUsbDeviceEnumerator::FindDevicesBy(this + 9, 0, *v22);
    RegQueryGuids(hKey, L"fEnableUsbBlockDeviceBySetupClass", L"UsbBlockDeviceBySetupClasses", &v35, &v31, v36);
    if ( v35 )
    {
      if ( (int)ValidateMultiStrings(v31, v36[0], &v36[1], &v42, (const unsigned __int16 ***)&v39) < 0 )
      {
        v6 = -2147024883;
LABEL_79:
        v1 = v32;
LABEL_80:
        v4 = v33;
        goto LABEL_29;
      }
      v26 = v36[1];
      v27 = (GUID *)operator new(saturated_mul(v36[1], 0x10u));
      if ( !v27 )
      {
        v6 = -2147024888;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v28);
        }
        goto LABEL_79;
      }
      v29 = 0;
      if ( v26 )
      {
        while ( 1 )
        {
          v6 = CLSIDFromString(v39[v29], &v27[(unsigned int)v29]);
          if ( v6 < 0 )
            break;
          v29 = (unsigned int)(v29 + 1);
          if ( (unsigned int)v29 >= v26 )
            goto LABEL_89;
        }
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v30, v6);
        }
        goto LABEL_79;
      }
LABEL_89:
      this[11] = (const unsigned __int16 **)v27;
      *((_DWORD *)this + 24) = v26;
      CUsbDeviceEnumerator::FindDevicesBy(this + 13, 1, v27);
    }
    v6 = 0;
    v1 = 0;
    goto LABEL_80;
  }
  v6 = -2147024883;
  v1 = 0;
LABEL_30:
  operator delete(v1);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  operator delete(Block);
  operator delete(v4);
  operator delete(v39);
  operator delete(v2);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1805f1bb0  mov     [rsp-8+arg_0], rbx
0x1805f1bb5  push    rbp
0x1805f1bb6  push    rsi
0x1805f1bb7  push    rdi
0x1805f1bb8  push    r12
0x1805f1bba  push    r13
0x1805f1bbc  push    r14
0x1805f1bbe  push    r15
0x1805f1bc0  lea     rbp, [rsp-27h]
0x1805f1bc5  sub     rsp, 0B0h
0x1805f1bcc  xor     r14d, r14d
0x1805f1bcf  mov     [rbp+57h+BytesReturned], 0
0x1805f1bd6  xor     edi, edi
0x1805f1bd8  mov     [rbp+57h+arg_10], 0
0x1805f1bdf  mov     rsi, rcx
0x1805f1be2  mov     [rsp+0E0h+hTemplateFile], rdi; hTemplateFile
0x1805f1be7  xor     r15d, r15d
0x1805f1bea  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1805f1bf2  lea     r8d, [r14+1]; dwShareMode
0x1805f1bf6  mov     [rbp+57h+var_58], 0
0x1805f1bfe  xor     r9d, r9d; lpSecurityAttributes
0x1805f1c01  mov     [rbp+57h+var_7C+4], 0
0x1805f1c08  mov     edx, 80000000h; dwDesiredAccess
0x1805f1c0d  mov     [rbp+57h+var_48], 0
0x1805f1c15  lea     rcx, FileName; "\\\\.\\TerminalServicesUSBFilterDriverC"...
0x1805f1c1c  mov     [rbp+57h+hKey], r14
0x1805f1c20  mov     [rbp+57h+arg_18], r14d
0x1805f1c24  mov     [rbp+57h+var_90], r15
0x1805f1c28  mov     [rbp+57h+var_88], r14d
0x1805f1c2c  mov     [rbp+57h+Block], r14
0x1805f1c30  mov     [rbp+57h+var_88+4], r14d
0x1805f1c34  mov     [rbp+57h+var_50], r14
0x1805f1c38  mov     [rbp+57h+var_80], r14d
0x1805f1c3c  mov     [rbp+57h+var_A0], rdi
0x1805f1c40  mov     [rbp+57h+var_7C], edi
0x1805f1c43  mov     [rbp+57h+var_60], rdi
0x1805f1c47  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1805f1c4f  call    cs:__imp_CreateFileW
0x1805f1c55  mov     [rbp+57h+hObject], rax
0x1805f1c59  mov     r12, rax
0x1805f1c5c  mov     r13d, 80070000h
0x1805f1c62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805f1c66  jnz     loc_1805F1D41
0x1805f1c6c  call    cs:__imp_GetLastError
0x1805f1c72  test    eax, eax
0x1805f1c74  jg      short loc_1805F1C7A
0x1805f1c76  mov     ebx, eax
0x1805f1c78  jmp     short loc_1805F1C80
0x1805f1c7a  movzx   ebx, ax
0x1805f1c7d  or      ebx, r13d
0x1805f1c80  cmp     eax, 2
0x1805f1c83  jnz     short loc_1805F1CD9
0x1805f1c85  mov     rax, cs:WPP_GLOBAL_Control
0x1805f1c8c  lea     rdi, WPP_GLOBAL_Control
0x1805f1c93  cmp     rax, rdi
0x1805f1c96  jz      loc_1805F1E06
0x1805f1c9c  test    byte ptr [rax+1Ch], 80h
0x1805f1ca0  jz      loc_1805F1E06
0x1805f1ca6  cmp     byte ptr [rax+19h], 3
0x1805f1caa  jb      loc_1805F1E06
0x1805f1cb0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f1cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1cbc  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f1cc3  mov     edx, 0Fh
0x1805f1cc8  mov     r9d, eax
0x1805f1ccb  mov     rcx, [rcx+10h]
0x1805f1ccf  call    WPP_SF_d
0x1805f1cd4  jmp     loc_1805F1E06
0x1805f1cd9  test    ebx, ebx
0x1805f1cdb  jns     short loc_1805F1D41
0x1805f1cdd  mov     rax, cs:WPP_GLOBAL_Control
0x1805f1ce4  lea     rdi, WPP_GLOBAL_Control
0x1805f1ceb  cmp     rax, rdi
0x1805f1cee  jz      loc_1805F1E06
0x1805f1cf4  test    byte ptr [rax+1Ch], 8
0x1805f1cf8  jz      loc_1805F1E06
0x1805f1cfe  cmp     byte ptr [rax+19h], 2
0x1805f1d02  jb      loc_1805F1E06
0x1805f1d08  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f1d0d  mov     edx, 10h
0x1805f1d12  lea     rcx, aCreatefileFail; "CreateFile failed"
0x1805f1d19  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx
0x1805f1d1d  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f1d24  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx
0x1805f1d29  mov     r9d, eax
0x1805f1d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1d33  mov     rcx, [rcx+10h]
0x1805f1d37  call    WPP_SF_DsD
0x1805f1d3c  jmp     loc_1805F1E06
0x1805f1d41  mov     [rsp+0E0h+lpOverlapped], rdi; lpOverlapped
0x1805f1d46  lea     rax, [rbp+57h+BytesReturned]
0x1805f1d4a  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1805f1d4f  xor     r9d, r9d; nInBufferSize
0x1805f1d52  mov     [rsp+0E0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1805f1d56  xor     r8d, r8d; lpInBuffer
0x1805f1d59  mov     edx, 224410h; dwIoControlCode
0x1805f1d5e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rdi; lpOutBuffer
0x1805f1d63  mov     rcx, r12; hDevice
0x1805f1d66  call    cs:__imp_DeviceIoControl
0x1805f1d6c  test    eax, eax
0x1805f1d6e  jnz     loc_1805F234E
0x1805f1d74  call    cs:__imp_GetLastError
0x1805f1d7a  xor     ebx, ebx
0x1805f1d7c  cmp     eax, 0EAh
0x1805f1d81  cmovnz  ebx, eax
0x1805f1d84  test    ebx, ebx
0x1805f1d86  jle     short loc_1805F1D90
0x1805f1d88  movzx   ebx, bx
0x1805f1d8b  or      ebx, r13d
0x1805f1d8e  test    ebx, ebx
0x1805f1d90  js      loc_1805F2353
0x1805f1d96  mov     ecx, [rbp+57h+BytesReturned]; Size
0x1805f1d99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805f1d9e  mov     [rbp+57h+var_98], rax
0x1805f1da2  mov     rcx, rax
0x1805f1da5  test    rax, rax
0x1805f1da8  jnz     loc_1805F1E70
0x1805f1dae  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1db5  lea     rdi, WPP_GLOBAL_Control
0x1805f1dbc  cmp     rcx, rdi
0x1805f1dbf  jz      short loc_1805F1DFD
0x1805f1dc1  test    byte ptr [rcx+1Ch], 8
0x1805f1dc5  jz      short loc_1805F1DFD
0x1805f1dc7  cmp     byte ptr [rcx+19h], 2
0x1805f1dcb  jb      short loc_1805F1DFD
0x1805f1dcd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f1dd2  lea     rcx, aIoctlTsusbFilt_5; "IOCTL_TSUSB_FILTER_QUERY_DISALLOW_DEVIC"...
0x1805f1dd9  mov     edx, 12h
0x1805f1dde  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx
0x1805f1de3  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f1dea  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1df1  mov     r9d, eax
0x1805f1df4  mov     rcx, [rcx+10h]
0x1805f1df8  call    WPP_SF_Ds
0x1805f1dfd  mov     ebx, 8007000Eh
0x1805f1e02  mov     r14, [rbp+57h+var_98]
0x1805f1e06  mov     rdi, [rbp+57h+var_A0]
0x1805f1e0a  mov     rcx, r14; Block
0x1805f1e0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1805f1e12  mov     rcx, [rbp+57h+hObject]; hObject
0x1805f1e16  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1805f1e1a  jz      short loc_1805F1E22
0x1805f1e1c  call    cs:__imp_CloseHandle
0x1805f1e22  mov     rcx, [rbp+57h+Block]; Block
0x1805f1e26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1805f1e2b  mov     rcx, r15; Block
0x1805f1e2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1805f1e33  mov     rcx, [rbp+57h+var_60]; Block
0x1805f1e37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1805f1e3c  mov     rcx, rdi; Block
0x1805f1e3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1805f1e44  mov     rcx, [rbp+57h+hKey]; hKey
0x1805f1e48  test    rcx, rcx
0x1805f1e4b  jz      short loc_1805F1E53
0x1805f1e4d  call    cs:__imp_RegCloseKey
0x1805f1e53  mov     eax, ebx
0x1805f1e55  mov     rbx, [rsp+0E0h+arg_0]
0x1805f1e5d  add     rsp, 0B0h
0x1805f1e64  pop     r15
0x1805f1e66  pop     r14
0x1805f1e68  pop     r13
0x1805f1e6a  pop     r12
0x1805f1e6c  pop     rdi
0x1805f1e6d  pop     rsi
0x1805f1e6e  pop     rbp
0x1805f1e6f  retn
0x1805f1e70  lea     rax, [rbp+57h+BytesReturned]
0x1805f1e74  mov     [rsp+0E0h+lpOverlapped], rdi; lpOverlapped
0x1805f1e79  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1805f1e7e  xor     r9d, r9d; nInBufferSize
0x1805f1e81  mov     eax, [rbp+57h+BytesReturned]
0x1805f1e84  xor     r8d, r8d; lpInBuffer
0x1805f1e87  mov     [rsp+0E0h+dwFlagsAndAttributes], eax; nOutBufferSize
0x1805f1e8b  mov     edx, 224410h; dwIoControlCode
0x1805f1e90  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx; lpOutBuffer
0x1805f1e95  mov     rcx, r12; hDevice
0x1805f1e98  call    cs:__imp_DeviceIoControl
0x1805f1e9e  test    eax, eax
0x1805f1ea0  jnz     short loc_1805F1F1C
0x1805f1ea2  call    cs:__imp_GetLastError
0x1805f1ea8  mov     ebx, eax
0x1805f1eaa  test    eax, eax
0x1805f1eac  jle     short loc_1805F1EB4
0x1805f1eae  movzx   ebx, ax
0x1805f1eb1  or      ebx, r13d
0x1805f1eb4  test    ebx, ebx
0x1805f1eb6  jns     short loc_1805F1F1C
0x1805f1eb8  mov     rax, cs:WPP_GLOBAL_Control
0x1805f1ebf  lea     rdi, WPP_GLOBAL_Control
0x1805f1ec6  cmp     rax, rdi
0x1805f1ec9  jz      loc_1805F1E02
0x1805f1ecf  test    byte ptr [rax+1Ch], 8
0x1805f1ed3  jz      loc_1805F1E02
0x1805f1ed9  cmp     byte ptr [rax+19h], 2
0x1805f1edd  jb      loc_1805F1E02
0x1805f1ee3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f1ee8  lea     rcx, aDeviceiocontro_0; "DeviceIoControl failed"
0x1805f1eef  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx
0x1805f1ef3  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx
0x1805f1ef8  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f1eff  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1f06  mov     edx, 13h
0x1805f1f0b  mov     r9d, eax
0x1805f1f0e  mov     rcx, [rcx+10h]
0x1805f1f12  call    WPP_SF_DsD
0x1805f1f17  jmp     loc_1805F1E02
0x1805f1f1c  mov     r14, [rbp+57h+var_98]
0x1805f1f20  lea     rax, [rsi+28h]
0x1805f1f24  mov     edx, [rbp+57h+BytesReturned]; unsigned __int64
0x1805f1f27  lea     r9, [rbp+57h+var_58]; unsigned __int64 *
0x1805f1f2b  mov     rcx, r14; unsigned __int16 *
0x1805f1f2e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; unsigned __int16 ***
0x1805f1f33  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x1805f1f37  call    ?ValidateMultiStrings@@YAJPEBG_KPEAKPEA_KPEAPEAPEBG@Z; ValidateMultiStrings(ushort const *,unsigned __int64,ulong *,unsigned __int64 *,ushort const * * *)
0x1805f1f3c  test    eax, eax
0x1805f1f3e  jns     short loc_1805F1F4A
0x1805f1f40  mov     ebx, 8007000Dh
0x1805f1f45  jmp     loc_1805F1E0A
0x1805f1f4a  mov     eax, [rbp+57h+arg_10]
0x1805f1f4d  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x1805f1f54  mov     [rsi+30h], eax
0x1805f1f57  mov     r9d, 20019h; samDesired
0x1805f1f5d  lea     rax, [rbp+57h+hKey]
0x1805f1f61  mov     [rbp+57h+var_98], rdi
0x1805f1f65  xor     r8d, r8d; ulOptions
0x1805f1f68  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; phkResult
0x1805f1f6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1805f1f74  call    cs:__imp_RegOpenKeyExW
0x1805f1f7a  mov     r14d, eax
0x1805f1f7d  test    eax, eax
0x1805f1f7f  jz      short loc_1805F1FD1
0x1805f1f81  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1f88  lea     rdi, WPP_GLOBAL_Control
0x1805f1f8f  cmp     rcx, rdi
0x1805f1f92  jz      short loc_1805F1FC9
0x1805f1f94  test    byte ptr [rcx+1Ch], 1
0x1805f1f98  jz      short loc_1805F1FC9
0x1805f1f9a  cmp     byte ptr [rcx+19h], 2
0x1805f1f9e  jb      short loc_1805F1FC9
0x1805f1fa0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f1fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f1fac  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f1fb3  mov     edx, 14h
0x1805f1fb8  mov     [rsp+0E0h+dwCreationDisposition], r14d
0x1805f1fbd  mov     r9d, eax
0x1805f1fc0  mov     rcx, [rcx+10h]
0x1805f1fc4  call    WPP_SF_Dd
0x1805f1fc9  mov     r14, r15
0x1805f1fcc  jmp     loc_1805F1E06
0x1805f1fd1  mov     rcx, [rbp+57h+hKey]; hKey
0x1805f1fd5  lea     rax, [rbp+57h+var_88]
0x1805f1fd9  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; unsigned int *
0x1805f1fde  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x1805f1fe2  lea     rax, [rbp+57h+var_90]
0x1805f1fe6  lea     r8, aUsbselectdevic; "UsbSelectDeviceByInterfaces"
0x1805f1fed  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; unsigned __int16 **
0x1805f1ff2  lea     rdx, aFenableusbsele; "fEnableUsbSelectDeviceByInterface"
0x1805f1ff9  call    ?RegQueryGuids@@YAXPEAUHKEY__@@PEBG1PEAKPEAPEAG2@Z; RegQueryGuids(HKEY__ *,ushort const *,ushort const *,ulong *,ushort * *,ulong *)
0x1805f1ffe  cmp     [rbp+57h+arg_18], edi
0x1805f2001  jz      loc_1805F2149
0x1805f2007  mov     r15, [rbp+57h+var_90]
0x1805f200b  lea     rax, [rbp+57h+Block]
0x1805f200f  mov     edx, [rbp+57h+var_88]; unsigned __int64
0x1805f2012  lea     r9, [rbp+57h+var_50]; unsigned __int64 *
0x1805f2016  mov     rcx, r15; unsigned __int16 *
0x1805f2019  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; unsigned __int16 ***
0x1805f201e  lea     r8, [rbp+57h+var_88+4]; unsigned int *
0x1805f2022  call    ?ValidateMultiStrings@@YAJPEBG_KPEAKPEA_KPEAPEAPEBG@Z; ValidateMultiStrings(ushort const *,unsigned __int64,ulong *,unsigned __int64 *,ushort const * * *)
0x1805f2027  test    eax, eax
0x1805f2029  jns     short loc_1805F2038
0x1805f202b  mov     ebx, 8007000Dh
0x1805f2030  mov     r14, rdi
0x1805f2033  jmp     loc_1805F1E0A
0x1805f2038  mov     r14d, [rbp+57h+var_88+4]
0x1805f203c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1805f2043  mov     eax, 10h
0x1805f2048  mul     r14
0x1805f204b  cmovb   rax, rcx
0x1805f204f  mov     rcx, rax; Size
0x1805f2052  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805f2057  mov     r12, rax
0x1805f205a  test    rax, rax
0x1805f205d  jnz     short loc_1805F20B8
0x1805f205f  mov     ebx, 80070008h
0x1805f2064  mov     rax, cs:WPP_GLOBAL_Control
0x1805f206b  lea     rdi, WPP_GLOBAL_Control
0x1805f2072  cmp     rax, rdi
0x1805f2075  jz      loc_1805F1E02
0x1805f207b  test    byte ptr [rax+1Ch], 1
0x1805f207f  jz      loc_1805F1E02
0x1805f2085  cmp     byte ptr [rax+19h], 2
0x1805f2089  jb      loc_1805F1E02
0x1805f208f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f2094  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f209b  lea     edx, [r12+15h]
0x1805f20a0  mov     r9d, eax
0x1805f20a3  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f20aa  mov     rcx, [rcx+10h]
0x1805f20ae  call    WPP_SF_d
0x1805f20b3  jmp     loc_1805F1E02
  ... truncated ...
```
