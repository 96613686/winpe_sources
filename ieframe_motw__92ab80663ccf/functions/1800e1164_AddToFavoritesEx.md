# AddToFavoritesEx

- ea: `0x1800e1164`
- end: `0x1800e1974`
- name: `AddToFavoritesEx`
- size: `2064`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, unsigned int, __int64, int, unsigned __int16 *, unsigned __int64, __int64)`
- caller_count: `9`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800df9e4`
- `0x1800e0b80`
- `0x1800e21d0`
- `0x1800e25a0`
- `0x180135590`
- `0x1801b0750`
- `0x1801b3534`
- `0x1801b86b0`
- `0x1801d8864`

## callees

- `0x180005030`
- `0x1800144d0`
- `0x180024bc4`
- `0x180069234`
- `0x1800692fc`
- `0x180075ea0`
- `0x180099c70`
- `0x1800d1a48`
- `0x1800de524`
- `0x1800de6ec`
- `0x1800de73c`
- `0x1800e1164`
- `0x1800e1d0c`
- `0x1800e1d90`
- `0x180101460`
- `0x180155594`
- `0x1803a06b4`
- `0x180454890`
- `0x18057a6ac`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800e1852`
- `KERNEL32!DeleteFileW` at `0x1800e18a3`
- `KERNEL32!DeleteFileW` at `0x1800e1852`
- `KERNEL32!DeleteFileW` at `0x1800e18a3`
- `KERNEL32!GetCurrentThreadId` at `0x1800e12c9`
- `KERNEL32!GetCurrentThreadId` at `0x1800e12c9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlIsW` at `0x1800e153b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlIsW` at `0x1800e153b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800e15ac`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800e15ac`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800e169a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800e1784`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800e169a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800e1784`
- `USER32!LoadCursorW` at `0x1800e1470`
- `USER32!LoadCursorW` at `0x1800e1470`
- `USER32!SetCursor` at `0x1800e147f`
- `USER32!SetCursor` at `0x1800e1942`
- `USER32!SetCursor` at `0x1800e147f`
- `USER32!SetCursor` at `0x1800e1942`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800e1599`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800e15f9`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800e1599`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800e15f9`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800e1320`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800e1320`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800e1374`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800e1374`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800e18e8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800e18e8`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800e11cb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800e11cb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800e11ea`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800e11ea`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800e1222`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800e1269`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800e12b3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800e1222`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800e1269`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800e12b3`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800e12ea`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800e12ea`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1800e18fe`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1800e18fe`

## pseudocode

