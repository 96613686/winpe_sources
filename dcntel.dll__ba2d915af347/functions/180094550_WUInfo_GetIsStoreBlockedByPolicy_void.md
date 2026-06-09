# WUInfo::GetIsStoreBlockedByPolicy(void)

- ea: `0x180094550`
- end: `0x1800948ba`
- name: `?GetIsStoreBlockedByPolicy@WUInfo@@AEBAEXZ`
- size: `874`
- prototype: `unsigned __int8 __fastcall(WUInfo *__hidden this)`
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
- `0x180094550`
- `0x18009f918`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180094580`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180094580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800945b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800945b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009489f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009489f`

## string_xrefs

- `0x1800945a9`: `WindowsCreateStringReference`
- `0x180094579`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18009485f`: `onecore\base\appcompat\programs\devicecensus\dlls\_wuinfo.cpp`
- `0x180094873`: `onecore\base\appcompat\programs\devicecensus\dlls\_wuinfo.cpp`
- `0x1800945fd`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int8 __fastcall WUInfo::GetIsStoreBlockedByPolicy(WUInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rcx
  unsigned __int8 result; // al
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
  try
  {
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
        (void *)0x36C,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\_wuinfo.cpp",
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
        (void *)0x373,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\_wuinfo.cpp",
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
      result = 2;
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
        JUMPOUT(0x1800948B8LL);
      }
      result = v18;
    }
  }
  catch ( ... )
  {
    return 2;
  }
  return result;
}

```

## disassembly

