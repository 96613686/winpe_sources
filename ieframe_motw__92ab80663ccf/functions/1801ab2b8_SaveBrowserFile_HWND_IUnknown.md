# SaveBrowserFile(HWND__ *,IUnknown *)

- ea: `0x1801ab2b8`
- end: `0x1801abac6`
- name: `?SaveBrowserFile@@YAXPEAUHWND__@@PEAUIUnknown@@@Z`
- size: `2062`
- prototype: `void __fastcall(HWND hWnd, struct IUnknown *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18015136c`

## callees

- `0x1800123f0`
- `0x1800144d0`
- `0x180078b9c`
- `0x1800cd150`
- `0x18018e168`
- `0x18018fef8`
- `0x1801ab0c0`
- `0x1801ab144`
- `0x1801ab2b8`
- `0x1801abbb0`
- `0x18043b170`
- `0x180446bf0`
- `0x1804549e4`
- `0x18047da7c`
- `0x180529a08`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab3f5`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab413`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab431`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab44f`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab469`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab483`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab49d`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab4b7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab6d5`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab3f5`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab413`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab431`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab44f`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab469`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab483`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab49d`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab4b7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ab6d5`
- `KERNEL32!RemoveDirectoryW` at `0x1801aba05`
- `KERNEL32!RemoveDirectoryW` at `0x1801aba05`
- `KERNEL32!CreateDirectoryW` at `0x1801ab89a`
- `KERNEL32!CreateDirectoryW` at `0x1801ab89a`
- `KERNEL32!GetLastError` at `0x1801ab8aa`
- `KERNEL32!GetLastError` at `0x1801ab8aa`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801ab3a9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801ab686`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801ab6bf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801ab3a9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801ab686`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801ab6bf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801ab839`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801ab839`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ab59f`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ab5d4`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ab59f`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801ab5d4`
- `USER32!EnableWindow` at `0x1801ab77b`
- `USER32!EnableWindow` at `0x1801ab80c`
- `USER32!EnableWindow` at `0x1801ab77b`
- `USER32!EnableWindow` at `0x1801ab80c`
- `USER32!GetAncestor` at `0x1801ab762`
- `USER32!GetAncestor` at `0x1801ab762`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aba5c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aba71`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aba86`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aba5c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aba71`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aba86`
- `SHELL32!__imp_PathCleanupSpec` at `0x1801ab705`
- `SHELL32!__imp_PathCleanupSpec` at `0x1801ab705`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801ab711`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801ab711`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801ab8cf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801ab8cf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1801ab581`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x1801ab581`

## pseudocode

