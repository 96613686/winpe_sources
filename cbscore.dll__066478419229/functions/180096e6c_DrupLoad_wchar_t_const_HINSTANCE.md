# DrupLoad(wchar_t const *,HINSTANCE__ * *)

- ea: `0x180096e6c`
- end: `0x180097533`
- name: `?DrupLoad@@YAJPEB_WPEAPEAUHINSTANCE__@@@Z`
- size: `1735`
- prototype: `__int64 __fastcall(const wchar_t *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x1800f3f0c`

## callees

- `0x180013250`
- `0x180016d40`
- `0x180049ec0`
- `0x180095e34`
- `0x180096e6c`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x18010c194`
- `0x18012cffc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180096f25`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180096ff0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097090`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097130`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800971d0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097270`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097310`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800973b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097450`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180096f25`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180096ff0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097090`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097130`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800971d0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097270`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097310`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800973b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800970a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800971e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800970a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800971e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097468`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180096ed9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180096ed9`

## string_xrefs

- `0x180096f60`: `Failed to get proc address for DriverUpdateOpenContext`
- `0x180097487`: `Failed to get proc address for DriverUpdateQueryUpdatesUninstallStatus`
- `0x180097027`: `Failed to get proc address for DriverUpdateCloseContext`
- `0x180097347`: `Failed to get proc address for DriverUpdateEnableDeviceInstall`
- `0x180097167`: `Failed to get proc address for DriverUpdateUnstageUpdates`
- `0x180097207`: `Failed to get proc address for DriverUpdateInstallUpdates`
- `0x1800973e7`: `Failed to get proc address for DriverUpdateOsVersionChange`
- `0x1800972a7`: `Failed to get proc address for DriverUpdateUninstallUpdates`
- `0x1800970c7`: `Failed to get proc address for DriverUpdateStageUpdates`
- `0x180096f03`: `Failed to load DrUpdate DLL: %ws (possibly expected)`
- `0x180096f17`: `DriverUpdateOpenContext`
- `0x180096fe6`: `DriverUpdateCloseContext`
- `0x180096ea6`: `DrUpdate.dll`
- `0x1800971c6`: `DriverUpdateInstallUpdates`
- `0x180097266`: `DriverUpdateUninstallUpdates`
- `0x180097086`: `DriverUpdateStageUpdates`
- `0x180097126`: `DriverUpdateUnstageUpdates`
- `0x180097446`: `DriverUpdateQueryUpdatesUninstallStatus`
- `0x180097306`: `DriverUpdateEnableDeviceInstall`
- `0x1800973a6`: `DriverUpdateOsVersionChange`

## pseudocode

```c
__int64 __fastcall DrupLoad(const wchar_t *a1, HINSTANCE *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  DWORD LastError; // eax
  signed int v7; // edi
  int v8; // edx
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v11; // edx
  unsigned int v12; // eax
  int v13; // edx
  unsigned int v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  int v19; // edx
  unsigned int v20; // eax
  int v21; // edx
  unsigned int v22; // eax
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  unsigned int v26; // eax
  unsigned int v28; // [rsp+20h] [rbp-40h]
  _BYTE v29[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v31[2]; // [rsp+38h] [rbp-28h] BYREF
  HMODULE v32; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  vhDrupDll = 0;
  lpLibFileName = 0;
  v2 = SczAllocConcat2Sz(&lpLibFileName, a1, L"DrUpdate.dll");
  v3 = v2;
  if ( v2 >= 0 )
  {
    LibraryW = LoadLibraryW(lpLibFileName);
    v32 = LibraryW;
    v5 = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *>(
        2,
        LastError,
        "Failed to load DrUpdate DLL: %ws (possibly expected)",
        &lpLibFileName);
LABEL_80:
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v32);
      v3 = 0;
      goto LABEL_81;
    }
    v29[0] = 1;
    vpfnDriverUpdateOpenContext = (struct HDRIVERUPDATECONTEXT__ *(*)(const wchar_t *, const wchar_t *))GetProcAddress(LibraryW, "DriverUpdateOpenContext");
    if ( vpfnDriverUpdateOpenContext )
    {
      vpfnDriverUpdateCloseContext = (int (*)(struct HDRIVERUPDATECONTEXT__ *))GetProcAddress(
                                                                                 v5,
                                                                                 "DriverUpdateCloseContext");
      if ( vpfnDriverUpdateCloseContext )
      {
        vpfnDriverUpdateStageUpdates = (unsigned int (*)(struct HDRIVERUPDATECONTEXT__ *, struct _DRIVER_UPDATE *, unsigned int, int (*)(struct _DRIVER_UPDATE *, unsigned int, unsigned int, __int64), __int64))GetProcAddress(v5, "DriverUpdateStageUpdates");
        if ( vpfnDriverUpdateStageUpdates )
        {
          vpfnDriverUpdateUnstageUpdates = (unsigned int (*)(struct HDRIVERUPDATECONTEXT__ *, struct _DRIVER_UPDATE *, unsigned int, int (*)(struct _DRIVER_UPDATE *, unsigned int, unsigned int, __int64), __int64))GetProcAddress(v5, "DriverUpdateUnstageUpdates");
          if ( vpfnDriverUpdateUnstageUpdates )
          {
            vpfnDriverUpdateInstallUpdates = (unsigned int (*)(struct HDRIVERUPDATECONTEXT__ *, struct _DRIVER_UPDATE *, unsigned int, int (*)(struct _DRIVER_UPDATE *, unsigned int, unsigned int, __int64), __int64, void *))GetProcAddress(v5, "DriverUpdateInstallUpdates");
            if ( vpfnDriverUpdateInstallUpdates )
            {
              vpfnDriverUpdateUninstallUpdates = (unsigned int (*)(struct HDRIVERUPDATECONTEXT__ *, struct _DRIVER_UPDATE *, unsigned int, int (*)(struct _DRIVER_UPDATE *, unsigned int, unsigned int, __int64), __int64, void *))GetProcAddress(v5, "DriverUpdateUninstallUpdates");
              if ( vpfnDriverUpdateUninstallUpdates )
              {
                vpfnDriverUpdateEnableDeviceInstall = (int (*)(struct HDRIVERUPDATECONTEXT__ *, int))GetProcAddress(v5, "DriverUpdateEnableDeviceInstall");
                if ( vpfnDriverUpdateEnableDeviceInstall )
                {
                  vpfnDriverUpdateOsVersionChange = (unsigned int (*)(struct HDRIVERUPDATECONTEXT__ *, unsigned int, unsigned int, void *))GetProcAddress(v5, "DriverUpdateOsVersionChange");
                  if ( vpfnDriverUpdateOsVersionChange )
                  {
                    vpfnDriverUpdateQueryUpdatesUninstallStatus = (unsigned int (*)(struct HDRIVERUPDATECONTEXT__ *, struct _DRIVER_UPDATE *, unsigned int, struct _DRIVER_UPDATE_STATUS *, int (*)(struct _DRIVER_UPDATE *, struct _DRIVER_UPDATE_STATUS *, unsigned int, __int64), __int64, void *))GetProcAddress(v5, "DriverUpdateQueryUpdatesUninstallStatus");
                    if ( vpfnDriverUpdateQueryUpdatesUninstallStatus )
                    {
                      v32 = 0;
                      vhDrupDll = v5;
                      v29[0] = 0;
                    }
                    else
                    {
                      v7 = GetLastError();
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(
                          LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed to get proc address for DriverUpdateQueryUpdatesUninstallStatus");
                        if ( v7 > 0 )
                          v26 = (unsigned __int16)v7 | 0x80070000;
                        else
                          v26 = v7;
                        v30 = v26;
                        LOBYTE(v25) = 1;
                        *(_QWORD *)v31 = &v30;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v25,
                          3,
                          (unsigned int)": {0}",
                          (__int64)v31);
                      }
                      if ( v7 )
                      {
                        v10 = 139;
                        goto LABEL_13;
                      }
                    }
                  }
                  else
                  {
                    v7 = GetLastError();
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed to get proc address for DriverUpdateOsVersionChange");
                      if ( v7 > 0 )
                        v24 = (unsigned __int16)v7 | 0x80070000;
                      else
                        v24 = v7;
                      v30 = v24;
                      LOBYTE(v23) = 1;
                      *(_QWORD *)v31 = &v30;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v23,
                        3,
                        (unsigned int)": {0}",
                        (__int64)v31);
                    }
                    if ( v7 )
                    {
                      v10 = 135;
                      goto LABEL_13;
                    }
                  }
                }
                else
                {
                  v7 = GetLastError();
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to get proc address for DriverUpdateEnableDeviceInstall");
                    if ( v7 > 0 )
                      v22 = (unsigned __int16)v7 | 0x80070000;
                    else
                      v22 = v7;
                    v30 = v22;
                    LOBYTE(v21) = 1;
                    *(_QWORD *)v31 = &v30;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v21,
                      3,
                      (unsigned int)": {0}",
                      (__int64)v31);
                  }
                  if ( v7 )
                  {
                    v10 = 131;
                    goto LABEL_13;
                  }
                }
              }
              else
              {
                v7 = GetLastError();
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get proc address for DriverUpdateUninstallUpdates");
                  if ( v7 > 0 )
                    v20 = (unsigned __int16)v7 | 0x80070000;
                  else
                    v20 = v7;
                  v30 = v20;
                  LOBYTE(v19) = 1;
                  *(_QWORD *)v31 = &v30;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v19,
                    3,
                    (unsigned int)": {0}",
                    (__int64)v31);
                }
                if ( v7 )
                {
                  v10 = 127;
                  goto LABEL_13;
                }
              }
            }
            else
            {
              v7 = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get proc address for DriverUpdateInstallUpdates");
                if ( v7 > 0 )
                  v18 = (unsigned __int16)v7 | 0x80070000;
                else
                  v18 = v7;
                v30 = v18;
                LOBYTE(v17) = 1;
                *(_QWORD *)v31 = &v30;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v17,
                  3,
                  (unsigned int)": {0}",
                  (__int64)v31);
              }
              if ( v7 )
              {
                v10 = 124;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v7 = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to get proc address for DriverUpdateUnstageUpdates");
              if ( v7 > 0 )
                v16 = (unsigned __int16)v7 | 0x80070000;
              else
                v16 = v7;
              v30 = v16;
              LOBYTE(v15) = 1;
              *(_QWORD *)v31 = &v30;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v15,
                3,
                (unsigned int)": {0}",
                (__int64)v31);
            }
            if ( v7 )
            {
              v10 = 121;
              goto LABEL_13;
            }
          }
        }
        else
        {
          v7 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to get proc address for DriverUpdateStageUpdates");
            if ( v7 > 0 )
              v14 = (unsigned __int16)v7 | 0x80070000;
            else
              v14 = v7;
            v30 = v14;
            LOBYTE(v13) = 1;
            *(_QWORD *)v31 = &v30;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v13,
              3,
              (unsigned int)": {0}",
              (__int64)v31);
          }
          if ( v7 )
          {
            v10 = 118;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v7 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to get proc address for DriverUpdateCloseContext");
          if ( v7 > 0 )
            v12 = (unsigned __int16)v7 | 0x80070000;
          else
            v12 = v7;
          v30 = v12;
          LOBYTE(v11) = 1;
          *(_QWORD *)v31 = &v30;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v11,
            3,
            (unsigned int)": {0}",
            (__int64)v31);
        }
        if ( v7 )
        {
          v10 = 115;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v7 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for DriverUpdateOpenContext");
        if ( v7 > 0 )
          v9 = (unsigned __int16)v7 | 0x80070000;
        else
          v9 = v7;
        v30 = v9;
        LOBYTE(v8) = 1;
        *(_QWORD *)v31 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v8,
          3,
          (unsigned int)": {0}",
          (__int64)v31);
      }
      if ( v7 )
      {
        v10 = 112;
LABEL_13:
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v10,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsdrupwrapper.cpp",
               (const char *)(unsigned int)v7,
               v28);
        Windows::Detail::OnBlockExitImpl__DrupLoad_::_2_::_lambda_1___::_OnBlockExitImpl__DrupLoad_::_2_::_lambda_1___(v29);
        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v32);
        goto LABEL_81;
      }
    }
    Windows::Detail::OnBlockExitImpl__DrupLoad_::_2_::_lambda_1___::_OnBlockExitImpl__DrupLoad_::_2_::_lambda_1___(v29);
    goto LABEL_80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x54,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsdrupwrapper.cpp",
    (const char *)(unsigned int)v2,
    v28);
