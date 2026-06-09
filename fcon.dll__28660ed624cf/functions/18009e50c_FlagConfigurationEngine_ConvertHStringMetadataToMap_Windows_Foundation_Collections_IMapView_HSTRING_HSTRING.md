# FlagConfigurationEngine::ConvertHStringMetadataToMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x18009e50c`
- end: `0x18009e701`
- name: `?ConvertHStringMetadataToMap@FlagConfigurationEngine@@CA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a17a0`

## callees

- `0x180003220`
- `0x18000796c`
- `0x1800120a0`
- `0x180015af4`
- `0x180019890`
- `0x180043ce8`
- `0x18005e758`
- `0x180089d74`
- `0x180089e34`
- `0x180089ea0`
- `0x18009be34`
- `0x18009c398`
- `0x18009e50c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e60f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e60f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009e641`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FlagConfigurationEngine::ConvertHStringMetadataToMap(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  int (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v5; // rsi
  int (__fastcall *v6)(__int64, HSTRING *); // rbx
  int (__fastcall *v7)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rbx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  int v14; // [rsp+28h] [rbp-51h]
  HSTRING v15; // [rsp+30h] [rbp-49h] BYREF
  __int64 v16; // [rsp+38h] [rbp-41h] BYREF
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-31h] BYREF
  int v19; // [rsp+50h] [rbp-29h]
  __int64 v20; // [rsp+60h] [rbp-19h] BYREF
  int v21; // [rsp+68h] [rbp-11h]
  __int64 v22; // [rsp+70h] [rbp-9h]
  __int64 v23; // [rsp+78h] [rbp-1h]
  _BYTE v24[16]; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v25[32]; // [rsp+90h] [rbp+17h] BYREF

  v23 = a1;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>();
  v14 = 1;
  if ( a2 )
  {
    v16 = 0;
    v4 = **a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    if ( v4(a2, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v16) >= 0 )
    {
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        v18,
        v16);
      v14 = 3;
      v20 = 0;
      v21 = -1;
      v22 = 0;
      while ( v19 != -1 )
      {
        v5 = *(_QWORD *)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator*(v18);
        v17 = v5;
        Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(&v17);
        v15 = 0;
        string = 0;
        v6 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v5 + 48LL);
        WindowsDeleteString(0);
        v15 = 0;
        if ( v6(v5, &v15) >= 0 )
        {
          v7 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v5 + 56LL);
          WindowsDeleteString(string);
          string = 0;
          if ( v7(v5, &string) >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            WindowsGetStringRawBuffer(v15, 0);
            std::wstring::wstring(v25);
            v9 = *(_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(a1, v24, v25) + 64LL;
            v10 = -1;
            do
              ++v10;
            while ( StringRawBuffer[v10] );
            std::wstring::_Assign<unsigned short>(v9, StringRawBuffer, v10);
            std::wstring::_Tidy_deallocate(v25, v11);
          }
        }
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v15);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator++(v18);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v20);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v18);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  }
  return a1;
}

