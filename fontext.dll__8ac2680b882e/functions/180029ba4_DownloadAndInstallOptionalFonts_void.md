# DownloadAndInstallOptionalFonts(void)

- ea: `0x180029ba4`
- end: `0x18002a0fd`
- name: `?DownloadAndInstallOptionalFonts@@YAJXZ`
- size: `1369`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a150`

## callees

- `0x1800062d0`
- `0x180006624`
- `0x180006668`
- `0x18001cd7c`
- `0x18001d928`
- `0x180023338`
- `0x180029600`
- `0x180029ba4`
- `0x18002a1dc`
- `0x18002a5a8`
- `0x18003104a`
- `0x180031070`
- `0x180031100`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180029ebf`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180029ebf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180029c3e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180029c3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029c06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029c06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029ea4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029ea4`
- `USER32!GetActiveWindow` at `0x180029f1f`
- `USER32!GetActiveWindow` at `0x180029fc9`
- `USER32!GetActiveWindow` at `0x180029f1f`
- `USER32!GetActiveWindow` at `0x180029fc9`

## string_xrefs

- `0x180029c56`: `shell\osshell\fontfldr\fontext2\dll\util.cpp`
- `0x180029cf6`: `shell\osshell\fontfldr\fontext2\dll\util.cpp`
- `0x180029f74`: `shell\osshell\fontfldr\fontext2\dll\util.cpp`
- `0x180029ff6`: `shell\osshell\fontfldr\fontext2\dll\util.cpp`
- `0x18002a04f`: `shell\osshell\fontfldr\fontext2\dll\util.cpp`
- `0x18002a0a8`: `shell\osshell\fontfldr\fontext2\dll\util.cpp`

## pseudocode

```c
__int64 DownloadAndInstallOptionalFonts(void)
{
  HRESULT Instance; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  IUnknown *v3; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v5; // eax
  union _ULARGE_INTEGER v6; // r14
  __int64 v7; // rsi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *, _DWORD *); // rbx
  int v10; // eax
  int v11; // edi
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rdx
  int v14; // r8d
  HWND ActiveWindow; // rax
  __int64 v16; // rdx
  HWND v17; // rax
  int v18; // eax
  int v19; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int *ppva; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-A0h] BYREF
  IUnknown *pProxy; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  void *v29; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v31[2]; // [rsp+8Ch] [rbp-74h] BYREF
  int v32; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v33; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v34; // [rsp+A0h] [rbp-60h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Value[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR NumberStr[32]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v39[6144]; // [rsp+340h] [rbp+240h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3388h] [rbp+3288h]

  pProxy = 0;
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&pProxy);
  Instance = CoCreateInstance(
               &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
               0,
               0x15u,
               &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
               (LPVOID *)&pProxy);
  v1 = Instance;
  if ( Instance < 0 )
  {
    v2 = 781;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\util.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
LABEL_41:
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&pProxy);
    return v1;
  }
  Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
  v1 = Instance;
  if ( Instance < 0 )
  {
    v2 = 782;
    goto LABEL_5;
  }
  ppv = 0;
  Instance = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const wchar_t *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
               pProxy,
               0,
               L"ControlPanelOptionalFontsDownload",
               0);
  v1 = Instance;
  if ( Instance < 0 )
  {
    v2 = 783;
    goto LABEL_5;
  }
  v3 = pProxy;
  v23 = 0;
  QueryInterface = pProxy->lpVtbl[6].QueryInterface;
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v23);
  LODWORD(ppva) = 0;
  v5 = ((__int64 (__fastcall *)(IUnknown *, __int64, const wchar_t *))QueryInterface)(v3, 5, L"Language.Fonts");
  v1 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\util.cpp",
      (const char *)(unsigned int)v5,
      0);
