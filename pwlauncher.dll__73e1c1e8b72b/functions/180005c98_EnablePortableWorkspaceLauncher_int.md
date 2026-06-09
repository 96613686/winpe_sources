# EnablePortableWorkspaceLauncher(int)

- ea: `0x180005c98`
- end: `0x1800065b6`
- name: `?EnablePortableWorkspaceLauncher@@YAHH@Z`
- size: `2334`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c530`

## callees

- `0x180005528`
- `0x180005c98`
- `0x1800070ec`
- `0x1800074e4`
- `0x1800075fc`
- `0x1800077f8`
- `0x18000830c`
- `0x180008488`
- `0x180008720`
- `0x180008a08`
- `0x180008a40`
- `0x180008a70`
- `0x180008ac8`
- `0x180008ba4`
- `0x180008cf0`
- `0x18000dbd0`
- `0x18000de18`
- `0x18000e1a0`
- `0x18000e430`
- `0x18000e6cc`
- `0x18000fdd6`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000652c`
- `KERNEL32!LocalFree` at `0x18000652c`
- `KERNEL32!CloseHandle` at `0x18000651c`
- `KERNEL32!CloseHandle` at `0x18000651c`
- `KERNEL32!DeleteFileW` at `0x18000640d`
- `KERNEL32!DeleteFileW` at `0x18000640d`
- `KERNEL32!SetFileAttributesW` at `0x1800063bc`
- `KERNEL32!SetFileAttributesW` at `0x1800063bc`
- `KERNEL32!GetLastError` at `0x180005e34`
- `KERNEL32!GetLastError` at `0x180005e90`
- `KERNEL32!GetLastError` at `0x180005f45`
- `KERNEL32!GetLastError` at `0x18000621e`
- `KERNEL32!GetLastError` at `0x1800062aa`
- `KERNEL32!GetLastError` at `0x1800062f4`
- `KERNEL32!GetLastError` at `0x18000637c`
- `KERNEL32!GetLastError` at `0x1800063c6`
- `KERNEL32!GetLastError` at `0x1800063d1`
- `KERNEL32!GetLastError` at `0x180006417`
- `KERNEL32!GetLastError` at `0x18000645d`
- `KERNEL32!GetLastError` at `0x180006551`
- `KERNEL32!GetLastError` at `0x180005e34`
- `KERNEL32!GetLastError` at `0x180005e90`
- `KERNEL32!GetLastError` at `0x180005f45`
- `KERNEL32!GetLastError` at `0x18000621e`
- `KERNEL32!GetLastError` at `0x1800062aa`
- `KERNEL32!GetLastError` at `0x1800062f4`
- `KERNEL32!GetLastError` at `0x18000637c`
- `KERNEL32!GetLastError` at `0x1800063c6`
- `KERNEL32!GetLastError` at `0x1800063d1`
- `KERNEL32!GetLastError` at `0x180006417`
- `KERNEL32!GetLastError` at `0x18000645d`
- `KERNEL32!GetLastError` at `0x180006551`
- `KERNEL32!SetLastError` at `0x180006539`
- `KERNEL32!SetLastError` at `0x180006539`
- `KERNEL32!CreateFileW` at `0x180006369`
- `KERNEL32!CreateFileW` at `0x180006369`
- `ntdll!RtlNtStatusToDosError` at `0x180005dad`
- `ntdll!RtlNtStatusToDosError` at `0x180005fb8`
- `ntdll!RtlNtStatusToDosError` at `0x18000602f`
- `ntdll!RtlNtStatusToDosError` at `0x180006084`
- `ntdll!RtlNtStatusToDosError` at `0x1800060df`
- `ntdll!RtlNtStatusToDosError` at `0x180006177`
- `ntdll!RtlNtStatusToDosError` at `0x1800061cb`
- `ntdll!RtlNtStatusToDosError` at `0x180005dad`
- `ntdll!RtlNtStatusToDosError` at `0x180005fb8`
- `ntdll!RtlNtStatusToDosError` at `0x18000602f`
- `ntdll!RtlNtStatusToDosError` at `0x180006084`
- `ntdll!RtlNtStatusToDosError` at `0x1800060df`
- `ntdll!RtlNtStatusToDosError` at `0x180006177`
- `ntdll!RtlNtStatusToDosError` at `0x1800061cb`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x180005d96`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x180005d96`
- `SHELL32!__imp_IsUserAnAdmin` at `0x180005d3c`
- `SHELL32!__imp_IsUserAnAdmin` at `0x180005d3c`

