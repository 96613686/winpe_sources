# WebRuntimeDiagnostics::GetHtmlDocumentFromHwnd(HWND__ * const,IDispatch * *)

- ea: `0x180012ed4`
- end: `0x1800131bd`
- name: `?GetHtmlDocumentFromHwnd@WebRuntimeDiagnostics@@YAXQEAUHWND__@@PEAPEAUIDispatch@@@Z`
- size: `745`
- prototype: `void __fastcall(HWND hWnd, HWND, struct IDispatch **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800131c4`
- `0x180013540`

## callees

- `0x18000b0ec`
- `0x180012ed4`
- `0x180018b30`
- `0x180023964`
- `0x18002bbd0`
- `0x18002bc38`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x180012f29`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x180012f29`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageTimeoutW` at `0x180012f71`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageTimeoutW` at `0x180012f71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fa9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fd6`

## string_xrefs

- `0x180012fa2`: `oleacc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall WebRuntimeDiagnostics::GetHtmlDocumentFromHwnd(HWND hWnd, _QWORD *a2, struct IDispatch **a3)
{
  LRESULT v5; // rax
  HMODULE Library; // rax
  const char *v7; // r9
  FARPROC ProcAddress; // rbx
  const char *v9; // r9
  int v10; // eax
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, SID *, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, GUID *, GUID *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v21; // eax
  int (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rcx
  UINT fuFlags; // [rsp+20h] [rbp-40h]
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  ULONG_PTR dwResult; // [rsp+48h] [rbp-18h] BYREF
  HMODULE v26[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+28h] BYREF
  __int64 v29; // [rsp+90h] [rbp+30h] BYREF
  __int64 v30; // [rsp+98h] [rbp+38h] BYREF

  if ( dword_1800B7170 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800B7170);
    if ( dword_1800B7170 == -1 )
    {
      Msg = RegisterWindowMessageW(L"WM_HTML_GETOBJECT");
      Init_thread_footer(&dword_1800B7170);
    }
  }
  dwResult = 0;
  v5 = SendMessageTimeoutW(hWnd, Msg, 0, 0, 2u, 0x7D0u, &dwResult);
  *a2 = 0;
  if ( v5 && dwResult )
  {
    v28 = 0;
    Library = LoadLibraryExW(L"oleacc.dll", 0, 0x800u);
    if ( !Library )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\htmldocumenthelper.cpp",
        v7);
    v26[0] = Library;
    ProcAddress = GetProcAddress(Library, "ObjectFromLresult");
    if ( !ProcAddress )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\htmldocumenthelper.cpp",
        v9);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v10 = ((__int64 (__fastcall *)(ULONG_PTR, GUID *, _QWORD, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))ProcAddress)(
            dwResult,
            &IID_IDispatch,
            0,
            &v28);
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\htmldocumenthelper.cpp",
        (const char *)(unsigned int)v10,
        fuFlags);
    v24 = 0;
    v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v12 = **v28;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    if ( v12(v11, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v24) >= 0 )
    {
      v30 = 0;
      v13 = v24;
      v14 = *(__int64 (__fastcall **)(__int64, SID *, GUID *, __int64 *))(*(_QWORD *)v24 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      v15 = v14(v13, &SID_STopLevelBrowser, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v30);
      if ( v15 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\htmldocumenthelper.cpp",
          (const char *)(unsigned int)v15,
          fuFlags);
      v29 = 0;
      v16 = v30;
      v17 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v30 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v18 = v17(v16, &IID_IWebBrowserApp, &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e, &v29);
      if ( v18 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x28,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\htmldocumenthelper.cpp",
          (const char *)(unsigned int)v18,
          fuFlags);
      v19 = v29;
      v20 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v29 + 144LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      v21 = v20(v19, &v28);
      if ( v21 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\htmldocumenthelper.cpp",
          (const char *)(unsigned int)v21,
          fuFlags);
      v22 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
      if ( v28 )
      {
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[1])(v28);
        v22 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
      }
      *a2 = v22;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  }
}

```