```

## disassembly

```asm
0x18009e50c  mov     [rsp-8+arg_10], rbx
0x18009e511  mov     [rsp-8+arg_18], rsi
0x18009e516  push    rbp
0x18009e517  push    rdi
0x18009e518  push    r14
0x18009e51a  lea     rbp, [rsp-47h]
0x18009e51f  sub     rsp, 0C0h
0x18009e526  mov     rax, cs:__security_cookie
0x18009e52d  xor     rax, rsp
0x18009e530  mov     [rbp+57h+var_20], rax
0x18009e534  mov     rsi, rdx
0x18009e537  mov     rdi, rcx
0x18009e53a  mov     [rbp+57h+var_58], rcx
0x18009e53e  xor     r14d, r14d
0x18009e541  mov     [rbp+57h+var_A8], r14d
0x18009e545  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18009e54a  mov     [rbp+57h+var_A8], 1
0x18009e551  test    rsi, rsi
0x18009e554  jz      loc_18009E6D9
0x18009e55a  mov     [rbp+57h+var_98], r14
0x18009e55e  mov     rax, [rsi]
0x18009e561  mov     rbx, [rax]
0x18009e564  lea     rcx, [rbp+57h+var_98]
0x18009e568  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e56d  lea     r8, [rbp+57h+var_98]
0x18009e571  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18009e578  mov     rcx, rsi
0x18009e57b  mov     rax, rbx
0x18009e57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e583  test    eax, eax
0x18009e585  js      loc_18009E6D0
0x18009e58b  mov     rdx, [rbp+57h+var_98]
0x18009e58f  lea     rcx, [rbp+57h+var_88]
0x18009e593  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *> *)
0x18009e598  mov     [rbp+57h+var_A8], 3
0x18009e59f  mov     [rbp+57h+var_70], r14
0x18009e5a3  mov     [rbp+57h+var_68], 0FFFFFFFFh
0x18009e5aa  mov     [rbp+57h+var_60], r14
0x18009e5ae  cmp     [rbp+57h+var_80], 0FFFFFFFFh
0x18009e5b2  jz      loc_18009E6BC
0x18009e5b8  lea     rcx, [rbp+57h+var_88]
0x18009e5bc  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x18009e5c1  mov     rsi, [rax]
0x18009e5c4  mov     [rbp+57h+var_90], rsi
0x18009e5c8  lea     rcx, [rbp+57h+var_90]
0x18009e5cc  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x18009e5d1  nop
0x18009e5d2  mov     [rbp+57h+var_A0], r14
0x18009e5d6  mov     [rbp+57h+string], r14
0x18009e5da  mov     rax, [rsi]
0x18009e5dd  mov     rbx, [rax+30h]
0x18009e5e1  xor     ecx, ecx; string
0x18009e5e3  call    cs:__imp_WindowsDeleteString
0x18009e5e9  mov     [rbp+57h+var_A0], r14
0x18009e5ed  lea     rdx, [rbp+57h+var_A0]
0x18009e5f1  mov     rcx, rsi
0x18009e5f4  mov     rax, rbx
0x18009e5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e5fc  test    eax, eax
0x18009e5fe  js      loc_18009E68C
0x18009e604  mov     rax, [rsi]
0x18009e607  mov     rbx, [rax+38h]
0x18009e60b  mov     rcx, [rbp+57h+string]; string
0x18009e60f  call    cs:__imp_WindowsDeleteString
0x18009e615  mov     [rbp+57h+string], r14
0x18009e619  lea     rdx, [rbp+57h+string]
0x18009e61d  mov     rcx, rsi
0x18009e620  mov     rax, rbx
0x18009e623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e628  test    eax, eax
0x18009e62a  js      short loc_18009E68C
0x18009e62c  xor     edx, edx; length
0x18009e62e  mov     rcx, [rbp+57h+string]; string
0x18009e632  call    cs:__imp_WindowsGetStringRawBuffer
0x18009e638  mov     rbx, rax
0x18009e63b  xor     edx, edx; length
0x18009e63d  mov     rcx, [rbp+57h+var_A0]; string
0x18009e641  call    cs:__imp_WindowsGetStringRawBuffer
0x18009e647  mov     rdx, rax
0x18009e64a  lea     rcx, [rbp+57h+var_40]
0x18009e64e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009e653  nop
0x18009e654  lea     r8, [rbp+57h+var_40]
0x18009e658  lea     rdx, [rbp+57h+var_50]
0x18009e65c  mov     rcx, rdi
0x18009e65f  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18009e664  mov     rcx, [rax]
0x18009e667  add     rcx, 40h ; '@'
0x18009e66b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009e66f  inc     r8
0x18009e672  cmp     [rbx+r8*2], r14w
0x18009e677  jnz     short loc_18009E66F
0x18009e679  mov     rdx, rbx
0x18009e67c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009e681  nop
0x18009e682  lea     rcx, [rbp+57h+var_40]
0x18009e686  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009e68b  nop
0x18009e68c  mov     rcx, [rbp+57h+string]; string
0x18009e690  call    cs:__imp_WindowsDeleteString
0x18009e696  mov     [rbp+57h+string], r14
0x18009e69a  mov     rcx, [rbp+57h+var_A0]; string
0x18009e69e  call    cs:__imp_WindowsDeleteString
0x18009e6a4  nop
0x18009e6a5  lea     rcx, [rbp+57h+var_90]
0x18009e6a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e6ae  lea     rcx, [rbp+57h+var_88]
0x18009e6b2  call    ??Eiterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x18009e6b7  jmp     loc_18009E5AE
0x18009e6bc  lea     rcx, [rbp+57h+var_70]
0x18009e6c0  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18009e6c5  nop
0x18009e6c6  lea     rcx, [rbp+57h+var_88]
0x18009e6ca  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18009e6cf  nop
0x18009e6d0  lea     rcx, [rbp+57h+var_98]
0x18009e6d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e6d9  mov     rax, rdi
0x18009e6dc  mov     rcx, [rbp+57h+var_20]
0x18009e6e0  xor     rcx, rsp; StackCookie
0x18009e6e3  call    __security_check_cookie
0x18009e6e8  lea     r11, [rsp+0D0h+var_10]
0x18009e6f0  mov     rbx, [r11+30h]
0x18009e6f4  mov     rsi, [r11+38h]
0x18009e6f8  mov     rsp, r11
0x18009e6fb  pop     r14
0x18009e6fd  pop     rdi
0x18009e6fe  pop     rbp
0x18009e6ff  retn
```
