# CTsUsbDevice::Initialize(ILocalDevice *,_GUID const &,IUsbRedirectionDeviceNotification *,ulong)

- ea: `0x1805f66d8`
- end: `0x1805f7476`
- name: `?Initialize@CTsUsbDevice@@AEAAJPEAUILocalDevice@@AEBU_GUID@@PEAUIUsbRedirectionDeviceNotification@@K@Z`
- size: `3486`
- prototype: `__int64 __usercall@<rax>(CTsUsbDevice *__hidden this@<rcx>, struct ILocalDevice *@<rdx>, const struct _GUID *@<r8>, struct IUsbRedirectionDeviceNotification *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1805f6588`

## callees

- `0x1800172ec`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18003cc5c`
- `0x1800e9b1c`
- `0x180101d30`
- `0x18012962c`
- `0x18012966c`
- `0x1801305a4`
- `0x1805f66d8`
- `0x1805f877c`
- `0x1805fa160`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x1805f7208`
- `ntdll!RtlStringFromGUID` at `0x1805f7208`
- `KERNEL32!DeviceIoControl` at `0x1805f6d95`
- `KERNEL32!DeviceIoControl` at `0x1805f6e21`
- `KERNEL32!DeviceIoControl` at `0x1805f6ec4`
- `KERNEL32!DeviceIoControl` at `0x1805f6f4b`
- `KERNEL32!DeviceIoControl` at `0x1805f6d95`
- `KERNEL32!DeviceIoControl` at `0x1805f6e21`
- `KERNEL32!DeviceIoControl` at `0x1805f6ec4`
- `KERNEL32!DeviceIoControl` at `0x1805f6f4b`
- `KERNEL32!GetLastError` at `0x1805f6b0c`
- `KERNEL32!GetLastError` at `0x1805f6b8d`
- `KERNEL32!GetLastError` at `0x1805f6c00`
- `KERNEL32!GetLastError` at `0x1805f6c94`
- `KERNEL32!GetLastError` at `0x1805f6d13`
- `KERNEL32!GetLastError` at `0x1805f6da3`
- `KERNEL32!GetLastError` at `0x1805f6e2b`
- `KERNEL32!GetLastError` at `0x1805f6ed2`
- `KERNEL32!GetLastError` at `0x1805f6f55`
- `KERNEL32!GetLastError` at `0x1805f6fcd`
- `KERNEL32!GetLastError` at `0x1805f7043`
- `KERNEL32!GetLastError` at `0x1805f70cd`
- `KERNEL32!GetLastError` at `0x1805f6b0c`
- `KERNEL32!GetLastError` at `0x1805f6b8d`
- `KERNEL32!GetLastError` at `0x1805f6c00`
- `KERNEL32!GetLastError` at `0x1805f6c94`
- `KERNEL32!GetLastError` at `0x1805f6d13`
- `KERNEL32!GetLastError` at `0x1805f6da3`
- `KERNEL32!GetLastError` at `0x1805f6e2b`
- `KERNEL32!GetLastError` at `0x1805f6ed2`
- `KERNEL32!GetLastError` at `0x1805f6f55`
- `KERNEL32!GetLastError` at `0x1805f6fcd`
- `KERNEL32!GetLastError` at `0x1805f7043`
- `KERNEL32!GetLastError` at `0x1805f70cd`
- `KERNEL32!CreateFileW` at `0x1805f6b00`
- `KERNEL32!CreateFileW` at `0x1805f6b81`
- `KERNEL32!CreateFileW` at `0x1805f6c88`
- `KERNEL32!CreateFileW` at `0x1805f6b00`
- `KERNEL32!CreateFileW` at `0x1805f6b81`
- `KERNEL32!CreateFileW` at `0x1805f6c88`
- `KERNEL32!CreateIoCompletionPort` at `0x1805f6bee`
- `KERNEL32!CreateIoCompletionPort` at `0x1805f6bee`
- `KERNEL32!CreateThread` at `0x1805f6d01`
- `KERNEL32!CreateThread` at `0x1805f6d01`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1805f7039`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1805f7039`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1805f70f1`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1805f70f1`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805f70bf`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805f70bf`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f7410`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f7410`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f6fbe`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f6fbe`
- `ADVAPI32!RegQueryValueExW` at `0x1805f7129`
- `ADVAPI32!RegQueryValueExW` at `0x1805f7129`
- `ADVAPI32!RegCloseKey` at `0x1805f7437`
- `ADVAPI32!RegCloseKey` at `0x1805f7437`
- `OLE32!CoTaskMemFree` at `0x1805f7447`
- `OLE32!CoTaskMemFree` at `0x1805f7447`
- `RPCRT4!UuidToStringW` at `0x1805f6951`
- `RPCRT4!UuidToStringW` at `0x1805f6951`
- `RPCRT4!RpcStringFreeW` at `0x1805f7423`
- `RPCRT4!RpcStringFreeW` at `0x1805f7423`

