# FlagConfigurationEngine::QueryAllFlags(Windows::Foundation::Collections::IVectorView<Windows::Internal::ConfigurationManagement::Flags::IFlag *> * *)

- ea: `0x1800a0ce0`
- end: `0x1800a11fb`
- name: `?QueryAllFlags@FlagConfigurationEngine@@UEAAJPEAPEAU?$IVectorView@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1307`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000796c`
- `0x18000949c`
- `0x18000fef0`
- `0x18004b4dc`
- `0x180096bd4`
- `0x18009b7a0`
- `0x18009c398`
- `0x18009cefc`
- `0x18009e708`
- `0x1800a0550`
- `0x1800a0ce0`
- `0x1800a5f24`
- `0x1800b7010`

## string_xrefs

- `0x1800a0d0f`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a0d7f`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a0e2b`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a0f06`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a0fc8`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a10be`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FlagConfigurationEngine::QueryAllFlags(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  const char *v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  ConfigurationManagement::Flags::DataModel::InventoryFlag *v9; // rbx
  ConfigurationManagement::Flags::DataModel::InventoryFlag *v10; // r15
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rax
  int v20; // [rsp+20h] [rbp-78h]
  _BYTE v21[8]; // [rsp+30h] [rbp-68h] BYREF
  std::_Ref_count_base *v22; // [rsp+38h] [rbp-60h]
  _BYTE v23[16]; // [rsp+40h] [rbp-58h] BYREF
  ConfigurationManagement::Flags::DataModel::InventoryFlag *v24; // [rsp+50h] [rbp-48h] BYREF
  __int128 v25; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v27; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v29; // [rsp+B8h] [rbp+20h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    try
    {
      FlagConfigurationEngine::GetInventoryFilter();
      std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v23);
      ConfigurationManagement::Flags::InventoryFilter::FilterFlagsByMetadata(v21, &v24, v23);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v23);
      if ( v24 == (ConfigurationManagement::Flags::DataModel::InventoryFlag *)v25 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
          (const char *)0x80070490LL,
          v20);
        if ( v24 )
        {
          std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v24);
          std::_Deallocate<16>(v24, 16 * ((__int64)(*((_QWORD *)&v25 + 1) - (_QWORD)v24) >> 4));
          v24 = 0;
          v25 = 0;
        }
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
        result = 2147943568LL;
      }
      else
      {
        v27 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(
               v6,
               &v27);
        v8 = v7;
        if ( v7 >= 0 )
        {
          v9 = v24;
          v10 = (ConfigurationManagement::Flags::DataModel::InventoryFlag *)v25;
          while ( v9 != v10 )
          {
            v28 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
            v20 = 0;
            v11 = FlagConfigurationEngine::ConvertInventoryFlagToFlag(a1, v9, &v28, 0);
            v12 = v11;
            if ( v11 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCA,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
                (const char *)(unsigned int)v11,
                0);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              if ( v24 )
              {
                std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v24);
                std::_Deallocate<16>(v24, 16 * ((__int64)(*((_QWORD *)&v25 + 1) - (_QWORD)v24) >> 4));
                v24 = 0;
                v25 = 0;
              }
              if ( v22 )
                std::_Ref_count_base::_Decref(v22);
              result = v12;
              goto LABEL_45;
            }
            v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 104LL))(v27, v28);
            v14 = v13;
            if ( v13 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
                (const char *)(unsigned int)v13,
                0);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              if ( v24 )
              {
                std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v24);
                std::_Deallocate<16>(v24, 16 * ((__int64)(*((_QWORD *)&v25 + 1) - (_QWORD)v24) >> 4));
                v24 = 0;
                v25 = 0;
              }
              if ( v22 )
                std::_Ref_count_base::_Decref(v22);
              result = v14;
              goto LABEL_45;
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
            v9 = (ConfigurationManagement::Flags::DataModel::InventoryFlag *)((char *)v9 + 240);
          }
          v29 = 0;
          v15 = v27;
          v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 64LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
          v17 = v16(v15, &v29);
          v18 = v17;
          if ( v17 >= 0 )
          {
            v19 = v29;
            v29 = 0;
            *a2 = v19;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
            if ( v24 )
            {
              std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v24);
              std::_Deallocate<16>(v24, 16 * ((__int64)(*((_QWORD *)&v25 + 1) - (_QWORD)v24) >> 4));
              v24 = 0;
              v25 = 0;
            }
            if ( v22 )
              std::_Ref_count_base::_Decref(v22);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCF,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
              (const char *)(unsigned int)v17,
              v20);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
            if ( v24 )
            {
              std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v24);
              std::_Deallocate<16>(v24, 16 * ((__int64)(*((_QWORD *)&v25 + 1) - (_QWORD)v24) >> 4));
              v24 = 0;
              v25 = 0;
            }
            if ( v22 )
              std::_Ref_count_base::_Decref(v22);
            result = v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC5,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
            (const char *)(unsigned int)v7,
            v20);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
          if ( v24 )
          {
            std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v24);
            std::_Deallocate<16>(v24, 16 * ((__int64)(*((_QWORD *)&v25 + 1) - (_QWORD)v24) >> 4));
            v24 = 0;
            v25 = 0;
          }
          if ( v22 )
            std::_Ref_count_base::_Decref(v22);
          result = v8;
        }
      }
    }
    catch ( ... )
    {
      LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0xD3,
                       (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagcon"
                                     "figurationengine.cpp",
                       v5);
      return (unsigned int)v27;
    }