LABEL_40:
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v23);
    goto LABEL_41;
  }
  v6.QuadPart = 0;
  v39[0] = 0;
  v7 = 0;
  do
  {
    v8 = v23;
    v24 = 0;
    v31[0] = 0;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, _DWORD *))(*(_QWORD *)v23 + 24LL);
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v24);
    v10 = v9(v8, 1, &v24, v31);
    v1 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x320,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\util.cpp",
        (const char *)(unsigned int)v10,
        (int)ppva);
      Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v24);
      goto LABEL_40;
    }
    if ( !v10 )
    {
      v25 = 0;
      v28 = 0;
      v27 = 0;
      v32 = 0;
      v31[1] = 0;
      ppva = &v32;
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, __int64 *, __int64 *))(*(_QWORD *)v24 + 112LL))(
              v24,
              &v25,
              &v28,
              &v27);
      if ( v11 < 0 )
      {
        v16 = 809;
        goto LABEL_32;
      }
      v34 = 0;
      v11 = StringCchLengthW(v25, 0x7FFFFFFFu, &v34);
      if ( v11 < 0 )
      {
        v16 = 813;
        goto LABEL_32;
      }
      v12 = v34;
      v13 = 6144 - v7;
      if ( v34 + 2 <= 6144 - v7 )
      {
        if ( v39[0] )
          v39[v7++] = v1 + 59;
        v11 = StringCchCopyW(&v39[v7], v13, v25);
        if ( v11 < 0 )
        {
          v16 = 823;
          goto LABEL_32;
        }
        v30 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 136LL))(v24, &v30);
        if ( v11 < 0 )
        {
          v16 = 827;
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\util.cpp",
            (const char *)(unsigned int)v11,
            (int)&v32);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
          Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v23);
          v1 = v11;
          goto LABEL_41;
        }
        v7 += v12;
        v6.QuadPart += v30;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
    }
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v24);
  }
  while ( !v1 );
  memset_0(Buffer, 0, 0x208u);
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( GetDiskFreeSpaceExW(Buffer, 0, 0, &TotalNumberOfFreeBytes) )
    {
      if ( v6.QuadPart > TotalNumberOfFreeBytes.QuadPart )
      {
        memset_0(Value, 0, sizeof(Value));
        memset_0(NumberStr, 0, sizeof(NumberStr));
        StringCchPrintfW(Value, 0x20u, L"%I64u", v6.QuadPart >> 20);
        FormatIntegerString(Value, NumberStr, v14);
        ActiveWindow = GetActiveWindow();
        if ( (unsigned int)FontMessageBox(ActiveWindow, 0x21u, 0x1FBFu, NumberStr) != 1 )
        {
          Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v23);
          v1 = -2147009292;
          goto LABEL_41;
        }
      }
    }
  }
  v29 = 0;
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v29);
  v17 = GetActiveWindow();
  v18 = CoCreateInstanceAsAdmin(
          v17,
          &GUID_c6b167ea_db3e_4659_badc_d1ccc00efe9c,
          &GUID_fe3ccccc_f5b9_4b61_86b8_697908ad690f,
          &v29);
  v1 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\util.cpp",
      (const char *)(unsigned int)v18,
      (int)ppva);
LABEL_37:
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v29);
    goto LABEL_40;
  }
  v33 = 0;
  v19 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD, unsigned __int16 *))(*(_QWORD *)v29 + 24LL))(
          v29,
          L"ControlPanelOptionalFontsDownload",
          0,
          v39);
  v1 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x360,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\util.cpp",
      (const char *)(unsigned int)v19,
      1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
    goto LABEL_37;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&pProxy);
  return 0;
}