LABEL_81:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  return v3;
}

```

## disassembly

```asm
0x180096e6c  mov     [rsp-8+arg_8], rbx
0x180096e71  mov     [rsp-8+arg_10], rdi
0x180096e76  push    rbp
0x180096e77  mov     rbp, rsp
0x180096e7a  sub     rsp, 60h
0x180096e7e  mov     rax, cs:__security_cookie
0x180096e85  xor     rax, rsp
0x180096e88  mov     [rbp+var_10], rax
0x180096e8c  mov     rdx, rcx
0x180096e8f  mov     cs:?vhDrupDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * vhDrupDll
0x180096e9a  lea     rcx, [rbp+lpLibFileName]
0x180096e9e  mov     [rbp+lpLibFileName], 0
0x180096ea6  lea     r8, aDrupdateDll; "DrUpdate.dll"
0x180096ead  call    SczAllocConcat2Sz
0x180096eb2  mov     ebx, eax
0x180096eb4  test    eax, eax
0x180096eb6  jns     short loc_180096ED5
0x180096eb8  mov     rcx, [rbp+8]; this
0x180096ebc  lea     r8, aOnecoreBaseCbs_45; "onecore\\base\\cbs\\core\\cbsdrupwrappe"...
0x180096ec3  mov     r9d, eax; char *
0x180096ec6  mov     edx, 54h ; 'T'; void *
0x180096ecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096ed0  jmp     loc_180097509
0x180096ed5  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180096ed9  call    cs:__imp_LoadLibraryW
0x180096ee0  nop     dword ptr [rax+rax+00h]
0x180096ee5  mov     [rbp+var_20], rax
0x180096ee9  mov     rbx, rax
0x180096eec  test    rax, rax
0x180096eef  jnz     short loc_180096F17
0x180096ef1  call    cs:__imp_GetLastError
0x180096ef8  nop     dword ptr [rax+rax+00h]
0x180096efd  mov     edx, eax
0x180096eff  lea     r9, [rbp+lpLibFileName]
0x180096f03  lea     r8, aFailedToLoadDr_1; "Failed to load DrUpdate DLL: %ws (possi"...
0x180096f0a  lea     ecx, [rbx+2]
0x180096f0d  call    ??$TraceAtLevelWin32@KPEA_W@LogAdapter@@YAXW4LogLevel@0@KQEBDAEBQEA_W@Z; LogAdapter::TraceAtLevelWin32<ulong,wchar_t *>(LogAdapter::LogLevel,ulong,char const * const,wchar_t * const &)
0x180096f12  jmp     loc_1800974FE
0x180096f17  lea     rdx, aDriverupdateop_0; "DriverUpdateOpenContext"
0x180096f1e  mov     [rbp+var_30], 1
0x180096f22  mov     rcx, rbx; hModule
0x180096f25  call    cs:__imp_GetProcAddress
0x180096f2c  nop     dword ptr [rax+rax+00h]
0x180096f31  mov     cs:?vpfnDriverUpdateOpenContext@@3P6APEAUHDRIVERUPDATECONTEXT__@@PEB_W0@ZEA, rax; HDRIVERUPDATECONTEXT__ * (*vpfnDriverUpdateOpenContext)(wchar_t const *,wchar_t const *)
0x180096f38  test    rax, rax
0x180096f3b  jnz     loc_180096FE6
0x180096f41  call    cs:__imp_GetLastError
0x180096f48  nop     dword ptr [rax+rax+00h]
0x180096f4d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180096f54  mov     edi, eax
0x180096f56  test    rcx, rcx
0x180096f59  jz      short loc_180096FAD
0x180096f5b  mov     ebx, 3
0x180096f60  lea     r9, aFailedToGetPro_20; "Failed to get proc address for DriverUp"...
0x180096f67  mov     r8d, ebx
0x180096f6a  xor     edx, edx
0x180096f6c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180096f71  test    edi, edi
0x180096f73  jg      short loc_180096F79
0x180096f75  mov     eax, edi
0x180096f77  jmp     short loc_180096F81
0x180096f79  movzx   eax, di
0x180096f7c  or      eax, 80070000h
0x180096f81  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180096f88  lea     r9, a0; ": {0}"
0x180096f8f  mov     [rbp+var_2C], eax
0x180096f92  mov     r8d, ebx
0x180096f95  lea     rax, [rbp+var_2C]
0x180096f99  mov     dl, 1
0x180096f9b  mov     qword ptr [rbp+var_28], rax
0x180096f9f  lea     rax, [rbp+var_28]
0x180096fa3  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x180096fa8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180096fad  test    edi, edi
0x180096faf  jz      loc_1800974F5
0x180096fb5  mov     edx, 70h ; 'p'; void *
0x180096fba  mov     rcx, [rbp+8]; this
0x180096fbe  lea     r8, aOnecoreBaseCbs_45; "onecore\\base\\cbs\\core\\cbsdrupwrappe"...
0x180096fc5  mov     r9d, edi; char *
0x180096fc8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180096fcd  lea     rcx, [rbp+var_30]
0x180096fd1  mov     ebx, eax
0x180096fd3  call    Windows__Detail__OnBlockExitImpl__DrupLoad____2____lambda_1______OnBlockExitImpl__DrupLoad____2____lambda_1___
0x180096fd8  lea     rcx, [rbp+var_20]
0x180096fdc  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180096fe1  jmp     loc_180097509
0x180096fe6  lea     rdx, aDriverupdatecl; "DriverUpdateCloseContext"
0x180096fed  mov     rcx, rbx; hModule
0x180096ff0  call    cs:__imp_GetProcAddress
0x180096ff7  nop     dword ptr [rax+rax+00h]
0x180096ffc  mov     cs:?vpfnDriverUpdateCloseContext@@3P6AHPEAUHDRIVERUPDATECONTEXT__@@@ZEA, rax; int (*vpfnDriverUpdateCloseContext)(HDRIVERUPDATECONTEXT__ *)
0x180097003  test    rax, rax
0x180097006  jnz     short loc_180097086
0x180097008  call    cs:__imp_GetLastError
0x18009700f  nop     dword ptr [rax+rax+00h]
0x180097014  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009701b  mov     edi, eax
0x18009701d  test    rcx, rcx
0x180097020  jz      short loc_180097074
0x180097022  mov     ebx, 3
0x180097027  lea     r9, aFailedToGetPro_0; "Failed to get proc address for DriverUp"...
0x18009702e  mov     r8d, ebx
0x180097031  xor     edx, edx
0x180097033  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097038  test    edi, edi
0x18009703a  jg      short loc_180097040
0x18009703c  mov     eax, edi
0x18009703e  jmp     short loc_180097048
0x180097040  movzx   eax, di
0x180097043  or      eax, 80070000h
0x180097048  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009704f  lea     r9, a0; ": {0}"
0x180097056  mov     [rbp+var_2C], eax
0x180097059  mov     r8d, ebx
0x18009705c  lea     rax, [rbp+var_2C]
0x180097060  mov     dl, 1
0x180097062  mov     qword ptr [rbp+var_28], rax
0x180097066  lea     rax, [rbp+var_28]
0x18009706a  mov     qword ptr [rsp+60h+var_40], rax
0x18009706f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097074  test    edi, edi
0x180097076  jz      loc_1800974F5
0x18009707c  mov     edx, 73h ; 's'
0x180097081  jmp     loc_180096FBA
0x180097086  lea     rdx, aDriverupdatest_0; "DriverUpdateStageUpdates"
0x18009708d  mov     rcx, rbx; hModule
0x180097090  call    cs:__imp_GetProcAddress
0x180097097  nop     dword ptr [rax+rax+00h]
0x18009709c  mov     cs:?vpfnDriverUpdateStageUpdates@@3P6AKPEAUHDRIVERUPDATECONTEXT__@@PEAU_DRIVER_UPDATE@@KP6AH1KK_J@Z2@ZEA, rax; ulong (*vpfnDriverUpdateStageUpdates)(HDRIVERUPDATECONTEXT__ *,_DRIVER_UPDATE *,ulong,int (*)(_DRIVER_UPDATE *,ulong,ulong,__int64),__int64)
0x1800970a3  test    rax, rax
0x1800970a6  jnz     short loc_180097126
0x1800970a8  call    cs:__imp_GetLastError
0x1800970af  nop     dword ptr [rax+rax+00h]
0x1800970b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800970bb  mov     edi, eax
0x1800970bd  test    rcx, rcx
0x1800970c0  jz      short loc_180097114
0x1800970c2  mov     ebx, 3
0x1800970c7  lea     r9, aFailedToGetPro_6; "Failed to get proc address for DriverUp"...
0x1800970ce  mov     r8d, ebx
0x1800970d1  xor     edx, edx
0x1800970d3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800970d8  test    edi, edi
0x1800970da  jg      short loc_1800970E0
0x1800970dc  mov     eax, edi
0x1800970de  jmp     short loc_1800970E8
0x1800970e0  movzx   eax, di
0x1800970e3  or      eax, 80070000h
0x1800970e8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800970ef  lea     r9, a0; ": {0}"
0x1800970f6  mov     [rbp+var_2C], eax
0x1800970f9  mov     r8d, ebx
0x1800970fc  lea     rax, [rbp+var_2C]
0x180097100  mov     dl, 1
0x180097102  mov     qword ptr [rbp+var_28], rax
0x180097106  lea     rax, [rbp+var_28]
0x18009710a  mov     qword ptr [rsp+60h+var_40], rax
0x18009710f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097114  test    edi, edi
0x180097116  jz      loc_1800974F5
0x18009711c  mov     edx, 76h ; 'v'
0x180097121  jmp     loc_180096FBA
0x180097126  lea     rdx, aDriverupdateun; "DriverUpdateUnstageUpdates"
0x18009712d  mov     rcx, rbx; hModule
0x180097130  call    cs:__imp_GetProcAddress
0x180097137  nop     dword ptr [rax+rax+00h]
0x18009713c  mov     cs:?vpfnDriverUpdateUnstageUpdates@@3P6AKPEAUHDRIVERUPDATECONTEXT__@@PEAU_DRIVER_UPDATE@@KP6AH1KK_J@Z2@ZEA, rax; ulong (*vpfnDriverUpdateUnstageUpdates)(HDRIVERUPDATECONTEXT__ *,_DRIVER_UPDATE *,ulong,int (*)(_DRIVER_UPDATE *,ulong,ulong,__int64),__int64)
0x180097143  test    rax, rax
0x180097146  jnz     short loc_1800971C6
0x180097148  call    cs:__imp_GetLastError
0x18009714f  nop     dword ptr [rax+rax+00h]
0x180097154  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009715b  mov     edi, eax
0x18009715d  test    rcx, rcx
0x180097160  jz      short loc_1800971B4
0x180097162  mov     ebx, 3
0x180097167  lea     r9, aFailedToGetPro_1; "Failed to get proc address for DriverUp"...
0x18009716e  mov     r8d, ebx
0x180097171  xor     edx, edx
0x180097173  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097178  test    edi, edi
0x18009717a  jg      short loc_180097180
0x18009717c  mov     eax, edi
0x18009717e  jmp     short loc_180097188
0x180097180  movzx   eax, di
0x180097183  or      eax, 80070000h
0x180097188  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009718f  lea     r9, a0; ": {0}"
0x180097196  mov     [rbp+var_2C], eax
0x180097199  mov     r8d, ebx
0x18009719c  lea     rax, [rbp+var_2C]
0x1800971a0  mov     dl, 1
0x1800971a2  mov     qword ptr [rbp+var_28], rax
0x1800971a6  lea     rax, [rbp+var_28]
0x1800971aa  mov     qword ptr [rsp+60h+var_40], rax
0x1800971af  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800971b4  test    edi, edi
0x1800971b6  jz      loc_1800974F5
0x1800971bc  mov     edx, 79h ; 'y'
0x1800971c1  jmp     loc_180096FBA
0x1800971c6  lea     rdx, aDriverupdatein_1; "DriverUpdateInstallUpdates"
0x1800971cd  mov     rcx, rbx; hModule
0x1800971d0  call    cs:__imp_GetProcAddress
0x1800971d7  nop     dword ptr [rax+rax+00h]
0x1800971dc  mov     cs:?vpfnDriverUpdateInstallUpdates@@3P6AKPEAUHDRIVERUPDATECONTEXT__@@PEAU_DRIVER_UPDATE@@KP6AH1KK_J@Z2PEAX@ZEA, rax; ulong (*vpfnDriverUpdateInstallUpdates)(HDRIVERUPDATECONTEXT__ *,_DRIVER_UPDATE *,ulong,int (*)(_DRIVER_UPDATE *,ulong,ulong,__int64),__int64,void *)
0x1800971e3  test    rax, rax
0x1800971e6  jnz     short loc_180097266
0x1800971e8  call    cs:__imp_GetLastError
0x1800971ef  nop     dword ptr [rax+rax+00h]
0x1800971f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800971fb  mov     edi, eax
0x1800971fd  test    rcx, rcx
0x180097200  jz      short loc_180097254
0x180097202  mov     ebx, 3
0x180097207  lea     r9, aFailedToGetPro_68; "Failed to get proc address for DriverUp"...
0x18009720e  mov     r8d, ebx
0x180097211  xor     edx, edx
0x180097213  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097218  test    edi, edi
0x18009721a  jg      short loc_180097220
0x18009721c  mov     eax, edi
0x18009721e  jmp     short loc_180097228
0x180097220  movzx   eax, di
0x180097223  or      eax, 80070000h
0x180097228  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009722f  lea     r9, a0; ": {0}"
0x180097236  mov     [rbp+var_2C], eax
0x180097239  mov     r8d, ebx
0x18009723c  lea     rax, [rbp+var_2C]
0x180097240  mov     dl, 1
0x180097242  mov     qword ptr [rbp+var_28], rax
0x180097246  lea     rax, [rbp+var_28]
0x18009724a  mov     qword ptr [rsp+60h+var_40], rax
0x18009724f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097254  test    edi, edi
0x180097256  jz      loc_1800974F5
0x18009725c  mov     edx, 7Ch ; '|'
0x180097261  jmp     loc_180096FBA
0x180097266  lea     rdx, aDriverupdateun_0; "DriverUpdateUninstallUpdates"
0x18009726d  mov     rcx, rbx; hModule
0x180097270  call    cs:__imp_GetProcAddress
0x180097277  nop     dword ptr [rax+rax+00h]
0x18009727c  mov     cs:?vpfnDriverUpdateUninstallUpdates@@3P6AKPEAUHDRIVERUPDATECONTEXT__@@PEAU_DRIVER_UPDATE@@KP6AH1KK_J@Z2PEAX@ZEA, rax; ulong (*vpfnDriverUpdateUninstallUpdates)(HDRIVERUPDATECONTEXT__ *,_DRIVER_UPDATE *,ulong,int (*)(_DRIVER_UPDATE *,ulong,ulong,__int64),__int64,void *)
0x180097283  test    rax, rax
0x180097286  jnz     short loc_180097306
0x180097288  call    cs:__imp_GetLastError
0x18009728f  nop     dword ptr [rax+rax+00h]
0x180097294  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009729b  mov     edi, eax
0x18009729d  test    rcx, rcx
0x1800972a0  jz      short loc_1800972F4
0x1800972a2  mov     ebx, 3
0x1800972a7  lea     r9, aFailedToGetPro_41; "Failed to get proc address for DriverUp"...
0x1800972ae  mov     r8d, ebx
0x1800972b1  xor     edx, edx
0x1800972b3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800972b8  test    edi, edi
0x1800972ba  jg      short loc_1800972C0
0x1800972bc  mov     eax, edi
0x1800972be  jmp     short loc_1800972C8
0x1800972c0  movzx   eax, di
0x1800972c3  or      eax, 80070000h
0x1800972c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800972cf  lea     r9, a0; ": {0}"
0x1800972d6  mov     [rbp+var_2C], eax
0x1800972d9  mov     r8d, ebx
0x1800972dc  lea     rax, [rbp+var_2C]
0x1800972e0  mov     dl, 1
0x1800972e2  mov     qword ptr [rbp+var_28], rax
0x1800972e6  lea     rax, [rbp+var_28]
0x1800972ea  mov     qword ptr [rsp+60h+var_40], rax
0x1800972ef  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800972f4  test    edi, edi
0x1800972f6  jz      loc_1800974F5
0x1800972fc  mov     edx, 7Fh
0x180097301  jmp     loc_180096FBA
0x180097306  lea     rdx, aDriverupdateen_1; "DriverUpdateEnableDeviceInstall"
0x18009730d  mov     rcx, rbx; hModule
0x180097310  call    cs:__imp_GetProcAddress
0x180097317  nop     dword ptr [rax+rax+00h]
0x18009731c  mov     cs:?vpfnDriverUpdateEnableDeviceInstall@@3P6AHPEAUHDRIVERUPDATECONTEXT__@@H@ZEA, rax; int (*vpfnDriverUpdateEnableDeviceInstall)(HDRIVERUPDATECONTEXT__ *,int)
0x180097323  test    rax, rax
0x180097326  jnz     short loc_1800973A6
0x180097328  call    cs:__imp_GetLastError
0x18009732f  nop     dword ptr [rax+rax+00h]
0x180097334  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009733b  mov     edi, eax
0x18009733d  test    rcx, rcx
0x180097340  jz      short loc_180097394
0x180097342  mov     ebx, 3
0x180097347  lea     r9, aFailedToGetPro_76; "Failed to get proc address for DriverUp"...
0x18009734e  mov     r8d, ebx
0x180097351  xor     edx, edx
0x180097353  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097358  test    edi, edi
0x18009735a  jg      short loc_180097360
0x18009735c  mov     eax, edi
0x18009735e  jmp     short loc_180097368
0x180097360  movzx   eax, di
0x180097363  or      eax, 80070000h
  ... truncated ...
```
