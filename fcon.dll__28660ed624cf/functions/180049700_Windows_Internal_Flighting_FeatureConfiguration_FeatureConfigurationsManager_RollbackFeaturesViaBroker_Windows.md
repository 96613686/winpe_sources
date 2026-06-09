# Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::RollbackFeaturesViaBroker(Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy> *)

- ea: `0x180049700`
- end: `0x18004999d`
- name: `?RollbackFeaturesViaBroker@FeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@UEAAJPEAU?$IVectorView@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@@Collections@Foundation@5@@Z`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003220`
- `0x18000fef0`
- `0x180010450`
- `0x1800107b0`
- `0x1800109ac`
- `0x180015af4`
- `0x180019704`
- `0x180019890`
- `0x18002cbf4`
- `0x1800352c0`
- `0x180036254`
- `0x180049700`
- `0x18004c7a8`
- `0x18004c85c`
- `0x18004ca60`
- `0x18004d7d0`
- `0x180075fa0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800497b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800497b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180049874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180049874`

## string_xrefs

- `0x1800497f2`: `RollbackPolicy`
- `0x18004998a`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::RollbackFeaturesViaBroker(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  char IsEnabled; // al
  unsigned int v4; // ecx
  const char *v5; // r9
  __int64 v6; // rdx
  HSTRING v7; // rbx
  __int64 v8; // rax
  int i; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rax
  INT32 result; // [rsp+20h] [rbp-128h] BYREF
  __int64 v14; // [rsp+28h] [rbp-120h] BYREF
  unsigned int v15; // [rsp+30h] [rbp-118h] BYREF
  int v16; // [rsp+34h] [rbp-114h]
  __int128 v17; // [rsp+38h] [rbp-110h]
  __int128 v18; // [rsp+48h] [rbp-100h] BYREF
  __int64 v19; // [rsp+58h] [rbp-F0h]
  __int64 v20; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+70h] [rbp-D8h] BYREF
  int v23; // [rsp+78h] [rbp-D0h]
  __int128 v24; // [rsp+80h] [rbp-C8h]
  __int128 v25; // [rsp+90h] [rbp-B8h]
  char v26[8]; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+A8h] [rbp-A0h]
  int v28; // [rsp+E8h] [rbp-60h]
  _BYTE v29[32]; // [rsp+110h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v18 = 0;
  v19 = 0;
  v14 = a2;
  v22 = a2;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  try
  {
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>,wil::err_exception_policy>::end();
    for ( i = v23; i != v28; i = ++v23 )
    {
      v2 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>,wil::err_exception_policy>::vector_iterator::operator*(&v22);
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_alrStagingTool>::GetImpl'::`2'::impl);
      v4 = *(_DWORD *)v2;
      if ( IsEnabled )
      {
        DWORD1(v17) = 0;
        v15 = v4;
        v16 = *(_DWORD *)(v2 + 4);
        LODWORD(v17) = *(unsigned __int8 *)(v2 + 24);
        *((_QWORD *)&v17 + 1) = WindowsGetStringRawBuffer(*(HSTRING *)(v2 + 16), 0);
        std::vector<__MIDL_ISmartFeatureRolloutBroker_0001>::push_back(&v18, &v15);
      }
      else
      {
        v14 = v4 | 0x400000000LL;
        StagingControls_GetFeatureProperties(v26, v14);
        std::wstring::wstring(v29);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
          v26,
          &v20,
          v29);
        std::wstring::_Tidy_deallocate(v29, v6);
        if ( v20 != v27 )
        {
          result = 0;
          v7 = *(HSTRING *)(v2 + 16);
          v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20 + 48);
          v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v29, &v21);
          WindowsCompareStringOrdinal(*(HSTRING *)(v8 + 24), v7, &result);
          if ( !result )
          {
            v15 = *(_DWORD *)v2;
            v16 = 4;
            v17 = 0u;
            std::vector<__MIDL_ISmartFeatureRolloutBroker_0001>::push_back(&v18, &v15);
          }
        }
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v26);
      }
    }
    v10 = v18;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v18 + 1) - v18) >> 3) )
    {
      wil::CoCreateInstance<ISmartFeatureRolloutBroker,wil::err_exception_policy>(&v14);
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v14 + 32LL))(
              v14,
              0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v18 + 1) - v18) >> 3));
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x42A,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
          (const char *)(unsigned int)v11,
          result);
      wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v14);
      v10 = v18;
    }
    if ( v10 )
      std::_Deallocate<16>(v10, 8 * ((v19 - v10) >> 3));
    v12 = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x42F,
                           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featurec"
                                         "onfigurationsmanager.cpp",
                           v5);
  }
  return v12;
}

