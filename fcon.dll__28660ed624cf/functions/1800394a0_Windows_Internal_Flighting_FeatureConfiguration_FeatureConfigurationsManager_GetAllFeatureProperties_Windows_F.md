# Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::GetAllFeatureProperties(Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem> * *)

- ea: `0x1800394a0`
- end: `0x1800396cc`
- name: `?GetAllFeatureProperties@FeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@UEAAJPEAPEAU?$IVectorView@UFeaturePropertyItem@FeatureConfiguration@Flighting@Internal@Windows@@@Collections@Foundation@5@@Z`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003220`
- `0x18000796c`
- `0x180010450`
- `0x1800109ac`
- `0x180019704`
- `0x180035264`
- `0x1800394a0`
- `0x180044998`
- `0x180075d90`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003959b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800395db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003959b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800395db`

## string_xrefs

- `0x180039666`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003967a`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x18003968f`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x1800396a4`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x1800396b9`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::GetAllFeatureProperties(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 *v5; // rsi
  __int64 *i; // rbx
  int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  _QWORD **v10; // r14
  _QWORD *j; // rdi
  __int64 v12; // rax
  HRESULT v13; // eax
  __int64 v14; // rax
  HRESULT v15; // eax
  int v16; // eax
  int v17[2]; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D0h] BYREF
  HSTRING newString[2]; // [rsp+30h] [rbp-C8h] BYREF
  HSTRING v20; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 *v22; // [rsp+58h] [rbp-A0h]
  __int128 v23; // [rsp+90h] [rbp-68h] BYREF
  HSTRING v24; // [rsp+A0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  v4 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem,FeaturePropertyItemEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem>>::Make(
         v3,
         v17);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D9,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
        (const char *)(unsigned int)v4,
        v17[0]);
    StagingControls_GetAllFeatureProperties(v21);
    v5 = v22;
    for ( i = (__int64 *)*v22; i != v5; i = (__int64 *)*i )
    {
      v10 = (_QWORD **)i[4];
      for ( j = *v10; j != v10; j = (_QWORD *)*j )
      {
        *(_OWORD *)newString = 0;
        v20 = 0;
        LODWORD(newString[0]) = *((_DWORD *)i + 4);
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j + 2);
        v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v23, &v18);
        v13 = WindowsDuplicateString(*(HSTRING *)(v12 + 24), &newString[1]);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E1,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
            (const char *)(unsigned int)v13,
            v17[0]);
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j + 6);
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v23, &v18);
        v15 = WindowsDuplicateString(*(HSTRING *)(v14 + 24), &v20);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E2,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
            (const char *)(unsigned int)v15,
            v17[0]);
        v23 = *(_OWORD *)newString;
        v24 = v20;
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v17 + 104LL))(*(_QWORD *)v17, &v23);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E3,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
            (const char *)(unsigned int)v16,
            v17[0]);
      }
    }
    __1___Hash_V___Umap_traits_KV__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__std__V___Uhash_compare_KU__hash_K_std__U__equal_to_K_2__2_V__allocator_U__pair___CBKV__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__std___std___2__0A__std___std__QEAA_XZ(v21);
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v17 + 64LL))(*(_QWORD *)v17, a2);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
        (const char *)(unsigned int)v7,
        v17[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2EA,
                           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featurec"
                                         "onfigurationsmanager.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800394a0  push    rbx
0x1800394a2  push    rsi
0x1800394a3  push    rdi
0x1800394a4  push    r13
0x1800394a6  push    r14
0x1800394a8  push    r15
0x1800394aa  sub     rsp, 0C8h
0x1800394b1  mov     rax, cs:__security_cookie
0x1800394b8  xor     rax, rsp
0x1800394bb  mov     [rsp+0F8h+var_48], rax
0x1800394c3  mov     r15, rdx
0x1800394c6  mov     qword ptr [rsp+0F8h+var_D8], 0; int
0x1800394cf  lea     rcx, [rsp+0F8h+var_D8]
0x1800394d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800394d9  lea     rdx, [rsp+0F8h+var_D8]
0x1800394de  call    ?Make@?$Vector@UFeaturePropertyItem@FeatureConfiguration@Flighting@Internal@Windows@@UFeaturePropertyItemEquality@@UPodLifetimeTraits@XWinRT@@U?$DefaultVectorOptions@UFeaturePropertyItem@FeatureConfiguration@Flighting@Internal@Windows@@@4Collections@Foundation@5@@Internal@Collections@Foundation@Windows@@SAJAEBUFeaturePropertyItemEquality@@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem,FeaturePropertyItemEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem>>::Make(FeaturePropertyItemEquality const &,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem,FeaturePropertyItemEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeaturePropertyItem>> * *)
0x1800394e3  mov     rcx, [rsp+0F8h]; this
0x1800394eb  test    eax, eax
0x1800394ed  js      loc_180039663
0x1800394f3  lea     rcx, [rsp+0F8h+var_A8]
0x1800394f8  call    ?StagingControls_GetAllFeatureProperties@@YA?AV?$unordered_map@KV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@@2@@std@@XZ; StagingControls_GetAllFeatureProperties(void)
0x1800394fd  nop
0x1800394fe  mov     rsi, [rsp+0F8h+var_A0]
0x180039503  mov     rbx, [rsi]
0x180039506  cmp     rbx, rsi
0x180039509  jnz     short loc_18003954A
0x18003950b  lea     rcx, [rsp+0F8h+var_A8]
0x180039510  call    ??1?$_Hash@V?$_Umap_traits@KV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x180039515  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x18003951a  mov     rax, [rcx]
0x18003951d  mov     rdx, r15
0x180039520  mov     rax, [rax+40h]
0x180039524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039529  mov     rcx, [rsp+0F8h]; this
0x180039531  test    eax, eax
0x180039533  js      loc_180039677
0x180039539  lea     rcx, [rsp+0F8h+var_D8]
0x18003953e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039543  xor     eax, eax
0x180039545  jmp     loc_180039642
0x18003954a  mov     r14, [rbx+20h]
0x18003954e  mov     rdi, [r14]
0x180039551  cmp     rdi, r14
0x180039554  jnz     short loc_18003955B
0x180039556  mov     rbx, [rbx]
0x180039559  jmp     short loc_180039506
0x18003955b  xorps   xmm0, xmm0
0x18003955e  xor     eax, eax
0x180039560  movups  xmmword ptr [rsp+0F8h+newString], xmm0
0x180039565  mov     [rsp+0F8h+var_B8], rax
0x18003956a  mov     eax, [rbx+10h]
0x18003956d  mov     dword ptr [rsp+0F8h+newString], eax
0x180039571  lea     rcx, [rdi+10h]
0x180039575  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003957a  mov     [rsp+0F8h+var_D0], rax
0x18003957f  lea     rdx, [rsp+0F8h+var_D0]
0x180039584  lea     rcx, [rsp+0F8h+var_68]
0x18003958c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180039591  nop
0x180039592  lea     rdx, [rsp+0F8h+newString+8]; newString
0x180039597  mov     rcx, [rax+18h]; string
0x18003959b  call    cs:__imp_WindowsDuplicateString
0x1800395a1  mov     rcx, [rsp+0F8h]; this
0x1800395a9  test    eax, eax
0x1800395ab  js      loc_18003968C
0x1800395b1  lea     rcx, [rdi+30h]
0x1800395b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800395ba  mov     [rsp+0F8h+var_D0], rax
0x1800395bf  lea     rdx, [rsp+0F8h+var_D0]
0x1800395c4  lea     rcx, [rsp+0F8h+var_68]
0x1800395cc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800395d1  nop
0x1800395d2  lea     rdx, [rsp+0F8h+var_B8]; newString
0x1800395d7  mov     rcx, [rax+18h]; string
0x1800395db  call    cs:__imp_WindowsDuplicateString
0x1800395e1  mov     rcx, [rsp+0F8h]; this
0x1800395e9  test    eax, eax
0x1800395eb  js      loc_1800396A1
0x1800395f1  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x1800395f6  movups  xmm0, xmmword ptr [rsp+0F8h+newString]
0x1800395fb  movaps  [rsp+0F8h+var_68], xmm0
0x180039603  movsd   xmm1, [rsp+0F8h+var_B8]
0x180039609  movsd   [rsp+0F8h+var_58], xmm1
0x180039612  mov     rax, [rcx]
0x180039615  lea     rdx, [rsp+0F8h+var_68]
0x18003961d  mov     rax, [rax+68h]
0x180039621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039626  mov     rcx, [rsp+0F8h]; this
0x18003962e  test    eax, eax
0x180039630  js      loc_1800396B6
0x180039636  mov     rdi, [rdi]
0x180039639  jmp     loc_180039551
0x18003963e  mov     eax, [rsp+0F8h+var_D8]
0x180039642  mov     rcx, [rsp+0F8h+var_48]
0x18003964a  xor     rcx, rsp; StackCookie
0x18003964d  call    __security_check_cookie
0x180039652  add     rsp, 0C8h
0x180039659  pop     r15
0x18003965b  pop     r14
0x18003965d  pop     r13
0x18003965f  pop     rdi
0x180039660  pop     rsi
0x180039661  pop     rbx
0x180039662  retn
0x180039663  mov     r9d, eax; char *
0x180039666  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18003966d  mov     edx, 2D9h; void *
0x180039672  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039677  mov     r9d, eax; char *
0x18003967a  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x180039681  mov     edx, 2E7h; void *
0x180039686  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003968c  mov     r9d, eax; char *
0x18003968f  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x180039696  mov     edx, 2E1h; void *
0x18003969b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800396a1  mov     r9d, eax; char *
0x1800396a4  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x1800396ab  mov     edx, 2E2h; void *
0x1800396b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800396b6  mov     r9d, eax; char *
0x1800396b9  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x1800396c0  mov     edx, 2E3h; void *
0x1800396c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