## disassembly

```asm
0x180012ed4  mov     [rsp-18h+arg_0], rbx
0x180012ed9  push    rbp
0x180012eda  push    rsi
0x180012edb  push    rdi
0x180012edc  mov     rbp, rsp
0x180012edf  sub     rsp, 60h
0x180012ee3  mov     rsi, rdx
0x180012ee6  mov     rbx, rcx
0x180012ee9  mov     r8d, cs:_tls_index
0x180012ef0  mov     rax, gs:58h
0x180012ef9  mov     ecx, 4
0x180012efe  mov     rax, [rax+r8*8]
0x180012f02  mov     eax, [rcx+rax]
0x180012f05  cmp     cs:dword_1800B7170, eax
0x180012f0b  jle     short loc_180012F41
0x180012f0d  lea     rcx, dword_1800B7170
0x180012f14  call    _Init_thread_header
0x180012f19  cmp     cs:dword_1800B7170, 0FFFFFFFFh
0x180012f20  jnz     short loc_180012F41
0x180012f22  lea     rcx, aWmHtmlGetobjec; "WM_HTML_GETOBJECT"
0x180012f29  call    cs:__imp_RegisterWindowMessageW
0x180012f2f  mov     cs:Msg, eax
0x180012f35  lea     rcx, dword_1800B7170
0x180012f3c  call    _Init_thread_footer
0x180012f41  mov     [rbp+dwResult], 0
0x180012f49  lea     rax, [rbp+dwResult]
0x180012f4d  mov     [rsp+60h+lpdwResult], rax; lpdwResult
0x180012f52  mov     [rsp+60h+uTimeout], 7D0h; uTimeout
0x180012f5a  mov     [rsp+60h+fuFlags], 2; int
0x180012f62  xor     r9d, r9d; lParam
0x180012f65  xor     r8d, r8d; wParam
0x180012f68  mov     edx, cs:Msg; Msg
0x180012f6e  mov     rcx, rbx; hWnd
0x180012f71  call    cs:__imp_SendMessageTimeoutW
0x180012f77  mov     qword ptr [rsi], 0
0x180012f7e  test    rax, rax
0x180012f81  jz      loc_1800131AD
0x180012f87  cmp     [rbp+dwResult], 0
0x180012f8c  jz      loc_1800131AD
0x180012f92  mov     [rbp+arg_8], 0
0x180012f9a  xor     edx, edx; hFile
0x180012f9c  mov     r8d, 800h; dwFlags
0x180012fa2  lea     rcx, aOleaccDll; "oleacc.dll"
0x180012fa9  call    cs:__imp_LoadLibraryExW
0x180012faf  mov     rcx, [rbp+18h]; this
0x180012fb3  test    rax, rax
0x180012fb6  jnz     short loc_180012FC8
0x180012fb8  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180012fbf  lea     edx, [rax+1Bh]; void *
0x180012fc2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180012fc8  mov     [rbp+var_10], rax
0x180012fcc  lea     rdx, aObjectfromlres; "ObjectFromLresult"
0x180012fd3  mov     rcx, rax; hModule
0x180012fd6  call    cs:__imp_GetProcAddress
0x180012fdc  mov     rbx, rax
0x180012fdf  mov     rcx, [rbp+18h]; this
0x180012fe3  test    rax, rax
0x180012fe6  jnz     short loc_180012FF8
0x180012fe8  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180012fef  lea     edx, [rax+1Ch]; void *
0x180012ff2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180012ff8  lea     rcx, [rbp+arg_8]
0x180012ffc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013001  lea     r9, [rbp+arg_8]
0x180013005  xor     r8d, r8d
0x180013008  lea     rdx, IID_IDispatch
0x18001300f  mov     rcx, [rbp+dwResult]
0x180013013  mov     rax, rbx
0x180013016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001301b  mov     rcx, [rbp+18h]; this
0x18001301f  test    eax, eax
0x180013021  jns     short loc_180013038
0x180013023  mov     r9d, eax; char *
0x180013026  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001302d  mov     edx, 1Dh; void *
0x180013032  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180013038  mov     [rbp+var_20], 0
0x180013040  mov     rdi, [rbp+arg_8]
0x180013044  mov     rax, [rdi]
0x180013047  mov     rbx, [rax]
0x18001304a  lea     rcx, [rbp+var_20]
0x18001304e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013053  lea     r8, [rbp+var_20]
0x180013057  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18001305e  mov     rcx, rdi
0x180013061  mov     rax, rbx
0x180013064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013069  test    eax, eax
0x18001306b  js      loc_180013190
0x180013071  mov     [rbp+arg_18], 0
0x180013079  mov     rdi, [rbp+var_20]
0x18001307d  mov     rax, [rdi]
0x180013080  mov     rbx, [rax+18h]
0x180013084  lea     rcx, [rbp+arg_18]
0x180013088  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001308d  lea     r9, [rbp+arg_18]
0x180013091  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180013098  lea     rdx, SID_STopLevelBrowser
0x18001309f  mov     rcx, rdi
0x1800130a2  mov     rax, rbx
0x1800130a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130aa  mov     rcx, [rbp+18h]; this
0x1800130ae  test    eax, eax
0x1800130b0  jns     short loc_1800130C7
0x1800130b2  mov     r9d, eax; char *
0x1800130b5  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800130bc  mov     edx, 26h ; '&'; void *
0x1800130c1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800130c7  mov     [rbp+arg_10], 0
0x1800130cf  mov     rdi, [rbp+arg_18]
0x1800130d3  mov     rax, [rdi]
0x1800130d6  mov     rbx, [rax+18h]
0x1800130da  lea     rcx, [rbp+arg_10]
0x1800130de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800130e3  lea     r9, [rbp+arg_10]
0x1800130e7  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x1800130ee  lea     rdx, IID_IWebBrowserApp
0x1800130f5  mov     rcx, rdi
0x1800130f8  mov     rax, rbx
0x1800130fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013100  mov     rcx, [rbp+18h]; this
0x180013104  test    eax, eax
0x180013106  jns     short loc_18001311D
0x180013108  mov     r9d, eax; char *
0x18001310b  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180013112  mov     edx, 28h ; '('; void *
0x180013117  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001311d  mov     rdi, [rbp+arg_10]
0x180013121  mov     rax, [rdi]
0x180013124  mov     rbx, [rax+90h]
0x18001312b  lea     rcx, [rbp+arg_8]
0x18001312f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013134  lea     rdx, [rbp+arg_8]
0x180013138  mov     rcx, rdi
0x18001313b  mov     rax, rbx
0x18001313e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013143  mov     rcx, [rbp+18h]; this
0x180013147  test    eax, eax
0x180013149  jns     short loc_180013160
0x18001314b  mov     r9d, eax; char *
0x18001314e  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180013155  mov     edx, 29h ; ')'; void *
0x18001315a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180013160  mov     rcx, [rbp+arg_8]
0x180013164  test    rcx, rcx
0x180013167  jz      short loc_180013179
0x180013169  mov     rax, [rcx]
0x18001316c  mov     rax, [rax+8]
0x180013170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013175  mov     rcx, [rbp+arg_8]
0x180013179  mov     [rsi], rcx
0x18001317c  lea     rcx, [rbp+arg_10]
0x180013180  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013185  nop
0x180013186  lea     rcx, [rbp+arg_18]
0x18001318a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001318f  nop
0x180013190  lea     rcx, [rbp+var_20]
0x180013194  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013199  nop
0x18001319a  lea     rcx, [rbp+var_10]
0x18001319e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800131a3  nop
0x1800131a4  lea     rcx, [rbp+arg_8]
0x1800131a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800131ad  mov     rbx, [rsp+60h+arg_0]
0x1800131b5  add     rsp, 60h
0x1800131b9  pop     rdi
0x1800131ba  pop     rsi
0x1800131bb  pop     rbp
0x1800131bc  retn
```
