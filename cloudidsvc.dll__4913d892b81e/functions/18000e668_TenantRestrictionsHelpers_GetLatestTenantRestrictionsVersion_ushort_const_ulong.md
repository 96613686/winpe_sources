# TenantRestrictionsHelpers::GetLatestTenantRestrictionsVersion(ushort const *,ulong)

- ea: `0x18000e668`
- end: `0x18000e8e2`
- name: `?GetLatestTenantRestrictionsVersion@TenantRestrictionsHelpers@@YA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBGK@Z`
- size: `634`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x180001a50`
- `0x1800040f4`
- `0x180004740`
- `0x180008d64`
- `0x180009da8`
- `0x180009e50`
- `0x18000c338`
- `0x18000c41c`
- `0x18000c498`
- `0x18000c874`
- `0x18000d0b4`
- `0x18000da04`
- `0x18000dcdc`
- `0x18000dd6c`
- `0x18000e4b0`
- `0x18000e5e0`
- `0x18000e668`
- `0x18000ed90`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e810`

## string_xrefs

- `0x18000e8a6`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e8bb`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e8d0`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
_QWORD *__fastcall TenantRestrictionsHelpers::GetLatestTenantRestrictionsVersion(_QWORD *a1, __int64 a2, int a3)
{
  __int64 v4; // rax
  unsigned int v5; // r15d
  struct Windows::Data::Json::IJsonArray *v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // r14
  HSTRING v15; // rbx
  __int64 v16; // rax
  int v17; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rbx
  PCWSTR v20; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  struct Windows::Data::Json::IJsonArray *v23; // rdx
  int v25; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  __int64 v27; // [rsp+38h] [rbp-61h] BYREF
  HSTRING v28; // [rsp+40h] [rbp-59h] BYREF
  TenantRestrictionsHelpers *v29; // [rsp+48h] [rbp-51h] BYREF
  int v30; // [rsp+50h] [rbp-49h]
  _BYTE v31[8]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD *v32; // [rsp+60h] [rbp-39h]
  _BYTE v33[16]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v34[32]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v35[4]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v32 = a1;
  v30 = 0;
  TenantRestrictionsHelpers::GetTenantRestrictionsO365ApiData(v35, (__int64)L"/version", 0, a2, a3);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  TenantRestrictionsHelpers::GetJsonArray((__int64 *)&v29, v4);
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(a1);
  v30 = 1;
  v5 = 0;
  if ( (unsigned int)TenantRestrictionsHelpers::GetJsonArraySize(v29, v6) )
  {
    do
    {
      v27 = 0;
      v7 = *(_QWORD *)v29;
      v27 = 0;
      v8 = (*(__int64 (__fastcall **)(TenantRestrictionsHelpers *, _QWORD, __int64 *))(v7 + 48))(v29, v5, &v27);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x121,
          (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
          (const char *)(unsigned int)v8,
          v25);
      v28 = 0;
      string = 0;
      v9 = v27;
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v27 + 80LL);
      v28 = 0;
      v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, off_180013450);
      v12 = v10(v9, *(_QWORD *)(v11 + 24), &v28);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x125,
          (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
          (const char *)(unsigned int)v12,
          v25);
      v13 = v27;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v27 + 80LL);
      v15 = string;
      if ( string )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v31);
        WindowsDeleteString(v15);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v31);
      }
      string = 0;
      v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, off_180013438);
      v17 = v14(v13, *(_QWORD *)(v16 + 24), &string);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x126,
          (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
          (const char *)(unsigned int)v17,
          v25);
      StringRawBuffer = WindowsGetStringRawBuffer(v28, 0);
      std::wstring::wstring((__int64)v34, (__int64)StringRawBuffer);
      v19 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(
                         a1,
                         (__int64)v33,
                         (__int64)v34);
      v20 = WindowsGetStringRawBuffer(string, 0);
      v21 = std::_WChar_traits<unsigned short>::length(v20);
      std::wstring::_Assign<unsigned short>(v19 + 48, v22, v21);
      std::wstring::_Tidy_deallocate((__int64)v34);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
      wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v27);
      ++v5;
    }
    while ( v5 < (unsigned int)TenantRestrictionsHelpers::GetJsonArraySize(v29, v23) );
  }
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>((__int64 *)&v29);
  std::wstring::_Tidy_deallocate((__int64)v35);
  return a1;
}

