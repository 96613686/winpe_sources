# TenantRestrictionsHelpers::ParseTenantRestrictionsHostnameAndIPData(ushort const *)

- ea: `0x18000f7cc`
- end: `0x18000fc00`
- name: `?ParseTenantRestrictionsHostnameAndIPData@TenantRestrictionsHelpers@@YA?AUTenantRestrictionsData@1@PEBG@Z`
- size: `1076`
- prototype: `TenantRestrictionsHelpers *__fastcall(TenantRestrictionsHelpers *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x180001a50`
- `0x180009a80`
- `0x180009da8`
- `0x180009ff0`
- `0x18000c338`
- `0x18000c41c`
- `0x18000c498`
- `0x18000d0b4`
- `0x18000dbd4`
- `0x18000dcdc`
- `0x18000dd6c`
- `0x18000e4b0`
- `0x18000e5e0`
- `0x18000f7cc`
- `0x18000fd90`
- `0x18000fea0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fa1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fae3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fa1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fae3`

## string_xrefs

- `0x18000fb9a`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000fbaf`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000fbc4`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000fbd9`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000fbee`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
TenantRestrictionsHelpers *__fastcall TenantRestrictionsHelpers::ParseTenantRestrictionsHostnameAndIPData(
        TenantRestrictionsHelpers *a1,
        __int64 a2)
{
  struct Windows::Data::Json::IJsonArray *v4; // rdx
  unsigned int JsonArraySize; // r15d
  unsigned int i; // r14d
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, int *); // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v15; // rax
  int v16; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rdi
  void (__fastcall *v19)(__int64, _QWORD, TenantRestrictionsHelpers **); // rbx
  __int64 v20; // rax
  __int64 v21; // rbx
  void (__fastcall *v22)(__int64, _QWORD, TenantRestrictionsHelpers **); // rdi
  TenantRestrictionsHelpers *v23; // rcx
  __int64 v24; // rax
  struct Windows::Data::Json::IJsonArray *v25; // rdx
  struct Windows::Data::Json::IJsonArray *v26; // rdx
  unsigned int v27; // edi
  unsigned int j; // ebx
  __int64 v29; // rax
  int v30; // eax
  PCWSTR v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  unsigned int v34; // edi
  unsigned int k; // ebx
  __int64 v36; // rax
  int v37; // eax
  PCWSTR v38; // rax
  int v40; // [rsp+20h] [rbp-A9h] BYREF
  HSTRING v41; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v42; // [rsp+30h] [rbp-99h] BYREF
  TenantRestrictionsHelpers *v43; // [rsp+38h] [rbp-91h] BYREF
  TenantRestrictionsHelpers *v44; // [rsp+40h] [rbp-89h] BYREF
  HSTRING string; // [rsp+48h] [rbp-81h] BYREF
  int v46; // [rsp+50h] [rbp-79h]
  TenantRestrictionsHelpers *v47[2]; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v48[16]; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v49[16]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v50[16]; // [rsp+88h] [rbp-41h] BYREF
  _BYTE v51[32]; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v52[32]; // [rsp+B8h] [rbp-11h] BYREF
  _BYTE v53[32]; // [rsp+D8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v47[1] = a1;
  TenantRestrictionsHelpers::TenantRestrictionsData::TenantRestrictionsData(a1);
  v46 = 1;
  TenantRestrictionsHelpers::GetJsonArray((__int64 *)v47, a2);
  JsonArraySize = TenantRestrictionsHelpers::GetJsonArraySize(v47[0], v4);
  for ( i = 0; i < JsonArraySize; ++i )
  {
    v42 = 0;
    v7 = *(_QWORD *)v47[0];
    v42 = 0;
    v8 = (*(__int64 (__fastcall **)(TenantRestrictionsHelpers *, _QWORD, __int64 *))(v7 + 48))(v47[0], i, &v42);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x137,
        (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)(unsigned int)v8,
        v40);
    LOBYTE(v40) = 0;
    v9 = v42;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v42 + 96LL);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, off_180013440);
    v12 = v10(v9, *(_QWORD *)(v11 + 24), &v40);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x13A,
        (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)(unsigned int)v12,
        v40);
    if ( (_BYTE)v40 )
    {
      string = 0;
      v13 = v42;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v42 + 80LL);
      string = 0;
      v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, &off_180013460);
      v16 = v14(v13, *(_QWORD *)(v15 + 24), &string);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x141,
          (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
          (const char *)(unsigned int)v16,
          v40);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring((__int64)v53, (__int64)StringRawBuffer);
      if ( !std::wstring::compare((__int64)v53, (__int64)L"Allow")
        || !std::wstring::compare((__int64)v53, (__int64)L"Optimize") )
      {
        v44 = 0;
        v43 = 0;
        v18 = v42;
        v19 = *(void (__fastcall **)(__int64, _QWORD, TenantRestrictionsHelpers **))(*(_QWORD *)v42 + 72LL);
        v44 = 0;
        v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, off_180013448);
        v19(v18, *(_QWORD *)(v20 + 24), &v44);
        v21 = v42;
        v22 = *(void (__fastcall **)(__int64, _QWORD, TenantRestrictionsHelpers **))(*(_QWORD *)v42 + 72LL);
        v23 = v43;
        v43 = 0;
        if ( v23 )
          (*(void (__fastcall **)(TenantRestrictionsHelpers *))(*(_QWORD *)v23 + 16LL))(v23);
        v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, off_180013458);
        v22(v21, *(_QWORD *)(v24 + 24), &v43);
        v27 = TenantRestrictionsHelpers::GetJsonArraySize(v44, v25);
        for ( j = 0; j < v27; ++j )
        {
          v41 = 0;
          v29 = *(_QWORD *)v44;
          v41 = 0;
          v30 = (*(__int64 (__fastcall **)(TenantRestrictionsHelpers *, _QWORD, HSTRING *))(v29 + 64))(v44, j, &v41);
          if ( v30 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x152,
              (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
              (const char *)(unsigned int)v30,
              v40);
          v31 = WindowsGetStringRawBuffer(v41, 0);
          std::wstring::wstring((__int64)v51, (__int64)v31);
          if ( *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() == 42 )
          {
            v33 = std::wstring::substr(v51, v52, v32, -1);
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
              (char *)a1 + 16,
              v48,
              v33);
            std::wstring::_Tidy_deallocate((__int64)v52);
          }
          else
          {
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
              a1,
              v49,
              v51);
          }
          std::wstring::_Tidy_deallocate((__int64)v51);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
        }
        v34 = TenantRestrictionsHelpers::GetJsonArraySize(v43, v26);
        for ( k = 0; k < v34; ++k )
        {
          v41 = 0;
          v36 = *(_QWORD *)v43;
          v41 = 0;
          v37 = (*(__int64 (__fastcall **)(TenantRestrictionsHelpers *, _QWORD, HSTRING *))(v36 + 64))(v43, k, &v41);
          if ( v37 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x163,
              (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
              (const char *)(unsigned int)v37,
              v40);
          v38 = WindowsGetStringRawBuffer(v41, 0);
          std::wstring::wstring((__int64)v51, (__int64)v38);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
            (char *)a1 + 32,
            v50,
            v51);
          std::wstring::_Tidy_deallocate((__int64)v51);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
        }
        wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>((__int64 *)&v43);
        wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>((__int64 *)&v44);
      }
      std::wstring::_Tidy_deallocate((__int64)v53);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    }
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v42);
  }
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>((__int64 *)v47);
  return a1;
}

