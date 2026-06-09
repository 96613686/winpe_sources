# Windows::Internal::ConfigurationManagement::Flags::Flag::get_Metadata(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x1800a9ed0`
- end: `0x1800aa137`
- name: `?get_Metadata@Flag@Flags@ConfigurationManagement@Internal@Windows@@UEAAJPEAPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@5@@Z`
- size: `615`
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
- `0x1800a9ed0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa0c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa0c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa127`

## string_xrefs

- `0x1800a9ef5`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flag.cpp`
- `0x1800a9f47`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flag.cpp`
- `0x1800a9fc5`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flag.cpp`
- `0x1800aa0b2`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flag.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::Flag::get_Metadata(__int64 a1, _QWORD *a2)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD **v9; // rdi
  _QWORD *i; // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // esi
  int v17; // [rsp+20h] [rbp-48h]
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v19; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v20[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v22; // [rsp+78h] [rbp+10h] BYREF
  __int64 v23; // [rsp+80h] [rbp+18h] BYREF
  __int64 v24; // [rsp+88h] [rbp+20h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v23 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v7 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
           v6,
           v5,
           &v23);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = *(_QWORD ***)(a1 + 96);
      for ( i = *v9; i != v9; i = (_QWORD *)*i )
      {
        v19 = 0;
        string = 0;
        v20[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v19, v20);
        v20[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 6);
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v20);
        LOBYTE(v22) = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, int *))(*(_QWORD *)v23 + 80LL))(
                v23,
                v19,
                string,
                &v22);
        v16 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7A,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flag.cpp",
            (const char *)(unsigned int)v15,
            v17);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v19);
          v19 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          return v16;
        }
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v19);
      }
      v24 = 0;
      v11 = v23;
      v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v13 = v12(v11, &v24);
      v14 = v13;
      if ( v13 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(&v24);
        *a2 = v24;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flag.cpp",
          (const char *)(unsigned int)v13,
          v17);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flag.cpp",
        (const char *)(unsigned int)v7,
        v17);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flag.cpp",
      (const char *)0x80004003LL,
      v17);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800a9ed0  mov     [rsp+arg_0], rbx
0x1800a9ed5  push    rsi
0x1800a9ed6  push    rdi
0x1800a9ed7  push    r14
0x1800a9ed9  sub     rsp, 50h
0x1800a9edd  mov     r14, rdx
0x1800a9ee0  mov     rdi, rcx
0x1800a9ee3  test    rdx, rdx
0x1800a9ee6  jnz     short loc_1800A9F0C
0x1800a9ee8  mov     rcx, [rsp+68h]; this
0x1800a9eed  mov     ebx, 80004003h
0x1800a9ef2  mov     r9d, ebx; char *
0x1800a9ef5  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\featuremanage"...
0x1800a9efc  lea     edx, [r14+6Bh]; void *
0x1800a9f00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9f05  mov     eax, ebx
0x1800a9f07  jmp     loc_1800AA100
0x1800a9f0c  mov     qword ptr [rdx], 0
0x1800a9f13  mov     [rsp+68h+arg_10], 0
0x1800a9f1f  lea     rcx, [rsp+68h+arg_10]
0x1800a9f27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a9f2c  lea     r8, [rsp+68h+arg_10]
0x1800a9f34  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> * *)
0x1800a9f39  mov     ebx, eax
0x1800a9f3b  test    eax, eax
0x1800a9f3d  jns     short loc_1800A9F6C
0x1800a9f3f  mov     rcx, [rsp+68h]; this
0x1800a9f44  mov     r9d, eax; char *
0x1800a9f47  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\featuremanage"...
0x1800a9f4e  mov     edx, 70h ; 'p'; void *
0x1800a9f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9f58  lea     rcx, [rsp+68h+arg_10]
0x1800a9f60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a9f65  mov     eax, ebx
0x1800a9f67  jmp     loc_1800AA100
0x1800a9f6c  mov     rdi, [rdi+60h]
0x1800a9f70  mov     rbx, [rdi]
0x1800a9f73  cmp     rbx, rdi
0x1800a9f76  jnz     loc_1800AA030
0x1800a9f7c  mov     [rsp+68h+arg_18], 0
0x1800a9f88  mov     rdi, [rsp+68h+arg_10]
0x1800a9f90  mov     rax, [rdi]
0x1800a9f93  mov     rbx, [rax+48h]
0x1800a9f97  lea     rcx, [rsp+68h+arg_18]
0x1800a9f9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a9fa4  lea     rdx, [rsp+68h+arg_18]
0x1800a9fac  mov     rcx, rdi
0x1800a9faf  mov     rax, rbx
0x1800a9fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9fb7  mov     ebx, eax
0x1800a9fb9  test    eax, eax
0x1800a9fbb  jns     short loc_1800A9FF7
0x1800a9fbd  mov     rcx, [rsp+68h]; this
0x1800a9fc2  mov     r9d, eax; char *
0x1800a9fc5  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\featuremanage"...
0x1800a9fcc  mov     edx, 7Eh ; '~'; void *
0x1800a9fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9fd6  lea     rcx, [rsp+68h+arg_18]
0x1800a9fde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a9fe3  lea     rcx, [rsp+68h+arg_10]
0x1800a9feb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a9ff0  mov     eax, ebx
0x1800a9ff2  jmp     loc_1800AA100
0x1800a9ff7  lea     rcx, [rsp+68h+arg_18]
0x1800a9fff  call    ?InternalAddRef@?$ComPtr@UIFlagConfiguration2@Flags@ConfigurationManagement@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration2>::InternalAddRef(void)
0x1800aa004  mov     rax, [rsp+68h+arg_18]
0x1800aa00c  mov     [r14], rax
0x1800aa00f  lea     rcx, [rsp+68h+arg_18]
0x1800aa017  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa01c  lea     rcx, [rsp+68h+arg_10]
0x1800aa024  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa029  xor     eax, eax
0x1800aa02b  jmp     loc_1800AA100
0x1800aa030  mov     [rsp+68h+var_30], 0
0x1800aa039  mov     [rsp+68h+string], 0
0x1800aa042  lea     rcx, [rbx+10h]
0x1800aa046  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa04b  mov     [rsp+68h+var_28], rax
0x1800aa050  lea     rdx, [rsp+68h+var_28]
0x1800aa055  lea     rcx, [rsp+68h+var_30]
0x1800aa05a  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800aa05f  lea     rcx, [rbx+30h]
0x1800aa063  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa068  mov     [rsp+68h+var_28], rax
0x1800aa06d  lea     rdx, [rsp+68h+var_28]
0x1800aa072  lea     rcx, [rsp+68h+string]
0x1800aa077  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800aa07c  mov     byte ptr [rsp+68h+arg_8], 0
0x1800aa081  mov     rcx, [rsp+68h+arg_10]
0x1800aa089  mov     rax, [rcx]
0x1800aa08c  lea     r9, [rsp+68h+arg_8]
0x1800aa091  mov     r8, [rsp+68h+string]
0x1800aa096  mov     rdx, [rsp+68h+var_30]
0x1800aa09b  mov     rax, [rax+50h]
0x1800aa09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa0a4  mov     esi, eax
0x1800aa0a6  test    eax, eax
0x1800aa0a8  jns     short loc_1800AA10E
0x1800aa0aa  mov     rcx, [rsp+68h]; this
0x1800aa0af  mov     r9d, eax; char *
0x1800aa0b2  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\featuremanage"...
0x1800aa0b9  mov     edx, 7Ah ; 'z'; void *
0x1800aa0be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa0c3  mov     rcx, [rsp+68h+string]; string
0x1800aa0c8  call    cs:__imp_WindowsDeleteString
0x1800aa0ce  mov     [rsp+68h+string], 0
0x1800aa0d7  mov     rcx, [rsp+68h+var_30]; string
0x1800aa0dc  call    cs:__imp_WindowsDeleteString
0x1800aa0e2  mov     [rsp+68h+var_30], 0
0x1800aa0eb  lea     rcx, [rsp+68h+arg_10]
0x1800aa0f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aa0f8  mov     eax, esi
0x1800aa0fa  jmp     short loc_1800AA100
0x1800aa0fc  mov     eax, [rsp+68h+arg_8]
0x1800aa100  mov     rbx, [rsp+68h+arg_0]
0x1800aa105  add     rsp, 50h
0x1800aa109  pop     r14
0x1800aa10b  pop     rdi
0x1800aa10c  pop     rsi
0x1800aa10d  retn
0x1800aa10e  mov     rcx, [rsp+68h+string]; string
0x1800aa113  call    cs:__imp_WindowsDeleteString
0x1800aa119  mov     [rsp+68h+string], 0
0x1800aa122  mov     rcx, [rsp+68h+var_30]; string
0x1800aa127  call    cs:__imp_WindowsDeleteString
0x1800aa12d  mov     rbx, [rbx]
0x1800aa130  jmp     loc_1800A9F73
```
