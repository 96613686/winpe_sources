# WinFlagsFeature::SetProperties(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x18008a208`
- end: `0x18008a3f8`
- name: `?SetProperties@WinFlagsFeature@@AEAAXPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008899c`

## callees

- `0x180003220`
- `0x18000796c`
- `0x180015af4`
- `0x180019890`
- `0x180043ce8`
- `0x18005e758`
- `0x1800772cc`
- `0x180089c64`
- `0x180089d74`
- `0x180089e34`
- `0x180089ea0`
- `0x18008a208`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a38c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a38c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a34e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a34e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinFlagsFeature::SetProperties(__int64 a1, int (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  __int64 v3; // rsi
  __int64 result; // rax
  int (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, HSTRING *); // rbx
  int (__fastcall *v8)(__int64, HSTRING *); // rbx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  HSTRING v14; // [rsp+28h] [rbp-61h] BYREF
  __int64 v15; // [rsp+30h] [rbp-59h] BYREF
  __int64 v16; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-49h] BYREF
  int v18; // [rsp+48h] [rbp-41h]
  __int64 v19; // [rsp+58h] [rbp-31h] BYREF
  int v20; // [rsp+60h] [rbp-29h]
  __int64 v21; // [rsp+68h] [rbp-21h]
  _BYTE v22[16]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v23[32]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v24[32]; // [rsp+A0h] [rbp+17h] BYREF

  v3 = a1 + 208;
  result = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(a1 + 208);
  if ( a2 )
  {
    v15 = 0;
    v5 = **a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    if ( v5(a2, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v15) >= 0 )
    {
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        v17,
        v15);
      v19 = 0;
      v20 = -1;
      v21 = 0;
      while ( v18 != -1 )
      {
        v6 = *(_QWORD *)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator*(v17);
        v16 = v6;
        Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(&v16);
        v14 = 0;
        string = 0;
        v7 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 48LL);
        WindowsDeleteString(0);
        v14 = 0;
        if ( v7(v6, &v14) >= 0 )
        {
          v8 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 56LL);
          WindowsDeleteString(string);
          string = 0;
          if ( v8(v6, &string) >= 0 )
          {
            WindowsGetStringRawBuffer(string, 0);
            v9 = std::wstring::wstring(v24);
            WindowsGetStringRawBuffer(v14, 0);
            v10 = std::wstring::wstring(v23);
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring,std::wstring>(
              v3,
              v22,
              v10,
              v9);
            std::wstring::_Tidy_deallocate(v23, v11);
            std::wstring::_Tidy_deallocate(v24, v12);
          }
        }
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v14);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator++(v17);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v19);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v17);
    }
    return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  }
  return result;
}

