# FlagConfigurationEngine::FilterInventory(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,bool)

- ea: `0x18009f0f8`
- end: `0x18009f359`
- name: `?FilterInventory@FlagConfigurationEngine@@AEAA?AV?$vector@U?$pair@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@UInventoryFlagConfiguration@234@@std@@V?$allocator@U?$pair@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@UInventoryFlagConfiguration@234@@std@@@2@@std@@VFlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@_N@Z`
- size: `609`
- prototype: ``
- caller_count: `8`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009dfb0`
- `0x1800a0830`
- `0x1800a1210`
- `0x1800a1450`
- `0x1800a1500`
- `0x1800a1d20`
- `0x1800a25a0`
- `0x1800a2ae0`

## callees

- `0x180003220`
- `0x18000796c`
- `0x1800120a0`
- `0x180015af4`
- `0x180019890`
- `0x1800352c0`
- `0x180043ce8`
- `0x18005e758`
- `0x180074900`
- `0x180074ee0`
- `0x180087a90`
- `0x180089d74`
- `0x180089e34`
- `0x180089ea0`
- `0x18009c90c`
- `0x18009f0f8`
- `0x18009f360`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f1e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f1e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f246`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FlagConfigurationEngine::FilterInventory(
        int a1,
        __int64 a2,
        const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *a3,
        int (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        char a5)
{
  int (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, HSTRING *); // rbx
  int (__fastcall *v12)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rbx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // ebx
  int v18; // eax
  __int64 v19; // rdx
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[64]; // [rsp+E0h] [rbp-20h] BYREF
  const struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *v33; // [rsp+120h] [rbp+20h]
  _BYTE v34[56]; // [rsp+128h] [rbp+28h] BYREF

  v24[0] = a2;
  v33 = a3;
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v31);
  if ( a4 )
  {
    v22 = 0;
    v9 = **a4;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    if ( v9(a4, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v22) >= 0 )
    {
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        v25,
        v22);
      v27 = 0;
      v28 = -1;
      v29 = 0;
      while ( v26 != -1 )
      {
        v10 = *(_QWORD *)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator*(v25);
        v24[0] = v10;
        Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(v24);
        v23 = 0;
        string = 0;
        v11 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL);
        WindowsDeleteString(0);
        v23 = 0;
        if ( v11(v10, &v23) >= 0 )
        {
          v12 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 56LL);
          WindowsDeleteString(string);
          string = 0;
          if ( v12(v10, &string) >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            WindowsGetStringRawBuffer(v23, 0);
            std::wstring::wstring(v34);
            v14 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(
                               v31,
                               v30,
                               v34)
                + 48LL;
            v15 = -1;
            do
              ++v15;
            while ( StringRawBuffer[v15] );
            std::wstring::_Assign<unsigned short>(v14, StringRawBuffer, v15);
            std::wstring::_Tidy_deallocate(v34, v16);
          }
        }
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v23);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator++(v25);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v27);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v25);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  }
  v24[0] = v32;
  v17 = std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v32, v31);
  v18 = ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(
          (ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *)v34,
          a3);
  FlagConfigurationEngine::FilterInventory(a1, a2, v18, v17, a5);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v31);
  std::wstring::_Tidy_deallocate(a3, v19);
  return a2;
}