```c
void __fastcall SaveBrowserFile(HWND hWnd, struct IUnknown *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  int FileNameFromURL; // ebx
  LPWSTR ExtensionW; // rdi
  bool v7; // r13
  __int64 v8; // rbx
  char v9; // di
  unsigned int v10; // edx
  __int64 v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // edx
  const unsigned __int16 *v14; // rax
  int v15; // eax
  const WCHAR *v16; // rax
  size_t v17; // rdx
  int v18; // r14d
  int v19; // eax
  HWND v20; // rdi
  BOOL v21; // r12d
  HWND Ancestor; // rax
  const unsigned __int16 *FileNameW; // rax
  __int64 v24; // rax
  signed int LastError; // eax
  bool v26; // al
  HINSTANCE v27; // rdx
  bool v28; // sf
  __int64 (*v29)(void); // rax
  int v30; // [rsp+50h] [rbp-B0h] BYREF
  struct IHTMLDocument2 *v31; // [rsp+58h] [rbp-A8h] BYREF
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR pszPath; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp-78h] BYREF
  BSTR v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39[2]; // [rsp+98h] [rbp-68h] BYREF
  int v40; // [rsp+A8h] [rbp-58h] BYREF
  char v41; // [rsp+ACh] [rbp-54h]
  __int128 v42; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  WCHAR pszSpec[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v47[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR PathName[264]; // [rsp+510h] [rbp+410h] BYREF

  lpVtbl = a2->lpVtbl;
  v30 = 0;
  v31 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  pszPath = 0;
  bstrString = 0;
  *(_OWORD *)v39 = 0;
  v38 = 0;
  v35 = 0;
  v42 = 0;
  v44 = 0;
  v43 = 0;
  v45 = 0;
  FileNameFromURL = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IHTMLDocument2 **))QueryInterface)(
                      a2,
                      &GUID_332c4425_26cb_11d0_b483_00c04fd90119,
                      &v31);
  if ( FileNameFromURL >= 0 )
  {
    if ( ((int (__fastcall *)(struct IHTMLDocument2 *, LPCWSTR *))v31->lpVtbl->get_URL)(v31, &pszPath) < 0 )
      goto LABEL_77;
    FileNameFromURL = ((__int64 (__fastcall *)(struct IHTMLDocument2 *, BSTR *))v31->lpVtbl->get_charset)(
                        v31,
                        &bstrString);
    if ( FileNameFromURL >= 0 )
    {
      v39[1] = (__int64)bstrString;
      v39[0] = 0;
      v30 = 3;
      ExtensionW = PathFindExtensionW(pszPath);
      FileNameFromURL = ((__int64 (__fastcall *)(struct IHTMLDocument2 *, GUID *, __int64 *))v31->lpVtbl->QueryInterface)(
                          v31,
                          &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
                          &v35);
      if ( FileNameFromURL >= 0 )
      {
        if ( *ExtensionW
          && (!StrCmpICW(ExtensionW, L".JPG")
           || !StrCmpICW(ExtensionW, L".GIF")
           || !StrCmpICW(ExtensionW, L".BMP")
           || !StrCmpICW(ExtensionW, L".ART")
           || !StrCmpICW(ExtensionW, L".PNG")
           || !StrCmpICW(ExtensionW, L".WMF")
           || !StrCmpICW(ExtensionW, L".TIFF")
           || !StrCmpICW(ExtensionW, L".JPEG")) )
        {
          FileNameFromURL = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v35 + 32LL))(
                              v35,
                              &CGID_MSHTML,
                              2270,
                              0,
                              0,
                              0);
          goto LABEL_72;
        }
        v40 = 59;
        FileNameFromURL = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, int *, _QWORD))(*(_QWORD *)v35 + 24LL))(
                            v35,
                            &CGID_ShellDocView,
                            1,
                            &v40,
                            0);
        if ( FileNameFromURL >= 0 )
        {
          v7 = 0;
          if ( (v41 & 4) != 0 )
          {
            pvData = 0;
            pcbData = 4;
            v7 = 1;
            if ( SHRegGetValueW(
                   HKEY_CURRENT_USER,
                   L"SOFTWARE\\Microsoft\\Internet Explorer\\Main",
                   L"NoSaveAsPOSTWarning",
                   16,
                   0,
                   &pvData,
                   &pcbData)
              || !pvData )
            {
              v8 = SetThreadDpiAwarenessContext(-2);
              v9 = SHFusionDialogBoxParam(g_hinstMUI, (LPCWSTR)0x4400, hWnd, (DLGPROC)SaveAsWarningDlgProc, 0);
              SetThreadDpiAwarenessContext(v8);
              if ( (v9 & 1) == 0 )
                goto LABEL_77;
              if ( (v9 & 2) != 0 )
              {
                LODWORD(pv) = 1;
                CIERegistryHelper::SetSingleValue(8195, &pv, 4, 0);
              }
            }
          }
          pszSpec[0] = 0;
          v11 = -1;
          if ( ((int (__fastcall *)(struct IHTMLDocument2 *, BSTR *))v31->lpVtbl->get_title)(v31, &v38) < 0 )
            goto LABEL_30;
          if ( !v38 )
            goto LABEL_30;
          v12 = -1;
          do
            ++v12;
          while ( v38[v12] );
          if ( v12 )
          {
            FileNameFromURL = StringCchCopyW(pszSpec, 0x104u, v38);
            if ( FileNameFromURL < 0 )
              goto LABEL_76;
            FileNameFromURL = GetFileNameFromURL(v47, v13, pszPath);
            if ( FileNameFromURL < 0 )
              goto LABEL_76;
            v14 = PathFindExtensionW(v47);
            v15 = StringCchCatW(pszSpec, 0x104u, v14);
          }
          else
          {
LABEL_30:
            v15 = GetFileNameFromURL(pszSpec, v10, pszPath);
          }
          FileNameFromURL = v15;
          if ( v15 >= 0 )
          {
            v16 = PathFindExtensionW(pszSpec);
            if ( StrCmpICW(v16, L".SVGZ")
              || (FileNameFromURL = PathCchRenameExtension(pszSpec, v17, L".svg"), FileNameFromURL >= 0) )
            {
              PathCleanupSpec(0, pszSpec);
              v18 = IsProtectedModeProcess();
              if ( !v18 )
              {
                pv = 0;
                v19 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v42);
                FileNameFromURL = v19;
                if ( v19 == -2147221007 || !v19 )
                {
                  v20 = 0;
                  v21 = IsXmlDocument(v31);
                  if ( hWnd )
                  {
                    Ancestor = GetAncestor(hWnd, 2u);
                    v20 = Ancestor;
                    if ( Ancestor )
                      EnableWindow(Ancestor, 0);
                  }
                  if ( FileNameFromURL >= 0 )
                  {
                    FileNameFromURL = (*(__int64 (__fastcall **)(_QWORD, HWND, WCHAR *, BSTR, bool, BOOL))(**((_QWORD **)&v43 + 1) + 408LL))(
                                        *((_QWORD *)&v43 + 1),
                                        hWnd,
                                        pszSpec,
                                        bstrString,
                                        v7,
                                        v21);
                    if ( FileNameFromURL >= 0 )
                    {
                      FileNameFromURL = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                                          &v42,
                                          0,
                                          0);
                      if ( FileNameFromURL >= 0 )
                        FileNameFromURL = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, char *, int *))(**((_QWORD **)&v43 + 1) + 416LL))(
                                            *((_QWORD *)&v43 + 1),
                                            &pv,
                                            (char *)v39 + 4,
                                            &v30);
                    }
                  }
                  if ( v20 )
                    EnableWindow(v20, 1);
                  if ( !FileNameFromURL )
                  {
                    StringCchCopyW(pszSpec, 0x104u, (const unsigned __int16 *)pv);
                    FileNameW = PathFindFileNameW(pszSpec);
                    StringCchCopyW(v47, 0x104u, FileNameW);
                    v24 = -1;
                    do
                      ++v24;
                    while ( v47[v24] );
                    do
                      ++v11;
                    while ( pszSpec[v11] );
                    StringCchCopyNW(PathName, 0x104u, pszSpec, v11 - v24);
                    if ( !CreateDirectoryW(PathName, 0) )
                    {
                      LastError = GetLastError();
                      FileNameFromURL = LastError;
                      if ( LastError > 0 )
                        FileNameFromURL = (unsigned __int16)LastError | 0x80070000;
                    }
                  }
                }
                if ( pv )
                  CoTaskMemFree(pv);
LABEL_57:
                v28 = FileNameFromURL < 0;
                if ( FileNameFromURL )
                  goto LABEL_73;
                FileNameFromURL = SaveToThicket(hWnd, pszSpec, v31, LODWORD(v39[0]), HIDWORD(v39[0]), v30);
                if ( FileNameFromURL )
                {
LABEL_72:
                  v28 = FileNameFromURL < 0;
LABEL_73:
                  if ( !v28 )
                    goto LABEL_77;
                  goto LABEL_76;
                }
                if ( v18 )
                  goto LABEL_77;
                if ( v30 == 1 )
                {
                  FileNameFromURL = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v43 + 1) + 424LL))(*((_QWORD *)&v43 + 1));
                  if ( FileNameFromURL < 0 )
                    goto LABEL_71;
                  FileNameFromURL = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                                      &v42,
                                      0,
                                      0);
                  if ( FileNameFromURL < 0 )
                    goto LABEL_71;
                  v29 = *(__int64 (**)(void))(**((_QWORD **)&v43 + 1) + 432LL);
                }
                else
                {
                  if ( v30 != 2 && v30 != 3 && (unsigned int)(v30 - 4) > 1 )
                    goto LABEL_71;
                  FileNameFromURL = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v43 + 1) + 440LL))(*((_QWORD *)&v43 + 1));
                  if ( FileNameFromURL < 0 )
                    goto LABEL_71;
                  FileNameFromURL = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                                      &v42,
                                      0,
                                      0);
                  if ( FileNameFromURL < 0 )
                    goto LABEL_71;
                  v29 = *(__int64 (**)(void))(**((_QWORD **)&v43 + 1) + 448LL);
                }
                FileNameFromURL = v29();
LABEL_71:
                RemoveDirectoryW(PathName);
                goto LABEL_72;
              }
              if ( v18 == 1 )
              {
                v26 = IsXmlDocument(v31);
                FileNameFromURL = GetFileNameForSaving(
                                    hWnd,
                                    v27,
                                    pszSpec,
                                    260,
                                    (__int64)v39,
                                    (enum PACKAGE_TYPE *)&v30,
                                    v7,
                                    v26,
                                    0);
                goto LABEL_57;
              }
              FileNameFromURL = -2147467259;
            }
          }
        }
      }
    }
  }
LABEL_76:
  ReportThicketError(hWnd, FileNameFromURL);
LABEL_77:
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v31 )
    ((void (__fastcall *)(struct IHTMLDocument2 *))v31->lpVtbl->Release)(v31);
  if ( pszPath )
    SysFreeString((BSTR)pszPath);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v38 )
    SysFreeString(v38);
  CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(&v42);
}

```