## string_xrefs

- `0x180005d79`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180005eb5`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180005f04`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180005fee`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180006054`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x18000629a`: `SeSecurityPrivilege`
- `0x180006505`: `SeSecurityPrivilege`
- `0x180005f35`: `SeSystemEnvironmentPrivilege`
- `0x1800064fc`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
__int64 __fastcall EnablePortableWorkspaceLauncher(int a1)
{
  enum _FIRMWARE_TYPE v2; // r12d
  __int64 v3; // r13
  ULONG v4; // ebx
  NTSTATUS v5; // eax
  ULONG v6; // eax
  DWORD LastError; // eax
  unsigned int v8; // edi
  DWORD v9; // eax
  const struct _GUID *v10; // rcx
  DWORD v11; // eax
  NTSTATUS BootEntryIdByGuid; // eax
  char v13; // si
  NTSTATUS NewBootEntryId; // eax
  const unsigned __int16 *v15; // rdx
  const struct _GUID *v16; // r8
  char v17; // si
  enum _FIRMWARE_TYPE v18; // esi
  NTSTATUS v19; // eax
  char v20; // r14
  NTSTATUS v21; // eax
  char v22; // si
  NTSTATUS v23; // eax
  char v24; // si
  NTSTATUS v25; // eax
  char v26; // si
  int v27; // r8d
  int v28; // r9d
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  DWORD v34; // eax
  DWORD v35; // eax
  __int64 v36; // rcx
  __int64 v37; // r8
  __int32 v38; // r12d
  const WCHAR *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  const char *v42; // rcx
  char hTemplateFile; // [rsp+30h] [rbp-D0h]
  char v45; // [rsp+40h] [rbp-C0h] BYREF
  bool Buffer[3]; // [rsp+41h] [rbp-BFh] BYREF
  enum _FIRMWARE_TYPE v47; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v48; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+50h] [rbp-B0h]
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v52[16]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v53; // [rsp+88h] [rbp-78h]
  __int64 v54; // [rsp+90h] [rbp-70h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v47 = FirmwareTypeUnknown;
  v2 = FirmwareTypeUnknown;
  memset_0(FileName, 0, 0x20Au);
  v3 = -1;
  hMem = 0;
  v48 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v49 = 0;
  Buffer[0] = 0;
  v45 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  if ( !IsUserAnAdmin() )
  {
    v4 = 5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        174,
        5);
LABEL_44:
    v8 = 0;
    LogLauncherSetErrorEvent(v4);
    goto LABEL_107;
  }
  v5 = RtlCheckPortableOperatingSystem(&v45);
  if ( v5 == -1073741275 )
  {
    v5 = 0;
    v45 = 0;
  }
  v6 = RtlNtStatusToDosError(v5);
  v4 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        177,
        v6);
    goto LABEL_44;
  }
  if ( v45 )
  {
    v4 = 50;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        180,
        50);
    goto LABEL_44;
  }
  if ( !(unsigned int)IsPortableWorkspaceLauncherEnabled((int *)&v48) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        182,
        LastError);
    goto LABEL_44;
  }
  v4 = 0;
  v8 = 1;
  if ( v48 != a1 )
  {
    if ( !(unsigned int)LauncherGetFirmwareType(&v47) )
    {
      v9 = GetLastError();
      v4 = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          186,
          v9);
      v2 = v47;
      goto LABEL_44;
    }
    v2 = v47;
    if ( v47 == FirmwareTypeBios )
    {
      if ( !(unsigned int)LauncherGetSystemPartitionFilePath(L"\\\\?\\GlobalRoot%s\\BOOTTGT", FileName) )
      {
        v29 = GetLastError();
        v4 = v29;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            111,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            192,
            v29);
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v27, v28, 193, (__int64)FileName);
      Buffer[0] = a1 != 0;
      if ( a1 )
      {
        if ( !(unsigned int)LauncherSetSelfPrivilege(L"SeSecurityPrivilege", 1) )
        {
          v30 = GetLastError();
          v4 = v30;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              201,
              v30);
          goto LABEL_44;
        }
        v49 = 1;
        if ( !(unsigned int)LauncherGetBootRedirectionSecurityDescriptor(&hMem) )
        {
          v31 = GetLastError();
          v4 = v31;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              114,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              204,
              v31);
          goto LABEL_44;
        }
        SecurityAttributes.nLength = 24;
        SecurityAttributes.lpSecurityDescriptor = hMem;
        SecurityAttributes.bInheritHandle = 0;
        v3 = (__int64)CreateFileW(FileName, 0x120116u, 7u, &SecurityAttributes, 2u, 7u, 0);
        if ( v3 == -1 )
        {
          v32 = GetLastError();
          v4 = v32;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              115,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              217,
              v32);
          goto LABEL_44;
        }
      }
      else if ( SetFileAttributesW(FileName, 6u) )
      {
        if ( !DeleteFileW(FileName) )
        {
          v34 = GetLastError();
          v4 = v34;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              232,
              v34);
          goto LABEL_44;
        }
      }
      else if ( GetLastError() != 2 )
      {
        v33 = GetLastError();
        v4 = v33;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            116,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            228,
            v33);
        goto LABEL_44;
      }
      if ( !(unsigned int)LauncherWriteBootNextFile(Buffer) )
      {
        v35 = GetLastError();
        v4 = v35;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            118,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            236,
            v35);
        goto LABEL_44;
      }
    }
    else if ( v47 == FirmwareTypeUefi )
    {
      if ( !(unsigned int)LauncherSetSelfPrivilege(L"SeSystemEnvironmentPrivilege", 1) )
      {
        v11 = GetLastError();
        v4 = v11;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            243,
            v11);
        goto LABEL_44;
      }
      v49 = 1;
      if ( a1 )
      {
        v47 = FirmwareTypeUnknown;
        BootEntryIdByGuid = FindBootEntryIdByGuid(v10, (unsigned int *)&v47);
        v13 = BootEntryIdByGuid;
        if ( BootEntryIdByGuid == -1073741275 )
        {
          NewBootEntryId = CreateNewBootEntryId((unsigned int *)&v47);
          v17 = NewBootEntryId;
          if ( NewBootEntryId < 0 )
          {
            v4 = RtlNtStatusToDosError(NewBootEntryId);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                120,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                5,
                v17);
            goto LABEL_44;
          }
          v18 = v47;
          v19 = AddUsbClassBootEntry(v47, v15, v16);
          v20 = v19;
          if ( v19 < 0 )
          {
            v4 = RtlNtStatusToDosError(v19);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                121,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                8,
                v20);
            goto LABEL_44;
          }
        }
        else
        {
          if ( BootEntryIdByGuid < 0 )
          {
            v4 = RtlNtStatusToDosError(BootEntryIdByGuid);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                122,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                12,
                v13);
            goto LABEL_44;
          }
          v18 = v47;
        }
        v21 = AddBootEntryToTopOfBootOrder(v18);
        v22 = v21;
        if ( v21 < 0 )
        {
          v4 = RtlNtStatusToDosError(v21);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              123,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              15,
              v22);
          goto LABEL_44;
        }
      }
      else
      {
        v48 = 0;
        v23 = FindBootEntryIdByGuid(v10, &v48);
        v24 = v23;
        if ( v23 == -1073741275 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
          goto LABEL_44;
        }
        if ( v23 < 0 )
        {
          v4 = RtlNtStatusToDosError(v23);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              125,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              38,
              v24);
          goto LABEL_44;
        }
        v25 = RemoveBootEntry(v48);
        v26 = v25;
        if ( v25 < 0 )
        {
          v4 = RtlNtStatusToDosError(v25);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              126,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              44,
              v26);
          goto LABEL_44;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          50,
          v47);
      v4 = 50;
    }
  }
  McGenEventRegister_EventRegister();
  if ( (Microsoft_Windows_WindowsToGo_StartupOptionsEnableBits & 1) != 0 )
  {
    v48 = a1 != 0;
    v54 = 4;
    v53 = &v48;
    McGenEventWrite_EventWriteTransfer(v36, &LauncherStateChangeEvent, v37, 2, v52);
  }
  McGenEventUnregister_EventUnregister();
LABEL_107:
  if ( !v49 )
    goto LABEL_113;
  v38 = v2 - 1;
  if ( v38 )
  {
    if ( v38 != 1 )
      goto LABEL_113;
    v39 = L"SeSystemEnvironmentPrivilege";
  }
  else
  {
    v39 = L"SeSecurityPrivilege";
  }
  LauncherSetSelfPrivilege(v39, 0);
LABEL_113:
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  SetLastError(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    hTemplateFile = GetLastError();
    v42 = "Success";
    if ( !v8 )
      v42 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, v40, v41, 102, (__int64)v42, hTemplateFile);
  }
  return v8;
}

```