```

## disassembly

```asm
0x18009f0f8  push    rbp
0x18009f0fa  push    rbx
0x18009f0fb  push    rsi
0x18009f0fc  push    rdi
0x18009f0fd  push    r12
0x18009f0ff  push    r13
0x18009f101  push    r14
0x18009f103  push    r15
0x18009f105  lea     rbp, [rsp-78h]
0x18009f10a  sub     rsp, 178h
0x18009f111  mov     rax, cs:__security_cookie
0x18009f118  xor     rax, rsp
0x18009f11b  mov     [rbp+0B0h+var_50], rax
0x18009f11f  mov     rdi, r9
0x18009f122  mov     r14, r8
0x18009f125  mov     rsi, rdx
0x18009f128  mov     r15, rcx
0x18009f12b  mov     [rsp+1B0h+var_168], rdx
0x18009f130  mov     [rbp+0B0h+var_90], r8
0x18009f134  mov     r12b, [rbp+0B0h+arg_20]
0x18009f13b  xor     r13d, r13d
0x18009f13e  lea     rcx, [rbp+0B0h+var_110]
0x18009f142  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x18009f147  nop
0x18009f148  test    rdi, rdi
0x18009f14b  jz      loc_18009F2E7
0x18009f151  mov     [rsp+1B0h+var_178], r13
0x18009f156  mov     rax, [rdi]
0x18009f159  mov     rbx, [rax]
0x18009f15c  lea     rcx, [rsp+1B0h+var_178]
0x18009f161  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009f166  lea     r8, [rsp+1B0h+var_178]
0x18009f16b  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18009f172  mov     rcx, rdi
0x18009f175  mov     rax, rbx
0x18009f178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f17d  test    eax, eax
0x18009f17f  js      loc_18009F2DD
0x18009f185  mov     rdx, [rsp+1B0h+var_178]
0x18009f18a  lea     rcx, [rsp+1B0h+var_158]
0x18009f18f  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *> *)
0x18009f194  nop
0x18009f195  mov     [rsp+1B0h+var_140], r13
0x18009f19a  mov     [rsp+1B0h+var_138], 0FFFFFFFFh
0x18009f1a2  mov     [rbp+0B0h+var_130], r13
0x18009f1a6  cmp     [rsp+1B0h+var_150], 0FFFFFFFFh
0x18009f1ab  jz      loc_18009F2C7
0x18009f1b1  lea     rcx, [rsp+1B0h+var_158]
0x18009f1b6  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x18009f1bb  mov     rdi, [rax]
0x18009f1be  mov     [rsp+1B0h+var_168], rdi
0x18009f1c3  lea     rcx, [rsp+1B0h+var_168]
0x18009f1c8  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x18009f1cd  nop
0x18009f1ce  mov     [rsp+1B0h+var_170], r13
0x18009f1d3  mov     [rsp+1B0h+string], r13
0x18009f1d8  mov     rax, [rdi]
0x18009f1db  mov     rbx, [rax+30h]
0x18009f1df  xor     ecx, ecx; string
0x18009f1e1  call    cs:__imp_WindowsDeleteString
0x18009f1e7  mov     [rsp+1B0h+var_170], r13
0x18009f1ec  lea     rdx, [rsp+1B0h+var_170]
0x18009f1f1  mov     rcx, rdi
0x18009f1f4  mov     rax, rbx
0x18009f1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f1fc  test    eax, eax
0x18009f1fe  js      loc_18009F292
0x18009f204  mov     rax, [rdi]
0x18009f207  mov     rbx, [rax+38h]
0x18009f20b  mov     rcx, [rsp+1B0h+string]; string
0x18009f210  call    cs:__imp_WindowsDeleteString
0x18009f216  mov     [rsp+1B0h+string], r13
0x18009f21b  lea     rdx, [rsp+1B0h+string]
0x18009f220  mov     rcx, rdi
0x18009f223  mov     rax, rbx
0x18009f226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f22b  test    eax, eax
0x18009f22d  js      short loc_18009F292
0x18009f22f  xor     edx, edx; length
0x18009f231  mov     rcx, [rsp+1B0h+string]; string
0x18009f236  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f23c  mov     rbx, rax
0x18009f23f  xor     edx, edx; length
0x18009f241  mov     rcx, [rsp+1B0h+var_170]; string
0x18009f246  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f24c  mov     rdx, rax
0x18009f24f  lea     rcx, [rbp+0B0h+var_88]
0x18009f253  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009f258  nop
0x18009f259  lea     r8, [rbp+0B0h+var_88]
0x18009f25d  lea     rdx, [rbp+0B0h+var_128]
0x18009f261  lea     rcx, [rbp+0B0h+var_110]
0x18009f265  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18009f26a  mov     rcx, [rax]
0x18009f26d  add     rcx, 30h ; '0'
0x18009f271  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009f275  inc     r8
0x18009f278  cmp     [rbx+r8*2], r13w
0x18009f27d  jnz     short loc_18009F275
0x18009f27f  mov     rdx, rbx
0x18009f282  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009f287  nop
0x18009f288  lea     rcx, [rbp+0B0h+var_88]
0x18009f28c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f291  nop
0x18009f292  mov     rcx, [rsp+1B0h+string]; string
0x18009f297  call    cs:__imp_WindowsDeleteString
0x18009f29d  mov     [rsp+1B0h+string], r13
0x18009f2a2  mov     rcx, [rsp+1B0h+var_170]; string
0x18009f2a7  call    cs:__imp_WindowsDeleteString
0x18009f2ad  nop
0x18009f2ae  lea     rcx, [rsp+1B0h+var_168]
0x18009f2b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009f2b8  lea     rcx, [rsp+1B0h+var_158]
0x18009f2bd  call    ??Eiterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x18009f2c2  jmp     loc_18009F1A6
0x18009f2c7  lea     rcx, [rsp+1B0h+var_140]
0x18009f2cc  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18009f2d1  nop
0x18009f2d2  lea     rcx, [rsp+1B0h+var_158]
0x18009f2d7  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18009f2dc  nop
0x18009f2dd  lea     rcx, [rsp+1B0h+var_178]
0x18009f2e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009f2e7  lea     rax, [rbp+0B0h+var_D0]
0x18009f2eb  mov     [rsp+1B0h+var_168], rax
0x18009f2f0  lea     rdx, [rbp+0B0h+var_110]
0x18009f2f4  lea     rcx, [rbp+0B0h+var_D0]
0x18009f2f8  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@AEBV01@@Z; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(std::unordered_map<std::wstring,std::wstring> const &)
0x18009f2fd  mov     rbx, rax
0x18009f300  mov     rdx, r14; struct ConfigurationManagement::Flags::DataModel::FlagConfigurationKey *
0x18009f303  lea     rcx, [rbp+0B0h+var_88]; this
0x18009f307  call    ??0FlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@QEAA@AEBV0123@@Z; ConfigurationManagement::Flags::DataModel::FlagConfigurationKey::FlagConfigurationKey(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey const &)
0x18009f30c  nop
0x18009f30d  mov     [rsp+1B0h+var_190], r12b
0x18009f312  mov     r9, rbx
0x18009f315  mov     r8, rax
0x18009f318  mov     rdx, rsi
0x18009f31b  mov     rcx, r15
0x18009f31e  call    ?FilterInventory@FlagConfigurationEngine@@AEAA?AV?$vector@U?$pair@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@UInventoryFlagConfiguration@234@@std@@V?$allocator@U?$pair@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@UInventoryFlagConfiguration@234@@std@@@2@@std@@VFlagConfigurationKey@DataModel@Flags@ConfigurationManagement@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@_N@Z; FlagConfigurationEngine::FilterInventory(ConfigurationManagement::Flags::DataModel::FlagConfigurationKey,std::unordered_map<std::wstring,std::wstring>,bool)
0x18009f323  nop
0x18009f324  lea     rcx, [rbp+0B0h+var_110]
0x18009f328  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18009f32d  nop
0x18009f32e  mov     rcx, r14
0x18009f331  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f336  mov     rax, rsi
0x18009f339  mov     rcx, [rbp+0B0h+var_50]
0x18009f33d  xor     rcx, rsp; StackCookie
0x18009f340  call    __security_check_cookie
0x18009f345  add     rsp, 178h
0x18009f34c  pop     r15
0x18009f34e  pop     r14
0x18009f350  pop     r13
0x18009f352  pop     r12
0x18009f354  pop     rdi
0x18009f355  pop     rsi
0x18009f356  pop     rbx
0x18009f357  pop     rbp
0x18009f358  retn
```
