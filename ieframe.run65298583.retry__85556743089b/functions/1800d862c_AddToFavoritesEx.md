# AddToFavoritesEx

- ea: `0x1800d862c`
- end: `0x1800d8db3`
- name: `AddToFavoritesEx`
- size: `1927`
- prototype: `__int64 __fastcall(__int64, struct _ITEMIDLIST_ABSOLUTE *, const unsigned __int16 *, const WCHAR *, unsigned __int16 *, unsigned int, __int64, int, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d709c`
- `0x1800d8080`
- `0x1800d95bc`
- `0x1800d9960`
- `0x180127d90`
- `0x18019c060`
- `0x18019eb34`
- `0x1801a3aec`
- `0x1801c1c30`

## callees

- `0x18000b9e0`
- `0x180011230`
- `0x18002320c`
- `0x180064cfc`
- `0x180065a9c`
- `0x1800708d8`
- `0x180092a2c`
- `0x1800c9dc4`
- `0x1800d5de8`
- `0x1800d5f6c`
- `0x1800d5fb8`
- `0x1800d862c`
- `0x1800d910c`
- `0x1800d9190`
- `0x1800f6730`
- `0x180145eb0`
- `0x180370b74`
- `0x18041b958`
- `0x180538024`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800d8cb4`
- `KERNEL32!DeleteFileW` at `0x1800d8cfb`
- `KERNEL32!DeleteFileW` at `0x1800d8cb4`
- `KERNEL32!DeleteFileW` at `0x1800d8cfb`
- `KERNEL32!GetCurrentThreadId` at `0x1800d8773`
- `KERNEL32!GetCurrentThreadId` at `0x1800d8773`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlIsW` at `0x1800d89c1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlIsW` at `0x1800d89c1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800d8a26`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800d8a26`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800d8b08`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800d8bec`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800d8b08`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800d8bec`
- `USER32!LoadCursorW` at `0x1800d8902`
- `USER32!LoadCursorW` at `0x1800d8902`
- `USER32!SetCursor` at `0x1800d890b`
- `USER32!SetCursor` at `0x1800d8d88`
- `USER32!SetCursor` at `0x1800d890b`
- `USER32!SetCursor` at `0x1800d8d88`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800d8a19`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800d8a6d`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800d8a19`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800d8a6d`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800d87be`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800d87be`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800d880c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800d880c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800d8d3a`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800d8d3a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800d8693`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800d8693`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800d86ac`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800d86ac`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800d86de`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800d871f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800d8763`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800d86de`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800d871f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800d8763`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800d878e`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1800d878e`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1800d8d4a`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1800d8d4a`

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
0x1800d862c  push    rbp
0x1800d862e  push    rbx
0x1800d862f  push    rsi
0x1800d8630  push    rdi
0x1800d8631  push    r12
0x1800d8633  push    r13
0x1800d8635  push    r14
0x1800d8637  push    r15
0x1800d8639  lea     rbp, [rsp-28C8h]
0x1800d8641  mov     eax, 29C8h
0x1800d8646  call    _alloca_probe
0x1800d864b  sub     rsp, rax
0x1800d864e  mov     rax, cs:__security_cookie
0x1800d8655  xor     rax, rsp
0x1800d8658  mov     [rbp+2900h+var_50], rax
0x1800d865f  mov     rax, [rbp+2900h+arg_30]
0x1800d8666  mov     rsi, r9
0x1800d8669  mov     r14, [rbp+2900h+arg_20]
0x1800d8670  mov     r12, r8
0x1800d8673  mov     r13, [rbp+2900h+arg_40]
0x1800d867a  mov     r15, rdx
0x1800d867d  mov     [rsp+2A00h+var_2990], rax
0x1800d8682  mov     rax, [rbp+2900h+arg_50]
0x1800d8689  mov     [rsp+2A00h+var_2988], rax
0x1800d868e  mov     qword ptr [rsp+2A00h+var_2998], rcx
0x1800d8693  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800d8699  xor     edi, edi
0x1800d869b  test    al, al
0x1800d869d  jz      loc_1800D87BE
0x1800d86a3  xor     edx, edx; cbInit
0x1800d86a5  mov     [rsp+2A00h+pstm], rdi
0x1800d86aa  xor     ecx, ecx; pInit
0x1800d86ac  call    cs:__imp_SHCreateMemStream
0x1800d86b2  mov     rdx, rax
0x1800d86b5  lea     rcx, [rsp+2A00h+pstm]
0x1800d86ba  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x1800d86bf  mov     rbx, [rsp+2A00h+pstm]
0x1800d86c4  test    rbx, rbx
0x1800d86c7  jnz     short loc_1800D86D3
0x1800d86c9  mov     edi, 8007000Eh
0x1800d86ce  jmp     loc_1800D87AF
0x1800d86d3  test    rsi, rsi
0x1800d86d6  jz      short loc_1800D86E8
0x1800d86d8  mov     rdx, rsi; psz
0x1800d86db  mov     rcx, rbx; pstm
0x1800d86de  call    cs:__imp_IStream_WriteStr
0x1800d86e4  xor     esi, esi
0x1800d86e6  jmp     short loc_1800D8725
0x1800d86e8  mov     [rsp+2A00h+var_29D8], rdi; __int64
0x1800d86ed  lea     r9, [rbp+2900h+psz]; int
0x1800d86f4  xor     r8d, r8d; int
0x1800d86f7  mov     [rsp+2A00h+cchBuf], 824h; cchBuf
0x1800d86ff  xor     edx, edx; int
0x1800d8701  mov     rcx, r15; int
0x1800d8704  call    IEGetNameAndFlagsEx
0x1800d8709  xor     esi, esi
0x1800d870b  mov     edi, eax
0x1800d870d  test    eax, eax
0x1800d870f  js      loc_1800D87AF
0x1800d8715  lea     rdx, [rbp+2900h+psz]; psz
0x1800d871c  mov     rcx, rbx; pstm
0x1800d871f  call    cs:__imp_IStream_WriteStr
0x1800d8725  mov     edi, eax
0x1800d8727  test    eax, eax
0x1800d8729  js      loc_1800D87AF
0x1800d872f  mov     [rsp+2A00h+var_29D8], rsi; __int64
0x1800d8734  lea     r9, [rbp+2900h+var_10A0]; int
0x1800d873b  xor     r8d, r8d; int
0x1800d873e  mov     [rsp+2A00h+cchBuf], 824h; cchBuf
0x1800d8746  mov     edx, 8000h; int
0x1800d874b  mov     rcx, r15; int
0x1800d874e  call    IEGetNameAndFlagsEx
0x1800d8753  mov     edi, eax
0x1800d8755  test    eax, eax
0x1800d8757  js      short loc_1800D87AF
0x1800d8759  lea     rdx, [rbp+2900h+var_10A0]; psz
0x1800d8760  mov     rcx, rbx; pstm
0x1800d8763  call    cs:__imp_IStream_WriteStr
0x1800d8769  mov     edi, eax
0x1800d876b  test    eax, eax
0x1800d876d  js      short loc_1800D87AF
0x1800d876f  mov     [rsp+2A00h+pcchPath], esi
0x1800d8773  call    cs:__imp_GetCurrentThreadId
0x1800d8779  xor     r8d, r8d; struct _IsoComponent **
0x1800d877c  lea     rdx, [rsp+2A00h+pcchPath]; unsigned int *
0x1800d8781  mov     ecx, eax; unsigned int
0x1800d8783  call    ?GetFrameTabComponentFromBrowserTabThread@@YAJKPEAKPEAPEAU_IsoComponent@@@Z; GetFrameTabComponentFromBrowserTabThread(ulong,ulong *,_IsoComponent * *)
0x1800d8788  mov     edi, eax
0x1800d878a  test    eax, eax
0x1800d878c  js      short loc_1800D87AF
0x1800d878e  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1800d8794  mov     ecx, [rsp+2A00h+pcchPath]; unsigned int
0x1800d8798  xor     r9d, r9d; unsigned int
0x1800d879b  mov     edx, eax; unsigned int
0x1800d879d  mov     qword ptr [rsp+2A00h+cchBuf], rbx; pstm
0x1800d87a2  mov     r8d, 140Dh; unsigned int
0x1800d87a8  call    ?LCIEPostMessageWithStream@@YAJKKKKPEAUIStream@@@Z; LCIEPostMessageWithStream(ulong,ulong,ulong,ulong,IStream *)
0x1800d87ad  mov     edi, eax
0x1800d87af  lea     rcx, [rsp+2A00h+pstm]; void *
0x1800d87b4  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800d87b9  jmp     loc_1800D8D8E
0x1800d87be  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800d87c4  mov     ebx, [rbp+2900h+arg_28]
0x1800d87ca  test    eax, eax
0x1800d87cc  jnz     loc_1800D88F6
0x1800d87d2  call    ?FavoritesFolderLocationRequiresBrokering@@YA_NXZ; FavoritesFolderLocationRequiresBrokering(void)
0x1800d87d7  test    al, al
0x1800d87d9  jnz     short loc_1800D87FD
0x1800d87db  test    bl, 0Ch
0x1800d87de  jnz     short loc_1800D87F4
0x1800d87e0  lea     rcx, ?FEATURE_BROKER_FAVORITES_FOR_EFS_KB2300135@FCK@@3VCFeatureControlKey@@A; this
0x1800d87e7  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800d87ec  test    eax, eax
0x1800d87ee  jnz     loc_1800D88F6
0x1800d87f4  test    bl, 1
0x1800d87f7  jz      loc_1800D88F6
0x1800d87fd  lea     rcx, [rsp+2A00h+pcchPath]
0x1800d8802  mov     [rsp+2A00h+hCursor], rdi
0x1800d8807  mov     qword ptr [rsp+2A00h+pcchPath], rdi
0x1800d880c  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1800d8812  xor     r14d, r14d
0x1800d8815  mov     edi, eax
0x1800d8817  test    eax, eax
0x1800d8819  js      loc_1800D8D8E
0x1800d881f  mov     rcx, qword ptr [rsp+2A00h+pcchPath]
0x1800d8824  lea     r9, [rsp+2A00h+pstm]
0x1800d8829  mov     [rsp+2A00h+pstm], r14
0x1800d882e  lea     r8, IID_IUnknown
0x1800d8835  lea     rdx, CLSID_CShdocvwBroker
0x1800d883c  mov     rax, [rcx]
0x1800d883f  mov     rax, [rax+30h]
0x1800d8843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8848  mov     edi, eax
0x1800d884a  test    eax, eax
0x1800d884c  js      short loc_1800D887D
0x1800d884e  mov     rcx, [rsp+2A00h+pstm]
0x1800d8853  lea     r8, [rsp+2A00h+hCursor]
0x1800d8858  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1800d885f  mov     rax, [rcx]
0x1800d8862  mov     rax, [rax]
0x1800d8865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d886a  mov     rcx, [rsp+2A00h+pstm]
0x1800d886f  mov     edi, eax
0x1800d8871  mov     rax, [rcx]
0x1800d8874  mov     rax, [rax+10h]
0x1800d8878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d887d  mov     rcx, qword ptr [rsp+2A00h+pcchPath]
0x1800d8882  mov     rax, [rcx]
0x1800d8885  mov     rax, [rax+10h]
0x1800d8889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d888e  test    edi, edi
0x1800d8890  js      loc_1800D8D8E
0x1800d8896  mov     r8, [rsp+2A00h+var_2988]
0x1800d889b  mov     r9, rsi
0x1800d889e  mov     rcx, [rsp+2A00h+hCursor]
0x1800d88a3  mov     rdx, qword ptr [rsp+2A00h+var_2998]
0x1800d88a8  mov     [rsp+2A00h+var_29C0], r8
0x1800d88ad  mov     r8d, dword ptr [rbp+2900h+arg_48]
0x1800d88b4  mov     rax, [rcx]
0x1800d88b7  mov     [rsp+2A00h+var_29C8], r8d
0x1800d88bc  mov     r8, [rsp+2A00h+var_2990]
0x1800d88c1  mov     qword ptr [rsp+2A00h+var_29D0], r13
0x1800d88c6  mov     rax, [rax+168h]
0x1800d88cd  mov     [rsp+2A00h+var_29D8], r8
0x1800d88d2  mov     r8, r15
0x1800d88d5  mov     [rsp+2A00h+cchBuf], ebx
0x1800d88d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d88de  mov     rcx, [rsp+2A00h+hCursor]
0x1800d88e3  mov     edi, eax
0x1800d88e5  mov     rax, [rcx]
0x1800d88e8  mov     rax, [rax+10h]
0x1800d88ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d88f1  jmp     loc_1800D8D8E
0x1800d88f6  mov     edx, 7F02h; lpCursorName
0x1800d88fb  xor     ecx, ecx; hInstance
0x1800d88fd  mov     edi, 80004005h
0x1800d8902  call    cs:__imp_LoadCursorW
0x1800d8908  mov     rcx, rax; hCursor
0x1800d890b  call    cs:__imp_SetCursor
0x1800d8911  mov     [rsp+2A00h+hCursor], rax
0x1800d8916  test    r15, r15
0x1800d8919  jz      loc_1800D8D83
0x1800d891f  test    rsi, rsi
0x1800d8922  jz      short loc_1800D893C
0x1800d8924  mov     r8, rsi; unsigned __int16 *
0x1800d8927  lea     rcx, [rbp+2900h+psz]; unsigned __int16 *
0x1800d892e  mov     edx, 824h; unsigned __int64
0x1800d8933  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d8938  xor     esi, esi
0x1800d893a  jmp     short loc_1800D8966
0x1800d893c  xor     r8d, r8d; int
0x1800d893f  mov     [rsp+2A00h+var_29D8], rsi; __int64
0x1800d8944  lea     r9, [rbp+2900h+psz]; int
0x1800d894b  mov     [rbp+2900h+psz], si
0x1800d8952  mov     rcx, r15; int
0x1800d8955  mov     [rsp+2A00h+cchBuf], 824h; cchBuf
0x1800d895d  lea     edx, [r8+1]; int
0x1800d8961  call    IEGetNameAndFlagsEx
0x1800d8966  mov     edi, eax
0x1800d8968  test    eax, eax
0x1800d896a  js      loc_1800D8D83
0x1800d8970  test    r14, r14
0x1800d8973  jz      short loc_1800D8995
0x1800d8975  cmp     [r14], si
0x1800d8979  jz      short loc_1800D8995
0x1800d897b  mov     r8, r14; unsigned __int16 *
0x1800d897e  lea     rcx, [rbp+2900h+pszDir]; unsigned __int16 *
0x1800d8985  mov     r14d, 104h
0x1800d898b  mov     edx, r14d; unsigned __int64
0x1800d898e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d8993  jmp     short loc_1800D89A9
0x1800d8995  lea     rdx, [rbp+2900h+pszDir]; unsigned __int16 *
0x1800d899c  mov     ecx, ebx; unsigned int
0x1800d899e  call    ?GetInitialATFDirectory@@YAJKPEAGK@Z; GetInitialATFDirectory(ulong,ushort *,ulong)
0x1800d89a3  mov     r14d, 104h
0x1800d89a9  mov     edi, eax
0x1800d89ab  test    eax, eax
0x1800d89ad  js      loc_1800D8D83
0x1800d89b3  xor     edx, edx; UrlIs
0x1800d89b5  mov     [rsp+2A00h+pcchPath], r14d
0x1800d89ba  lea     rcx, [rbp+2900h+psz]; pszUrl
0x1800d89c1  call    cs:__imp_UrlIsW
0x1800d89c7  test    eax, eax
0x1800d89c9  jz      short loc_1800D89EB
0x1800d89cb  lea     r8, [rsp+2A00h+pcchPath]; pcchPath
0x1800d89d0  lea     rdx, [rbp+2900h+pszSpec]; unsigned __int16 *
0x1800d89d7  lea     rcx, [rbp+2900h+psz]; unsigned __int16 *
0x1800d89de  call    PrepareURLForDisplayW
0x1800d89e3  test    eax, eax
0x1800d89e5  jz      short loc_1800D89EB
0x1800d89e7  mov     edi, esi
0x1800d89e9  jmp     short loc_1800D8A0B
0x1800d89eb  lea     r8, [rbp+2900h+psz]; unsigned __int16 *
0x1800d89f2  mov     rdx, r14; unsigned __int64
0x1800d89f5  lea     rcx, [rbp+2900h+pszSpec]; unsigned __int16 *
0x1800d89fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d8a01  mov     edi, eax
0x1800d8a03  test    eax, eax
0x1800d8a05  js      loc_1800D8D83
0x1800d8a0b  lea     rdx, [rbp+2900h+pszSpec]; pszSpec
0x1800d8a12  lea     rcx, [rbp+2900h+pszDir]; pszDir
0x1800d8a19  call    cs:__imp_PathCleanupSpec
0x1800d8a1f  lea     rcx, [rbp+2900h+pszSpec]; pszPath
0x1800d8a26  call    cs:__imp_PathRemoveBlanksW
0x1800d8a2c  cmp     [rbp+2900h+pszSpec], si
0x1800d8a33  jnz     short loc_1800D8A73
0x1800d8a35  xor     r8d, r8d; int
0x1800d8a38  mov     [rsp+2A00h+var_29D8], rsi; __int64
0x1800d8a3d  lea     r9, [rbp+2900h+pszSpec]; int
0x1800d8a44  mov     [rsp+2A00h+cchBuf], r14d; cchBuf
0x1800d8a49  mov     rcx, r15; int
0x1800d8a4c  lea     edx, [r8+1]; int
0x1800d8a50  call    IEGetNameAndFlagsEx
0x1800d8a55  mov     edi, eax
0x1800d8a57  test    eax, eax
0x1800d8a59  js      loc_1800D8D83
0x1800d8a5f  lea     rdx, [rbp+2900h+pszSpec]; pszSpec
0x1800d8a66  lea     rcx, [rbp+2900h+pszDir]; pszDir
0x1800d8a6d  call    cs:__imp_PathCleanupSpec
0x1800d8a73  mov     r14d, ebx
0x1800d8a76  mov     ecx, 1
0x1800d8a7b  and     r14d, ecx
0x1800d8a7e  jz      short loc_1800D8ACB
0x1800d8a80  mov     eax, esi
0x1800d8a82  test    bl, 2
0x1800d8a85  jz      short loc_1800D8A93
0x1800d8a87  mov     al, bl
0x1800d8a89  and     al, 4
0x1800d8a8b  neg     al
0x1800d8a8d  sbb     eax, eax
0x1800d8a8f  neg     eax
0x1800d8a91  add     eax, ecx
0x1800d8a93  mov     rcx, qword ptr [rsp+2A00h+var_2998]; int
0x1800d8a98  lea     r9, [rbp+2900h+pszSpec]; int
0x1800d8a9f  mov     [rsp+2A00h+var_29D0], eax; int
0x1800d8aa3  lea     rdx, [rbp+2900h+pszDir]; int
0x1800d8aaa  mov     [rsp+2A00h+var_29D8], r15; struct _ITEMIDLIST_ABSOLUTE *
0x1800d8aaf  mov     r8d, 104h; int
0x1800d8ab5  mov     [rsp+2A00h+cchBuf], 104h; int
0x1800d8abd  call    DoSafeAddToFavDlgEx
0x1800d8ac2  test    eax, eax
0x1800d8ac4  jnz     short loc_1800D8AD3
0x1800d8ac6  mov     edi, 80004005h
0x1800d8acb  test    edi, edi
0x1800d8acd  js      loc_1800D8D7E
0x1800d8ad3  call    ?IEAddToFavoritesDialogOKPressed@BrowserTelemetry@@SAXXZ; BrowserTelemetry::IEAddToFavoritesDialogOKPressed(void)
0x1800d8ad8  xor     edx, edx; Val
0x1800d8ada  mov     [rbp+2900h+pszPath], si
0x1800d8ade  mov     r8d, 206h; Size
0x1800d8ae4  lea     rcx, [rbp+2900h+var_292E]; void *
0x1800d8ae8  call    memset_0
0x1800d8aed  lea     rcx, [rbp+2900h+pszSpec]; pszPath
0x1800d8af4  call    PathCchRemoveExtension
0x1800d8af9  lea     rcx, [rbp+2900h+pszSpec]; pszPath
0x1800d8b00  mov     [rbp+2900h+var_2940], rsi
0x1800d8b04  mov     [rbp+2900h+var_2980], r15
0x1800d8b08  call    cs:__imp_PathFindFileNameW
0x1800d8b0e  mov     r8, [rsp+2A00h+var_2990]
0x1800d8b13  mov     ecx, 1
0x1800d8b18  mov     [rbp+2900h+var_2978], rax
  ... truncated ...
```