```c
__int64 __fastcall AddToFavoritesEx(
        __int64 a1,
        struct _ITEMIDLIST_ABSOLUTE *a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        unsigned __int16 *a9,
        unsigned __int64 a10,
        unsigned __int16 *a11)
{
  IStream *v14; // rax
  IStream *v15; // rbx
  int FrameTabComponentFromBrowserTabThread; // edi
  HRESULT v17; // eax
  DWORD CurrentThreadId; // eax
  unsigned int CurrentProcessManager; // eax
  HCURSOR CursorW; // rax
  int v21; // eax
  unsigned int v22; // r8d
  int v23; // eax
  int v24; // eax
  size_t v25; // rdx
  int v26; // eax
  const unsigned __int16 *FileNameW; // rax
  size_t v28; // rdx
  int v29; // eax
  DWORD pcchPath[2]; // [rsp+50h] [rbp-B0h] BYREF
  IStream *pstm; // [rsp+58h] [rbp-A8h] BYREF
  HCURSOR hCursor; // [rsp+60h] [rbp-A0h] BYREF
  int v34[2]; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v36; // [rsp+78h] [rbp-88h]
  _QWORD v37[3]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *p_pszPath; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  BOOL v40; // [rsp+A8h] [rbp-58h]
  int v41; // [rsp+ACh] [rbp-54h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  WCHAR pszPath; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v46[526]; // [rsp+D2h] [rbp-2Eh] BYREF
  WCHAR pszSpec[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR pszDir[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  WCHAR v49; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v50[526]; // [rsp+702h] [rbp+602h] BYREF
  WCHAR psz[2088]; // [rsp+910h] [rbp+810h] BYREF
  WCHAR v52[2088]; // [rsp+1960h] [rbp+1860h] BYREF

  v35 = a7;
  v36 = a11;
  *(_QWORD *)v34 = a1;
  if ( IsDualEngineProcess() )
  {
    pstm = 0;
    v14 = SHCreateMemStream(0, 0);
    ATL::CComPtrBase<IProtectionUtil>::Attach(&pstm, v14);
    v15 = pstm;
    if ( !pstm )
    {
      FrameTabComponentFromBrowserTabThread = -2147024882;
LABEL_13:
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pstm);
      return (unsigned int)FrameTabComponentFromBrowserTabThread;
    }
    if ( a4 )
    {
      v17 = IStream_WriteStr(pstm, a4);
    }
    else
    {
      FrameTabComponentFromBrowserTabThread = IEGetNameAndFlagsEx((int)a2, 0, 0, (int)psz, 0x824u, 0);
      if ( FrameTabComponentFromBrowserTabThread < 0 )
        goto LABEL_13;
      v17 = IStream_WriteStr(v15, psz);
    }
    FrameTabComponentFromBrowserTabThread = v17;
    if ( v17 >= 0 )
    {
      FrameTabComponentFromBrowserTabThread = IEGetNameAndFlagsEx((int)a2, 0x8000, 0, (int)v52, 0x824u, 0);
      if ( FrameTabComponentFromBrowserTabThread >= 0 )
      {
        FrameTabComponentFromBrowserTabThread = IStream_WriteStr(v15, v52);
        if ( FrameTabComponentFromBrowserTabThread >= 0 )
        {
          pcchPath[0] = 0;
          CurrentThreadId = GetCurrentThreadId();
          FrameTabComponentFromBrowserTabThread = GetFrameTabComponentFromBrowserTabThread(CurrentThreadId, pcchPath, 0);
          if ( FrameTabComponentFromBrowserTabThread >= 0 )
          {
            CurrentProcessManager = IsoGetCurrentProcessManager();
            FrameTabComponentFromBrowserTabThread = LCIEPostMessageWithStream(
                                                      pcchPath[0],
                                                      CurrentProcessManager,
                                                      0x140Du,
                                                      0,
                                                      v15);
          }
        }
      }
    }
    goto LABEL_13;
  }
  if ( IsProtectedModeProcess()
    || !FavoritesFolderLocationRequiresBrokering()
    && ((a6 & 0xC) == 0
     && (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_BROKER_FAVORITES_FOR_EFS_KB2300135)
     || (a6 & 1) == 0) )
  {
    FrameTabComponentFromBrowserTabThread = -2147467259;
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    hCursor = SetCursor(CursorW);
    if ( !a2 )
      goto LABEL_81;
    if ( a4 )
    {
      v21 = StringCchCopyW(psz, 0x824u, a4);
    }
    else
    {
      psz[0] = 0;
      v21 = IEGetNameAndFlagsEx((int)a2, 1, 0, (int)psz, 0x824u, 0);
    }
    FrameTabComponentFromBrowserTabThread = v21;
    if ( v21 < 0 )
      goto LABEL_81;
    v23 = a5 && *a5 ? StringCchCopyW(pszDir, 0x104u, a5) : GetInitialATFDirectory(a6, pszDir, v22);
    FrameTabComponentFromBrowserTabThread = v23;
    if ( v23 < 0 )
      goto LABEL_81;
    pcchPath[0] = 260;
    if ( UrlIsW(psz, URLIS_URL) && (unsigned int)PrepareURLForDisplayW(psz, pszSpec, pcchPath) )
    {
      FrameTabComponentFromBrowserTabThread = 0;
    }
    else
    {
      FrameTabComponentFromBrowserTabThread = StringCchCopyW(pszSpec, 0x104u, psz);
      if ( FrameTabComponentFromBrowserTabThread < 0 )
        goto LABEL_81;
    }
    PathCleanupSpec(pszDir, pszSpec);
    PathRemoveBlanksW(pszSpec);
    if ( !pszSpec[0] )
    {
      FrameTabComponentFromBrowserTabThread = IEGetNameAndFlagsEx((int)a2, 1, 0, (int)pszSpec, 0x104u, 0);
      if ( FrameTabComponentFromBrowserTabThread < 0 )
        goto LABEL_81;
      PathCleanupSpec(pszDir, pszSpec);
    }
    if ( (a6 & 1) != 0 )
    {
      v24 = 0;
      if ( (a6 & 2) != 0 )
        v24 = ((a6 & 4) != 0) + 1;
      if ( (unsigned int)DoSafeAddToFavDlgEx(v34[0], (int)pszDir, 260, (int)pszSpec, 260, a2, v24) )
      {
LABEL_47:
        BrowserTelemetry::IEAddToFavoritesDialogOKPressed();
        pszPath = 0;
        memset_0(v46, 0, 0x206u);
        PathCchRemoveExtension(pszSpec, v25);
        v44 = 0;
        v37[0] = a2;
        v37[1] = PathFindFileNameW(pszSpec);
        v37[2] = pszDir;
        p_pszPath = &pszPath;
        v39 = 260;
        v41 = 1;
        v42 = v35;
        v43 = 0;
        v40 = (a6 & 0x20) == 0 && ((a6 & 1) == 0 || (a6 & 0xC) != 0);
        v26 = v44;
        if ( (a6 & 0x40) != 0 )
          v26 = 1;
        LODWORD(v44) = v26;
        if ( (a6 & 0x80u) != 0 )
          LODWORD(v44) = v26 | 2;
        FrameTabComponentFromBrowserTabThread = CreateShortcutInDirEx(v37);
        if ( FrameTabComponentFromBrowserTabThread < 0 )
          goto LABEL_72;
        if ( (a6 & 4) != 0 || (a6 & 8) != 0 )
        {
          v52[0] = 0;
          FrameTabComponentFromBrowserTabThread = IEGetNameAndFlagsEx((int)a2, 0x8000, 0, (int)v52, 0x824u, 0);
          if ( FrameTabComponentFromBrowserTabThread < 0
            || (v49 = 0,
                memset_0(v50, 0, 0x206u),
                FileNameW = PathFindFileNameW(&pszPath),
                FrameTabComponentFromBrowserTabThread = StringCchCopyW(&v49, 0x104u, FileNameW),
                FrameTabComponentFromBrowserTabThread < 0)
            || (PathCchRemoveExtension(&v49, v28),
                FrameTabComponentFromBrowserTabThread = EnsureSubscribedUrl(v52, &v49, (a6 & 4) != 0, (a6 & 0x10) == 0),
                FrameTabComponentFromBrowserTabThread < 0)
            || (FrameTabComponentFromBrowserTabThread = WriteGenericPropertyToShortcut(
                                                          L"MonitoredItem",
                                                          &pszPath,
                                                          L"FeedUrl",
                                                          v52),
                FrameTabComponentFromBrowserTabThread < 0) )
          {
LABEL_71:
            DeleteFileW(&pszPath);
LABEL_72:
            if ( (a6 & 1) != 0 )
              SHIEErrorMsgBox(0, (__int64)pszSpec, 833, 0x10u);
LABEL_74:
            if ( FrameTabComponentFromBrowserTabThread >= 0 )
            {
              if ( (unsigned int)IEConfiguration_GetDWORD(536870929) )
              {
                v29 = EfsClientDecryptFile(p_pszPath, 0);
                FrameTabComponentFromBrowserTabThread = v29;
                if ( v29 > 0 )
                  FrameTabComponentFromBrowserTabThread = (unsigned __int16)v29 | 0x80070000;
              }
            }
            goto LABEL_81;
          }
          if ( v36 )
            WriteGenericPropertyToShortcut(L"MonitoredItem", &pszPath, L"PreviewSize", v36);
          if ( (a6 & 4) != 0 )
            WriteGenericPropertyToShortcut(L"MonitoredItem", &pszPath, L"IsLivePreview", L"true");
        }
        if ( !a3
          || !(unsigned int)IsBookmarkletURL(a3)
          || (FrameTabComponentFromBrowserTabThread = WriteGenericPropertyToShortcut(
                                                        L"Bookmarklet",
                                                        &pszPath,
                                                        L"ExtendedURL",
                                                        a3),
              FrameTabComponentFromBrowserTabThread >= 0) )
        {
          if ( a9 )
            StringCchCopyW(a9, (unsigned int)a10, &pszPath);
          goto LABEL_74;
        }
        goto LABEL_71;
      }
      FrameTabComponentFromBrowserTabThread = -2147467259;
    }
    if ( FrameTabComponentFromBrowserTabThread >= 0 )
      goto LABEL_47;
    FrameTabComponentFromBrowserTabThread = -2147467259;
LABEL_81:
    SetCursor(hCursor);
    return (unsigned int)FrameTabComponentFromBrowserTabThread;
  }
  hCursor = 0;
  *(_QWORD *)pcchPath = 0;
  FrameTabComponentFromBrowserTabThread = CoCreateUserBroker((struct IEUserBroker **)pcchPath);
  if ( FrameTabComponentFromBrowserTabThread >= 0 )
  {
    pstm = 0;
    FrameTabComponentFromBrowserTabThread = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, IStream **))(**(_QWORD **)pcchPath + 48LL))(
                                              *(_QWORD *)pcchPath,
                                              &CLSID_CShdocvwBroker,
                                              &IID_IUnknown,
                                              &pstm);
    if ( FrameTabComponentFromBrowserTabThread >= 0 )
    {
      FrameTabComponentFromBrowserTabThread = (**(__int64 (__fastcall ***)(IStream *, GUID *, HCURSOR *))pstm)(
                                                pstm,
                                                &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                                                &hCursor);
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcchPath + 16LL))(*(_QWORD *)pcchPath);
    if ( FrameTabComponentFromBrowserTabThread >= 0 )
    {
      FrameTabComponentFromBrowserTabThread = (*(__int64 (__fastcall **)(HCURSOR, _QWORD, struct _ITEMIDLIST_ABSOLUTE *, const WCHAR *, unsigned int, __int64, unsigned __int16 *, _DWORD, unsigned __int16 *))(*(_QWORD *)hCursor + 360LL))(
                                                hCursor,
                                                *(_QWORD *)v34,
                                                a2,
                                                a4,
                                                a6,
                                                v35,
                                                a9,
                                                a10,
                                                v36);
      (*(void (__fastcall **)(HCURSOR))(*(_QWORD *)hCursor + 16LL))(hCursor);
    }
  }
  return (unsigned int)FrameTabComponentFromBrowserTabThread;
}

```

