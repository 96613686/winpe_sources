# CWUInfo::GetIsStoreBlockedByPolicy(void)

- ea: `0x1800d7190`
- end: `0x1800d74fa`
- name: `?GetIsStoreBlockedByPolicy@CWUInfo@@QEBAEXZ`
- size: `874`
- prototype: `unsigned __int8 __fastcall(CWUInfo *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008dc0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180030554`
- `0x18008fbb8`
- `0x18008fc6c`
- `0x18009f918`
- `0x1800d7190`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d71c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d71c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d71f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d71f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d74c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d74df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d74c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d74df`

## string_xrefs

- `0x1800d71e9`: `WindowsCreateStringReference`
- `0x1800d71b9`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800d723d`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x1800d749f`: `onecore\base\appcompat\programs\devicecensus\dlls\wuinfo.cpp`
- `0x1800d74b3`: `onecore\base\appcompat\programs\devicecensus\dlls\wuinfo.cpp`

## pseudocode

```c
unsigned __int8 __fastcall CWUInfo::GetIsStoreBlockedByPolicy(CWUInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rcx
  __int64 *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v8; // rsi
  Delayed::HStringReference *v9; // rax
  int v10; // eax
  DWORD v11; // edx
  int v12; // r8d
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  bool v18; // bl
  __int64 v19; // rcx
  __int64 v20; // rcx
  signed int LastError; // eax
  int v22; // edx
  unsigned int v23; // r8d
  signed int v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  signed int v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  signed int v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  int v33; // [rsp+20h] [rbp-B8h]
  char v34; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v35[7]; // [rsp+31h] [rbp-A7h] BYREF
  __int64 v36; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-98h] BYREF
  const int *v38; // [rsp+48h] [rbp-90h] BYREF
  HMODULE v39; // [rsp+50h] [rbp-88h]
  FARPROC v40; // [rsp+58h] [rbp-80h]
  _BYTE v41[32]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v42[32]; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v39 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WindowsCreateStringReference");
    v40 = ProcAddress;
    Library = v39;
  }
  else
  {
    ProcAddress = 0;
    v40 = 0;
  }
  v37 = 0;
  v36 = 0;
  v35[0] = 0;
  if ( !ProcAddress )
  {
    v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( Library && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v38) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v22, v23);
      __debugbreak();
    }
    return 2;
  }
  v4 = (__int64 *)Delayed::HStringReference::HStringReference(
                    (Delayed::HStringReference *)v41,
                    (const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *)&v38,
                    L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager");
  if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
              *v4,
              &v37) < 0 )
  {
    v5 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( !v39 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v38) )
      return 2;
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
LABEL_39:
    wil::details::in1diag3::_Throw_Hr(
      v13,
      (void *)0x370,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\wuinfo.cpp",
      (const char *)(unsigned int)v10,
      v33);
  }
  v6 = v37;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v37 + 184LL);
  v8 = *(_QWORD *)Delayed::HStringReference::HStringReference(
                    (Delayed::HStringReference *)v41,
                    (const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *)&v38,
                    L"CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US");
  v9 = Delayed::HStringReference::HStringReference(
         (Delayed::HStringReference *)v42,
         (const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *)&v38,
         L"Microsoft.WindowsStore");
  v10 = v7(v6, *(_QWORD *)v9, v8, &v36);
  v13 = retaddr;
  if ( v10 < 0 )
    goto LABEL_39;
  v34 = 0;
  v14 = v36;
  v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v36, v11, v12, &v34);
  if ( v15 >= 0 )
    v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v14 + 64LL))(v14, v35);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x377,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\wuinfo.cpp",
      (const char *)(unsigned int)v15,
      v33);
  if ( v34 )
  {
    v16 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v39 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v38) )
    {
      v27 = GetLastError();
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
      __debugbreak();
    }
    return 2;
  }
  else
  {
    v18 = v35[0] != 0;
    v19 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v39 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v38) )
    {
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
      JUMPOUT(0x1800D74F8LL);
    }
    return v18;
  }
}