## disassembly

```asm
0x180005c98  push    rbp
0x180005c9a  push    rbx
0x180005c9b  push    rsi
0x180005c9c  push    rdi
0x180005c9d  push    r12
0x180005c9f  push    r13
0x180005ca1  push    r14
0x180005ca3  push    r15
0x180005ca5  lea     rbp, [rsp-1C8h]
0x180005cad  sub     rsp, 2C8h
0x180005cb4  mov     rax, cs:__security_cookie
0x180005cbb  xor     rax, rsp
0x180005cbe  mov     [rbp+200h+var_50], rax
0x180005cc5  mov     r15d, ecx
0x180005cc8  xor     r14d, r14d
0x180005ccb  lea     rcx, [rbp+200h+FileName]; void *
0x180005ccf  mov     [rsp+300h+var_2BC], r14d
0x180005cd4  xor     edx, edx; Val
0x180005cd6  mov     r8d, 20Ah; Size
0x180005cdc  mov     r12d, r14d
0x180005cdf  call    memset_0
0x180005ce4  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005ce8  mov     [rsp+300h+hMem], r14
0x180005ced  xor     eax, eax
0x180005cef  mov     [rsp+300h+var_2B8], r14d
0x180005cf4  xorps   xmm0, xmm0
0x180005cf7  mov     qword ptr [rsp+300h+SecurityAttributes.bInheritHandle], rax
0x180005cfc  movups  xmmword ptr [rsp+300h+SecurityAttributes.nLength], xmm0
0x180005d01  mov     [rsp+300h+var_2B0], r14d
0x180005d06  mov     [rsp+300h+Buffer], r14b
0x180005d0b  mov     [rsp+300h+var_2C0], r14b
0x180005d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d17  lea     rsi, WPP_GLOBAL_Control
0x180005d1e  cmp     rcx, rsi
0x180005d21  jz      short loc_180005D3C
0x180005d23  test    byte ptr [rcx+1Ch], 8
0x180005d27  jz      short loc_180005D3C
0x180005d29  mov     rcx, [rcx+10h]
0x180005d2d  lea     edx, [rax+69h]
0x180005d30  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005d37  call    WPP_SF_
0x180005d3c  call    cs:__imp_IsUserAnAdmin
0x180005d42  test    eax, eax
0x180005d44  jnz     short loc_180005D91
0x180005d46  lea     ebx, [rax+5]
0x180005d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d50  cmp     rcx, rsi
0x180005d53  jz      loc_180006008
0x180005d59  lea     edi, [rax+1]
0x180005d5c  test    [rcx+1Ch], dil
0x180005d60  jz      loc_180006008
0x180005d66  mov     [rsp+300h+dwFlagsAndAttributes], ebx
0x180005d6a  lea     edx, [rax+6Ah]
0x180005d6d  mov     [rsp+300h+dwCreationDisposition], 5AEh
0x180005d75  mov     rcx, [rcx+10h]
0x180005d79  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180005d80  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005d87  call    WPP_SF_sdD
0x180005d8c  jmp     loc_180006008
0x180005d91  lea     rcx, [rsp+300h+var_2C0]
0x180005d96  call    cs:__imp_RtlCheckPortableOperatingSystem
0x180005d9c  cmp     eax, 0C0000225h
0x180005da1  jnz     short loc_180005DAB
0x180005da3  mov     eax, r14d
0x180005da6  mov     [rsp+300h+var_2C0], r14b
0x180005dab  mov     ecx, eax; Status
0x180005dad  call    cs:__imp_RtlNtStatusToDosError
0x180005db3  mov     ebx, eax
0x180005db5  test    eax, eax
0x180005db7  jz      short loc_180005DE9
0x180005db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dc0  cmp     rcx, rsi
0x180005dc3  jz      loc_180006008
0x180005dc9  mov     edi, 1
0x180005dce  test    [rcx+1Ch], dil
0x180005dd2  jz      loc_180006008
0x180005dd8  mov     [rsp+300h+dwFlagsAndAttributes], eax
0x180005ddc  lea     edx, [rdi+6Ah]
0x180005ddf  mov     [rsp+300h+dwCreationDisposition], 5B1h
0x180005de7  jmp     short loc_180005D75
0x180005de9  cmp     [rsp+300h+var_2C0], r14b
0x180005dee  jz      short loc_180005E26
0x180005df0  mov     ebx, 32h ; '2'
0x180005df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dfc  cmp     rcx, rsi
0x180005dff  jz      loc_180006008
0x180005e05  lea     edi, [rbx-31h]
0x180005e08  test    [rcx+1Ch], dil
0x180005e0c  jz      loc_180006008
0x180005e12  mov     [rsp+300h+dwFlagsAndAttributes], ebx
0x180005e16  lea     edx, [rbx+3Ah]
0x180005e19  mov     [rsp+300h+dwCreationDisposition], 5B4h
0x180005e21  jmp     loc_180005D75
0x180005e26  lea     rcx, [rsp+300h+var_2B8]; int *
0x180005e2b  call    ?IsPortableWorkspaceLauncherEnabled@@YAHPEAH@Z; IsPortableWorkspaceLauncherEnabled(int *)
0x180005e30  test    eax, eax
0x180005e32  jnz     short loc_180005E6F
0x180005e34  call    cs:__imp_GetLastError
0x180005e3a  mov     ebx, eax
0x180005e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e43  cmp     rcx, rsi
0x180005e46  jz      loc_180006008
0x180005e4c  mov     edi, 1
0x180005e51  test    [rcx+1Ch], dil
0x180005e55  jz      loc_180006008
0x180005e5b  mov     [rsp+300h+dwFlagsAndAttributes], eax
0x180005e5f  lea     edx, [rdi+6Ch]
0x180005e62  mov     [rsp+300h+dwCreationDisposition], 5B6h
0x180005e6a  jmp     loc_180005D75
0x180005e6f  mov     ebx, r14d
0x180005e72  mov     edi, 1
0x180005e77  cmp     [rsp+300h+var_2B8], r15d
0x180005e7c  jz      loc_18000649C
0x180005e82  lea     rcx, [rsp+300h+var_2BC]; enum _FIRMWARE_TYPE *
0x180005e87  call    ?LauncherGetFirmwareType@@YAHPEAW4_FIRMWARE_TYPE@@@Z; LauncherGetFirmwareType(_FIRMWARE_TYPE *)
0x180005e8c  test    eax, eax
0x180005e8e  jnz     short loc_180005EDA
0x180005e90  call    cs:__imp_GetLastError
0x180005e96  mov     ebx, eax
0x180005e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e9f  cmp     rcx, rsi
0x180005ea2  jz      short loc_180005ED0
0x180005ea4  test    [rcx+1Ch], dil
0x180005ea8  jz      short loc_180005ED0
0x180005eaa  mov     rcx, [rcx+10h]
0x180005eae  lea     edx, [rdi+6Dh]
0x180005eb1  mov     [rsp+300h+dwFlagsAndAttributes], eax
0x180005eb5  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180005ebc  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005ec3  mov     [rsp+300h+dwCreationDisposition], 5BAh
0x180005ecb  call    WPP_SF_sdD
0x180005ed0  mov     r12d, [rsp+300h+var_2BC]
0x180005ed5  jmp     loc_180006008
0x180005eda  mov     r12d, [rsp+300h+var_2BC]
0x180005edf  mov     ecx, r12d
0x180005ee2  sub     ecx, edi
0x180005ee4  jz      loc_18000620A
0x180005eea  cmp     ecx, edi
0x180005eec  jz      short loc_180005F33
0x180005eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ef5  cmp     rcx, rsi
0x180005ef8  jz      short loc_180005F29
0x180005efa  test    byte ptr [rcx+1Ch], 2
0x180005efe  jz      short loc_180005F29
0x180005f00  mov     rcx, [rcx+10h]
0x180005f04  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180005f0b  mov     edx, 7Fh
0x180005f10  mov     [rsp+300h+dwFlagsAndAttributes], r12d
0x180005f15  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005f1c  mov     [rsp+300h+dwCreationDisposition], 632h
0x180005f24  call    WPP_SF_sdD
0x180005f29  mov     ebx, 32h ; '2'
0x180005f2e  jmp     loc_18000649C
0x180005f33  mov     edx, edi; int
0x180005f35  lea     rcx, Name; "SeSystemEnvironmentPrivilege"
0x180005f3c  call    ?LauncherSetSelfPrivilege@@YAHPEBGH@Z; LauncherSetSelfPrivilege(ushort const *,int)
0x180005f41  test    eax, eax
0x180005f43  jnz     short loc_180005F7D
0x180005f45  call    cs:__imp_GetLastError
0x180005f4b  mov     ebx, eax
0x180005f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f54  cmp     rcx, rsi
0x180005f57  jz      loc_180006008
0x180005f5d  test    [rcx+1Ch], dil
0x180005f61  jz      loc_180006008
0x180005f67  mov     [rsp+300h+dwFlagsAndAttributes], eax
0x180005f6b  mov     edx, 77h ; 'w'
0x180005f70  mov     [rsp+300h+dwCreationDisposition], 5F3h
0x180005f78  jmp     loc_180005D75
0x180005f7d  mov     [rsp+300h+var_2B0], edi
0x180005f81  test    r15d, r15d
0x180005f84  jz      loc_18000611E
0x180005f8a  lea     rdx, [rsp+300h+var_2BC]; unsigned int *
0x180005f8f  mov     [rsp+300h+var_2BC], r14d
0x180005f94  call    ?FindBootEntryIdByGuid@@YAJAEBU_GUID@@PEAK@Z; FindBootEntryIdByGuid(_GUID const &,ulong *)
0x180005f99  mov     esi, eax
0x180005f9b  cmp     eax, 0C0000225h
0x180005fa0  jnz     loc_18000607E
0x180005fa6  lea     rcx, [rsp+300h+var_2BC]; unsigned int *
0x180005fab  call    ?CreateNewBootEntryId@@YAJPEAK@Z; CreateNewBootEntryId(ulong *)
0x180005fb0  mov     esi, eax
0x180005fb2  test    eax, eax
0x180005fb4  jns     short loc_180006017
0x180005fb6  mov     ecx, eax; Status
0x180005fb8  call    cs:__imp_RtlNtStatusToDosError
0x180005fbe  mov     ebx, eax
0x180005fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fc7  lea     rax, WPP_GLOBAL_Control
0x180005fce  cmp     rcx, rax
0x180005fd1  jz      short loc_180006001
0x180005fd3  test    [rcx+1Ch], dil
0x180005fd7  jz      short loc_180006001
0x180005fd9  mov     [rsp+300h+dwFlagsAndAttributes], esi
0x180005fdd  mov     edx, 78h ; 'x'
0x180005fe2  mov     [rsp+300h+dwCreationDisposition], 605h
0x180005fea  mov     rcx, [rcx+10h]
0x180005fee  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180005ff5  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005ffc  call    WPP_SF_sdD
0x180006001  lea     rsi, WPP_GLOBAL_Control
0x180006008  mov     ecx, ebx; unsigned int
0x18000600a  mov     edi, r14d
0x18000600d  call    ?LogLauncherSetErrorEvent@@YAXI@Z; LogLauncherSetErrorEvent(uint)
0x180006012  jmp     loc_1800064E9
0x180006017  mov     esi, [rsp+300h+var_2BC]
0x18000601b  mov     ecx, esi; unsigned int
0x18000601d  call    ?AddUsbClassBootEntry@@YAJKPEBGPEBU_GUID@@@Z; AddUsbClassBootEntry(ulong,ushort const *,_GUID const *)
0x180006022  mov     r14d, eax
0x180006025  test    eax, eax
0x180006027  jns     loc_1800060C9
0x18000602d  mov     ecx, eax; Status
0x18000602f  call    cs:__imp_RtlNtStatusToDosError
0x180006035  mov     ebx, eax
0x180006037  mov     rcx, cs:WPP_GLOBAL_Control
0x18000603e  lea     rsi, WPP_GLOBAL_Control
0x180006045  cmp     rcx, rsi
0x180006048  jz      short loc_180006079
0x18000604a  test    [rcx+1Ch], dil
0x18000604e  jz      short loc_180006079
0x180006050  mov     rcx, [rcx+10h]
0x180006054  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000605b  mov     edx, 79h ; 'y'
0x180006060  mov     [rsp+300h+dwFlagsAndAttributes], r14d
0x180006065  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000606c  mov     [rsp+300h+dwCreationDisposition], 608h
0x180006074  call    WPP_SF_sdD
0x180006079  xor     r14d, r14d
0x18000607c  jmp     short loc_180006008
0x18000607e  test    esi, esi
0x180006080  jns     short loc_1800060C3
0x180006082  mov     ecx, esi; Status
0x180006084  call    cs:__imp_RtlNtStatusToDosError
0x18000608a  mov     ebx, eax
0x18000608c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006093  lea     rax, WPP_GLOBAL_Control
0x18000609a  cmp     rcx, rax
0x18000609d  jz      loc_180006001
0x1800060a3  test    [rcx+1Ch], dil
0x1800060a7  jz      loc_180006001
0x1800060ad  mov     [rsp+300h+dwFlagsAndAttributes], esi
0x1800060b1  mov     edx, 7Ah ; 'z'
0x1800060b6  mov     [rsp+300h+dwCreationDisposition], 60Ch
0x1800060be  jmp     loc_180005FEA
0x1800060c3  mov     esi, [rsp+300h+var_2BC]
0x1800060c7  jmp     short loc_1800060CC
0x1800060c9  xor     r14d, r14d
0x1800060cc  mov     ecx, esi; unsigned int
0x1800060ce  call    ?AddBootEntryToTopOfBootOrder@@YAJK@Z; AddBootEntryToTopOfBootOrder(ulong)
0x1800060d3  mov     esi, eax
0x1800060d5  test    eax, eax
0x1800060d7  jns     loc_180006495
0x1800060dd  mov     ecx, eax; Status
0x1800060df  call    cs:__imp_RtlNtStatusToDosError
0x1800060e5  mov     ebx, eax
0x1800060e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060ee  lea     rax, WPP_GLOBAL_Control
0x1800060f5  cmp     rcx, rax
0x1800060f8  jz      loc_180006001
0x1800060fe  test    [rcx+1Ch], dil
0x180006102  jz      loc_180006001
0x180006108  mov     [rsp+300h+dwFlagsAndAttributes], esi
0x18000610c  mov     edx, 7Bh ; '{'
0x180006111  mov     [rsp+300h+dwCreationDisposition], 60Fh
0x180006119  jmp     loc_180005FEA
0x18000611e  lea     rdx, [rsp+300h+var_2B8]; unsigned int *
0x180006123  mov     [rsp+300h+var_2B8], r14d
0x180006128  call    ?FindBootEntryIdByGuid@@YAJAEBU_GUID@@PEAK@Z; FindBootEntryIdByGuid(_GUID const &,ulong *)
0x18000612d  mov     esi, eax
0x18000612f  cmp     eax, 0C0000225h
0x180006134  jnz     short loc_180006171
0x180006136  mov     rcx, cs:WPP_GLOBAL_Control
0x18000613d  lea     rsi, WPP_GLOBAL_Control
0x180006144  cmp     rcx, rsi
0x180006147  jz      loc_180006008
0x18000614d  test    byte ptr [rcx+1Ch], 2
0x180006151  jz      loc_180006008
0x180006157  mov     rcx, [rcx+10h]
0x18000615b  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006162  mov     edx, 7Ch ; '|'
0x180006167  call    WPP_SF_
0x18000616c  jmp     loc_180006008
0x180006171  test    esi, esi
0x180006173  jns     short loc_1800061B6
0x180006175  mov     ecx, esi; Status
0x180006177  call    cs:__imp_RtlNtStatusToDosError
0x18000617d  mov     ebx, eax
0x18000617f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006186  lea     rax, WPP_GLOBAL_Control
0x18000618d  cmp     rcx, rax
0x180006190  jz      loc_180006001
0x180006196  test    [rcx+1Ch], dil
0x18000619a  jz      loc_180006001
0x1800061a0  mov     [rsp+300h+dwFlagsAndAttributes], esi
0x1800061a4  mov     edx, 7Dh ; '}'
0x1800061a9  mov     [rsp+300h+dwCreationDisposition], 626h
0x1800061b1  jmp     loc_180005FEA
0x1800061b6  mov     ecx, [rsp+300h+var_2B8]; unsigned int
0x1800061ba  call    ?RemoveBootEntry@@YAJK@Z; RemoveBootEntry(ulong)
0x1800061bf  mov     esi, eax
0x1800061c1  test    eax, eax
  ... truncated ...
```