LABEL_45:
    ;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
      (const char *)0x80070057LL,
      v20);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800a0ce0  mov     [rsp+arg_0], rbx
0x1800a0ce5  push    rsi
0x1800a0ce6  push    rdi
0x1800a0ce7  push    r12
0x1800a0ce9  push    r14
0x1800a0ceb  push    r15
0x1800a0ced  sub     rsp, 70h
0x1800a0cf1  mov     rsi, rdx
0x1800a0cf4  mov     r14, rcx
0x1800a0cf7  xor     r12d, r12d
0x1800a0cfa  test    rdx, rdx
0x1800a0cfd  jnz     short loc_1800A0D27
0x1800a0cff  mov     rcx, [rsp+98h]; this
0x1800a0d07  mov     ebx, 80070057h
0x1800a0d0c  mov     r9d, ebx; char *
0x1800a0d0f  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a0d16  mov     edx, 0BDh; void *
0x1800a0d1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0d20  mov     eax, ebx
0x1800a0d22  jmp     loc_1800A11E5
0x1800a0d27  mov     [rdx], r12
0x1800a0d2a  lea     rdx, [rsp+98h+var_68]
0x1800a0d2f  call    ?GetInventoryFilter@FlagConfigurationEngine@@QEAA?AVInventoryFilter@Flags@ConfigurationManagement@@XZ; FlagConfigurationEngine::GetInventoryFilter(void)
0x1800a0d34  nop
0x1800a0d35  lea     rcx, [rsp+98h+var_58]
0x1800a0d3a  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800a0d3f  nop
0x1800a0d40  lea     r8, [rsp+98h+var_58]
0x1800a0d45  lea     rdx, [rsp+98h+var_48]
0x1800a0d4a  lea     rcx, [rsp+98h+var_68]
0x1800a0d4f  call    ?FilterFlagsByMetadata@InventoryFilter@Flags@ConfigurationManagement@@QEBA?AV?$vector@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@5@@Z; ConfigurationManagement::Flags::InventoryFilter::FilterFlagsByMetadata(std::map<std::wstring,std::wstring> const &)
0x1800a0d54  nop
0x1800a0d55  lea     rcx, [rsp+98h+var_58]
0x1800a0d5a  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800a0d5f  mov     rax, qword ptr [rsp+98h+var_40]
0x1800a0d64  cmp     [rsp+98h+var_48], rax
0x1800a0d69  jnz     loc_1800A0DF4
0x1800a0d6f  mov     rcx, [rsp+98h]; this
0x1800a0d77  mov     ebx, 80070490h
0x1800a0d7c  mov     r9d, ebx; char *
0x1800a0d7f  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a0d86  mov     edx, 0C2h; void *
0x1800a0d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0d90  nop
0x1800a0d91  mov     rcx, [rsp+98h+var_48]; this
0x1800a0d96  test    rcx, rcx
0x1800a0d99  jz      short loc_1800A0DDE
0x1800a0d9b  mov     rdx, qword ptr [rsp+98h+var_40]
0x1800a0da0  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a0da5  mov     rcx, [rsp+98h+var_48]
0x1800a0daa  mov     rax, qword ptr [rsp+98h+var_40+8]
0x1800a0daf  sub     rax, rcx
0x1800a0db2  sar     rax, 4
0x1800a0db6  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a0dc0  imul    rax, rdx
0x1800a0dc4  imul    rdx, rax, 0F0h
0x1800a0dcb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0dd0  mov     [rsp+98h+var_48], r12
0x1800a0dd5  xorps   xmm0, xmm0
0x1800a0dd8  movdqu  [rsp+98h+var_40], xmm0
0x1800a0dde  mov     rcx, [rsp+98h+var_60]; this
0x1800a0de3  test    rcx, rcx
0x1800a0de6  jz      short loc_1800A0DED
0x1800a0de8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a0ded  mov     eax, ebx
0x1800a0def  jmp     loc_1800A11E5
0x1800a0df4  mov     [rsp+98h+arg_8], r12
0x1800a0dfc  lea     rcx, [rsp+98h+arg_8]
0x1800a0e04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0e09  lea     rdx, [rsp+98h+arg_8]
0x1800a0e11  call    ??$CreateExternalObjectVector@UIFlag@Flags@ConfigurationManagement@Internal@Windows@@V?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>> * *)
0x1800a0e16  mov     ebx, eax
0x1800a0e18  test    eax, eax
0x1800a0e1a  jns     loc_1800A0EAE
0x1800a0e20  mov     rcx, [rsp+98h]; this
0x1800a0e28  mov     r9d, eax; char *
0x1800a0e2b  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a0e32  mov     edx, 0C5h; void *
0x1800a0e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0e3c  nop
0x1800a0e3d  lea     rcx, [rsp+98h+arg_8]
0x1800a0e45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0e4a  nop
0x1800a0e4b  mov     rcx, [rsp+98h+var_48]; this
0x1800a0e50  test    rcx, rcx
0x1800a0e53  jz      short loc_1800A0E98
0x1800a0e55  mov     rdx, qword ptr [rsp+98h+var_40]
0x1800a0e5a  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a0e5f  mov     rcx, [rsp+98h+var_48]
0x1800a0e64  mov     rax, qword ptr [rsp+98h+var_40+8]
0x1800a0e69  sub     rax, rcx
0x1800a0e6c  sar     rax, 4
0x1800a0e70  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a0e7a  imul    rax, rdx
0x1800a0e7e  imul    rdx, rax, 0F0h
0x1800a0e85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0e8a  mov     [rsp+98h+var_48], r12
0x1800a0e8f  xorps   xmm0, xmm0
0x1800a0e92  movdqu  [rsp+98h+var_40], xmm0
0x1800a0e98  mov     rcx, [rsp+98h+var_60]; this
0x1800a0e9d  test    rcx, rcx
0x1800a0ea0  jz      short loc_1800A0EA7
0x1800a0ea2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a0ea7  mov     eax, ebx
0x1800a0ea9  jmp     loc_1800A11E5
0x1800a0eae  mov     rbx, [rsp+98h+var_48]
0x1800a0eb3  mov     r15, qword ptr [rsp+98h+var_40]
0x1800a0eb8  cmp     rbx, r15
0x1800a0ebb  jz      loc_1800A1072
0x1800a0ec1  mov     [rsp+98h+arg_10], r12
0x1800a0ec9  lea     rcx, [rsp+98h+arg_10]
0x1800a0ed1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0ed6  mov     [rsp+98h+var_78], r12d; int
0x1800a0edb  xor     r9d, r9d
0x1800a0ede  lea     r8, [rsp+98h+arg_10]
0x1800a0ee6  mov     rdx, rbx
0x1800a0ee9  mov     rcx, r14
0x1800a0eec  call    ?ConvertInventoryFlagToFlag@FlagConfigurationEngine@@AEAAJAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@PEAPEAUIFlag@45Internal@Windows@@PEBUFlagStateInformation@45@W4OperationResult@4578@@Z; FlagConfigurationEngine::ConvertInventoryFlagToFlag(ConfigurationManagement::Flags::DataModel::InventoryFlag const &,Windows::Internal::ConfigurationManagement::Flags::IFlag * *,ConfigurationManagement::Flags::FlagStateInformation const *,Windows::Internal::ConfigurationManagement::Flags::OperationResult)
0x1800a0ef1  mov     edi, eax
0x1800a0ef3  test    eax, eax
0x1800a0ef5  jns     loc_1800A0F97
0x1800a0efb  mov     rcx, [rsp+98h]; this
0x1800a0f03  mov     r9d, eax; char *
0x1800a0f06  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a0f0d  mov     edx, 0CAh; void *
0x1800a0f12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0f17  nop
0x1800a0f18  lea     rcx, [rsp+98h+arg_10]
0x1800a0f20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0f25  nop
0x1800a0f26  lea     rcx, [rsp+98h+arg_8]
0x1800a0f2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0f33  nop
0x1800a0f34  mov     rcx, [rsp+98h+var_48]; this
0x1800a0f39  test    rcx, rcx
0x1800a0f3c  jz      short loc_1800A0F81
0x1800a0f3e  mov     rdx, qword ptr [rsp+98h+var_40]
0x1800a0f43  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a0f48  mov     rcx, [rsp+98h+var_48]
0x1800a0f4d  mov     rax, qword ptr [rsp+98h+var_40+8]
0x1800a0f52  sub     rax, rcx
0x1800a0f55  sar     rax, 4
0x1800a0f59  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a0f63  imul    rax, rdx
0x1800a0f67  imul    rdx, rax, 0F0h
0x1800a0f6e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0f73  mov     [rsp+98h+var_48], r12
0x1800a0f78  xorps   xmm0, xmm0
0x1800a0f7b  movdqu  [rsp+98h+var_40], xmm0
0x1800a0f81  mov     rcx, [rsp+98h+var_60]; this
0x1800a0f86  test    rcx, rcx
0x1800a0f89  jz      short loc_1800A0F90
0x1800a0f8b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a0f90  mov     eax, edi
0x1800a0f92  jmp     loc_1800A11E5
0x1800a0f97  mov     rcx, [rsp+98h+arg_8]
0x1800a0f9f  mov     rax, [rcx]
0x1800a0fa2  mov     rdx, [rsp+98h+arg_10]
0x1800a0faa  mov     rax, [rax+68h]
0x1800a0fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0fb3  mov     edi, eax
0x1800a0fb5  test    eax, eax
0x1800a0fb7  jns     loc_1800A1059
0x1800a0fbd  mov     rcx, [rsp+98h]; this
0x1800a0fc5  mov     r9d, eax; char *
0x1800a0fc8  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a0fcf  mov     edx, 0CBh; void *
0x1800a0fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0fd9  nop
0x1800a0fda  lea     rcx, [rsp+98h+arg_10]
0x1800a0fe2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0fe7  nop
0x1800a0fe8  lea     rcx, [rsp+98h+arg_8]
0x1800a0ff0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0ff5  nop
0x1800a0ff6  mov     rcx, [rsp+98h+var_48]; this
0x1800a0ffb  test    rcx, rcx
0x1800a0ffe  jz      short loc_1800A1043
0x1800a1000  mov     rdx, qword ptr [rsp+98h+var_40]
0x1800a1005  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a100a  mov     rcx, [rsp+98h+var_48]
0x1800a100f  mov     rax, qword ptr [rsp+98h+var_40+8]
0x1800a1014  sub     rax, rcx
0x1800a1017  sar     rax, 4
0x1800a101b  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a1025  imul    rax, rdx
0x1800a1029  imul    rdx, rax, 0F0h
0x1800a1030  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a1035  mov     [rsp+98h+var_48], r12
0x1800a103a  xorps   xmm0, xmm0
0x1800a103d  movdqu  [rsp+98h+var_40], xmm0
0x1800a1043  mov     rcx, [rsp+98h+var_60]; this
0x1800a1048  test    rcx, rcx
0x1800a104b  jz      short loc_1800A1052
0x1800a104d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1052  mov     eax, edi
0x1800a1054  jmp     loc_1800A11E5
0x1800a1059  lea     rcx, [rsp+98h+arg_10]
0x1800a1061  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1066  add     rbx, 0F0h
0x1800a106d  jmp     loc_1800A0EB8
0x1800a1072  mov     [rsp+98h+arg_18], r12
0x1800a107a  mov     rdi, [rsp+98h+arg_8]
0x1800a1082  mov     rax, [rdi]
0x1800a1085  mov     rbx, [rax+40h]
0x1800a1089  lea     rcx, [rsp+98h+arg_18]
0x1800a1091  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1096  lea     rdx, [rsp+98h+arg_18]
0x1800a109e  mov     rcx, rdi
0x1800a10a1  mov     rax, rbx
0x1800a10a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a10a9  mov     ebx, eax
0x1800a10ab  test    eax, eax
0x1800a10ad  jns     loc_1800A114F
0x1800a10b3  mov     rcx, [rsp+98h]; this
0x1800a10bb  mov     r9d, eax; char *
0x1800a10be  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a10c5  mov     edx, 0CFh; void *
0x1800a10ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a10cf  nop
0x1800a10d0  lea     rcx, [rsp+98h+arg_18]
0x1800a10d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a10dd  nop
0x1800a10de  lea     rcx, [rsp+98h+arg_8]
0x1800a10e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a10eb  nop
0x1800a10ec  mov     rcx, [rsp+98h+var_48]; this
0x1800a10f1  test    rcx, rcx
0x1800a10f4  jz      short loc_1800A1139
0x1800a10f6  mov     rdx, qword ptr [rsp+98h+var_40]
0x1800a10fb  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1100  mov     rcx, [rsp+98h+var_48]
0x1800a1105  mov     rax, qword ptr [rsp+98h+var_40+8]
0x1800a110a  sub     rax, rcx
0x1800a110d  sar     rax, 4
0x1800a1111  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a111b  imul    rax, rdx
0x1800a111f  imul    rdx, rax, 0F0h
0x1800a1126  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a112b  mov     [rsp+98h+var_48], r12
0x1800a1130  xorps   xmm0, xmm0
0x1800a1133  movdqu  [rsp+98h+var_40], xmm0
0x1800a1139  mov     rcx, [rsp+98h+var_60]; this
0x1800a113e  test    rcx, rcx
0x1800a1141  jz      short loc_1800A1148
0x1800a1143  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1148  mov     eax, ebx
0x1800a114a  jmp     loc_1800A11E5
0x1800a114f  mov     rax, [rsp+98h+arg_18]
0x1800a1157  mov     [rsp+98h+arg_18], r12
0x1800a115f  mov     [rsi], rax
0x1800a1162  lea     rcx, [rsp+98h+arg_18]
0x1800a116a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a116f  nop
0x1800a1170  lea     rcx, [rsp+98h+arg_8]
0x1800a1178  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a117d  nop
0x1800a117e  mov     rcx, [rsp+98h+var_48]; this
0x1800a1183  test    rcx, rcx
0x1800a1186  jz      short loc_1800A11CB
0x1800a1188  mov     rdx, qword ptr [rsp+98h+var_40]
0x1800a118d  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1192  mov     rcx, [rsp+98h+var_48]
0x1800a1197  mov     rax, qword ptr [rsp+98h+var_40+8]
0x1800a119c  sub     rax, rcx
0x1800a119f  sar     rax, 4
0x1800a11a3  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a11ad  imul    rax, rdx
0x1800a11b1  imul    rdx, rax, 0F0h
0x1800a11b8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a11bd  mov     [rsp+98h+var_48], r12
0x1800a11c2  xorps   xmm0, xmm0
0x1800a11c5  movdqu  [rsp+98h+var_40], xmm0
0x1800a11cb  mov     rcx, [rsp+98h+var_60]; this
0x1800a11d0  test    rcx, rcx
0x1800a11d3  jz      short loc_1800A11DA
0x1800a11d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a11da  xor     eax, eax
0x1800a11dc  jmp     short loc_1800A11E5
0x1800a11de  mov     eax, dword ptr [rsp+98h+arg_8]
0x1800a11e5  mov     rbx, [rsp+98h+arg_0]
0x1800a11ed  add     rsp, 70h
0x1800a11f1  pop     r15
0x1800a11f3  pop     r14
0x1800a11f5  pop     r12
0x1800a11f7  pop     rdi
0x1800a11f8  pop     rsi
0x1800a11f9  retn
```