```

## disassembly

```asm
0x180049700  mov     r11, rsp
0x180049703  mov     [r11+8], rbx
0x180049707  push    rdi
0x180049708  sub     rsp, 140h
0x18004970f  mov     rax, cs:__security_cookie
0x180049716  xor     rax, rsp
0x180049719  mov     [rsp+148h+var_18], rax
0x180049721  xorps   xmm0, xmm0
0x180049724  movdqu  [rsp+148h+var_100], xmm0
0x18004972a  mov     [rsp+148h+var_F0], 0
0x180049733  mov     [rsp+148h+var_120], rdx
0x180049738  mov     [rsp+148h+var_D8], rdx
0x18004973d  mov     [rsp+148h+var_D0], 0
0x180049745  movups  [rsp+148h+var_C8], xmm0
0x18004974d  movups  [rsp+148h+var_B8], xmm0
0x180049755  lea     rdx, [r11-68h]
0x180049759  lea     rcx, [rsp+148h+var_120]
0x18004975e  call    ?end@?$vector_range@U?$IVectorView@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>,wil::err_exception_policy>::end(void)
0x180049763  mov     eax, [rsp+148h+var_D0]
0x180049767  cmp     eax, [rsp+148h+var_60]
0x18004976e  jz      loc_1800498CC
0x180049774  lea     rcx, [rsp+148h+var_D8]
0x180049779  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBUtype@?$MapToSmartType@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@X@details@2@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18004977e  mov     rdi, rax
0x180049781  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_alrStagingTool@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_alrStagingTool@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool> `wil::Feature<__WilFeatureTraits_Feature_alrStagingTool>::GetImpl(void)'::`2'::impl
0x180049788  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_alrStagingTool@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_alrStagingTool>::__private_IsEnabled(void)
0x18004978d  mov     ecx, [rdi]
0x18004978f  test    al, al
0x180049791  jz      short loc_1800497D3
0x180049793  mov     dword ptr [rsp+148h+var_110+4], 0
0x18004979b  mov     [rsp+148h+var_118], ecx
0x18004979f  mov     eax, [rdi+4]
0x1800497a2  mov     [rsp+148h+var_114], eax
0x1800497a6  movzx   eax, byte ptr [rdi+18h]
0x1800497aa  mov     dword ptr [rsp+148h+var_110], eax
0x1800497ae  xor     edx, edx; length
0x1800497b0  mov     rcx, [rdi+10h]; string
0x1800497b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800497ba  mov     qword ptr [rsp+148h+var_110+8], rax
0x1800497bf  lea     rdx, [rsp+148h+var_118]
0x1800497c4  lea     rcx, [rsp+148h+var_100]
0x1800497c9  call    ?push_back@?$vector@U__MIDL_ISmartFeatureRolloutBroker_0001@@V?$allocator@U__MIDL_ISmartFeatureRolloutBroker_0001@@@std@@@std@@QEAAX$$QEAU__MIDL_ISmartFeatureRolloutBroker_0001@@@Z; std::vector<__MIDL_ISmartFeatureRolloutBroker_0001>::push_back(__MIDL_ISmartFeatureRolloutBroker_0001 &&)
0x1800497ce  jmp     loc_1800498BD
0x1800497d3  mov     dword ptr [rsp+148h+var_120], ecx
0x1800497d7  mov     dword ptr [rsp+148h+var_120+4], 4
0x1800497df  mov     rdx, [rsp+148h+var_120]
0x1800497e4  lea     rcx, [rsp+148h+var_A8]
0x1800497ec  call    ?StagingControls_GetFeatureProperties@@YA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@U_RTL_FEATURE_CONFIGURATION_ID@@@Z; StagingControls_GetFeatureProperties(_RTL_FEATURE_CONFIGURATION_ID)
0x1800497f1  nop
0x1800497f2  lea     rdx, ?RollbackPolicy@FeatureMetadataUtils@@3QBGB; "RollbackPolicy"
0x1800497f9  lea     rcx, [rsp+148h+var_38]
0x180049801  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049806  lea     r8, [rsp+148h+var_38]
0x18004980e  lea     rdx, [rsp+148h+var_E8]
0x180049813  lea     rcx, [rsp+148h+var_A8]
0x18004981b  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180049820  lea     rcx, [rsp+148h+var_38]
0x180049828  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004982d  mov     rcx, [rsp+148h+var_E8]
0x180049832  cmp     rcx, [rsp+148h+var_A0]
0x18004983a  jz      short loc_1800498B0
0x18004983c  mov     [rsp+148h+result], 0
0x180049844  mov     rbx, [rdi+10h]
0x180049848  add     rcx, 30h ; '0'
0x18004984c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049851  mov     [rsp+148h+var_E0], rax
0x180049856  lea     rdx, [rsp+148h+var_E0]
0x18004985b  lea     rcx, [rsp+148h+var_38]
0x180049863  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049868  lea     r8, [rsp+148h+result]; result
0x18004986d  mov     rdx, rbx; string2
0x180049870  mov     rcx, [rax+18h]; string1
0x180049874  call    cs:__imp_WindowsCompareStringOrdinal
0x18004987a  cmp     [rsp+148h+result], 0
0x18004987f  jnz     short loc_1800498B0
0x180049881  mov     eax, [rdi]
0x180049883  mov     [rsp+148h+var_118], eax
0x180049887  mov     [rsp+148h+var_114], 4
0x18004988f  xorps   xmm0, xmm0
0x180049892  movups  [rsp+148h+var_110], xmm0
0x180049897  mov     qword ptr [rsp+148h+var_110+8], 0
0x1800498a0  lea     rdx, [rsp+148h+var_118]
0x1800498a5  lea     rcx, [rsp+148h+var_100]
0x1800498aa  call    ?push_back@?$vector@U__MIDL_ISmartFeatureRolloutBroker_0001@@V?$allocator@U__MIDL_ISmartFeatureRolloutBroker_0001@@@std@@@std@@QEAAX$$QEAU__MIDL_ISmartFeatureRolloutBroker_0001@@@Z; std::vector<__MIDL_ISmartFeatureRolloutBroker_0001>::push_back(__MIDL_ISmartFeatureRolloutBroker_0001 &&)
0x1800498af  nop
0x1800498b0  lea     rcx, [rsp+148h+var_A8]
0x1800498b8  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800498bd  mov     eax, [rsp+148h+var_D0]
0x1800498c1  inc     eax
0x1800498c3  mov     [rsp+148h+var_D0], eax
0x1800498c7  jmp     loc_180049767
0x1800498cc  mov     rax, qword ptr [rsp+148h+var_100+8]
0x1800498d1  mov     rcx, qword ptr [rsp+148h+var_100]
0x1800498d6  sub     rax, rcx
0x1800498d9  sar     rax, 3
0x1800498dd  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1800498e7  imul    rax, rbx
0x1800498eb  test    rax, rax
0x1800498ee  jz      short loc_18004993C
0x1800498f0  lea     rcx, [rsp+148h+var_120]
0x1800498f5  call    ??$CoCreateInstance@UISmartFeatureRolloutBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UISmartFeatureRolloutBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<ISmartFeatureRolloutBroker,wil::err_exception_policy>(_GUID const &,ulong)
0x1800498fa  nop
0x1800498fb  mov     rcx, [rsp+148h+var_120]
0x180049900  mov     r8, qword ptr [rsp+148h+var_100]
0x180049905  mov     rax, [rcx]
0x180049908  mov     rdx, qword ptr [rsp+148h+var_100+8]
0x18004990d  sub     rdx, r8
0x180049910  sar     rdx, 3
0x180049914  imul    rdx, rbx
0x180049918  mov     rax, [rax+20h]
0x18004991c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049921  mov     rcx, [rsp+148h]; this
0x180049929  test    eax, eax
0x18004992b  js      short loc_180049987
0x18004992d  lea     rcx, [rsp+148h+var_120]
0x180049932  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180049937  mov     rcx, qword ptr [rsp+148h+var_100]
0x18004993c  test    rcx, rcx
0x18004993f  jz      short loc_18004995E
0x180049941  mov     rax, [rsp+148h+var_F0]
0x180049946  sub     rax, rcx
0x180049949  sar     rax, 3
0x18004994d  imul    rax, rbx
0x180049951  lea     rdx, [rax+rax*2]
0x180049955  shl     rdx, 3
0x180049959  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004995e  xor     eax, eax
0x180049960  jmp     short loc_180049966
0x180049962  mov     eax, [rsp+148h+result]
0x180049966  mov     rcx, [rsp+148h+var_18]
0x18004996e  xor     rcx, rsp; StackCookie
0x180049971  call    __security_check_cookie
0x180049976  mov     rbx, [rsp+148h+arg_0]
0x18004997e  add     rsp, 140h
0x180049985  pop     rdi
0x180049986  retn
0x180049987  mov     r9d, eax; char *
0x18004998a  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x180049991  mov     edx, 42Ah; void *
0x180049996  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