```

## disassembly

```asm
0x180029ba4  push    rbp
0x180029ba6  push    rbx
0x180029ba7  push    rsi
0x180029ba8  push    rdi
0x180029ba9  push    r12
0x180029bab  push    r14
0x180029bad  push    r15
0x180029baf  lea     rbp, [rsp-3250h]
0x180029bb7  mov     eax, 3350h
0x180029bbc  call    _alloca_probe
0x180029bc1  sub     rsp, rax
0x180029bc4  mov     rax, cs:__security_cookie
0x180029bcb  xor     rax, rsp
0x180029bce  mov     [rbp+3280h+var_40], rax
0x180029bd5  xor     r12d, r12d
0x180029bd8  lea     rcx, [rsp+3380h+pProxy]
0x180029bdd  mov     [rsp+3380h+pProxy], r12
0x180029be2  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029be7  lea     rax, [rsp+3380h+pProxy]
0x180029bec  xor     edx, edx; pUnkOuter
0x180029bee  lea     r9, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22; riid
0x180029bf5  mov     [rsp+3380h+ppv], rax; ppv
0x180029bfa  lea     r8d, [r12+15h]; dwClsContext
0x180029bff  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x180029c06  call    cs:__imp_CoCreateInstance
0x180029c0c  mov     ebx, eax
0x180029c0e  test    eax, eax
0x180029c10  jns     short loc_180029C19
0x180029c12  mov     edx, 30Dh
0x180029c17  jmp     short loc_180029C4F
0x180029c19  mov     rcx, [rsp+3380h+pProxy]; pProxy
0x180029c1e  mov     eax, 3
0x180029c23  mov     [rsp+3380h+dwCapabilities], r12d; dwCapabilities
0x180029c28  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180029c2b  mov     [rsp+3380h+pAuthInfo], r12; pAuthInfo
0x180029c30  mov     r8d, edx; dwAuthzSvc
0x180029c33  mov     [rsp+3380h+dwImpLevel], eax; dwImpLevel
0x180029c37  xor     r9d, r9d; pServerPrincName
0x180029c3a  mov     dword ptr [rsp+3380h+ppv], eax; int
0x180029c3e  call    cs:__imp_CoSetProxyBlanket
0x180029c44  mov     ebx, eax
0x180029c46  test    eax, eax
0x180029c48  jns     short loc_180029C6A
0x180029c4a  mov     edx, 30Eh; void *
0x180029c4f  mov     rcx, [rbp+3288h]; this
0x180029c56  lea     r8, aShellOsshellFo_0; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180029c5d  mov     r9d, eax; char *
0x180029c60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029c65  jmp     loc_18002A0D0
0x180029c6a  mov     rcx, [rsp+3380h+pProxy]
0x180029c6f  lea     r8, aControlpanelop; "ControlPanelOptionalFontsDownload"
0x180029c76  xor     r9d, r9d
0x180029c79  mov     [rsp+3380h+ppv], r12
0x180029c7e  xor     edx, edx
0x180029c80  mov     rax, [rcx]
0x180029c83  mov     rax, [rax+18h]
0x180029c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c8c  mov     ebx, eax
0x180029c8e  test    eax, eax
0x180029c90  jns     short loc_180029C99
0x180029c92  mov     edx, 30Fh
0x180029c97  jmp     short loc_180029C4F
0x180029c99  mov     rdi, [rsp+3380h+pProxy]
0x180029c9e  lea     rcx, [rsp+3380h+var_3330]
0x180029ca3  mov     [rsp+3380h+var_3330], r12
0x180029ca8  mov     rax, [rdi]
0x180029cab  mov     rbx, [rax+90h]
0x180029cb2  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029cb7  xor     r9d, r9d
0x180029cba  lea     rax, [rsp+3380h+var_3330]
0x180029cbf  mov     qword ptr [rsp+3380h+dwCapabilities], rax
0x180029cc4  lea     r8, aLanguageFonts; "Language.Fonts"
0x180029ccb  mov     dword ptr [rsp+3380h+pAuthInfo], r12d
0x180029cd0  mov     rcx, rdi
0x180029cd3  mov     [rsp+3380h+dwImpLevel], r12d
0x180029cd8  mov     rax, rbx
0x180029cdb  lea     edx, [r9+5]
0x180029cdf  mov     [rsp+3380h+ppv], r12; int
0x180029ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ce9  mov     ebx, eax
0x180029ceb  test    eax, eax
0x180029ced  jns     short loc_180029D0F
0x180029cef  mov     rcx, [rbp+3288h]; this
0x180029cf6  lea     r8, aShellOsshellFo_0; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180029cfd  mov     r9d, eax; char *
0x180029d00  mov     edx, 313h; void *
0x180029d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d0a  jmp     loc_18002A0C6
0x180029d0f  mov     r14, r12
0x180029d12  mov     [rbp+3280h+var_3040], r12w
0x180029d1a  mov     rsi, r12
0x180029d1d  mov     rdi, [rsp+3380h+var_3330]
0x180029d22  lea     rcx, [rsp+3380h+var_3328]
0x180029d27  mov     [rsp+3380h+var_3328], r12
0x180029d2c  mov     [rbp+3280h+var_32F4], r12d
0x180029d30  mov     rax, [rdi]
0x180029d33  mov     rbx, [rax+18h]
0x180029d37  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029d3c  lea     r9, [rbp+3280h+var_32F4]
0x180029d40  mov     edx, 1
0x180029d45  lea     r8, [rsp+3380h+var_3328]
0x180029d4a  mov     rcx, rdi
0x180029d4d  mov     rax, rbx
0x180029d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d55  mov     ebx, eax
0x180029d57  test    eax, eax
0x180029d59  js      loc_18002A0A1
0x180029d5f  test    eax, eax
0x180029d61  jnz     loc_180029E74
0x180029d67  mov     rcx, [rsp+3380h+var_3328]
0x180029d6c  lea     r9, [rsp+3380h+var_3310]
0x180029d71  mov     [rsp+3380h+var_3320], r12
0x180029d76  lea     r8, [rsp+3380h+var_3308]
0x180029d7b  mov     [rsp+3380h+var_3308], r12
0x180029d80  mov     [rsp+3380h+var_3310], r12
0x180029d85  mov     [rbp+3280h+var_32EC], r12d
0x180029d89  mov     [rbp+3280h+var_32F0], r12d
0x180029d8d  mov     rdx, [rcx]
0x180029d90  mov     rax, [rdx+70h]
0x180029d94  lea     rdx, [rbp+3280h+var_32F0]
0x180029d98  mov     qword ptr [rsp+3380h+dwImpLevel], rdx
0x180029d9d  lea     rdx, [rbp+3280h+var_32EC]
0x180029da1  mov     [rsp+3380h+ppv], rdx; int
0x180029da6  lea     rdx, [rsp+3380h+var_3320]
0x180029dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029db0  mov     edi, eax
0x180029db2  test    eax, eax
0x180029db4  js      loc_180029F68
0x180029dba  mov     rcx, [rsp+3380h+var_3320]; unsigned __int16 *
0x180029dbf  lea     r8, [rbp+3280h+var_32E0]; unsigned __int64 *
0x180029dc3  mov     edx, 7FFFFFFFh; unsigned __int64
0x180029dc8  mov     [rbp+3280h+var_32E0], r12
0x180029dcc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180029dd1  mov     edi, eax
0x180029dd3  test    eax, eax
0x180029dd5  js      loc_180029F61
0x180029ddb  mov     r15, [rbp+3280h+var_32E0]
0x180029ddf  mov     edx, 1800h
0x180029de4  sub     rdx, rsi; unsigned __int64
0x180029de7  lea     rax, [r15+2]
0x180029deb  cmp     rax, rdx
0x180029dee  ja      short loc_180029E56
0x180029df0  cmp     [rbp+3280h+var_3040], r12w
0x180029df8  jz      short loc_180029E08
0x180029dfa  lea     eax, [rbx+3Bh]
0x180029dfd  mov     [rbp+rsi*2+3280h+var_3040], ax
0x180029e05  inc     rsi
0x180029e08  mov     r8, [rsp+3380h+var_3320]; unsigned __int16 *
0x180029e0d  lea     rcx, [rbp+3280h+var_3040]
0x180029e14  lea     rcx, [rcx+rsi*2]; unsigned __int16 *
0x180029e18  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029e1d  mov     edi, eax
0x180029e1f  test    eax, eax
0x180029e21  js      loc_180029F5A
0x180029e27  mov     rcx, [rsp+3380h+var_3328]
0x180029e2c  lea     rdx, [rbp+3280h+var_32F8]
0x180029e30  mov     [rbp+3280h+var_32F8], r12d
0x180029e34  mov     rax, [rcx]
0x180029e37  mov     rax, [rax+88h]
0x180029e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e43  mov     edi, eax
0x180029e45  test    eax, eax
0x180029e47  js      loc_180029F53
0x180029e4d  mov     eax, [rbp+3280h+var_32F8]
0x180029e50  add     rsi, r15
0x180029e53  add     r14, rax
0x180029e56  lea     rcx, [rsp+3380h+var_3310]
0x180029e5b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029e60  lea     rcx, [rsp+3380h+var_3308]
0x180029e65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029e6a  lea     rcx, [rsp+3380h+var_3320]
0x180029e6f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029e74  lea     rcx, [rsp+3380h+var_3328]
0x180029e79  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029e7e  test    ebx, ebx
0x180029e80  jz      loc_180029D1D
0x180029e86  xor     edx, edx; Val
0x180029e88  lea     rcx, [rbp+3280h+Buffer]; void *
0x180029e8c  mov     r8d, 208h; Size
0x180029e92  call    memset_0
0x180029e97  mov     edx, 104h; uSize
0x180029e9c  mov     qword ptr [rbp+3280h+TotalNumberOfFreeBytes], r12
0x180029ea0  lea     rcx, [rbp+3280h+Buffer]; lpBuffer
0x180029ea4  call    cs:__imp_GetSystemDirectoryW
0x180029eaa  test    eax, eax
0x180029eac  jz      loc_180029FBC
0x180029eb2  lea     r9, [rbp+3280h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180029eb6  xor     r8d, r8d; lpTotalNumberOfBytes
0x180029eb9  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180029ebb  lea     rcx, [rbp+3280h+Buffer]; lpDirectoryName
0x180029ebf  call    cs:__imp_GetDiskFreeSpaceExW
0x180029ec5  test    eax, eax
0x180029ec7  jz      loc_180029FBC
0x180029ecd  cmp     r14, qword ptr [rbp+3280h+TotalNumberOfFreeBytes]
0x180029ed1  jbe     loc_180029FBC
0x180029ed7  mov     ebx, 40h ; '@'
0x180029edc  lea     rcx, [rbp+3280h+Value]; void *
0x180029ee0  mov     r8d, ebx; Size
0x180029ee3  xor     edx, edx; Val
0x180029ee5  call    memset_0
0x180029eea  mov     r8d, ebx; Size
0x180029eed  lea     rcx, [rbp+3280h+NumberStr]; void *
0x180029ef1  xor     edx, edx; Val
0x180029ef3  call    memset_0
0x180029ef8  shr     r14, 14h
0x180029efc  lea     r8, aI64u; "%I64u"
0x180029f03  mov     r9, r14
0x180029f06  lea     edx, [rbx-20h]; unsigned __int64
0x180029f09  lea     rcx, [rbp+3280h+Value]; unsigned __int16 *
0x180029f0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029f12  lea     rdx, [rbp+3280h+NumberStr]; lpNumberStr
0x180029f16  lea     rcx, [rbp+3280h+Value]; lpValue
0x180029f1a  call    ?FormatIntegerString@@YAHPEBGPEAGH@Z; FormatIntegerString(ushort const *,ushort *,int)
0x180029f1f  call    cs:__imp_GetActiveWindow
0x180029f25  lea     r9, [rbp+3280h+NumberStr]
0x180029f29  mov     r8d, 1FBFh; unsigned int
0x180029f2f  mov     rcx, rax; HWND
0x180029f32  lea     edx, [rbx-1Fh]; unsigned int
0x180029f35  call    ?FontMessageBox@@YAHPEAUHWND__@@IIZZ; FontMessageBox(HWND__ *,uint,uint,...)
0x180029f3a  cmp     eax, 1
0x180029f3d  jz      short loc_180029FBC
0x180029f3f  lea     rcx, [rsp+3380h+var_3330]
0x180029f44  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029f49  mov     ebx, 80073CF4h
0x180029f4e  jmp     loc_18002A0D0
0x180029f53  mov     edx, 33Bh
0x180029f58  jmp     short loc_180029F6D
0x180029f5a  mov     edx, 337h
0x180029f5f  jmp     short loc_180029F6D
0x180029f61  mov     edx, 32Dh
0x180029f66  jmp     short loc_180029F6D
0x180029f68  mov     edx, 329h; void *
0x180029f6d  mov     rcx, [rbp+3288h]; this
0x180029f74  lea     r8, aShellOsshellFo_0; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180029f7b  mov     r9d, edi; char *
0x180029f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f83  lea     rcx, [rsp+3380h+var_3310]
0x180029f88  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029f8d  lea     rcx, [rsp+3380h+var_3308]
0x180029f92  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029f97  lea     rcx, [rsp+3380h+var_3320]
0x180029f9c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029fa1  lea     rcx, [rsp+3380h+var_3328]
0x180029fa6  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029fab  lea     rcx, [rsp+3380h+var_3330]
0x180029fb0  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029fb5  mov     ebx, edi
0x180029fb7  jmp     loc_18002A0D0
0x180029fbc  lea     rcx, [rbp+3280h+var_3300]
0x180029fc0  mov     [rbp+3280h+var_3300], r12
0x180029fc4  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x180029fc9  call    cs:__imp_GetActiveWindow
0x180029fcf  mov     rcx, rax; HWND
0x180029fd2  lea     r9, [rbp+3280h+var_3300]; void **
0x180029fd6  lea     r8, _GUID_fe3ccccc_f5b9_4b61_86b8_697908ad690f; struct _GUID *
0x180029fdd  lea     rdx, _GUID_c6b167ea_db3e_4659_badc_d1ccc00efe9c; struct _GUID *
0x180029fe4  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180029fe9  mov     ebx, eax
0x180029feb  test    eax, eax
0x180029fed  jns     short loc_18002A00C
0x180029fef  mov     rcx, [rbp+3288h]; this
0x180029ff6  lea     r8, aShellOsshellFo_0; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180029ffd  mov     r9d, eax; char *
0x18002a000  mov     edx, 35Eh; void *
0x18002a005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a00a  jmp     short loc_18002A06C
0x18002a00c  mov     rcx, [rbp+3280h+var_3300]
0x18002a010  lea     r8, [rbp+3280h+var_32E8]
0x18002a014  mov     qword ptr [rsp+3380h+dwImpLevel], r8
0x18002a019  lea     r9, [rbp+3280h+var_3040]
0x18002a020  mov     [rbp+3280h+var_32E8], r12
0x18002a024  lea     rdx, aControlpanelop; "ControlPanelOptionalFontsDownload"
0x18002a02b  xor     r8d, r8d
0x18002a02e  mov     dword ptr [rsp+3380h+ppv], 1; int
0x18002a036  mov     rax, [rcx]
0x18002a039  mov     rax, [rax+18h]
0x18002a03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a042  mov     ebx, eax
0x18002a044  test    eax, eax
0x18002a046  jns     short loc_18002A077
0x18002a048  mov     rcx, [rbp+3288h]; this
0x18002a04f  lea     r8, aShellOsshellFo_0; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002a056  mov     r9d, eax; char *
0x18002a059  mov     edx, 360h; void *
0x18002a05e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a063  lea     rcx, [rbp+3280h+var_32E8]
0x18002a067  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a06c  lea     rcx, [rbp+3280h+var_3300]
0x18002a070  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x18002a075  jmp     short loc_18002A0C6
0x18002a077  lea     rcx, [rbp+3280h+var_32E8]
0x18002a07b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a080  lea     rcx, [rbp+3280h+var_3300]
0x18002a084  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x18002a089  lea     rcx, [rsp+3380h+var_3330]
0x18002a08e  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x18002a093  lea     rcx, [rsp+3380h+pProxy]
0x18002a098  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x18002a09d  xor     eax, eax
0x18002a09f  jmp     short loc_18002A0DC
  ... truncated ...
```