## string_xrefs

- `0x1805f708d`: `DevObjOpenDeviceInterface failed`
- `0x1805f7017`: `DevObjCreateDeviceInfoList failed`
- `0x1805f681e`: `CSimpleHash::CreateInstance failed`

## pseudocode

```c
__int64 __fastcall CTsUsbDevice::Initialize(
        CTsUsbDevice *this,
        struct ILocalDevice *a2,
        const struct _GUID *a3,
        struct IUsbRedirectionDeviceNotification *a4,
        unsigned int a5)
{
  unsigned __int16 *v6; // r13
  __int64 DeviceInfoList; // r12
  int Version; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx
  int Instance; // ebx
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  HANDLE FileW; // rax
  signed int v23; // eax
  HANDLE v24; // rax
  signed int LastError; // eax
  HANDLE IoCompletionPort; // rax
  signed int v27; // edi
  unsigned int v28; // eax
  HANDLE v29; // rax
  signed int v30; // eax
  HANDLE Thread; // rax
  signed int v32; // eax
  void *v33; // rcx
  signed int v34; // eax
  void *v35; // rax
  signed int v36; // eax
  void *v37; // rcx
  signed int v38; // eax
  void *v39; // rax
  signed int v40; // eax
  signed int v41; // eax
  signed int v42; // eax
  HKEY v43; // rax
  LSTATUS v44; // eax
  bool v45; // cc
  __int64 v46; // rax
  NTSTATUS v47; // ebx
  unsigned int v48; // eax
  unsigned int v49; // eax
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-D8h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int InBuffer; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h]
  __int128 v62; // [rsp+80h] [rbp-80h] BYREF
  __int128 v63; // [rsp+90h] [rbp-70h] BYREF
  __int128 v64; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v65[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v66[3]; // [rsp+D0h] [rbp-30h] BYREF

  *((_DWORD *)this + 13) |= 2u;
  v59 = 0;
  InBuffer = 0;
  BytesReturned = 0;
  v60 = 0;
  memset(v66, 0, sizeof(v66));
  cbData = 0;
  v6 = 0;
  Type = 0;
  DeviceInfoList = -1;
  pv = 0;
  memset(v65, 0, sizeof(v65));
  StringUuid = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v63 = 0;
  if ( !(unsigned int)CTSCriticalSection::Initialize((CTsUsbDevice *)((char *)this + 296)) )
  {
    Version = -2147467259;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 13;
LABEL_6:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_93936833bc2036c13ede136827ee6600_Traceguids,
        CurrentThreadActivityIdPrefix);
      goto LABEL_180;
    }
    goto LABEL_180;
  }
  Instance = CSimpleHash::CreateInstance(0x10u, (struct CSimpleHash **)this + 35);
  if ( Instance < 0 )
  {
    Version = Instance | 0x10000000;
    if ( Version < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_180;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 14;
      v17 = "CSimpleHash::CreateInstance failed";
      goto LABEL_179;
    }
  }
  Version = (*(__int64 (__fastcall **)(struct ILocalDevice *, _QWORD, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, 0, &v63);
  if ( Version < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_180;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 15;
    v17 = "ILocalDevice::GetInterfaceGuid FAILED";
    goto LABEL_179;
  }
  v18 = *(_QWORD *)a2;
  v62 = v63;
  Version = (*(__int64 (__fastcall **)(struct ILocalDevice *, __int128 *, LPVOID *))(v18 + 40))(a2, &v62, &pv);
  if ( Version < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_180;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 16;
    v17 = "ILocalDevice::GetFileName FAILED";
    goto LABEL_179;
  }
  Version = StringCbLengthW((const unsigned __int16 *)pv, 0xFFFFu, &v59);
  if ( Version < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_180;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 17;
    v17 = "StringCbLengthW failed";
    goto LABEL_179;
  }
  if ( UuidToStringW(a3, &StringUuid) )
  {
    Version = -2147024888;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_93936833bc2036c13ede136827ee6600_Traceguids,
        v19,
        (__int64)"UuidToString failed",
        -2147024888);
    }
    goto LABEL_180;
  }
  Version = StringCchLengthW(StringUuid, 0xFFFFu, &v60);
  if ( Version < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_180;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 19;
    v17 = "StringCchLengthW(interfaceStr) failed";
    goto LABEL_179;
  }
  v20 = v59 + 2 * (v60 + 4);
  if ( v20 < v59 )
  {
    Version = -2147467259;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_93936833bc2036c13ede136827ee6600_Traceguids,
        v21,
        (__int64)"SizeTAdd failed",
        -2147467259);
    }
    goto LABEL_180;
  }
  v6 = (unsigned __int16 *)operator new(v59 + 2 * (v60 + 4));
  Version = StringCbPrintfW(v6, v20, L"%ws\\{%ws}", pv, StringUuid);
  if ( Version < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_180;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 21;
    v17 = "StringCbPrintfW failed";
    goto LABEL_179;
  }
  FileW = CreateFileW(v6, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    *((_QWORD *)this + 26) = FileW;
    v24 = CreateFileW(v6, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    if ( v24 == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      Version = LastError;
      if ( LastError > 0 )
        Version = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 23;
        goto LABEL_6;
      }
      goto LABEL_180;
    }
    *((_QWORD *)this + 27) = v24;
    IoCompletionPort = CreateIoCompletionPort(v24, 0, 0, 0);
    *((_QWORD *)this + 29) = IoCompletionPort;
    if ( !IoCompletionPort )
    {
      v27 = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_93936833bc2036c13ede136827ee6600_Traceguids, v28, v27);
      }
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      if ( v27 >= 0 )
        v27 = -2147467259;
      Version = v27;
      goto LABEL_180;
    }
    v29 = CreateFileW(v6, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( v29 == (HANDLE)-1LL )
    {
      v30 = GetLastError();
      Version = v30;
      if ( v30 > 0 )
        Version = (unsigned __int16)v30 | 0x80070000;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 25;
        goto LABEL_6;
      }
      goto LABEL_180;
    }
    *((_QWORD *)this + 28) = v29;
    Thread = CreateThread(0, 0, CTsUsbDevice::CompletionThread, this, 0, 0);
    *((_QWORD *)this + 30) = Thread;
    if ( !Thread )
    {
      v32 = GetLastError();
      Version = v32;
      if ( v32 > 0 )
        Version = (unsigned __int16)v32 | 0x80070000;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 26;
        goto LABEL_6;
      }
      goto LABEL_180;
    }
    v33 = (void *)*((_QWORD *)this + 28);
    InBuffer = 0;
    if ( DeviceIoControl(v33, 0x224404u, &InBuffer, 4u, 0, 0, &BytesReturned, 0) )
    {
      Version = -2147024883;
    }
    else
    {
      v34 = GetLastError();
      if ( v34 > 0 )
        Version = (unsigned __int16)v34 | 0x80070000;
      else
        Version = v34;
      if ( v34 == 234 )
      {
        v35 = operator new(BytesReturned);
        *((_QWORD *)this + 9) = v35;
        if ( !v35 )
        {
          Version = -2147024888;
          goto LABEL_174;
        }
LABEL_94:
        if ( !DeviceIoControl(
                *((HANDLE *)this + 28),
                0x224404u,
                &InBuffer,
                4u,
                *((LPVOID *)this + 9),
                BytesReturned,
                &BytesReturned,
                0) )
        {
          v36 = GetLastError();
          Version = v36;
          if ( v36 > 0 )
            Version = (unsigned __int16)v36 | 0x80070000;
          if ( Version < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_180;
            }
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            v16 = 28;
            goto LABEL_178;
          }
        }
        v37 = (void *)*((_QWORD *)this + 28);
        *((_DWORD *)this + 20) = BytesReturned;
        InBuffer = 1;
        if ( DeviceIoControl(v37, 0x224404u, &InBuffer, 4u, 0, 0, &BytesReturned, 0) )
        {
          Version = -2147024883;
        }
        else
        {
          v38 = GetLastError();
          if ( v38 > 0 )
            Version = (unsigned __int16)v38 | 0x80070000;
          else
            Version = v38;
          if ( v38 == 234 )
          {
            v39 = operator new(BytesReturned);
            *((_QWORD *)this + 11) = v39;
            if ( !v39 )
            {
              Version = -2147024888;
              goto LABEL_169;
            }
LABEL_110:
            if ( !DeviceIoControl(
                    *((HANDLE *)this + 28),
                    0x224404u,
                    &InBuffer,
                    4u,
                    *((LPVOID *)this + 11),
                    BytesReturned,
                    &BytesReturned,
                    0) )
            {
              v40 = GetLastError();
              Version = v40;
              if ( v40 > 0 )
                Version = (unsigned __int16)v40 | 0x80070000;
              if ( Version < 0 )
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_180;
                }
                v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                v16 = 30;
                goto LABEL_178;
              }
            }
            *((_DWORD *)this + 24) = BytesReturned;
            DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
            if ( DeviceInfoList == -1 )
            {
              v41 = GetLastError();
              Version = v41;
              if ( v41 > 0 )
                Version = (unsigned __int16)v41 | 0x80070000;
              if ( Version < 0 )
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_180;
                }
                v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                v16 = 31;
                v17 = "DevObjCreateDeviceInfoList failed";
                goto LABEL_179;
              }
            }
            LODWORD(v65[0]) = 32;
            if ( !(unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, pv, 0, v65) )
            {
              v42 = GetLastError();
              Version = v42;
              if ( v42 > 0 )
                Version = (unsigned __int16)v42 | 0x80070000;
              if ( Version < 0 )
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_180;
                }
                v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                v16 = 32;
                v17 = "DevObjOpenDeviceInterface failed";
                goto LABEL_179;
              }
            }
            LODWORD(v66[0]) = 48;
            if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v65, 0, 0, 0, v66) )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v49 = RdpWppGetCurrentThreadActivityIdPrefix();
                dwFlagsAndAttributesa[0] = -2147024883;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33,
                  (unsigned int)WPP_93936833bc2036c13ede136827ee6600_Traceguids,
                  v49,
                  (__int64)"unable to get DO_DEVINFO_DATA",
                  *(_QWORD *)dwFlagsAndAttributesa);
              }
              Version = -2147024883;
              goto LABEL_180;
            }
            GetLastError();
            v43 = (HKEY)DevObjOpenDevRegKey(DeviceInfoList, v66, 1);
            cbData = 74;
            hKey = v43;
            v44 = RegQueryValueExW(v43, L"ProxyDeviceInstanceID", 0, &Type, (LPBYTE)this + 100, &cbData);
            Version = v44;
            v45 = v44 <= 0;
            if ( !v44 )
            {
              if ( Type != 1 )
                goto LABEL_141;
              if ( cbData == 74 )
                goto LABEL_146;
              v45 = 1;
            }
            if ( !v45 )
              Version = (unsigned __int16)v44 | 0x80070000;
LABEL_141:
            if ( Version < 0 )
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_180;
              }
              v15 = RdpWppGetCurrentThreadActivityIdPrefix();
              v16 = 34;
              v17 = "unable to get instance id";
              goto LABEL_179;
            }
LABEL_146:
            v46 = *(_QWORD *)a2;
            v64 = 0;
            Version = (*(__int64 (__fastcall **)(struct ILocalDevice *, __int128 *))(v46 + 64))(a2, &v64);
            if ( Version >= 0 )
            {
              *(_OWORD *)((char *)this + 248) = v64;
              v47 = RtlStringFromGUID((const GUID *const)((char *)this + 248), (PUNICODE_STRING)((char *)this + 264));
              if ( v47 >= 0 || (Version = v47 | 0x10000000, Version >= 0) )
              {
                Version = CTsUsbDevice::UsbdiGetVersion(
                            this,
                            (unsigned int *)this + 46,
                            (unsigned int *)this + 47,
                            (unsigned int *)this + 48,
                            (unsigned int *)this + 49,
                            (unsigned int *)this + 50);
                if ( Version >= 0 )
                {
                  *((_DWORD *)this + 51) = a5;
                  *((_QWORD *)this + 44) = a4;
                  (*(void (__fastcall **)(struct IUsbRedirectionDeviceNotification *))(*(_QWORD *)a4 + 8LL))(a4);
                  Version = 0;
                }
                else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                       && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v48 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    37,
                    WPP_93936833bc2036c13ede136827ee6600_Traceguids,
                    v48,
                    Version);
                }
                goto LABEL_180;
              }
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_180;
              }
              v15 = RdpWppGetCurrentThreadActivityIdPrefix();
              v16 = 36;
              v17 = "RtlStringFromGUID";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_180;
              }
              v15 = RdpWppGetCurrentThreadActivityIdPrefix();
              v16 = 35;
              v17 = "ILocalDevice::GetContainerId FAILED";
            }
LABEL_179:
            dwFlagsAndAttributes[0] = Version;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v16,
              (unsigned int)WPP_93936833bc2036c13ede136827ee6600_Traceguids,
              v15,
              (__int64)v17,
              *(_QWORD *)dwFlagsAndAttributes);
            goto LABEL_180;
          }
          if ( Version >= 0 )
            goto LABEL_110;
        }
LABEL_169:
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_180;
        }
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 29;
        goto LABEL_178;
      }
      if ( Version >= 0 )
        goto LABEL_94;
    }
LABEL_174:
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_180;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 27;
LABEL_178:
    v17 = "unable to get real hw id size";
    goto LABEL_179;
  }
  v23 = GetLastError();
  Version = v23;
  if ( v23 > 0 )
    Version = (unsigned __int16)v23 | 0x80070000;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 22;
    goto LABEL_6;
  }
LABEL_180:
  operator delete(v6);
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)Version;
}

```

