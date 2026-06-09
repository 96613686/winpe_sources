# WinFlagsProvider::GetFilterMetadata(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * *,bool)

- ea: `0x18008a908`
- end: `0x18008aa8d`
- name: `?GetFilterMetadata@WinFlagsProvider@@QEAAJPEAPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@_N@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008aba0`

## callees

- `0x18000949c`
- `0x1800107b0`
- `0x1800442c0`
- `0x18008a400`
- `0x18008a908`
- `0x18008af34`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a9e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a9f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a9e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a9f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008aa65`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinFlagsProvider::GetFilterMetadata(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  int v3; // edi
  int v5; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rbx
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-20h]
  HSTRING v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v17 = a1;
  v3 = a3;
  v15 = 0;
  v5 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
         a1,
         a2,
         &v15);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v14 = 0;
    string = 0;
    LOBYTE(v17) = 0;
    Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
      &v14,
      &WinFlagsFeature::c_winflagsPreviewFlagEligibleProp);
    v7 = L"true";
    if ( !(_BYTE)v3 )
      v7 = L"false";
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v7, (v3 ^ 1) + 4);
    v8 = v15;
    v9 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v15 + 80LL))(
           v15,
           v14,
           string,
           &v17);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 72LL))(v8, a2);
      v6 = v11;
      if ( v11 >= 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v14);
        v6 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsprovider.cpp",
          (const char *)(unsigned int)v11,
          v13);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v14);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsprovider.cpp",
        (const char *)(unsigned int)v9,
        v13);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v14);
      v6 = v10;
    }
    v14 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsprovider.cpp",
      (const char *)(unsigned int)v5,
      v13);
  }
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v15);
  return v6;
}

```

## disassembly

```asm
0x18008a908  mov     [rsp-18h+arg_8], rbx
0x18008a90d  mov     [rsp-18h+arg_0], rcx
0x18008a912  push    rbp
0x18008a913  push    rsi
0x18008a914  push    rdi
0x18008a915  mov     rbp, rsp
0x18008a918  sub     rsp, 40h
0x18008a91c  movzx   edi, r8b
0x18008a920  mov     rsi, rdx
0x18008a923  mov     [rbp+var_8], 0
0x18008a92b  lea     r8, [rbp+var_8]
0x18008a92f  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> * *)
0x18008a934  mov     ebx, eax
0x18008a936  test    eax, eax
0x18008a938  jns     short loc_18008A957
0x18008a93a  mov     rcx, [rbp+18h]; this
0x18008a93e  mov     r9d, eax; char *
0x18008a941  lea     r8, aOnecoreBaseFli_68; "onecore\\base\\flighting\\featuremanage"...
0x18008a948  mov     edx, 52h ; 'R'; void *
0x18008a94d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a952  jmp     loc_18008AA75
0x18008a957  mov     [rbp+var_10], 0
0x18008a95f  mov     [rbp+string], 0
0x18008a967  mov     byte ptr [rbp+arg_0], 0
0x18008a96b  lea     rdx, ?c_winflagsPreviewFlagEligibleProp@WinFlagsFeature@@2QEBGEB; ushort const * const WinFlagsFeature::c_winflagsPreviewFlagEligibleProp
0x18008a972  lea     rcx, [rbp+var_10]
0x18008a976  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008a97b  mov     r8d, edi
0x18008a97e  xor     r8d, 1
0x18008a982  add     r8d, 4; unsigned int
0x18008a986  lea     rax, aFalse; "false"
0x18008a98d  lea     rdx, aTrue; "true"
0x18008a994  test    dil, dil
0x18008a997  cmovz   rdx, rax; unsigned __int16 *
0x18008a99b  lea     rcx, [rbp+string]; this
0x18008a99f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18008a9a4  mov     rbx, [rbp+var_8]
0x18008a9a8  mov     rax, [rbx]
0x18008a9ab  lea     r9, [rbp+arg_0]
0x18008a9af  mov     r8, [rbp+string]
0x18008a9b3  mov     rdx, [rbp+var_10]
0x18008a9b7  mov     rcx, rbx
0x18008a9ba  mov     rax, [rax+50h]
0x18008a9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a9c3  mov     edi, eax
0x18008a9c5  test    eax, eax
0x18008a9c7  jns     short loc_18008AA01
0x18008a9c9  mov     rcx, [rbp+18h]; this
0x18008a9cd  mov     r9d, eax; char *
0x18008a9d0  lea     r8, aOnecoreBaseFli_68; "onecore\\base\\flighting\\featuremanage"...
0x18008a9d7  mov     edx, 5Eh ; '^'; void *
0x18008a9dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a9e1  mov     rcx, [rbp+string]; string
0x18008a9e5  call    cs:__imp_WindowsDeleteString
0x18008a9eb  mov     [rbp+string], 0
0x18008a9f3  mov     rcx, [rbp+var_10]; string
0x18008a9f7  call    cs:__imp_WindowsDeleteString
0x18008a9fd  mov     ebx, edi
0x18008a9ff  jmp     short loc_18008AA6D
0x18008aa01  mov     rax, [rbx]
0x18008aa04  mov     rdx, rsi
0x18008aa07  mov     rcx, rbx
0x18008aa0a  mov     rax, [rax+48h]
0x18008aa0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aa13  mov     ebx, eax
0x18008aa15  test    eax, eax
0x18008aa17  jns     short loc_18008AA4F
0x18008aa19  mov     rcx, [rbp+18h]; this
0x18008aa1d  mov     r9d, eax; char *
0x18008aa20  lea     r8, aOnecoreBaseFli_68; "onecore\\base\\flighting\\featuremanage"...
0x18008aa27  mov     edx, 5Fh ; '_'; void *
0x18008aa2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008aa31  mov     rcx, [rbp+string]; string
0x18008aa35  call    cs:__imp_WindowsDeleteString
0x18008aa3b  mov     [rbp+string], 0
0x18008aa43  mov     rcx, [rbp+var_10]; string
0x18008aa47  call    cs:__imp_WindowsDeleteString
0x18008aa4d  jmp     short loc_18008AA6D
0x18008aa4f  mov     rcx, [rbp+string]; string
0x18008aa53  call    cs:__imp_WindowsDeleteString
0x18008aa59  mov     [rbp+string], 0
0x18008aa61  mov     rcx, [rbp+var_10]; string
0x18008aa65  call    cs:__imp_WindowsDeleteString
0x18008aa6b  xor     ebx, ebx
0x18008aa6d  mov     [rbp+var_10], 0
0x18008aa75  lea     rcx, [rbp+var_8]
0x18008aa79  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18008aa7e  mov     eax, ebx
0x18008aa80  mov     rbx, [rsp+40h+arg_8]
0x18008aa85  add     rsp, 40h
0x18008aa89  pop     rdi
0x18008aa8a  pop     rsi
0x18008aa8b  pop     rbp
0x18008aa8c  retn
```