```

## disassembly

```asm
0x1800d7190  push    rbx
0x1800d7192  push    rsi
0x1800d7193  push    rdi
0x1800d7194  push    r14
0x1800d7196  push    r15
0x1800d7198  sub     rsp, 0B0h
0x1800d719f  mov     rax, cs:__security_cookie
0x1800d71a6  xor     rax, rsp
0x1800d71a9  mov     [rsp+0D8h+var_38], rax
0x1800d71b1  xor     edx, edx; hFile
0x1800d71b3  mov     r8d, 800h; dwFlags
0x1800d71b9  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800d71c0  call    cs:__imp_LoadLibraryExW
0x1800d71c6  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800d71cd  mov     [rsp+0D8h+var_90], r15
0x1800d71d2  mov     [rsp+0D8h+var_88], rax
0x1800d71d7  xor     r14d, r14d
0x1800d71da  test    rax, rax
0x1800d71dd  jnz     short loc_1800D71E9
0x1800d71df  mov     ecx, r14d
0x1800d71e2  mov     [rsp+0D8h+var_80], rcx
0x1800d71e7  jmp     short loc_1800D7206
0x1800d71e9  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800d71f0  mov     rcx, rax; hModule
0x1800d71f3  call    cs:__imp_GetProcAddress
0x1800d71f9  mov     rcx, rax
0x1800d71fc  mov     [rsp+0D8h+var_80], rax
0x1800d7201  mov     rax, [rsp+0D8h+var_88]
0x1800d7206  mov     [rsp+0D8h+var_98], r14
0x1800d720b  mov     [rsp+0D8h+var_A0], r14
0x1800d7210  mov     [rsp+0D8h+var_A7], r14b
0x1800d7215  test    rcx, rcx
0x1800d7218  jnz     short loc_1800D723D
0x1800d721a  mov     [rsp+0D8h+var_90], r15
0x1800d721f  test    rax, rax
0x1800d7222  jz      short loc_1800D7236
0x1800d7224  lea     rcx, [rsp+0D8h+var_90]
0x1800d7229  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d722e  test    al, al
0x1800d7230  jz      loc_1800D7468
0x1800d7236  mov     al, 2
0x1800d7238  jmp     loc_1800D7449
0x1800d723d  lea     r8, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x1800d7244  lea     rdx, [rsp+0D8h+var_90]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800d7249  lea     rcx, [rsp+0D8h+var_78]; this
0x1800d724e  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800d7253  lea     rdx, [rsp+0D8h+var_98]
0x1800d7258  mov     rcx, [rax]
0x1800d725b  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x1800d7260  test    eax, eax
0x1800d7262  jns     short loc_1800D72C1
0x1800d7264  mov     rcx, [rsp+0D8h+var_A0]
0x1800d7269  test    rcx, rcx
0x1800d726c  jz      short loc_1800D7280
0x1800d726e  mov     [rsp+0D8h+var_A0], r14
0x1800d7273  mov     rax, [rcx]
0x1800d7276  mov     rax, [rax+10h]
0x1800d727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d727f  nop
0x1800d7280  mov     rcx, [rsp+0D8h+var_98]
0x1800d7285  test    rcx, rcx
0x1800d7288  jz      short loc_1800D729C
0x1800d728a  mov     [rsp+0D8h+var_98], r14
0x1800d728f  mov     rax, [rcx]
0x1800d7292  mov     rax, [rax+10h]
0x1800d7296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d729b  nop
0x1800d729c  mov     [rsp+0D8h+var_90], r15
0x1800d72a1  cmp     [rsp+0D8h+var_88], r14
0x1800d72a6  jz      short loc_1800D72BA
0x1800d72a8  lea     rcx, [rsp+0D8h+var_90]
0x1800d72ad  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d72b2  test    al, al
0x1800d72b4  jz      loc_1800D7482
0x1800d72ba  mov     al, 2
0x1800d72bc  jmp     loc_1800D7449
0x1800d72c1  mov     rbx, [rsp+0D8h+var_98]
0x1800d72c6  mov     rax, [rbx]
0x1800d72c9  mov     rdi, [rax+0B8h]
0x1800d72d0  mov     rcx, [rsp+0D8h+var_A0]
0x1800d72d5  test    rcx, rcx
0x1800d72d8  jz      short loc_1800D72EC
0x1800d72da  mov     [rsp+0D8h+var_A0], r14
0x1800d72df  mov     rax, [rcx]
0x1800d72e2  mov     rax, [rax+10h]
0x1800d72e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d72eb  nop
0x1800d72ec  lea     r8, aCnMicrosoftCor; "CN=Microsoft Corporation, O=Microsoft C"...
0x1800d72f3  lea     rdx, [rsp+0D8h+var_90]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800d72f8  lea     rcx, [rsp+0D8h+var_78]; this
0x1800d72fd  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800d7302  mov     rsi, [rax]
0x1800d7305  lea     r8, aMicrosoftWindo_0; "Microsoft.WindowsStore"
0x1800d730c  lea     rdx, [rsp+0D8h+var_90]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800d7311  lea     rcx, [rsp+0D8h+var_58]; this
0x1800d7319  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800d731e  lea     r9, [rsp+0D8h+var_A0]
0x1800d7323  mov     r8, rsi
0x1800d7326  mov     rdx, [rax]
0x1800d7329  mov     rcx, rbx
0x1800d732c  mov     rax, rdi
0x1800d732f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7334  mov     rcx, [rsp+0D8h]
0x1800d733c  test    eax, eax
0x1800d733e  js      loc_1800D749C
0x1800d7344  mov     [rsp+0D8h+var_A8], r14b
0x1800d7349  mov     rbx, [rsp+0D8h+var_A0]
0x1800d734e  lea     r9, [rsp+0D8h+var_A8]
0x1800d7353  mov     rcx, rbx
0x1800d7356  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x1800d735b  test    eax, eax
0x1800d735d  js      short loc_1800D7374
0x1800d735f  mov     rax, [rbx]
0x1800d7362  lea     rdx, [rsp+0D8h+var_A7]
0x1800d7367  mov     rcx, rbx
0x1800d736a  mov     rax, [rax+40h]
0x1800d736e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7373  nop
0x1800d7374  mov     rcx, [rsp+0D8h]; this
0x1800d737c  test    eax, eax
0x1800d737e  js      loc_1800D74B0
0x1800d7384  cmp     [rsp+0D8h+var_A8], r14b
0x1800d7389  jz      short loc_1800D73E5
0x1800d738b  mov     rcx, [rsp+0D8h+var_A0]
0x1800d7390  test    rcx, rcx
0x1800d7393  jz      short loc_1800D73A7
0x1800d7395  mov     [rsp+0D8h+var_A0], r14
0x1800d739a  mov     rax, [rcx]
0x1800d739d  mov     rax, [rax+10h]
0x1800d73a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d73a6  nop
0x1800d73a7  mov     rcx, [rsp+0D8h+var_98]
0x1800d73ac  test    rcx, rcx
0x1800d73af  jz      short loc_1800D73C3
0x1800d73b1  mov     [rsp+0D8h+var_98], r14
0x1800d73b6  mov     rax, [rcx]
0x1800d73b9  mov     rax, [rax+10h]
0x1800d73bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d73c2  nop
0x1800d73c3  mov     [rsp+0D8h+var_90], r15
0x1800d73c8  cmp     [rsp+0D8h+var_88], r14
0x1800d73cd  jz      short loc_1800D73E1
0x1800d73cf  lea     rcx, [rsp+0D8h+var_90]
0x1800d73d4  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d73d9  test    al, al
0x1800d73db  jz      loc_1800D74C5
0x1800d73e1  mov     al, 2
0x1800d73e3  jmp     short loc_1800D7449
0x1800d73e5  cmp     [rsp+0D8h+var_A7], r14b
0x1800d73ea  setnz   bl
0x1800d73ed  mov     rcx, [rsp+0D8h+var_A0]
0x1800d73f2  test    rcx, rcx
0x1800d73f5  jz      short loc_1800D7409
0x1800d73f7  mov     [rsp+0D8h+var_A0], r14
0x1800d73fc  mov     rax, [rcx]
0x1800d73ff  mov     rax, [rax+10h]
0x1800d7403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7408  nop
0x1800d7409  mov     rcx, [rsp+0D8h+var_98]
0x1800d740e  test    rcx, rcx
0x1800d7411  jz      short loc_1800D7425
0x1800d7413  mov     [rsp+0D8h+var_98], r14
0x1800d7418  mov     rax, [rcx]
0x1800d741b  mov     rax, [rax+10h]
0x1800d741f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7424  nop
0x1800d7425  mov     [rsp+0D8h+var_90], r15
0x1800d742a  cmp     [rsp+0D8h+var_88], r14
0x1800d742f  jz      short loc_1800D7443
0x1800d7431  lea     rcx, [rsp+0D8h+var_90]
0x1800d7436  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d743b  test    al, al
0x1800d743d  jz      loc_1800D74DF
0x1800d7443  mov     al, bl
0x1800d7445  jmp     short loc_1800D7449
0x1800d7447  mov     al, 2
0x1800d7449  mov     rcx, [rsp+0D8h+var_38]
0x1800d7451  xor     rcx, rsp; StackCookie
0x1800d7454  call    __security_check_cookie
0x1800d7459  add     rsp, 0B0h
0x1800d7460  pop     r15
0x1800d7462  pop     r14
0x1800d7464  pop     rdi
0x1800d7465  pop     rsi
0x1800d7466  pop     rbx
0x1800d7467  retn
0x1800d7468  call    cs:__imp_GetLastError
0x1800d746e  test    eax, eax
0x1800d7470  jle     short loc_1800D747A
0x1800d7472  movzx   eax, ax
0x1800d7475  or      eax, 80070000h
0x1800d747a  mov     ecx, eax; this
0x1800d747c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d7481  int     3; Trap to Debugger
0x1800d7482  call    cs:__imp_GetLastError
0x1800d7488  test    eax, eax
0x1800d748a  jle     short loc_1800D7494
0x1800d748c  movzx   eax, ax
0x1800d748f  or      eax, 80070000h
0x1800d7494  mov     ecx, eax; this
0x1800d7496  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d749b  nop
0x1800d749c  mov     r9d, eax; char *
0x1800d749f  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d74a6  mov     edx, 370h; void *
0x1800d74ab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d74b0  mov     r9d, eax; char *
0x1800d74b3  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d74ba  mov     edx, 377h; void *
0x1800d74bf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d74c5  call    cs:__imp_GetLastError
0x1800d74cb  test    eax, eax
0x1800d74cd  jle     short loc_1800D74D7
0x1800d74cf  movzx   eax, ax
0x1800d74d2  or      eax, 80070000h
0x1800d74d7  mov     ecx, eax; this
0x1800d74d9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d74de  int     3; Trap to Debugger
0x1800d74df  call    cs:__imp_GetLastError
0x1800d74e5  test    eax, eax
0x1800d74e7  jle     short loc_1800D74F1
0x1800d74e9  movzx   eax, ax
0x1800d74ec  or      eax, 80070000h
0x1800d74f1  mov     ecx, eax; this
0x1800d74f3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