```

## disassembly

```asm
0x18000e668  mov     [rsp-8+arg_18], rbx
0x18000e66d  push    rbp
0x18000e66e  push    rsi
0x18000e66f  push    rdi
0x18000e670  push    r14
0x18000e672  push    r15
0x18000e674  lea     rbp, [rsp-37h]
0x18000e679  sub     rsp, 0D0h
0x18000e680  mov     rax, cs:__security_cookie
0x18000e687  xor     rax, rsp
0x18000e68a  mov     [rbp+57h+var_30], rax
0x18000e68e  mov     rsi, rcx
0x18000e691  mov     [rbp+57h+var_90], rcx
0x18000e695  mov     [rbp+57h+var_A0], 0
0x18000e69c  mov     [rsp+0F0h+var_D0], r8d; int
0x18000e6a1  mov     r9, rdx
0x18000e6a4  xor     r8d, r8d
0x18000e6a7  lea     rdx, aVersion; "/version"
0x18000e6ae  lea     rcx, [rbp+57h+var_50]
0x18000e6b2  call    ?GetTenantRestrictionsO365ApiData@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00K@Z; TenantRestrictionsHelpers::GetTenantRestrictionsO365ApiData(ushort const *,ushort const *,ushort const *,ulong)
0x18000e6b7  nop
0x18000e6b8  lea     rcx, [rbp+57h+var_50]
0x18000e6bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000e6c1  mov     rdx, rax
0x18000e6c4  lea     rcx, [rbp+57h+var_A8]
0x18000e6c8  call    ?GetJsonArray@TenantRestrictionsHelpers@@YA?AV?$com_ptr_t@UIJsonArray@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z; TenantRestrictionsHelpers::GetJsonArray(ushort const *)
0x18000e6cd  nop
0x18000e6ce  mov     rcx, rsi
0x18000e6d1  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x18000e6d6  mov     [rbp+57h+var_A0], 1
0x18000e6dd  xor     r15d, r15d
0x18000e6e0  mov     rcx, [rbp+57h+var_A8]; this
0x18000e6e4  call    ?GetJsonArraySize@TenantRestrictionsHelpers@@YAIPEAUIJsonArray@Json@Data@Windows@@@Z; TenantRestrictionsHelpers::GetJsonArraySize(Windows::Data::Json::IJsonArray *)
0x18000e6e9  test    eax, eax
0x18000e6eb  jz      loc_18000E86A
0x18000e6f1  mov     [rbp+57h+var_B8], 0
0x18000e6f9  mov     rcx, [rbp+57h+var_A8]
0x18000e6fd  mov     rax, [rcx]
0x18000e700  mov     [rbp+57h+var_B8], 0
0x18000e708  lea     r8, [rbp+57h+var_B8]
0x18000e70c  mov     edx, r15d
0x18000e70f  mov     rax, [rax+30h]
0x18000e713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e718  mov     rcx, [rbp+5Fh]; this
0x18000e71c  test    eax, eax
0x18000e71e  js      loc_18000E8CD
0x18000e724  mov     [rbp+57h+var_B0], 0
0x18000e72c  mov     [rbp+57h+string], 0
0x18000e734  mov     rdi, [rbp+57h+var_B8]
0x18000e738  mov     rax, [rdi]
0x18000e73b  mov     rbx, [rax+50h]
0x18000e73f  mov     [rbp+57h+var_B0], 0
0x18000e747  lea     rdx, off_180013450; "instance"
0x18000e74e  lea     rcx, [rbp+57h+var_70]
0x18000e752  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000e757  nop
0x18000e758  lea     r8, [rbp+57h+var_B0]
0x18000e75c  mov     rdx, [rax+18h]
0x18000e760  mov     rcx, rdi
0x18000e763  mov     rax, rbx
0x18000e766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e76b  mov     rcx, [rbp+5Fh]; this
0x18000e76f  test    eax, eax
0x18000e771  js      loc_18000E8B8
0x18000e777  mov     rdi, [rbp+57h+var_B8]
0x18000e77b  mov     rax, [rdi]
0x18000e77e  mov     r14, [rax+50h]
0x18000e782  mov     rbx, [rbp+57h+string]
0x18000e786  test    rbx, rbx
0x18000e789  jz      short loc_18000E7A6
0x18000e78b  lea     rcx, [rbp+57h+var_98]; this
0x18000e78f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e794  mov     rcx, rbx; string
0x18000e797  call    cs:__imp_WindowsDeleteString
0x18000e79d  lea     rcx, [rbp+57h+var_98]; this
0x18000e7a1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e7a6  mov     [rbp+57h+string], 0
0x18000e7ae  lea     rdx, off_180013438; "latest"
0x18000e7b5  lea     rcx, [rbp+57h+var_70]
0x18000e7b9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000e7be  nop
0x18000e7bf  lea     r8, [rbp+57h+string]
0x18000e7c3  mov     rdx, [rax+18h]
0x18000e7c7  mov     rcx, rdi
0x18000e7ca  mov     rax, r14
0x18000e7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d2  mov     rcx, [rbp+5Fh]; this
0x18000e7d6  test    eax, eax
0x18000e7d8  js      loc_18000E8A3
0x18000e7de  xor     edx, edx; length
0x18000e7e0  mov     rcx, [rbp+57h+var_B0]; string
0x18000e7e4  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e7ea  mov     rdx, rax
0x18000e7ed  lea     rcx, [rbp+57h+var_70]
0x18000e7f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000e7f6  nop
0x18000e7f7  lea     r8, [rbp+57h+var_70]
0x18000e7fb  lea     rdx, [rbp+57h+var_80]
0x18000e7ff  mov     rcx, rsi
0x18000e802  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18000e807  mov     rbx, [rax]
0x18000e80a  xor     edx, edx; length
0x18000e80c  mov     rcx, [rbp+57h+string]; string
0x18000e810  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e816  mov     rcx, rax
0x18000e819  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000e81e  mov     r8, rax
0x18000e821  mov     rdx, rcx
0x18000e824  lea     rcx, [rbx+30h]
0x18000e828  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000e82d  nop
0x18000e82e  lea     rcx, [rbp+57h+var_70]
0x18000e832  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e837  nop
0x18000e838  lea     rcx, [rbp+57h+string]
0x18000e83c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000e841  nop
0x18000e842  lea     rcx, [rbp+57h+var_B0]
0x18000e846  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000e84b  nop
0x18000e84c  lea     rcx, [rbp+57h+var_B8]
0x18000e850  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000e855  inc     r15d
0x18000e858  mov     rcx, [rbp+57h+var_A8]; this
0x18000e85c  call    ?GetJsonArraySize@TenantRestrictionsHelpers@@YAIPEAUIJsonArray@Json@Data@Windows@@@Z; TenantRestrictionsHelpers::GetJsonArraySize(Windows::Data::Json::IJsonArray *)
0x18000e861  cmp     r15d, eax
0x18000e864  jb      loc_18000E6F1
0x18000e86a  lea     rcx, [rbp+57h+var_A8]
0x18000e86e  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000e873  nop
0x18000e874  lea     rcx, [rbp+57h+var_50]
0x18000e878  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e87d  mov     rax, rsi
0x18000e880  mov     rcx, [rbp+57h+var_30]
0x18000e884  xor     rcx, rsp; StackCookie
0x18000e887  call    __security_check_cookie
0x18000e88c  mov     rbx, [rsp+0F0h+arg_18]
0x18000e894  add     rsp, 0D0h
0x18000e89b  pop     r15
0x18000e89d  pop     r14
0x18000e89f  pop     rdi
0x18000e8a0  pop     rsi
0x18000e8a1  pop     rbp
0x18000e8a2  retn
0x18000e8a3  mov     r9d, eax; char *
0x18000e8a6  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e8ad  mov     edx, 126h; void *
0x18000e8b2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e8b8  mov     r9d, eax; char *
0x18000e8bb  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e8c2  mov     edx, 125h; void *
0x18000e8c7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e8cd  mov     r9d, eax; char *
0x18000e8d0  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e8d7  mov     edx, 121h; void *
0x18000e8dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