```

## disassembly

```asm
0x18000f7cc  mov     [rsp-8+arg_10], rbx
0x18000f7d1  mov     [rsp-8+arg_18], rsi
0x18000f7d6  push    rbp
0x18000f7d7  push    rdi
0x18000f7d8  push    r12
0x18000f7da  push    r14
0x18000f7dc  push    r15
0x18000f7de  lea     rbp, [rsp-37h]
0x18000f7e3  sub     rsp, 100h
0x18000f7ea  mov     rax, cs:__security_cookie
0x18000f7f1  xor     rax, rsp
0x18000f7f4  mov     [rbp+57h+var_28], rax
0x18000f7f8  mov     rbx, rdx
0x18000f7fb  mov     rsi, rcx
0x18000f7fe  mov     [rbp+57h+var_C0], rcx
0x18000f802  xor     r12d, r12d
0x18000f805  mov     [rbp+57h+var_D0], r12d
0x18000f809  call    ??0TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::TenantRestrictionsData(void)
0x18000f80e  mov     [rbp+57h+var_D0], 1
0x18000f815  mov     rdx, rbx
0x18000f818  lea     rcx, [rbp+57h+var_C8]
0x18000f81c  call    ?GetJsonArray@TenantRestrictionsHelpers@@YA?AV?$com_ptr_t@UIJsonArray@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z; TenantRestrictionsHelpers::GetJsonArray(ushort const *)
0x18000f821  nop
0x18000f822  mov     rcx, [rbp+57h+var_C8]; this
0x18000f826  call    ?GetJsonArraySize@TenantRestrictionsHelpers@@YAIPEAUIJsonArray@Json@Data@Windows@@@Z; TenantRestrictionsHelpers::GetJsonArraySize(Windows::Data::Json::IJsonArray *)
0x18000f82b  mov     r15d, eax
0x18000f82e  mov     r14d, r12d
0x18000f831  test    eax, eax
0x18000f833  jz      loc_18000FB63
0x18000f839  mov     [rsp+120h+var_F0], r12
0x18000f83e  mov     rcx, [rbp+57h+var_C8]
0x18000f842  mov     rax, [rcx]
0x18000f845  mov     [rsp+120h+var_F0], r12
0x18000f84a  lea     r8, [rsp+120h+var_F0]
0x18000f84f  mov     edx, r14d
0x18000f852  mov     rax, [rax+30h]
0x18000f856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f85b  mov     rcx, [rbp+5Fh]; this
0x18000f85f  test    eax, eax
0x18000f861  js      loc_18000FBEB
0x18000f867  mov     byte ptr [rsp+120h+var_100], r12b; int
0x18000f86c  mov     rdi, [rsp+120h+var_F0]
0x18000f871  mov     rax, [rdi]
0x18000f874  mov     rbx, [rax+60h]
0x18000f878  lea     rdx, off_180013440; "required"
0x18000f87f  lea     rcx, [rbp+57h+var_68]
0x18000f883  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000f888  nop
0x18000f889  lea     r8, [rsp+120h+var_100]
0x18000f88e  mov     rdx, [rax+18h]
0x18000f892  mov     rcx, rdi
0x18000f895  mov     rax, rbx
0x18000f898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f89d  mov     rcx, [rbp+5Fh]; this
0x18000f8a1  test    eax, eax
0x18000f8a3  js      loc_18000FBD6
0x18000f8a9  cmp     byte ptr [rsp+120h+var_100], r12b
0x18000f8ae  jz      loc_18000FB4D
0x18000f8b4  mov     [rsp+120h+string], r12
0x18000f8b9  mov     rdi, [rsp+120h+var_F0]
0x18000f8be  mov     rax, [rdi]
0x18000f8c1  mov     rbx, [rax+50h]
0x18000f8c5  mov     [rsp+120h+string], r12
0x18000f8ca  lea     rdx, off_180013460; "category"
0x18000f8d1  lea     rcx, [rbp+57h+var_68]
0x18000f8d5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000f8da  nop
0x18000f8db  lea     r8, [rsp+120h+string]
0x18000f8e0  mov     rdx, [rax+18h]
0x18000f8e4  mov     rcx, rdi
0x18000f8e7  mov     rax, rbx
0x18000f8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ef  mov     rcx, [rbp+5Fh]; this
0x18000f8f3  test    eax, eax
0x18000f8f5  js      loc_18000FBC1
0x18000f8fb  xor     edx, edx; length
0x18000f8fd  mov     rcx, [rsp+120h+string]; string
0x18000f902  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f908  mov     rdx, rax
0x18000f90b  lea     rcx, [rbp+57h+var_48]
0x18000f90f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000f914  nop
0x18000f915  lea     rdx, aAllow; "Allow"
0x18000f91c  lea     rcx, [rbp+57h+var_48]
0x18000f920  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18000f925  test    eax, eax
0x18000f927  jz      short loc_18000F941
0x18000f929  lea     rdx, aOptimize; "Optimize"
0x18000f930  lea     rcx, [rbp+57h+var_48]
0x18000f934  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18000f939  test    eax, eax
0x18000f93b  jnz     loc_18000FB38
0x18000f941  mov     [rsp+120h+var_E0], r12
0x18000f946  mov     [rsp+120h+var_E8], r12
0x18000f94b  mov     rdi, [rsp+120h+var_F0]
0x18000f950  mov     rax, [rdi]
0x18000f953  mov     rbx, [rax+48h]
0x18000f957  mov     [rsp+120h+var_E0], r12
0x18000f95c  lea     rdx, off_180013448; "urls"
0x18000f963  lea     rcx, [rbp+57h+var_68]
0x18000f967  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000f96c  nop
0x18000f96d  lea     r8, [rsp+120h+var_E0]
0x18000f972  mov     rdx, [rax+18h]
0x18000f976  mov     rcx, rdi
0x18000f979  mov     rax, rbx
0x18000f97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f981  nop
0x18000f982  mov     rbx, [rsp+120h+var_F0]
0x18000f987  mov     rax, [rbx]
0x18000f98a  mov     rdi, [rax+48h]
0x18000f98e  mov     rcx, [rsp+120h+var_E8]
0x18000f993  mov     [rsp+120h+var_E8], r12
0x18000f998  test    rcx, rcx
0x18000f99b  jz      short loc_18000F9AA
0x18000f99d  mov     rax, [rcx]
0x18000f9a0  mov     rax, [rax+10h]
0x18000f9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9a9  nop
0x18000f9aa  lea     rdx, off_180013458; "ips"
0x18000f9b1  lea     rcx, [rbp+57h+var_68]
0x18000f9b5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000f9ba  nop
0x18000f9bb  lea     r8, [rsp+120h+var_E8]
0x18000f9c0  mov     rdx, [rax+18h]
0x18000f9c4  mov     rcx, rbx
0x18000f9c7  mov     rax, rdi
0x18000f9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9cf  nop
0x18000f9d0  mov     rcx, [rsp+120h+var_E0]; this
0x18000f9d5  call    ?GetJsonArraySize@TenantRestrictionsHelpers@@YAIPEAUIJsonArray@Json@Data@Windows@@@Z; TenantRestrictionsHelpers::GetJsonArraySize(Windows::Data::Json::IJsonArray *)
0x18000f9da  mov     edi, eax
0x18000f9dc  mov     ebx, r12d
0x18000f9df  test    eax, eax
0x18000f9e1  jz      loc_18000FA9B
0x18000f9e7  mov     [rsp+120h+var_F8], r12
0x18000f9ec  mov     rcx, [rsp+120h+var_E0]
0x18000f9f1  mov     rax, [rcx]
0x18000f9f4  mov     [rsp+120h+var_F8], r12
0x18000f9f9  lea     r8, [rsp+120h+var_F8]
0x18000f9fe  mov     edx, ebx
0x18000fa00  mov     rax, [rax+40h]
0x18000fa04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa09  mov     rcx, [rbp+5Fh]; this
0x18000fa0d  test    eax, eax
0x18000fa0f  js      loc_18000FB97
0x18000fa15  xor     edx, edx; length
0x18000fa17  mov     rcx, [rsp+120h+var_F8]; string
0x18000fa1c  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fa22  mov     rdx, rax
0x18000fa25  lea     rcx, [rbp+57h+var_88]
0x18000fa29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000fa2e  nop
0x18000fa2f  lea     rcx, [rbp+57h+var_88]
0x18000fa33  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000fa38  cmp     word ptr [rax], 2Ah ; '*'
0x18000fa3c  jnz     short loc_18000FA6C
0x18000fa3e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000fa42  lea     rdx, [rbp+57h+var_68]
0x18000fa46  lea     rcx, [rbp+57h+var_88]
0x18000fa4a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000fa4f  nop
0x18000fa50  lea     rcx, [rsi+10h]
0x18000fa54  mov     r8, rax
0x18000fa57  lea     rdx, [rbp+57h+var_B8]
0x18000fa5b  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000fa60  nop
0x18000fa61  lea     rcx, [rbp+57h+var_68]
0x18000fa65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fa6a  jmp     short loc_18000FA7D
0x18000fa6c  lea     r8, [rbp+57h+var_88]
0x18000fa70  lea     rdx, [rbp+57h+var_A8]
0x18000fa74  mov     rcx, rsi
0x18000fa77  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18000fa7c  nop
0x18000fa7d  lea     rcx, [rbp+57h+var_88]
0x18000fa81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fa86  nop
0x18000fa87  lea     rcx, [rsp+120h+var_F8]
0x18000fa8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000fa91  inc     ebx
0x18000fa93  cmp     ebx, edi
0x18000fa95  jb      loc_18000F9E7
0x18000fa9b  mov     rcx, [rsp+120h+var_E8]; this
0x18000faa0  call    ?GetJsonArraySize@TenantRestrictionsHelpers@@YAIPEAUIJsonArray@Json@Data@Windows@@@Z; TenantRestrictionsHelpers::GetJsonArraySize(Windows::Data::Json::IJsonArray *)
0x18000faa5  mov     edi, eax
0x18000faa7  mov     ebx, r12d
0x18000faaa  test    eax, eax
0x18000faac  jz      short loc_18000FB22
0x18000faae  mov     [rsp+120h+var_F8], r12
0x18000fab3  mov     rcx, [rsp+120h+var_E8]
0x18000fab8  mov     rax, [rcx]
0x18000fabb  mov     [rsp+120h+var_F8], r12
0x18000fac0  lea     r8, [rsp+120h+var_F8]
0x18000fac5  mov     edx, ebx
0x18000fac7  mov     rax, [rax+40h]
0x18000facb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad0  mov     rcx, [rbp+5Fh]; this
0x18000fad4  test    eax, eax
0x18000fad6  js      loc_18000FBAC
0x18000fadc  xor     edx, edx; length
0x18000fade  mov     rcx, [rsp+120h+var_F8]; string
0x18000fae3  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fae9  mov     rdx, rax
0x18000faec  lea     rcx, [rbp+57h+var_88]
0x18000faf0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000faf5  nop
0x18000faf6  lea     rcx, [rsi+20h]
0x18000fafa  lea     r8, [rbp+57h+var_88]
0x18000fafe  lea     rdx, [rbp+57h+var_98]
0x18000fb02  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18000fb07  nop
0x18000fb08  lea     rcx, [rbp+57h+var_88]
0x18000fb0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fb11  nop
0x18000fb12  lea     rcx, [rsp+120h+var_F8]
0x18000fb17  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000fb1c  inc     ebx
0x18000fb1e  cmp     ebx, edi
0x18000fb20  jb      short loc_18000FAAE
0x18000fb22  lea     rcx, [rsp+120h+var_E8]
0x18000fb27  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000fb2c  nop
0x18000fb2d  lea     rcx, [rsp+120h+var_E0]
0x18000fb32  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000fb37  nop
0x18000fb38  lea     rcx, [rbp+57h+var_48]
0x18000fb3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fb41  nop
0x18000fb42  lea     rcx, [rsp+120h+string]
0x18000fb47  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000fb4c  nop
0x18000fb4d  lea     rcx, [rsp+120h+var_F0]
0x18000fb52  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000fb57  inc     r14d
0x18000fb5a  cmp     r14d, r15d
0x18000fb5d  jb      loc_18000F839
0x18000fb63  lea     rcx, [rbp+57h+var_C8]
0x18000fb67  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000fb6c  mov     rax, rsi
0x18000fb6f  mov     rcx, [rbp+57h+var_28]
0x18000fb73  xor     rcx, rsp; StackCookie
0x18000fb76  call    __security_check_cookie
0x18000fb7b  lea     r11, [rsp+120h+var_20]
0x18000fb83  mov     rbx, [r11+40h]
0x18000fb87  mov     rsi, [r11+48h]
0x18000fb8b  mov     rsp, r11
0x18000fb8e  pop     r15
0x18000fb90  pop     r14
0x18000fb92  pop     r12
0x18000fb94  pop     rdi
0x18000fb95  pop     rbp
0x18000fb96  retn
0x18000fb97  mov     r9d, eax; char *
0x18000fb9a  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fba1  mov     edx, 152h; void *
0x18000fba6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fbac  mov     r9d, eax; char *
0x18000fbaf  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fbb6  mov     edx, 163h; void *
0x18000fbbb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fbc1  mov     r9d, eax; char *
0x18000fbc4  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fbcb  mov     edx, 141h; void *
0x18000fbd0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fbd6  mov     r9d, eax; char *
0x18000fbd9  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fbe0  mov     edx, 13Ah; void *
0x18000fbe5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fbeb  mov     r9d, eax; char *
0x18000fbee  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fbf5  mov     edx, 137h; void *
0x18000fbfa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