```asm
0x180094550  push    rbx
0x180094552  push    rsi
0x180094553  push    rdi
0x180094554  push    r14
0x180094556  push    r15
0x180094558  sub     rsp, 0B0h
0x18009455f  mov     rax, cs:__security_cookie
0x180094566  xor     rax, rsp
0x180094569  mov     [rsp+0D8h+var_38], rax
0x180094571  xor     edx, edx; hFile
0x180094573  mov     r8d, 800h; dwFlags
0x180094579  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180094580  call    cs:__imp_LoadLibraryExW
0x180094586  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18009458d  mov     [rsp+0D8h+var_90], r15
0x180094592  mov     [rsp+0D8h+var_88], rax
0x180094597  xor     r14d, r14d
0x18009459a  test    rax, rax
0x18009459d  jnz     short loc_1800945A9
0x18009459f  mov     ecx, r14d
0x1800945a2  mov     [rsp+0D8h+var_80], rcx
0x1800945a7  jmp     short loc_1800945C6
0x1800945a9  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800945b0  mov     rcx, rax; hModule
0x1800945b3  call    cs:__imp_GetProcAddress
0x1800945b9  mov     rcx, rax
0x1800945bc  mov     [rsp+0D8h+var_80], rax
0x1800945c1  mov     rax, [rsp+0D8h+var_88]
0x1800945c6  mov     [rsp+0D8h+var_98], r14
0x1800945cb  mov     [rsp+0D8h+var_A0], r14
0x1800945d0  mov     [rsp+0D8h+var_A7], r14b
0x1800945d5  test    rcx, rcx
0x1800945d8  jnz     short loc_1800945FD
0x1800945da  mov     [rsp+0D8h+var_90], r15
0x1800945df  test    rax, rax
0x1800945e2  jz      short loc_1800945F6
0x1800945e4  lea     rcx, [rsp+0D8h+var_90]
0x1800945e9  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800945ee  test    al, al
0x1800945f0  jz      loc_180094828
0x1800945f6  mov     al, 2
0x1800945f8  jmp     loc_180094809
0x1800945fd  lea     r8, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180094604  lea     rdx, [rsp+0D8h+var_90]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x180094609  lea     rcx, [rsp+0D8h+var_78]; this
0x18009460e  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x180094613  lea     rdx, [rsp+0D8h+var_98]
0x180094618  mov     rcx, [rax]
0x18009461b  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x180094620  test    eax, eax
0x180094622  jns     short loc_180094681
0x180094624  mov     rcx, [rsp+0D8h+var_A0]
0x180094629  test    rcx, rcx
0x18009462c  jz      short loc_180094640
0x18009462e  mov     [rsp+0D8h+var_A0], r14
0x180094633  mov     rax, [rcx]
0x180094636  mov     rax, [rax+10h]
0x18009463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009463f  nop
0x180094640  mov     rcx, [rsp+0D8h+var_98]
0x180094645  test    rcx, rcx
0x180094648  jz      short loc_18009465C
0x18009464a  mov     [rsp+0D8h+var_98], r14
0x18009464f  mov     rax, [rcx]
0x180094652  mov     rax, [rax+10h]
0x180094656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009465b  nop
0x18009465c  mov     [rsp+0D8h+var_90], r15
0x180094661  cmp     [rsp+0D8h+var_88], r14
0x180094666  jz      short loc_18009467A
0x180094668  lea     rcx, [rsp+0D8h+var_90]
0x18009466d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180094672  test    al, al
0x180094674  jz      loc_180094842
0x18009467a  mov     al, 2
0x18009467c  jmp     loc_180094809
0x180094681  mov     rbx, [rsp+0D8h+var_98]
0x180094686  mov     rax, [rbx]
0x180094689  mov     rdi, [rax+0B8h]
0x180094690  mov     rcx, [rsp+0D8h+var_A0]
0x180094695  test    rcx, rcx
0x180094698  jz      short loc_1800946AC
0x18009469a  mov     [rsp+0D8h+var_A0], r14
0x18009469f  mov     rax, [rcx]
0x1800946a2  mov     rax, [rax+10h]
0x1800946a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800946ab  nop
0x1800946ac  lea     r8, aCnMicrosoftCor; "CN=Microsoft Corporation, O=Microsoft C"...
0x1800946b3  lea     rdx, [rsp+0D8h+var_90]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800946b8  lea     rcx, [rsp+0D8h+var_78]; this
0x1800946bd  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800946c2  mov     rsi, [rax]
0x1800946c5  lea     r8, aMicrosoftWindo_0; "Microsoft.WindowsStore"
0x1800946cc  lea     rdx, [rsp+0D8h+var_90]; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800946d1  lea     rcx, [rsp+0D8h+var_58]; this
0x1800946d9  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800946de  lea     r9, [rsp+0D8h+var_A0]
0x1800946e3  mov     r8, rsi
0x1800946e6  mov     rdx, [rax]
0x1800946e9  mov     rcx, rbx
0x1800946ec  mov     rax, rdi
0x1800946ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800946f4  mov     rcx, [rsp+0D8h]
0x1800946fc  test    eax, eax
0x1800946fe  js      loc_18009485C
0x180094704  mov     [rsp+0D8h+var_A8], r14b
0x180094709  mov     rbx, [rsp+0D8h+var_A0]
0x18009470e  lea     r9, [rsp+0D8h+var_A8]
0x180094713  mov     rcx, rbx
0x180094716  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18009471b  test    eax, eax
0x18009471d  js      short loc_180094734
0x18009471f  mov     rax, [rbx]
0x180094722  lea     rdx, [rsp+0D8h+var_A7]
0x180094727  mov     rcx, rbx
0x18009472a  mov     rax, [rax+40h]
0x18009472e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094733  nop
0x180094734  mov     rcx, [rsp+0D8h]; this
0x18009473c  test    eax, eax
0x18009473e  js      loc_180094870
0x180094744  cmp     [rsp+0D8h+var_A8], r14b
0x180094749  jz      short loc_1800947A5
0x18009474b  mov     rcx, [rsp+0D8h+var_A0]
0x180094750  test    rcx, rcx
0x180094753  jz      short loc_180094767
0x180094755  mov     [rsp+0D8h+var_A0], r14
0x18009475a  mov     rax, [rcx]
0x18009475d  mov     rax, [rax+10h]
0x180094761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094766  nop
0x180094767  mov     rcx, [rsp+0D8h+var_98]
0x18009476c  test    rcx, rcx
0x18009476f  jz      short loc_180094783
0x180094771  mov     [rsp+0D8h+var_98], r14
0x180094776  mov     rax, [rcx]
0x180094779  mov     rax, [rax+10h]
0x18009477d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094782  nop
0x180094783  mov     [rsp+0D8h+var_90], r15
0x180094788  cmp     [rsp+0D8h+var_88], r14
0x18009478d  jz      short loc_1800947A1
0x18009478f  lea     rcx, [rsp+0D8h+var_90]
0x180094794  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180094799  test    al, al
0x18009479b  jz      loc_180094885
0x1800947a1  mov     al, 2
0x1800947a3  jmp     short loc_180094809
0x1800947a5  cmp     [rsp+0D8h+var_A7], r14b
0x1800947aa  setnz   bl
0x1800947ad  mov     rcx, [rsp+0D8h+var_A0]
0x1800947b2  test    rcx, rcx
0x1800947b5  jz      short loc_1800947C9
0x1800947b7  mov     [rsp+0D8h+var_A0], r14
0x1800947bc  mov     rax, [rcx]
0x1800947bf  mov     rax, [rax+10h]
0x1800947c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800947c8  nop
0x1800947c9  mov     rcx, [rsp+0D8h+var_98]
0x1800947ce  test    rcx, rcx
0x1800947d1  jz      short loc_1800947E5
0x1800947d3  mov     [rsp+0D8h+var_98], r14
0x1800947d8  mov     rax, [rcx]
0x1800947db  mov     rax, [rax+10h]
0x1800947df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800947e4  nop
0x1800947e5  mov     [rsp+0D8h+var_90], r15
0x1800947ea  cmp     [rsp+0D8h+var_88], r14
0x1800947ef  jz      short loc_180094803
0x1800947f1  lea     rcx, [rsp+0D8h+var_90]
0x1800947f6  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800947fb  test    al, al
0x1800947fd  jz      loc_18009489F
0x180094803  mov     al, bl
0x180094805  jmp     short loc_180094809
0x180094807  mov     al, 2
0x180094809  mov     rcx, [rsp+0D8h+var_38]
0x180094811  xor     rcx, rsp; StackCookie
0x180094814  call    __security_check_cookie
0x180094819  add     rsp, 0B0h
0x180094820  pop     r15
0x180094822  pop     r14
0x180094824  pop     rdi
0x180094825  pop     rsi
0x180094826  pop     rbx
0x180094827  retn
0x180094828  call    cs:__imp_GetLastError
0x18009482e  test    eax, eax
0x180094830  jle     short loc_18009483A
0x180094832  movzx   eax, ax
0x180094835  or      eax, 80070000h
0x18009483a  mov     ecx, eax; this
0x18009483c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180094841  int     3; Trap to Debugger
0x180094842  call    cs:__imp_GetLastError
0x180094848  test    eax, eax
0x18009484a  jle     short loc_180094854
0x18009484c  movzx   eax, ax
0x18009484f  or      eax, 80070000h
0x180094854  mov     ecx, eax; this
0x180094856  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009485b  nop
0x18009485c  mov     r9d, eax; char *
0x18009485f  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\programs\\dev"...
0x180094866  mov     edx, 36Ch; void *
0x18009486b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180094870  mov     r9d, eax; char *
0x180094873  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appcompat\\programs\\dev"...
0x18009487a  mov     edx, 373h; void *
0x18009487f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180094885  call    cs:__imp_GetLastError
0x18009488b  test    eax, eax
0x18009488d  jle     short loc_180094897
0x18009488f  movzx   eax, ax
0x180094892  or      eax, 80070000h
0x180094897  mov     ecx, eax; this
0x180094899  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009489e  int     3; Trap to Debugger
0x18009489f  call    cs:__imp_GetLastError
0x1800948a5  test    eax, eax
0x1800948a7  jle     short loc_1800948B1
0x1800948a9  movzx   eax, ax
0x1800948ac  or      eax, 80070000h
0x1800948b1  mov     ecx, eax; this
0x1800948b3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