## disassembly

```asm
0x1805f66d8  mov     [rsp-8+arg_18], rbx
0x1805f66dd  push    rbp
0x1805f66de  push    rsi
0x1805f66df  push    rdi
0x1805f66e0  push    r12
0x1805f66e2  push    r13
0x1805f66e4  push    r14
0x1805f66e6  push    r15
0x1805f66e8  lea     rbp, [rsp-10h]
0x1805f66ed  sub     rsp, 110h
0x1805f66f4  mov     rax, cs:__security_cookie
0x1805f66fb  xor     rax, rsp
0x1805f66fe  mov     [rbp+40h+var_40], rax
0x1805f6702  or      dword ptr [rcx+34h], 2
0x1805f6706  xor     ebx, ebx
0x1805f6708  xorps   xmm0, xmm0
0x1805f670b  mov     [rsp+140h+var_E0], rbx
0x1805f6710  or      rax, 0FFFFFFFFFFFFFFFFh
0x1805f6714  mov     [rsp+140h+InBuffer], ebx
0x1805f6718  mov     rdi, rcx
0x1805f671b  mov     [rsp+140h+BytesReturned], ebx
0x1805f671f  add     rcx, 128h; this
0x1805f6726  mov     [rsp+140h+var_D8], rbx
0x1805f672b  movups  [rbp+40h+var_70], xmm0
0x1805f672f  mov     [rsp+140h+cbData], ebx
0x1805f6733  mov     r13d, ebx
0x1805f6736  movups  [rbp+40h+var_60], xmm0
0x1805f673a  mov     [rsp+140h+Type], ebx
0x1805f673e  mov     r12, rax
0x1805f6741  movups  [rbp+40h+var_50], xmm0
0x1805f6745  mov     [rsp+140h+pv], rbx
0x1805f674a  mov     r15, r9
0x1805f674d  movups  [rbp+40h+var_90], xmm0
0x1805f6751  mov     [rsp+140h+StringUuid], rbx
0x1805f6756  mov     rsi, r8
0x1805f6759  movups  [rbp+40h+var_80], xmm0
0x1805f675d  mov     [rsp+140h+hKey], rax
0x1805f6762  mov     r14, rdx
0x1805f6765  movups  [rbp+40h+var_B0], xmm0
0x1805f6769  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1805f676e  test    eax, eax
0x1805f6770  jnz     short loc_1805F67CA
0x1805f6772  mov     ebx, 80004005h
0x1805f6777  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f677e  lea     rax, WPP_GLOBAL_Control
0x1805f6785  cmp     rcx, rax
0x1805f6788  jz      loc_1805F73FF
0x1805f678e  test    byte ptr [rcx+1Ch], 1
0x1805f6792  jz      loc_1805F73FF
0x1805f6798  cmp     byte ptr [rcx+19h], 2
0x1805f679c  jb      loc_1805F73FF
0x1805f67a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f67a7  lea     edx, [r13+0Dh]
0x1805f67ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f67b2  lea     r8, WPP_93936833bc2036c13ede136827ee6600_Traceguids
0x1805f67b9  mov     r9d, eax
0x1805f67bc  mov     rcx, [rcx+10h]
0x1805f67c0  call    WPP_SF_d
0x1805f67c5  jmp     loc_1805F73FF
0x1805f67ca  lea     rdx, [rdi+118h]; struct CSimpleHash **
0x1805f67d1  mov     ecx, 10h; unsigned int
0x1805f67d6  call    ?CreateInstance@CSimpleHash@@SAJKPEAPEAV1@@Z; CSimpleHash::CreateInstance(ulong,CSimpleHash * *)
0x1805f67db  mov     ebx, eax
0x1805f67dd  test    eax, eax
0x1805f67df  jns     short loc_1805F682A
0x1805f67e1  or      ebx, 10000000h
0x1805f67e7  jge     short loc_1805F682A
0x1805f67e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f67f0  lea     rax, WPP_GLOBAL_Control
0x1805f67f7  cmp     rcx, rax
0x1805f67fa  jz      loc_1805F73FF
0x1805f6800  test    byte ptr [rcx+1Ch], 8
0x1805f6804  jz      loc_1805F73FF
0x1805f680a  cmp     byte ptr [rcx+19h], 2
0x1805f680e  jb      loc_1805F73FF
0x1805f6814  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6819  mov     edx, 0Eh
0x1805f681e  lea     rcx, aCsimplehashCre; "CSimpleHash::CreateInstance failed"
0x1805f6825  jmp     loc_1805F73DC
0x1805f682a  mov     rax, [r14]
0x1805f682d  lea     r8, [rbp+40h+var_B0]
0x1805f6831  xor     edx, edx
0x1805f6833  mov     rcx, r14
0x1805f6836  mov     rax, [rax+20h]
0x1805f683a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805f683f  mov     ebx, eax
0x1805f6841  test    eax, eax
0x1805f6843  jns     short loc_1805F6886
0x1805f6845  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f684c  lea     rax, WPP_GLOBAL_Control
0x1805f6853  cmp     rcx, rax
0x1805f6856  jz      loc_1805F73FF
0x1805f685c  test    byte ptr [rcx+1Ch], 8
0x1805f6860  jz      loc_1805F73FF
0x1805f6866  cmp     byte ptr [rcx+19h], 2
0x1805f686a  jb      loc_1805F73FF
0x1805f6870  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6875  mov     edx, 0Fh
0x1805f687a  lea     rcx, aIlocaldeviceGe_4; "ILocalDevice::GetInterfaceGuid FAILED"
0x1805f6881  jmp     loc_1805F73DC
0x1805f6886  mov     rax, [r14]
0x1805f6889  lea     r8, [rsp+140h+pv]
0x1805f688e  movaps  xmm0, [rbp+40h+var_B0]
0x1805f6892  lea     rdx, [rbp+40h+var_C0]
0x1805f6896  mov     rcx, r14
0x1805f6899  movdqa  [rbp+40h+var_C0], xmm0
0x1805f689e  mov     rax, [rax+28h]
0x1805f68a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805f68a7  mov     ebx, eax
0x1805f68a9  test    eax, eax
0x1805f68ab  jns     short loc_1805F68EE
0x1805f68ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f68b4  lea     rax, WPP_GLOBAL_Control
0x1805f68bb  cmp     rcx, rax
0x1805f68be  jz      loc_1805F73FF
0x1805f68c4  test    byte ptr [rcx+1Ch], 8
0x1805f68c8  jz      loc_1805F73FF
0x1805f68ce  cmp     byte ptr [rcx+19h], 2
0x1805f68d2  jb      loc_1805F73FF
0x1805f68d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f68dd  mov     edx, 10h
0x1805f68e2  lea     rcx, aIlocaldeviceGe_2; "ILocalDevice::GetFileName FAILED"
0x1805f68e9  jmp     loc_1805F73DC
0x1805f68ee  mov     rcx, [rsp+140h+pv]; unsigned __int16 *
0x1805f68f3  lea     r8, [rsp+140h+var_E0]; unsigned __int64 *
0x1805f68f8  mov     edx, 0FFFFh; unsigned __int64
0x1805f68fd  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1805f6902  mov     ebx, eax
0x1805f6904  test    eax, eax
0x1805f6906  jns     short loc_1805F6949
0x1805f6908  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f690f  lea     rax, WPP_GLOBAL_Control
0x1805f6916  cmp     rcx, rax
0x1805f6919  jz      loc_1805F73FF
0x1805f691f  test    byte ptr [rcx+1Ch], 8
0x1805f6923  jz      loc_1805F73FF
0x1805f6929  cmp     byte ptr [rcx+19h], 2
0x1805f692d  jb      loc_1805F73FF
0x1805f6933  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6938  mov     edx, 11h
0x1805f693d  lea     rcx, aStringcblength_1; "StringCbLengthW failed"
0x1805f6944  jmp     loc_1805F73DC
0x1805f6949  lea     rdx, [rsp+140h+StringUuid]; StringUuid
0x1805f694e  mov     rcx, rsi; Uuid
0x1805f6951  call    cs:__imp_UuidToStringW
0x1805f6957  xor     esi, esi
0x1805f6959  test    eax, eax
0x1805f695b  jz      short loc_1805F69A9
0x1805f695d  mov     ebx, 80070008h
0x1805f6962  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f6969  lea     rax, WPP_GLOBAL_Control
0x1805f6970  cmp     rcx, rax
0x1805f6973  jz      loc_1805F73FF
0x1805f6979  test    byte ptr [rcx+1Ch], 8
0x1805f697d  jz      loc_1805F73FF
0x1805f6983  cmp     byte ptr [rcx+19h], 2
0x1805f6987  jb      loc_1805F73FF
0x1805f698d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6992  lea     edx, [rsi+12h]
0x1805f6995  mov     [rsp+140h+dwFlagsAndAttributes], 80070008h
0x1805f699d  lea     rcx, aUuidtostringFa; "UuidToString failed"
0x1805f69a4  jmp     loc_1805F73E0
0x1805f69a9  mov     rcx, [rsp+140h+StringUuid]; unsigned __int16 *
0x1805f69ae  lea     r8, [rsp+140h+var_D8]; unsigned __int64 *
0x1805f69b3  mov     edx, 0FFFFh; unsigned __int64
0x1805f69b8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1805f69bd  mov     ebx, eax
0x1805f69bf  test    eax, eax
0x1805f69c1  jns     short loc_1805F6A04
0x1805f69c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f69ca  lea     rax, WPP_GLOBAL_Control
0x1805f69d1  cmp     rcx, rax
0x1805f69d4  jz      loc_1805F73FF
0x1805f69da  test    byte ptr [rcx+1Ch], 8
0x1805f69de  jz      loc_1805F73FF
0x1805f69e4  cmp     byte ptr [rcx+19h], 2
0x1805f69e8  jb      loc_1805F73FF
0x1805f69ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f69f3  mov     edx, 13h
0x1805f69f8  lea     rcx, aStringcchlengt_27; "StringCchLengthW(interfaceStr) failed"
0x1805f69ff  jmp     loc_1805F73DC
0x1805f6a04  mov     rcx, [rsp+140h+var_E0]
0x1805f6a09  mov     rbx, [rsp+140h+var_D8]
0x1805f6a0e  add     rbx, 4
0x1805f6a12  lea     rbx, [rcx+rbx*2]
0x1805f6a16  cmp     rbx, rcx
0x1805f6a19  jnb     short loc_1805F6A69
0x1805f6a1b  mov     ebx, 80004005h
0x1805f6a20  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f6a27  lea     rax, WPP_GLOBAL_Control
0x1805f6a2e  cmp     rcx, rax
0x1805f6a31  jz      loc_1805F73FF
0x1805f6a37  test    byte ptr [rcx+1Ch], 8
0x1805f6a3b  jz      loc_1805F73FF
0x1805f6a41  cmp     byte ptr [rcx+19h], 2
0x1805f6a45  jb      loc_1805F73FF
0x1805f6a4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6a50  mov     edx, 14h
0x1805f6a55  mov     [rsp+140h+dwFlagsAndAttributes], 80004005h
0x1805f6a5d  lea     rcx, aSizetaddFailed_1; "SizeTAdd failed"
0x1805f6a64  jmp     loc_1805F73E0
0x1805f6a69  mov     rcx, rbx; Size
0x1805f6a6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805f6a71  mov     rcx, [rsp+140h+StringUuid]
0x1805f6a76  lea     r8, aWsWs_0; "%ws\\{%ws}"
0x1805f6a7d  mov     r9, [rsp+140h+pv]
0x1805f6a82  mov     rdx, rbx; unsigned __int64
0x1805f6a85  mov     qword ptr [rsp+140h+dwCreationDisposition], rcx
0x1805f6a8a  mov     r13, rax
0x1805f6a8d  mov     rcx, rax; unsigned __int16 *
0x1805f6a90  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1805f6a95  mov     ebx, eax
0x1805f6a97  test    eax, eax
0x1805f6a99  jns     short loc_1805F6ADC
0x1805f6a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f6aa2  lea     rax, WPP_GLOBAL_Control
0x1805f6aa9  cmp     rcx, rax
0x1805f6aac  jz      loc_1805F73FF
0x1805f6ab2  test    byte ptr [rcx+1Ch], 8
0x1805f6ab6  jz      loc_1805F73FF
0x1805f6abc  cmp     byte ptr [rcx+19h], 2
0x1805f6ac0  jb      loc_1805F73FF
0x1805f6ac6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6acb  mov     edx, 15h
0x1805f6ad0  lea     rcx, aStringcbprintf_3; "StringCbPrintfW failed"
0x1805f6ad7  jmp     loc_1805F73DC
0x1805f6adc  mov     ebx, 3
0x1805f6ae1  mov     [rsp+140h+hTemplateFile], rsi; hTemplateFile
0x1805f6ae6  mov     r8d, ebx; dwShareMode
0x1805f6ae9  mov     [rsp+140h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1805f6af1  xor     r9d, r9d; lpSecurityAttributes
0x1805f6af4  mov     [rsp+140h+dwCreationDisposition], ebx; dwCreationDisposition
0x1805f6af8  mov     edx, 0C0000000h; dwDesiredAccess
0x1805f6afd  mov     rcx, r13; lpFileName
0x1805f6b00  call    cs:__imp_CreateFileW
0x1805f6b06  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805f6b0a  jnz     short loc_1805F6B5B
0x1805f6b0c  call    cs:__imp_GetLastError
0x1805f6b12  mov     ebx, eax
0x1805f6b14  test    eax, eax
0x1805f6b16  jle     short loc_1805F6B21
0x1805f6b18  movzx   ebx, ax
0x1805f6b1b  or      ebx, 80070000h
0x1805f6b21  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f6b28  lea     rax, WPP_GLOBAL_Control
0x1805f6b2f  cmp     rcx, rax
0x1805f6b32  jz      loc_1805F73FF
0x1805f6b38  test    byte ptr [rcx+1Ch], 1
0x1805f6b3c  jz      loc_1805F73FF
0x1805f6b42  cmp     byte ptr [rcx+19h], 2
0x1805f6b46  jb      loc_1805F73FF
0x1805f6b4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6b51  mov     edx, 16h
0x1805f6b56  jmp     loc_1805F67AB
0x1805f6b5b  mov     [rsp+140h+hTemplateFile], rsi; hTemplateFile
0x1805f6b60  xor     r9d, r9d; lpSecurityAttributes
0x1805f6b63  mov     [rsp+140h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1805f6b6b  mov     r8d, ebx; dwShareMode
0x1805f6b6e  mov     edx, 0C0000000h; dwDesiredAccess
0x1805f6b73  mov     [rsp+140h+dwCreationDisposition], ebx; dwCreationDisposition
0x1805f6b77  mov     rcx, r13; lpFileName
0x1805f6b7a  mov     [rdi+0D0h], rax
0x1805f6b81  call    cs:__imp_CreateFileW
0x1805f6b87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805f6b8b  jnz     short loc_1805F6BDC
0x1805f6b8d  call    cs:__imp_GetLastError
0x1805f6b93  mov     ebx, eax
0x1805f6b95  test    eax, eax
0x1805f6b97  jle     short loc_1805F6BA2
0x1805f6b99  movzx   ebx, ax
0x1805f6b9c  or      ebx, 80070000h
0x1805f6ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f6ba9  lea     rax, WPP_GLOBAL_Control
0x1805f6bb0  cmp     rcx, rax
0x1805f6bb3  jz      loc_1805F73FF
0x1805f6bb9  test    byte ptr [rcx+1Ch], 1
0x1805f6bbd  jz      loc_1805F73FF
0x1805f6bc3  cmp     byte ptr [rcx+19h], 2
0x1805f6bc7  jb      loc_1805F73FF
0x1805f6bcd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f6bd2  mov     edx, 17h
0x1805f6bd7  jmp     loc_1805F67AB
0x1805f6bdc  xor     r9d, r9d; NumberOfConcurrentThreads
0x1805f6bdf  mov     [rdi+0D8h], rax
0x1805f6be6  xor     r8d, r8d; CompletionKey
0x1805f6be9  xor     edx, edx; ExistingCompletionPort
0x1805f6beb  mov     rcx, rax; FileHandle
0x1805f6bee  call    cs:__imp_CreateIoCompletionPort
0x1805f6bf4  mov     [rdi+0E8h], rax
0x1805f6bfb  test    rax, rax
0x1805f6bfe  jnz     short loc_1805F6C6D
0x1805f6c00  call    cs:__imp_GetLastError
0x1805f6c06  mov     edi, eax
0x1805f6c08  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f6c0f  lea     rax, WPP_GLOBAL_Control
0x1805f6c16  cmp     rcx, rax
0x1805f6c19  jz      short loc_1805F6C4F
0x1805f6c1b  test    byte ptr [rcx+1Ch], 8
0x1805f6c1f  jz      short loc_1805F6C4F
0x1805f6c21  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