## disassembly

```asm
0x1800e1164  push    rbp
0x1800e1166  push    rbx
0x1800e1167  push    rsi
0x1800e1168  push    rdi
0x1800e1169  push    r12
0x1800e116b  push    r13
0x1800e116d  push    r14
0x1800e116f  push    r15
0x1800e1171  lea     rbp, [rsp-28C8h]
0x1800e1179  mov     eax, 29C8h
0x1800e117e  call    _alloca_probe
0x1800e1183  sub     rsp, rax
0x1800e1186  mov     rax, cs:__security_cookie
0x1800e118d  xor     rax, rsp
0x1800e1190  mov     [rbp+2900h+var_50], rax
0x1800e1197  mov     rax, [rbp+2900h+arg_30]
0x1800e119e  mov     rsi, r9
0x1800e11a1  mov     r14, [rbp+2900h+arg_20]
0x1800e11a8  mov     r12, r8
0x1800e11ab  mov     r13, [rbp+2900h+arg_40]
0x1800e11b2  mov     r15, rdx
0x1800e11b5  mov     [rsp+2A00h+var_2990], rax
0x1800e11ba  mov     rax, [rbp+2900h+arg_50]
0x1800e11c1  mov     [rsp+2A00h+var_2988], rax
0x1800e11c6  mov     qword ptr [rsp+2A00h+var_2998], rcx
0x1800e11cb  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800e11d2  nop     dword ptr [rax+rax+00h]
0x1800e11d7  xor     edi, edi
0x1800e11d9  test    al, al
0x1800e11db  jz      loc_1800E1320
0x1800e11e1  xor     edx, edx; cbInit
0x1800e11e3  mov     [rsp+2A00h+pstm], rdi
0x1800e11e8  xor     ecx, ecx; pInit
0x1800e11ea  call    cs:__imp_SHCreateMemStream
0x1800e11f1  nop     dword ptr [rax+rax+00h]
0x1800e11f6  mov     rdx, rax
0x1800e11f9  lea     rcx, [rsp+2A00h+pstm]
0x1800e11fe  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x1800e1203  mov     rbx, [rsp+2A00h+pstm]
0x1800e1208  test    rbx, rbx
0x1800e120b  jnz     short loc_1800E1217
0x1800e120d  mov     edi, 8007000Eh
0x1800e1212  jmp     loc_1800E1311
0x1800e1217  test    rsi, rsi
0x1800e121a  jz      short loc_1800E1232
0x1800e121c  mov     rdx, rsi; psz
0x1800e121f  mov     rcx, rbx; pstm
0x1800e1222  call    cs:__imp_IStream_WriteStr
0x1800e1229  nop     dword ptr [rax+rax+00h]
0x1800e122e  xor     esi, esi
0x1800e1230  jmp     short loc_1800E1275
0x1800e1232  mov     [rsp+2A00h+var_29D8], rdi; __int64
0x1800e1237  lea     r9, [rbp+2900h+psz]; int
0x1800e123e  xor     r8d, r8d; int
0x1800e1241  mov     [rsp+2A00h+cchBuf], 824h; cchBuf
0x1800e1249  xor     edx, edx; int
0x1800e124b  mov     rcx, r15; int
0x1800e124e  call    IEGetNameAndFlagsEx
0x1800e1253  xor     esi, esi
0x1800e1255  mov     edi, eax
0x1800e1257  test    eax, eax
0x1800e1259  js      loc_1800E1311
0x1800e125f  lea     rdx, [rbp+2900h+psz]; psz
0x1800e1266  mov     rcx, rbx; pstm
0x1800e1269  call    cs:__imp_IStream_WriteStr
0x1800e1270  nop     dword ptr [rax+rax+00h]
0x1800e1275  mov     edi, eax
0x1800e1277  test    eax, eax
0x1800e1279  js      loc_1800E1311
0x1800e127f  mov     [rsp+2A00h+var_29D8], rsi; __int64
0x1800e1284  lea     r9, [rbp+2900h+var_10A0]; int
0x1800e128b  xor     r8d, r8d; int
0x1800e128e  mov     [rsp+2A00h+cchBuf], 824h; cchBuf
0x1800e1296  mov     edx, 8000h; int
0x1800e129b  mov     rcx, r15; int
0x1800e129e  call    IEGetNameAndFlagsEx
0x1800e12a3  mov     edi, eax
0x1800e12a5  test    eax, eax
0x1800e12a7  js      short loc_1800E1311
0x1800e12a9  lea     rdx, [rbp+2900h+var_10A0]; psz
0x1800e12b0  mov     rcx, rbx; pstm
0x1800e12b3  call    cs:__imp_IStream_WriteStr
0x1800e12ba  nop     dword ptr [rax+rax+00h]
0x1800e12bf  mov     edi, eax
0x1800e12c1  test    eax, eax
0x1800e12c3  js      short loc_1800E1311
0x1800e12c5  mov     [rsp+2A00h+pcchPath], esi
0x1800e12c9  call    cs:__imp_GetCurrentThreadId
0x1800e12d0  nop     dword ptr [rax+rax+00h]
0x1800e12d5  xor     r8d, r8d; struct _IsoComponent **
0x1800e12d8  lea     rdx, [rsp+2A00h+pcchPath]; unsigned int *
0x1800e12dd  mov     ecx, eax; unsigned int
0x1800e12df  call    ?GetFrameTabComponentFromBrowserTabThread@@YAJKPEAKPEAPEAU_IsoComponent@@@Z; GetFrameTabComponentFromBrowserTabThread(ulong,ulong *,_IsoComponent * *)
0x1800e12e4  mov     edi, eax
0x1800e12e6  test    eax, eax
0x1800e12e8  js      short loc_1800E1311
0x1800e12ea  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1800e12f1  nop     dword ptr [rax+rax+00h]
0x1800e12f6  mov     ecx, [rsp+2A00h+pcchPath]; unsigned int
0x1800e12fa  xor     r9d, r9d; unsigned int
0x1800e12fd  mov     edx, eax; unsigned int
0x1800e12ff  mov     qword ptr [rsp+2A00h+cchBuf], rbx; pstm
0x1800e1304  mov     r8d, 140Dh; unsigned int
0x1800e130a  call    ?LCIEPostMessageWithStream@@YAJKKKKPEAUIStream@@@Z; LCIEPostMessageWithStream(ulong,ulong,ulong,ulong,IStream *)
0x1800e130f  mov     edi, eax
0x1800e1311  lea     rcx, [rsp+2A00h+pstm]; void *
0x1800e1316  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800e131b  jmp     loc_1800E194E
0x1800e1320  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800e1327  nop     dword ptr [rax+rax+00h]
0x1800e132c  mov     ebx, [rbp+2900h+arg_28]
0x1800e1332  test    eax, eax
0x1800e1334  jnz     loc_1800E1464
0x1800e133a  call    ?FavoritesFolderLocationRequiresBrokering@@YA_NXZ; FavoritesFolderLocationRequiresBrokering(void)
0x1800e133f  test    al, al
0x1800e1341  jnz     short loc_1800E1365
0x1800e1343  test    bl, 0Ch
0x1800e1346  jnz     short loc_1800E135C
0x1800e1348  lea     rcx, ?FEATURE_BROKER_FAVORITES_FOR_EFS_KB2300135@FCK@@3VCFeatureControlKey@@A; this
0x1800e134f  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800e1354  test    eax, eax
0x1800e1356  jnz     loc_1800E1464
0x1800e135c  test    bl, 1
0x1800e135f  jz      loc_1800E1464
0x1800e1365  lea     rcx, [rsp+2A00h+pcchPath]
0x1800e136a  mov     [rsp+2A00h+hCursor], rdi
0x1800e136f  mov     qword ptr [rsp+2A00h+pcchPath], rdi
0x1800e1374  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1800e137b  nop     dword ptr [rax+rax+00h]
0x1800e1380  xor     r14d, r14d
0x1800e1383  mov     edi, eax
0x1800e1385  test    eax, eax
0x1800e1387  js      loc_1800E194E
0x1800e138d  mov     rcx, qword ptr [rsp+2A00h+pcchPath]
0x1800e1392  lea     r9, [rsp+2A00h+pstm]
0x1800e1397  mov     [rsp+2A00h+pstm], r14
0x1800e139c  lea     r8, IID_IUnknown
0x1800e13a3  lea     rdx, CLSID_CShdocvwBroker
0x1800e13aa  mov     rax, [rcx]
0x1800e13ad  mov     rax, [rax+30h]
0x1800e13b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13b6  mov     edi, eax
0x1800e13b8  test    eax, eax
0x1800e13ba  js      short loc_1800E13EB
0x1800e13bc  mov     rcx, [rsp+2A00h+pstm]
0x1800e13c1  lea     r8, [rsp+2A00h+hCursor]
0x1800e13c6  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1800e13cd  mov     rax, [rcx]
0x1800e13d0  mov     rax, [rax]
0x1800e13d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13d8  mov     rcx, [rsp+2A00h+pstm]
0x1800e13dd  mov     edi, eax
0x1800e13df  mov     rax, [rcx]
0x1800e13e2  mov     rax, [rax+10h]
0x1800e13e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13eb  mov     rcx, qword ptr [rsp+2A00h+pcchPath]
0x1800e13f0  mov     rax, [rcx]
0x1800e13f3  mov     rax, [rax+10h]
0x1800e13f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13fc  test    edi, edi
0x1800e13fe  js      loc_1800E194E
0x1800e1404  mov     r8, [rsp+2A00h+var_2988]
0x1800e1409  mov     r9, rsi
0x1800e140c  mov     rcx, [rsp+2A00h+hCursor]
0x1800e1411  mov     rdx, qword ptr [rsp+2A00h+var_2998]
0x1800e1416  mov     [rsp+2A00h+var_29C0], r8
0x1800e141b  mov     r8d, dword ptr [rbp+2900h+arg_48]
0x1800e1422  mov     rax, [rcx]
0x1800e1425  mov     [rsp+2A00h+var_29C8], r8d
0x1800e142a  mov     r8, [rsp+2A00h+var_2990]
0x1800e142f  mov     qword ptr [rsp+2A00h+var_29D0], r13
0x1800e1434  mov     rax, [rax+168h]
0x1800e143b  mov     [rsp+2A00h+var_29D8], r8
0x1800e1440  mov     r8, r15
0x1800e1443  mov     [rsp+2A00h+cchBuf], ebx
0x1800e1447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e144c  mov     rcx, [rsp+2A00h+hCursor]
0x1800e1451  mov     edi, eax
0x1800e1453  mov     rax, [rcx]
0x1800e1456  mov     rax, [rax+10h]
0x1800e145a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e145f  jmp     loc_1800E194E
0x1800e1464  mov     edx, 7F02h; lpCursorName
0x1800e1469  xor     ecx, ecx; hInstance
0x1800e146b  mov     edi, 80004005h
0x1800e1470  call    cs:__imp_LoadCursorW
0x1800e1477  nop     dword ptr [rax+rax+00h]
0x1800e147c  mov     rcx, rax; hCursor
0x1800e147f  call    cs:__imp_SetCursor
0x1800e1486  nop     dword ptr [rax+rax+00h]
0x1800e148b  mov     [rsp+2A00h+hCursor], rax
0x1800e1490  test    r15, r15
0x1800e1493  jz      loc_1800E193D
0x1800e1499  test    rsi, rsi
0x1800e149c  jz      short loc_1800E14B6
0x1800e149e  mov     r8, rsi; unsigned __int16 *
0x1800e14a1  lea     rcx, [rbp+2900h+psz]; unsigned __int16 *
0x1800e14a8  mov     edx, 824h; unsigned __int64
0x1800e14ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e14b2  xor     esi, esi
0x1800e14b4  jmp     short loc_1800E14E0
0x1800e14b6  xor     r8d, r8d; int
0x1800e14b9  mov     [rsp+2A00h+var_29D8], rsi; __int64
0x1800e14be  lea     r9, [rbp+2900h+psz]; int
0x1800e14c5  mov     [rbp+2900h+psz], si
0x1800e14cc  mov     rcx, r15; int
0x1800e14cf  mov     [rsp+2A00h+cchBuf], 824h; cchBuf
0x1800e14d7  lea     edx, [r8+1]; int
0x1800e14db  call    IEGetNameAndFlagsEx
0x1800e14e0  mov     edi, eax
0x1800e14e2  test    eax, eax
0x1800e14e4  js      loc_1800E193D
0x1800e14ea  test    r14, r14
0x1800e14ed  jz      short loc_1800E150F
0x1800e14ef  cmp     [r14], si
0x1800e14f3  jz      short loc_1800E150F
0x1800e14f5  mov     r8, r14; unsigned __int16 *
0x1800e14f8  lea     rcx, [rbp+2900h+pszDir]; unsigned __int16 *
0x1800e14ff  mov     r14d, 104h
0x1800e1505  mov     edx, r14d; unsigned __int64
0x1800e1508  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e150d  jmp     short loc_1800E1523
0x1800e150f  lea     rdx, [rbp+2900h+pszDir]; unsigned __int16 *
0x1800e1516  mov     ecx, ebx; unsigned int
0x1800e1518  call    ?GetInitialATFDirectory@@YAJKPEAGK@Z; GetInitialATFDirectory(ulong,ushort *,ulong)
0x1800e151d  mov     r14d, 104h
0x1800e1523  mov     edi, eax
0x1800e1525  test    eax, eax
0x1800e1527  js      loc_1800E193D
0x1800e152d  xor     edx, edx; UrlIs
0x1800e152f  mov     [rsp+2A00h+pcchPath], r14d
0x1800e1534  lea     rcx, [rbp+2900h+psz]; pszUrl
0x1800e153b  call    cs:__imp_UrlIsW
0x1800e1542  nop     dword ptr [rax+rax+00h]
0x1800e1547  test    eax, eax
0x1800e1549  jz      short loc_1800E156B
0x1800e154b  lea     r8, [rsp+2A00h+pcchPath]; pcchPath
0x1800e1550  lea     rdx, [rbp+2900h+pszSpec]; unsigned __int16 *
0x1800e1557  lea     rcx, [rbp+2900h+psz]; unsigned __int16 *
0x1800e155e  call    PrepareURLForDisplayW
0x1800e1563  test    eax, eax
0x1800e1565  jz      short loc_1800E156B
0x1800e1567  mov     edi, esi
0x1800e1569  jmp     short loc_1800E158B
0x1800e156b  lea     r8, [rbp+2900h+psz]; unsigned __int16 *
0x1800e1572  mov     rdx, r14; unsigned __int64
0x1800e1575  lea     rcx, [rbp+2900h+pszSpec]; unsigned __int16 *
0x1800e157c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e1581  mov     edi, eax
0x1800e1583  test    eax, eax
0x1800e1585  js      loc_1800E193D
0x1800e158b  lea     rdx, [rbp+2900h+pszSpec]; pszSpec
0x1800e1592  lea     rcx, [rbp+2900h+pszDir]; pszDir
0x1800e1599  call    cs:__imp_PathCleanupSpec
0x1800e15a0  nop     dword ptr [rax+rax+00h]
0x1800e15a5  lea     rcx, [rbp+2900h+pszSpec]; pszPath
0x1800e15ac  call    cs:__imp_PathRemoveBlanksW
0x1800e15b3  nop     dword ptr [rax+rax+00h]
0x1800e15b8  cmp     [rbp+2900h+pszSpec], si
0x1800e15bf  jnz     short loc_1800E1605
0x1800e15c1  xor     r8d, r8d; int
0x1800e15c4  mov     [rsp+2A00h+var_29D8], rsi; __int64
0x1800e15c9  lea     r9, [rbp+2900h+pszSpec]; int
0x1800e15d0  mov     [rsp+2A00h+cchBuf], r14d; cchBuf
0x1800e15d5  mov     rcx, r15; int
0x1800e15d8  lea     edx, [r8+1]; int
0x1800e15dc  call    IEGetNameAndFlagsEx
0x1800e15e1  mov     edi, eax
0x1800e15e3  test    eax, eax
0x1800e15e5  js      loc_1800E193D
0x1800e15eb  lea     rdx, [rbp+2900h+pszSpec]; pszSpec
0x1800e15f2  lea     rcx, [rbp+2900h+pszDir]; pszDir
0x1800e15f9  call    cs:__imp_PathCleanupSpec
0x1800e1600  nop     dword ptr [rax+rax+00h]
0x1800e1605  mov     r14d, ebx
0x1800e1608  mov     ecx, 1
0x1800e160d  and     r14d, ecx
0x1800e1610  jz      short loc_1800E165D
0x1800e1612  mov     eax, esi
0x1800e1614  test    bl, 2
0x1800e1617  jz      short loc_1800E1625
0x1800e1619  mov     al, bl
0x1800e161b  and     al, 4
0x1800e161d  neg     al
0x1800e161f  sbb     eax, eax
0x1800e1621  neg     eax
0x1800e1623  add     eax, ecx
0x1800e1625  mov     rcx, qword ptr [rsp+2A00h+var_2998]; int
0x1800e162a  lea     r9, [rbp+2900h+pszSpec]; int
0x1800e1631  mov     [rsp+2A00h+var_29D0], eax; int
0x1800e1635  lea     rdx, [rbp+2900h+pszDir]; int
0x1800e163c  mov     [rsp+2A00h+var_29D8], r15; struct _ITEMIDLIST_ABSOLUTE *
0x1800e1641  mov     r8d, 104h; int
0x1800e1647  mov     [rsp+2A00h+cchBuf], 104h; int
0x1800e164f  call    DoSafeAddToFavDlgEx
0x1800e1654  test    eax, eax
0x1800e1656  jnz     short loc_1800E1665
0x1800e1658  mov     edi, 80004005h
0x1800e165d  test    edi, edi
0x1800e165f  js      loc_1800E1938
  ... truncated ...
```