## disassembly

```asm
0x1801ab2b8  mov     [rsp-8+arg_10], rbx
0x1801ab2bd  push    rbp
0x1801ab2be  push    rsi
0x1801ab2bf  push    rdi
0x1801ab2c0  push    r12
0x1801ab2c2  push    r13
0x1801ab2c4  push    r14
0x1801ab2c6  push    r15
0x1801ab2c8  lea     rbp, [rsp-630h]
0x1801ab2d0  sub     rsp, 730h
0x1801ab2d7  mov     rax, cs:__security_cookie
0x1801ab2de  xor     rax, rsp
0x1801ab2e1  mov     [rbp+660h+var_40], rax
0x1801ab2e8  mov     rax, [rdx]
0x1801ab2eb  lea     r8, [rsp+760h+var_708]
0x1801ab2f0  xor     r12d, r12d
0x1801ab2f3  mov     r9, rdx
0x1801ab2f6  xorps   xmm0, xmm0
0x1801ab2f9  mov     [rsp+760h+var_710], r12d
0x1801ab2fe  mov     r15, rcx
0x1801ab301  mov     [rsp+760h+var_708], r12
0x1801ab306  mov     rax, [rax]
0x1801ab309  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1801ab310  xorps   xmm1, xmm1
0x1801ab313  mov     [rsp+760h+pszPath], r12
0x1801ab318  mov     rcx, r9
0x1801ab31b  mov     [rbp+660h+bstrString], r12
0x1801ab31f  movups  xmmword ptr [rbp+660h+var_6C8], xmm0
0x1801ab323  mov     [rbp+660h+var_6D0], r12
0x1801ab327  mov     [rsp+760h+var_6E8], r12
0x1801ab32c  movdqu  [rbp+660h+var_6B0], xmm0
0x1801ab331  mov     [rbp+660h+var_690], r12d
0x1801ab335  movdqu  [rbp+660h+var_6A0], xmm1
0x1801ab33a  mov     [rbp+660h+var_688], r12
0x1801ab33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab343  mov     ebx, eax
0x1801ab345  test    eax, eax
0x1801ab347  js      loc_1801ABA1C
0x1801ab34d  mov     rcx, [rsp+760h+var_708]
0x1801ab352  lea     rdx, [rsp+760h+pszPath]
0x1801ab357  mov     rax, [rcx]
0x1801ab35a  mov     rax, [rax+140h]
0x1801ab361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab366  test    eax, eax
0x1801ab368  js      loc_1801ABA26
0x1801ab36e  mov     rcx, [rsp+760h+var_708]
0x1801ab373  lea     rdx, [rbp+660h+bstrString]
0x1801ab377  mov     rax, [rcx]
0x1801ab37a  mov     rax, [rax+180h]
0x1801ab381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab386  mov     ebx, eax
0x1801ab388  test    eax, eax
0x1801ab38a  js      loc_1801ABA1C
0x1801ab390  mov     rax, [rbp+660h+bstrString]
0x1801ab394  mov     rcx, [rsp+760h+pszPath]; pszPath
0x1801ab399  mov     [rbp+660h+var_6C8+8], rax
0x1801ab39d  mov     [rbp+660h+var_6C8], r12
0x1801ab3a1  mov     [rsp+760h+var_710], 3
0x1801ab3a9  call    cs:__imp_PathFindExtensionW
0x1801ab3b0  nop     dword ptr [rax+rax+00h]
0x1801ab3b5  mov     r9, [rsp+760h+var_708]
0x1801ab3ba  lea     r8, [rsp+760h+var_6E8]
0x1801ab3bf  mov     rdi, rax
0x1801ab3c2  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x1801ab3c9  mov     rcx, [r9]
0x1801ab3cc  mov     rax, [rcx]
0x1801ab3cf  mov     rcx, r9
0x1801ab3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab3d7  mov     ebx, eax
0x1801ab3d9  test    eax, eax
0x1801ab3db  js      loc_1801ABA1C
0x1801ab3e1  cmp     [rdi], r12w
0x1801ab3e5  jz      loc_1801AB4F9
0x1801ab3eb  lea     rdx, aJpg; ".JPG"
0x1801ab3f2  mov     rcx, rdi; pszStr1
0x1801ab3f5  call    cs:__imp_StrCmpICW
0x1801ab3fc  nop     dword ptr [rax+rax+00h]
0x1801ab401  test    eax, eax
0x1801ab403  jz      loc_1801AB4C7
0x1801ab409  lea     rdx, aGif; ".GIF"
0x1801ab410  mov     rcx, rdi; pszStr1
0x1801ab413  call    cs:__imp_StrCmpICW
0x1801ab41a  nop     dword ptr [rax+rax+00h]
0x1801ab41f  test    eax, eax
0x1801ab421  jz      loc_1801AB4C7
0x1801ab427  lea     rdx, aBmp; ".BMP"
0x1801ab42e  mov     rcx, rdi; pszStr1
0x1801ab431  call    cs:__imp_StrCmpICW
0x1801ab438  nop     dword ptr [rax+rax+00h]
0x1801ab43d  test    eax, eax
0x1801ab43f  jz      loc_1801AB4C7
0x1801ab445  lea     rdx, aArt; ".ART"
0x1801ab44c  mov     rcx, rdi; pszStr1
0x1801ab44f  call    cs:__imp_StrCmpICW
0x1801ab456  nop     dword ptr [rax+rax+00h]
0x1801ab45b  test    eax, eax
0x1801ab45d  jz      short loc_1801AB4C7
0x1801ab45f  lea     rdx, aPng_0; ".PNG"
0x1801ab466  mov     rcx, rdi; pszStr1
0x1801ab469  call    cs:__imp_StrCmpICW
0x1801ab470  nop     dword ptr [rax+rax+00h]
0x1801ab475  test    eax, eax
0x1801ab477  jz      short loc_1801AB4C7
0x1801ab479  lea     rdx, aWmf; ".WMF"
0x1801ab480  mov     rcx, rdi; pszStr1
0x1801ab483  call    cs:__imp_StrCmpICW
0x1801ab48a  nop     dword ptr [rax+rax+00h]
0x1801ab48f  test    eax, eax
0x1801ab491  jz      short loc_1801AB4C7
0x1801ab493  lea     rdx, aTiff; ".TIFF"
0x1801ab49a  mov     rcx, rdi; pszStr1
0x1801ab49d  call    cs:__imp_StrCmpICW
0x1801ab4a4  nop     dword ptr [rax+rax+00h]
0x1801ab4a9  test    eax, eax
0x1801ab4ab  jz      short loc_1801AB4C7
0x1801ab4ad  lea     rdx, aJpeg; ".JPEG"
0x1801ab4b4  mov     rcx, rdi; pszStr1
0x1801ab4b7  call    cs:__imp_StrCmpICW
0x1801ab4be  nop     dword ptr [rax+rax+00h]
0x1801ab4c3  test    eax, eax
0x1801ab4c5  jnz     short loc_1801AB4F9
0x1801ab4c7  mov     rcx, [rsp+760h+var_6E8]
0x1801ab4cc  lea     rdx, CGID_MSHTML
0x1801ab4d3  mov     [rsp+760h+pvData], r12
0x1801ab4d8  xor     r9d, r9d
0x1801ab4db  mov     r8d, 8DEh
0x1801ab4e1  mov     [rsp+760h+pdwType], r12
0x1801ab4e6  mov     rax, [rcx]
0x1801ab4e9  mov     rax, [rax+20h]
0x1801ab4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab4f2  mov     ebx, eax
0x1801ab4f4  jmp     loc_1801ABA11
0x1801ab4f9  mov     rcx, [rsp+760h+var_6E8]
0x1801ab4fe  lea     r9, [rbp+660h+var_6B8]
0x1801ab502  mov     [rbp+660h+var_6B8], 3Bh ; ';'
0x1801ab509  lea     rdx, CGID_ShellDocView
0x1801ab510  mov     r14d, 1
0x1801ab516  mov     [rsp+760h+pdwType], r12
0x1801ab51b  mov     r8d, r14d
0x1801ab51e  mov     rax, [rcx]
0x1801ab521  mov     rax, [rax+18h]
0x1801ab525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab52a  mov     ebx, eax
0x1801ab52c  test    eax, eax
0x1801ab52e  js      loc_1801ABA1C
0x1801ab534  lea     esi, [r14+3]
0x1801ab538  mov     r13b, r12b
0x1801ab53b  test    [rbp+660h+var_6B4], sil
0x1801ab53f  jz      loc_1801AB609
0x1801ab545  lea     rax, [rbp+660h+var_6D8]
0x1801ab549  mov     [rsp+760h+var_700], r12d
0x1801ab54e  mov     [rsp+760h+pcbData], rax; pcbData
0x1801ab553  lea     r9d, [r14+0Fh]; srrfFlags
0x1801ab557  lea     rax, [rsp+760h+var_700]
0x1801ab55c  mov     [rbp+660h+var_6D8], esi
0x1801ab55f  mov     [rsp+760h+pvData], rax; pvData
0x1801ab564  lea     r8, aNosaveaspostwa; "NoSaveAsPOSTWarning"
0x1801ab56b  lea     rdx, aSoftwareMicros_45; "SOFTWARE\\Microsoft\\Internet Explorer"...
0x1801ab572  mov     [rsp+760h+pdwType], r12; pdwType
0x1801ab577  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1801ab57e  mov     r13b, r14b
0x1801ab581  call    cs:__imp_SHRegGetValueW
0x1801ab588  nop     dword ptr [rax+rax+00h]
0x1801ab58d  test    eax, eax
0x1801ab58f  jnz     short loc_1801AB598
0x1801ab591  cmp     [rsp+760h+var_700], r12d
0x1801ab596  jnz     short loc_1801AB609
0x1801ab598  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1801ab59f  call    cs:__imp_SetThreadDpiAwarenessContext
0x1801ab5a6  nop     dword ptr [rax+rax+00h]
0x1801ab5ab  mov     rcx, cs:g_hinstMUI; hInstance
0x1801ab5b2  lea     r9, ?SaveAsWarningDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1801ab5b9  mov     r8, r15; hWndParent
0x1801ab5bc  mov     [rsp+760h+pdwType], r12; LPARAM
0x1801ab5c1  mov     edx, 4400h; lpTemplateName
0x1801ab5c6  mov     rbx, rax
0x1801ab5c9  call    SHFusionDialogBoxParam
0x1801ab5ce  mov     rcx, rbx
0x1801ab5d1  mov     rdi, rax
0x1801ab5d4  call    cs:__imp_SetThreadDpiAwarenessContext
0x1801ab5db  nop     dword ptr [rax+rax+00h]
0x1801ab5e0  test    r14b, dil
0x1801ab5e3  jz      loc_1801ABA26
0x1801ab5e9  test    dil, 2
0x1801ab5ed  jz      short loc_1801AB609
0x1801ab5ef  xor     r9d, r9d
0x1801ab5f2  mov     dword ptr [rsp+760h+pv], r14d
0x1801ab5f7  mov     r8d, esi
0x1801ab5fa  lea     rdx, [rsp+760h+pv]
0x1801ab5ff  mov     ecx, 2003h
0x1801ab604  call    ?SetSingleValue@CIERegistryHelper@@SAJKPEAEKW4_CallType@1@@Z; CIERegistryHelper::SetSingleValue(ulong,uchar *,ulong,CIERegistryHelper::_CallType)
0x1801ab609  mov     rcx, [rsp+760h+var_708]
0x1801ab60e  lea     rdx, [rbp+660h+var_6D0]
0x1801ab612  mov     [rbp+660h+pszSpec], r12w
0x1801ab617  mov     rax, [rcx]
0x1801ab61a  mov     rax, [rax+88h]
0x1801ab621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab626  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801ab62a  mov     edi, 104h
0x1801ab62f  test    eax, eax
0x1801ab631  js      short loc_1801AB6A3
0x1801ab633  mov     r8, [rbp+660h+var_6D0]; unsigned __int16 *
0x1801ab637  test    r8, r8
0x1801ab63a  jz      short loc_1801AB6A3
0x1801ab63c  mov     rax, rsi
0x1801ab63f  inc     rax
0x1801ab642  cmp     [r8+rax*2], r12w
0x1801ab647  jnz     short loc_1801AB63F
0x1801ab649  test    rax, rax
0x1801ab64c  jz      short loc_1801AB6A3
0x1801ab64e  mov     rdx, rdi; unsigned __int64
0x1801ab651  lea     rcx, [rbp+660h+pszSpec]; unsigned __int16 *
0x1801ab655  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801ab65a  mov     ebx, eax
0x1801ab65c  test    eax, eax
0x1801ab65e  js      loc_1801ABA1C
0x1801ab664  mov     r8, [rsp+760h+pszPath]; unsigned __int16 *
0x1801ab669  lea     rcx, [rbp+660h+var_460]; unsigned __int16 *
0x1801ab670  call    ?GetFileNameFromURL@@YAJPEAGKPEBG@Z; GetFileNameFromURL(ushort *,ulong,ushort const *)
0x1801ab675  mov     ebx, eax
0x1801ab677  test    eax, eax
0x1801ab679  js      loc_1801ABA1C
0x1801ab67f  lea     rcx, [rbp+660h+var_460]; pszPath
0x1801ab686  call    cs:__imp_PathFindExtensionW
0x1801ab68d  nop     dword ptr [rax+rax+00h]
0x1801ab692  mov     rdx, rdi; unsigned __int64
0x1801ab695  lea     rcx, [rbp+660h+pszSpec]; unsigned __int16 *
0x1801ab699  mov     r8, rax; unsigned __int16 *
0x1801ab69c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801ab6a1  jmp     short loc_1801AB6B1
0x1801ab6a3  mov     r8, [rsp+760h+pszPath]; unsigned __int16 *
0x1801ab6a8  lea     rcx, [rbp+660h+pszSpec]; unsigned __int16 *
0x1801ab6ac  call    ?GetFileNameFromURL@@YAJPEAGKPEBG@Z; GetFileNameFromURL(ushort *,ulong,ushort const *)
0x1801ab6b1  mov     ebx, eax
0x1801ab6b3  test    eax, eax
0x1801ab6b5  js      loc_1801ABA1C
0x1801ab6bb  lea     rcx, [rbp+660h+pszSpec]; pszPath
0x1801ab6bf  call    cs:__imp_PathFindExtensionW
0x1801ab6c6  nop     dword ptr [rax+rax+00h]
0x1801ab6cb  mov     rcx, rax; pszStr1
0x1801ab6ce  lea     rdx, aSvgz; ".SVGZ"
0x1801ab6d5  call    cs:__imp_StrCmpICW
0x1801ab6dc  nop     dword ptr [rax+rax+00h]
0x1801ab6e1  test    eax, eax
0x1801ab6e3  jnz     short loc_1801AB6FF
0x1801ab6e5  lea     r8, pszExt; ".svg"
0x1801ab6ec  lea     rcx, [rbp+660h+pszSpec]; pszPath
0x1801ab6f0  call    PathCchRenameExtension
0x1801ab6f5  mov     ebx, eax
0x1801ab6f7  test    eax, eax
0x1801ab6f9  js      loc_1801ABA1C
0x1801ab6ff  lea     rdx, [rbp+660h+pszSpec]; pszSpec
0x1801ab703  xor     ecx, ecx; pszDir
0x1801ab705  call    cs:__imp_PathCleanupSpec
0x1801ab70c  nop     dword ptr [rax+rax+00h]
0x1801ab711  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1801ab718  nop     dword ptr [rax+rax+00h]
0x1801ab71d  mov     r14d, eax
0x1801ab720  test    eax, eax
0x1801ab722  jnz     loc_1801AB8DD
0x1801ab728  lea     rcx, [rbp+660h+var_6B0]
0x1801ab72c  mov     [rsp+760h+pv], r12
0x1801ab731  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1801ab736  mov     ebx, eax
0x1801ab738  cmp     eax, 800401F1h
0x1801ab73d  jz      short loc_1801AB747
0x1801ab73f  test    eax, eax
0x1801ab741  jnz     loc_1801AB8C5
0x1801ab747  mov     rcx, [rsp+760h+var_708]; struct IHTMLDocument2 *
0x1801ab74c  call    ?IsXmlDocument@@YA_NPEAUIHTMLDocument2@@@Z; IsXmlDocument(IHTMLDocument2 *)
0x1801ab751  xor     edi, edi
0x1801ab753  movzx   r12d, al
0x1801ab757  test    r15, r15
0x1801ab75a  jz      short loc_1801AB787
0x1801ab75c  lea     edx, [rdi+2]; gaFlags
0x1801ab75f  mov     rcx, r15; hwnd
0x1801ab762  call    cs:__imp_GetAncestor
0x1801ab769  nop     dword ptr [rax+rax+00h]
0x1801ab76e  mov     rdi, rax
0x1801ab771  test    rax, rax
0x1801ab774  jz      short loc_1801AB787
0x1801ab776  xor     edx, edx; bEnable
0x1801ab778  mov     rcx, rax; hWnd
0x1801ab77b  call    cs:__imp_EnableWindow
0x1801ab782  nop     dword ptr [rax+rax+00h]
0x1801ab787  test    ebx, ebx
0x1801ab789  js      short loc_1801AB7FC
0x1801ab78b  mov     r10, qword ptr [rbp+660h+var_6A0+8]
0x1801ab78f  mov     rdx, r15
0x1801ab792  mov     r9, [rbp+660h+bstrString]
0x1801ab796  movzx   r8d, r13b
0x1801ab79a  mov     dword ptr [rsp+760h+pvData], r12d
0x1801ab79f  mov     rcx, [r10]
0x1801ab7a2  mov     dword ptr [rsp+760h+pdwType], r8d
0x1801ab7a7  lea     r8, [rbp+660h+pszSpec]
0x1801ab7ab  mov     rax, [rcx+198h]
0x1801ab7b2  mov     rcx, r10
0x1801ab7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab7ba  xor     r12d, r12d
0x1801ab7bd  mov     ebx, eax
  ... truncated ...
```
