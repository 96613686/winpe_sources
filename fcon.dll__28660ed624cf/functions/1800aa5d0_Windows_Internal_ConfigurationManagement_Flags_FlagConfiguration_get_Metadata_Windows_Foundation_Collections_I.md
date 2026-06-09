# Windows::Internal::ConfigurationManagement::Flags::FlagConfiguration::get_Metadata(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x1800aa5d0`
- end: `0x1800aa7d8`
- name: `?get_Metadata@FlagConfiguration@Flags@ConfigurationManagement@Internal@Windows@@UEAAJPEAPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@5@@Z`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000796c`
- `0x18000949c`
- `0x180019704`
- `0x180043ce8`
- `0x1800442c0`
- `0x18008a400`
- `0x1800aa5d0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa6f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa6f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa709`

## string_xrefs

- `0x1800aa5f5`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfiguration.cpp`
- `0x1800aa647`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfiguration.cpp`
- `0x1800aa760`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfiguration::get_Metadata(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD **v9; // rbx
  _QWORD *i; // rdi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-48h]
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v17; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v18[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v20; // [rsp+78h] [rbp+10h] BYREF
  __int64 v21; // [rsp+80h] [rbp+18h] BYREF
  __int64 v22; // [rsp+88h] [rbp+20h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v21 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v7 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
           v6,
           v5,
           &v21);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = *(_QWORD ***)(a1 + 64);
      for ( i = *v9; i != v9; i = (_QWORD *)*i )
      {
        v17 = 0;
        string = 0;
        v18[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v17, v18);
        v18[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 6);
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v18);
        LOBYTE(v20) = 0;
        (*(void (__fastcall **)(__int64, HSTRING, HSTRING, int *))(*(_QWORD *)v21 + 80LL))(v21, v17, string, &v20);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v17);
      }
      v22 = 0;
      v11 = v21;
      v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      v13 = v12(v11, &v22);
      v14 = v13;
      if ( v13 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(&v22);
        *a2 = v22;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfiguration.cpp",
          (const char *)(unsigned int)v13,
          v15);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfiguration.cpp",
        (const char *)(unsigned int)v7,
        v15);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfiguration.cpp",
      (const char *)0x80004003LL,
      v15);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800aa5d0  mov     [rsp+arg_0], rbx
0x1800aa5d5  push    rsi
0x1800aa5d6  push    rdi
0x1800aa5d7  push    r14
0x1800aa5d9  sub     rsp, 50h
0x1800aa5dd  mov     r14, rdx
0x1800aa5e0  mov     rdi, rcx
0x1800aa5e3  test    rdx, rdx
0x1800aa5e6  jnz     short loc_1800AA60C
0x1800aa5e8  mov     rcx, [rsp+68h]; this
0x1800aa5ed  mov     ebx, 80004003h
0x1800aa5f2  mov     r9d, ebx; char *
0x1800aa5f5  lea     r8, aOnecoreBaseFli_65; "onecore\\base\\flighting\\featuremanage"...
0x1800aa5fc  lea     edx, [r14+3Bh]; void *
0x1800aa600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa605  mov     eax, ebx
0x1800aa607  jmp     loc_1800AA7C9
0x1800aa60c  mov     qword ptr [rdx], 0
0x1800aa613  mov     [rsp+68h+arg_10], 0
0x1800aa61f  lea     rcx, [rsp+68h+arg_10]
0x1800aa627  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa62c  lea     r8, [rsp+68h+arg_10]
0x1800aa634  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> * *)
0x1800aa639  mov     ebx, eax
0x1800aa63b  test    eax, eax
0x1800aa63d  jns     short loc_1800AA66C
0x1800aa63f  mov     rcx, [rsp+68h]; this
0x1800aa644  mov     r9d, eax; char *
0x1800aa647  lea     r8, aOnecoreBaseFli_65; "onecore\\base\\flighting\\featuremanage"...
0x1800aa64e  mov     edx, 41h ; 'A'; void *
0x1800aa653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa658  lea     rcx, [rsp+68h+arg_10]
0x1800aa660  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa665  mov     eax, ebx
0x1800aa667  jmp     loc_1800AA7C9
0x1800aa66c  mov     rbx, [rdi+40h]
0x1800aa670  mov     rdi, [rbx]
0x1800aa673  cmp     rdi, rbx
0x1800aa676  jz      loc_1800AA717
0x1800aa67c  mov     [rsp+68h+var_30], 0
0x1800aa685  mov     [rsp+68h+string], 0
0x1800aa68e  lea     rcx, [rdi+10h]
0x1800aa692  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa697  mov     [rsp+68h+var_28], rax
0x1800aa69c  lea     rdx, [rsp+68h+var_28]
0x1800aa6a1  lea     rcx, [rsp+68h+var_30]
0x1800aa6a6  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800aa6ab  lea     rcx, [rdi+30h]
0x1800aa6af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa6b4  mov     [rsp+68h+var_28], rax
0x1800aa6b9  lea     rdx, [rsp+68h+var_28]
0x1800aa6be  lea     rcx, [rsp+68h+string]
0x1800aa6c3  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800aa6c8  mov     byte ptr [rsp+68h+arg_8], 0
0x1800aa6cd  mov     rcx, [rsp+68h+arg_10]
0x1800aa6d5  mov     rax, [rcx]
0x1800aa6d8  lea     r9, [rsp+68h+arg_8]
0x1800aa6dd  mov     r8, [rsp+68h+string]
0x1800aa6e2  mov     rdx, [rsp+68h+var_30]
0x1800aa6e7  mov     rax, [rax+50h]
0x1800aa6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa6f0  mov     rcx, [rsp+68h+string]; string
0x1800aa6f5  call    cs:__imp_WindowsDeleteString
0x1800aa6fb  mov     [rsp+68h+string], 0
0x1800aa704  mov     rcx, [rsp+68h+var_30]; string
0x1800aa709  call    cs:__imp_WindowsDeleteString
0x1800aa70f  mov     rdi, [rdi]
0x1800aa712  jmp     loc_1800AA673
0x1800aa717  mov     [rsp+68h+arg_18], 0
0x1800aa723  mov     rdi, [rsp+68h+arg_10]
0x1800aa72b  mov     rax, [rdi]
0x1800aa72e  mov     rbx, [rax+48h]
0x1800aa732  lea     rcx, [rsp+68h+arg_18]
0x1800aa73a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa73f  lea     rdx, [rsp+68h+arg_18]
0x1800aa747  mov     rcx, rdi
0x1800aa74a  mov     rax, rbx
0x1800aa74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa752  mov     ebx, eax
0x1800aa754  test    eax, eax
0x1800aa756  jns     short loc_1800AA78F
0x1800aa758  mov     rcx, [rsp+68h]; this
0x1800aa75d  mov     r9d, eax; char *
0x1800aa760  lea     r8, aOnecoreBaseFli_65; "onecore\\base\\flighting\\featuremanage"...
0x1800aa767  mov     edx, 51h ; 'Q'; void *
0x1800aa76c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa771  lea     rcx, [rsp+68h+arg_18]
0x1800aa779  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa77e  lea     rcx, [rsp+68h+arg_10]
0x1800aa786  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa78b  mov     eax, ebx
0x1800aa78d  jmp     short loc_1800AA7C9
0x1800aa78f  lea     rcx, [rsp+68h+arg_18]
0x1800aa797  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x1800aa79c  mov     rax, [rsp+68h+arg_18]
0x1800aa7a4  mov     [r14], rax
0x1800aa7a7  lea     rcx, [rsp+68h+arg_18]
0x1800aa7af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa7b4  lea     rcx, [rsp+68h+arg_10]
0x1800aa7bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa7c1  xor     eax, eax
0x1800aa7c3  jmp     short loc_1800AA7C9
0x1800aa7c5  mov     eax, [rsp+68h+arg_8]
0x1800aa7c9  mov     rbx, [rsp+68h+arg_0]
0x1800aa7ce  add     rsp, 50h
0x1800aa7d2  pop     r14
0x1800aa7d4  pop     rdi
0x1800aa7d5  pop     rsi
0x1800aa7d6  retn
```