```

## disassembly

```asm
0x18008a208  mov     [rsp-8+arg_10], rbx
0x18008a20d  push    rbp
0x18008a20e  push    rsi
0x18008a20f  push    rdi
0x18008a210  lea     rbp, [rsp-47h]
0x18008a215  sub     rsp, 0D0h
0x18008a21c  mov     rax, cs:__security_cookie
0x18008a223  xor     rax, rsp
0x18008a226  mov     [rbp+57h+var_20], rax
0x18008a22a  mov     rdi, rdx
0x18008a22d  lea     rsi, [rcx+0D0h]
0x18008a234  mov     rcx, rsi
0x18008a237  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x18008a23c  test    rdi, rdi
0x18008a23f  jz      loc_18008A3D9
0x18008a245  mov     [rbp+57h+var_B0], 0
0x18008a24d  mov     rax, [rdi]
0x18008a250  mov     rbx, [rax]
0x18008a253  lea     rcx, [rbp+57h+var_B0]
0x18008a257  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008a25c  lea     r8, [rbp+57h+var_B0]
0x18008a260  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18008a267  mov     rcx, rdi
0x18008a26a  mov     rax, rbx
0x18008a26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a272  test    eax, eax
0x18008a274  js      loc_18008A3D0
0x18008a27a  mov     rdx, [rbp+57h+var_B0]
0x18008a27e  lea     rcx, [rbp+57h+var_A0]
0x18008a282  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *> *)
0x18008a287  nop
0x18008a288  mov     [rbp+57h+var_88], 0
0x18008a290  mov     [rbp+57h+var_80], 0FFFFFFFFh
0x18008a297  mov     [rbp+57h+var_78], 0
0x18008a29f  cmp     [rbp+57h+var_98], 0FFFFFFFFh
0x18008a2a3  jz      loc_18008A3BC
0x18008a2a9  lea     rcx, [rbp+57h+var_A0]
0x18008a2ad  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x18008a2b2  mov     rdi, [rax]
0x18008a2b5  mov     [rbp+57h+var_A8], rdi
0x18008a2b9  lea     rcx, [rbp+57h+var_A8]
0x18008a2bd  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x18008a2c2  nop
0x18008a2c3  mov     [rbp+57h+var_B8], 0
0x18008a2cb  mov     [rbp+57h+string], 0
0x18008a2d3  mov     rax, [rdi]
0x18008a2d6  mov     rbx, [rax+30h]
0x18008a2da  xor     ecx, ecx; string
0x18008a2dc  call    cs:__imp_WindowsDeleteString
0x18008a2e2  mov     [rbp+57h+var_B8], 0
0x18008a2ea  lea     rdx, [rbp+57h+var_B8]
0x18008a2ee  mov     rcx, rdi
0x18008a2f1  mov     rax, rbx
0x18008a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a2f9  test    eax, eax
0x18008a2fb  js      loc_18008A388
0x18008a301  mov     rax, [rdi]
0x18008a304  mov     rbx, [rax+38h]
0x18008a308  mov     rcx, [rbp+57h+string]; string
0x18008a30c  call    cs:__imp_WindowsDeleteString
0x18008a312  mov     [rbp+57h+string], 0
0x18008a31a  lea     rdx, [rbp+57h+string]
0x18008a31e  mov     rcx, rdi
0x18008a321  mov     rax, rbx
0x18008a324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a329  test    eax, eax
0x18008a32b  js      short loc_18008A388
0x18008a32d  xor     edx, edx; length
0x18008a32f  mov     rcx, [rbp+57h+string]; string
0x18008a333  call    cs:__imp_WindowsGetStringRawBuffer
0x18008a339  mov     rdx, rax
0x18008a33c  lea     rcx, [rbp+57h+var_40]
0x18008a340  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008a345  mov     rbx, rax
0x18008a348  xor     edx, edx; length
0x18008a34a  mov     rcx, [rbp+57h+var_B8]; string
0x18008a34e  call    cs:__imp_WindowsGetStringRawBuffer
0x18008a354  mov     rdx, rax
0x18008a357  lea     rcx, [rbp+57h+var_60]
0x18008a35b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008a360  nop
0x18008a361  mov     r9, rbx
0x18008a364  mov     r8, rax
0x18008a367  lea     rdx, [rbp+57h+var_70]
0x18008a36b  mov     rcx, rsi
0x18008a36e  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring,std::wstring>(std::wstring &&,std::wstring &&)
0x18008a373  nop
0x18008a374  lea     rcx, [rbp+57h+var_60]
0x18008a378  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008a37d  nop
0x18008a37e  lea     rcx, [rbp+57h+var_40]
0x18008a382  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008a387  nop
0x18008a388  mov     rcx, [rbp+57h+string]; string
0x18008a38c  call    cs:__imp_WindowsDeleteString
0x18008a392  mov     [rbp+57h+string], 0
0x18008a39a  mov     rcx, [rbp+57h+var_B8]; string
0x18008a39e  call    cs:__imp_WindowsDeleteString
0x18008a3a4  nop
0x18008a3a5  lea     rcx, [rbp+57h+var_A8]
0x18008a3a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008a3ae  lea     rcx, [rbp+57h+var_A0]
0x18008a3b2  call    ??Eiterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x18008a3b7  jmp     loc_18008A29F
0x18008a3bc  lea     rcx, [rbp+57h+var_88]
0x18008a3c0  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18008a3c5  nop
0x18008a3c6  lea     rcx, [rbp+57h+var_A0]
0x18008a3ca  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18008a3cf  nop
0x18008a3d0  lea     rcx, [rbp+57h+var_B0]
0x18008a3d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008a3d9  mov     rcx, [rbp+57h+var_20]
0x18008a3dd  xor     rcx, rsp; StackCookie
0x18008a3e0  call    __security_check_cookie
0x18008a3e5  mov     rbx, [rsp+0E0h+arg_10]
0x18008a3ed  add     rsp, 0D0h
0x18008a3f4  pop     rdi
0x18008a3f5  pop     rsi
0x18008a3f6  pop     rbp
0x18008a3f7  retn
```
