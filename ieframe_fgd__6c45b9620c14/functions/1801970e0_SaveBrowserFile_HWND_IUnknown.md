# SaveBrowserFile(HWND__ *,IUnknown *)

- ea: `0x1801970e0`
- end: `0x18019783d`
- name: `?SaveBrowserFile@@YAXPEAUHWND__@@PEAUIUnknown@@@Z`
- size: `1885`
- prototype: `void __fastcall(HWND hWnd, struct IUnknown *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801420a8`

## callees

- `0x18000f3d0`
- `0x180011230`
- `0x180073910`
- `0x1800c5d04`
- `0x18017bf18`
- `0x18017d9c0`
- `0x180196efc`
- `0x180196f78`
- `0x1801970e0`
- `0x18019790c`
- `0x180403bf4`
- `0x18040e9a0`
- `0x18041baa4`
- `0x180442e30`
- `0x1804eadb8`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180197217`
- `SHLWAPI!__imp_StrCmpICW` at `0x18019722f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197243`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197257`
- `SHLWAPI!__imp_StrCmpICW` at `0x18019726b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18019727f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197293`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801972a7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801974a1`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197217`
- `SHLWAPI!__imp_StrCmpICW` at `0x18019722f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197243`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197257`
- `SHLWAPI!__imp_StrCmpICW` at `0x18019726b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18019727f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180197293`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801972a7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801974a1`
- `KERNEL32!RemoveDirectoryW` at `0x180197795`
- `KERNEL32!RemoveDirectoryW` at `0x180197795`
- `KERNEL32!CreateDirectoryW` at `0x18019763c`
- `KERNEL32!CreateDirectoryW` at `0x18019763c`
- `KERNEL32!GetLastError` at `0x180197646`
- `KERNEL32!GetLastError` at `0x180197646`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801971d1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x18019745e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180197491`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801971d1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x18019745e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180197491`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801975e1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801975e1`
- `USER32!SetThreadDpiAwarenessContext` at `0x180197383`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801973b2`
- `USER32!SetThreadDpiAwarenessContext` at `0x180197383`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801973b2`
- `USER32!EnableWindow` at `0x18019752f`
- `USER32!EnableWindow` at `0x1801975ba`
- `USER32!EnableWindow` at `0x18019752f`
- `USER32!EnableWindow` at `0x1801975ba`
- `USER32!GetAncestor` at `0x18019751c`
- `USER32!GetAncestor` at `0x18019751c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801977e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801977f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180197804`
- `OLEAUT32!__imp_SysFreeString` at `0x1801977e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801977f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180197804`
- `SHELL32!__imp_PathCleanupSpec` at `0x1801974cb`
- `SHELL32!__imp_PathCleanupSpec` at `0x1801974cb`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801974d1`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801974d1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180197665`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180197665`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18019736b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18019736b`

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
0x1801970e0  mov     [rsp-8+arg_10], rbx
0x1801970e5  push    rbp
0x1801970e6  push    rsi
0x1801970e7  push    rdi
0x1801970e8  push    r12
0x1801970ea  push    r13
0x1801970ec  push    r14
0x1801970ee  push    r15
0x1801970f0  lea     rbp, [rsp-630h]
0x1801970f8  sub     rsp, 730h
0x1801970ff  mov     rax, cs:__security_cookie
0x180197106  xor     rax, rsp
0x180197109  mov     [rbp+660h+var_40], rax
0x180197110  mov     rax, [rdx]
0x180197113  lea     r8, [rsp+760h+var_708]
0x180197118  xor     r12d, r12d
0x18019711b  mov     r9, rdx
0x18019711e  xorps   xmm0, xmm0
0x180197121  mov     [rsp+760h+var_710], r12d
0x180197126  mov     r15, rcx
0x180197129  mov     [rsp+760h+var_708], r12
0x18019712e  mov     rax, [rax]
0x180197131  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x180197138  xorps   xmm1, xmm1
0x18019713b  mov     [rsp+760h+pszPath], r12
0x180197140  mov     rcx, r9
0x180197143  mov     [rbp+660h+bstrString], r12
0x180197147  movups  xmmword ptr [rbp+660h+var_6C8], xmm0
0x18019714b  mov     [rbp+660h+var_6D0], r12
0x18019714f  mov     [rsp+760h+var_6E8], r12
0x180197154  movdqu  [rbp+660h+var_6B0], xmm0
0x180197159  mov     [rbp+660h+var_690], r12d
0x18019715d  movdqu  [rbp+660h+var_6A0], xmm1
0x180197162  mov     [rbp+660h+var_688], r12
0x180197166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019716b  mov     ebx, eax
0x18019716d  test    eax, eax
0x18019716f  js      loc_1801977A6
0x180197175  mov     rcx, [rsp+760h+var_708]
0x18019717a  lea     rdx, [rsp+760h+pszPath]
0x18019717f  mov     rax, [rcx]
0x180197182  mov     rax, [rax+140h]
0x180197189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019718e  test    eax, eax
0x180197190  js      loc_1801977B0
0x180197196  mov     rcx, [rsp+760h+var_708]
0x18019719b  lea     rdx, [rbp+660h+bstrString]
0x18019719f  mov     rax, [rcx]
0x1801971a2  mov     rax, [rax+180h]
0x1801971a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801971ae  mov     ebx, eax
0x1801971b0  test    eax, eax
0x1801971b2  js      loc_1801977A6
0x1801971b8  mov     rax, [rbp+660h+bstrString]
0x1801971bc  mov     rcx, [rsp+760h+pszPath]; pszPath
0x1801971c1  mov     [rbp+660h+var_6C8+8], rax
0x1801971c5  mov     [rbp+660h+var_6C8], r12
0x1801971c9  mov     [rsp+760h+var_710], 3
0x1801971d1  call    cs:__imp_PathFindExtensionW
0x1801971d7  mov     r9, [rsp+760h+var_708]
0x1801971dc  lea     r8, [rsp+760h+var_6E8]
0x1801971e1  mov     rdi, rax
0x1801971e4  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x1801971eb  mov     rcx, [r9]
0x1801971ee  mov     rax, [rcx]
0x1801971f1  mov     rcx, r9
0x1801971f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801971f9  mov     ebx, eax
0x1801971fb  test    eax, eax
0x1801971fd  js      loc_1801977A6
0x180197203  cmp     [rdi], r12w
0x180197207  jz      loc_1801972E3
0x18019720d  lea     rdx, aJpg; ".JPG"
0x180197214  mov     rcx, rdi; pszStr1
0x180197217  call    cs:__imp_StrCmpICW
0x18019721d  test    eax, eax
0x18019721f  jz      loc_1801972B1
0x180197225  lea     rdx, aGif; ".GIF"
0x18019722c  mov     rcx, rdi; pszStr1
0x18019722f  call    cs:__imp_StrCmpICW
0x180197235  test    eax, eax
0x180197237  jz      short loc_1801972B1
0x180197239  lea     rdx, aBmp; ".BMP"
0x180197240  mov     rcx, rdi; pszStr1
0x180197243  call    cs:__imp_StrCmpICW
0x180197249  test    eax, eax
0x18019724b  jz      short loc_1801972B1
0x18019724d  lea     rdx, aArt; ".ART"
0x180197254  mov     rcx, rdi; pszStr1
0x180197257  call    cs:__imp_StrCmpICW
0x18019725d  test    eax, eax
0x18019725f  jz      short loc_1801972B1
0x180197261  lea     rdx, aPng_0; ".PNG"
0x180197268  mov     rcx, rdi; pszStr1
0x18019726b  call    cs:__imp_StrCmpICW
0x180197271  test    eax, eax
0x180197273  jz      short loc_1801972B1
0x180197275  lea     rdx, aWmf; ".WMF"
0x18019727c  mov     rcx, rdi; pszStr1
0x18019727f  call    cs:__imp_StrCmpICW
0x180197285  test    eax, eax
0x180197287  jz      short loc_1801972B1
0x180197289  lea     rdx, aTiff; ".TIFF"
0x180197290  mov     rcx, rdi; pszStr1
0x180197293  call    cs:__imp_StrCmpICW
0x180197299  test    eax, eax
0x18019729b  jz      short loc_1801972B1
0x18019729d  lea     rdx, aJpeg; ".JPEG"
0x1801972a4  mov     rcx, rdi; pszStr1
0x1801972a7  call    cs:__imp_StrCmpICW
0x1801972ad  test    eax, eax
0x1801972af  jnz     short loc_1801972E3
0x1801972b1  mov     rcx, [rsp+760h+var_6E8]
0x1801972b6  lea     rdx, CGID_MSHTML
0x1801972bd  mov     [rsp+760h+pvData], r12
0x1801972c2  xor     r9d, r9d
0x1801972c5  mov     r8d, 8DEh
0x1801972cb  mov     [rsp+760h+pdwType], r12
0x1801972d0  mov     rax, [rcx]
0x1801972d3  mov     rax, [rax+20h]
0x1801972d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801972dc  mov     ebx, eax
0x1801972de  jmp     loc_18019779B
0x1801972e3  mov     rcx, [rsp+760h+var_6E8]
0x1801972e8  lea     r9, [rbp+660h+var_6B8]
0x1801972ec  mov     [rbp+660h+var_6B8], 3Bh ; ';'
0x1801972f3  lea     rdx, CGID_ShellDocView
0x1801972fa  mov     r14d, 1
0x180197300  mov     [rsp+760h+pdwType], r12
0x180197305  mov     r8d, r14d
0x180197308  mov     rax, [rcx]
0x18019730b  mov     rax, [rax+18h]
0x18019730f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197314  mov     ebx, eax
0x180197316  test    eax, eax
0x180197318  js      loc_1801977A6
0x18019731e  lea     esi, [r14+3]
0x180197322  mov     r13b, r12b
0x180197325  test    [rbp+660h+var_6B4], sil
0x180197329  jz      loc_1801973E1
0x18019732f  lea     rax, [rbp+660h+var_6D8]
0x180197333  mov     [rsp+760h+var_700], r12d
0x180197338  mov     [rsp+760h+pcbData], rax; pcbData
0x18019733d  lea     r9d, [r14+0Fh]; srrfFlags
0x180197341  lea     rax, [rsp+760h+var_700]
0x180197346  mov     [rbp+660h+var_6D8], esi
0x180197349  mov     [rsp+760h+pvData], rax; pvData
0x18019734e  lea     r8, aNosaveaspostwa; "NoSaveAsPOSTWarning"
0x180197355  lea     rdx, aSoftwareMicros_45; "SOFTWARE\\Microsoft\\Internet Explorer"...
0x18019735c  mov     [rsp+760h+pdwType], r12; pdwType
0x180197361  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180197368  mov     r13b, r14b
0x18019736b  call    cs:__imp_SHRegGetValueW
0x180197371  test    eax, eax
0x180197373  jnz     short loc_18019737C
0x180197375  cmp     [rsp+760h+var_700], r12d
0x18019737a  jnz     short loc_1801973E1
0x18019737c  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180197383  call    cs:__imp_SetThreadDpiAwarenessContext
0x180197389  mov     rcx, cs:g_hinstMUI; hInstance
0x180197390  lea     r9, ?SaveAsWarningDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180197397  mov     r8, r15; hWndParent
0x18019739a  mov     [rsp+760h+pdwType], r12; LPARAM
0x18019739f  mov     edx, 4400h; lpTemplateName
0x1801973a4  mov     rbx, rax
0x1801973a7  call    SHFusionDialogBoxParam
0x1801973ac  mov     rcx, rbx
0x1801973af  mov     rdi, rax
0x1801973b2  call    cs:__imp_SetThreadDpiAwarenessContext
0x1801973b8  test    r14b, dil
0x1801973bb  jz      loc_1801977B0
0x1801973c1  test    dil, 2
0x1801973c5  jz      short loc_1801973E1
0x1801973c7  xor     r9d, r9d
0x1801973ca  mov     dword ptr [rsp+760h+pv], r14d
0x1801973cf  mov     r8d, esi
0x1801973d2  lea     rdx, [rsp+760h+pv]
0x1801973d7  mov     ecx, 2003h
0x1801973dc  call    ?SetSingleValue@CIERegistryHelper@@SAJKPEAEKW4_CallType@1@@Z; CIERegistryHelper::SetSingleValue(ulong,uchar *,ulong,CIERegistryHelper::_CallType)
0x1801973e1  mov     rcx, [rsp+760h+var_708]
0x1801973e6  lea     rdx, [rbp+660h+var_6D0]
0x1801973ea  mov     [rbp+660h+pszSpec], r12w
0x1801973ef  mov     rax, [rcx]
0x1801973f2  mov     rax, [rax+88h]
0x1801973f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801973fe  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180197402  mov     edi, 104h
0x180197407  test    eax, eax
0x180197409  js      short loc_180197475
0x18019740b  mov     r8, [rbp+660h+var_6D0]; unsigned __int16 *
0x18019740f  test    r8, r8
0x180197412  jz      short loc_180197475
0x180197414  mov     rax, rsi
0x180197417  inc     rax
0x18019741a  cmp     [r8+rax*2], r12w
0x18019741f  jnz     short loc_180197417
0x180197421  test    rax, rax
0x180197424  jz      short loc_180197475
0x180197426  mov     rdx, rdi; unsigned __int64
0x180197429  lea     rcx, [rbp+660h+pszSpec]; unsigned __int16 *
0x18019742d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180197432  mov     ebx, eax
0x180197434  test    eax, eax
0x180197436  js      loc_1801977A6
0x18019743c  mov     r8, [rsp+760h+pszPath]; unsigned __int16 *
0x180197441  lea     rcx, [rbp+660h+var_460]; unsigned __int16 *
0x180197448  call    ?GetFileNameFromURL@@YAJPEAGKPEBG@Z; GetFileNameFromURL(ushort *,ulong,ushort const *)
0x18019744d  mov     ebx, eax
0x18019744f  test    eax, eax
0x180197451  js      loc_1801977A6
0x180197457  lea     rcx, [rbp+660h+var_460]; pszPath
0x18019745e  call    cs:__imp_PathFindExtensionW
0x180197464  mov     rdx, rdi; unsigned __int64
0x180197467  lea     rcx, [rbp+660h+pszSpec]; unsigned __int16 *
0x18019746b  mov     r8, rax; unsigned __int16 *
0x18019746e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180197473  jmp     short loc_180197483
0x180197475  mov     r8, [rsp+760h+pszPath]; unsigned __int16 *
0x18019747a  lea     rcx, [rbp+660h+pszSpec]; unsigned __int16 *
0x18019747e  call    ?GetFileNameFromURL@@YAJPEAGKPEBG@Z; GetFileNameFromURL(ushort *,ulong,ushort const *)
0x180197483  mov     ebx, eax
0x180197485  test    eax, eax
0x180197487  js      loc_1801977A6
0x18019748d  lea     rcx, [rbp+660h+pszSpec]; pszPath
0x180197491  call    cs:__imp_PathFindExtensionW
0x180197497  mov     rcx, rax; pszStr1
0x18019749a  lea     rdx, aSvgz; ".SVGZ"
0x1801974a1  call    cs:__imp_StrCmpICW
0x1801974a7  test    eax, eax
0x1801974a9  jnz     short loc_1801974C5
0x1801974ab  lea     r8, pszExt; ".svg"
0x1801974b2  lea     rcx, [rbp+660h+pszSpec]; pszPath
0x1801974b6  call    PathCchRenameExtension
0x1801974bb  mov     ebx, eax
0x1801974bd  test    eax, eax
0x1801974bf  js      loc_1801977A6
0x1801974c5  lea     rdx, [rbp+660h+pszSpec]; pszSpec
0x1801974c9  xor     ecx, ecx; pszDir
0x1801974cb  call    cs:__imp_PathCleanupSpec
0x1801974d1  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1801974d7  mov     r14d, eax
0x1801974da  test    eax, eax
0x1801974dc  jnz     loc_18019766D
0x1801974e2  lea     rcx, [rbp+660h+var_6B0]
0x1801974e6  mov     [rsp+760h+pv], r12
0x1801974eb  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1801974f0  mov     ebx, eax
0x1801974f2  cmp     eax, 800401F1h
0x1801974f7  jz      short loc_180197501
0x1801974f9  test    eax, eax
0x1801974fb  jnz     loc_18019765B
0x180197501  mov     rcx, [rsp+760h+var_708]; struct IHTMLDocument2 *
0x180197506  call    ?IsXmlDocument@@YA_NPEAUIHTMLDocument2@@@Z; IsXmlDocument(IHTMLDocument2 *)
0x18019750b  xor     edi, edi
0x18019750d  movzx   r12d, al
0x180197511  test    r15, r15
0x180197514  jz      short loc_180197535
0x180197516  lea     edx, [rdi+2]; gaFlags
0x180197519  mov     rcx, r15; hwnd
0x18019751c  call    cs:__imp_GetAncestor
0x180197522  mov     rdi, rax
0x180197525  test    rax, rax
0x180197528  jz      short loc_180197535
0x18019752a  xor     edx, edx; bEnable
0x18019752c  mov     rcx, rax; hWnd
0x18019752f  call    cs:__imp_EnableWindow
0x180197535  test    ebx, ebx
0x180197537  js      short loc_1801975AA
0x180197539  mov     r10, qword ptr [rbp+660h+var_6A0+8]
0x18019753d  mov     rdx, r15
0x180197540  mov     r9, [rbp+660h+bstrString]
0x180197544  movzx   r8d, r13b
0x180197548  mov     dword ptr [rsp+760h+pvData], r12d
0x18019754d  mov     rcx, [r10]
0x180197550  mov     dword ptr [rsp+760h+pdwType], r8d
0x180197555  lea     r8, [rbp+660h+pszSpec]
0x180197559  mov     rax, [rcx+198h]
0x180197560  mov     rcx, r10
0x180197563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197568  xor     r12d, r12d
0x18019756b  mov     ebx, eax
0x18019756d  test    eax, eax
0x18019756f  js      short loc_1801975AD
0x180197571  xor     r8d, r8d
0x180197574  lea     rcx, [rbp+660h+var_6B0]
0x180197578  xor     edx, edx
0x18019757a  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x18019757f  mov     ebx, eax
0x180197581  test    eax, eax
0x180197583  js      short loc_1801975AD
0x180197585  mov     rcx, qword ptr [rbp+660h+var_6A0+8]
0x180197589  lea     r9, [rsp+760h+var_710]
0x18019758e  lea     r8, [rbp+660h+var_6C8+4]
0x180197592  lea     rdx, [rsp+760h+pv]
0x180197597  mov     rax, [rcx]
0x18019759a  mov     rax, [rax+1A0h]
0x1801975a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801975a6  mov     ebx, eax
0x1801975a8  jmp     short loc_1801975AD
0x1801975aa  xor     r12d, r12d
  ... truncated ...
```
