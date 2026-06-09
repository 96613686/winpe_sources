# FlagConfigurationEngine::QueryFlagsByMetadata(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::Collections::IVectorView<Windows::Internal::ConfigurationManagement::Flags::IFlag *> * *)

- ea: `0x1800a17a0`
- end: `0x1800a1d11`
- name: `?QueryFlagsByMetadata@FlagConfigurationEngine@@UEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAU?$IVectorView@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@345@@Z`
- size: `1393`
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
- `0x18009cefc`
- `0x18009e50c`
- `0x18009e708`
- `0x1800a0550`
- `0x1800a17a0`
- `0x1800a5f24`
- `0x1800b7010`

## string_xrefs

- `0x1800a17d2`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a17ff`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a1868`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a191f`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a1a05`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a1ad2`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`
- `0x1800a1bca`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FlagConfigurationEngine::QueryFlagsByMetadata(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _QWORD *a3)
{
  __int64 result; // rax
  const char *v7; // r9
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  ConfigurationManagement::Flags::DataModel::InventoryFlag *v11; // rbx
  ConfigurationManagement::Flags::DataModel::InventoryFlag *v12; // r15
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  int v22; // [rsp+20h] [rbp-78h]
  __int64 v23; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v24[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-50h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-48h]
  ConfigurationManagement::Flags::DataModel::InventoryFlag *v27; // [rsp+58h] [rbp-40h] BYREF
  __int128 v28; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v30; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v31; // [rsp+B8h] [rbp+20h] BYREF

  if ( a2 )
  {
    if ( a3 )
    {
      *a3 = 0;
      try
      {
        FlagConfigurationEngine::GetInventoryFilter();
        FlagConfigurationEngine::ConvertHStringMetadataToMap((__int64)v24, a2);
        ConfigurationManagement::Flags::InventoryFilter::FilterFlagsByMetadata(v25, &v27, v24);
        if ( v27 == (ConfigurationManagement::Flags::DataModel::InventoryFlag *)v28 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
            (const char *)0x80070490LL,
            v22);
          if ( v27 )
          {
            std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v27);
            std::_Deallocate<16>(v27, 16 * ((__int64)(*((_QWORD *)&v28 + 1) - (_QWORD)v27) >> 4));
            v27 = 0;
            v28 = 0;
          }
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v24);
          if ( v26 )
            std::_Ref_count_base::_Decref(v26);
          result = 2147943568LL;
        }
        else
        {
          v30 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(
                 v8,
                 &v30);
          v10 = v9;
          if ( v9 >= 0 )
          {
            v11 = v27;
            v12 = (ConfigurationManagement::Flags::DataModel::InventoryFlag *)v28;
            while ( v11 != v12 )
            {
              v31 = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
              v22 = 0;
              v13 = FlagConfigurationEngine::ConvertInventoryFlagToFlag(a1, v11, &v31, 0);
              v14 = v13;
              if ( v13 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xFB,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
                  (const char *)(unsigned int)v13,
                  0);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                if ( v27 )
                {
                  std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v27);
                  std::_Deallocate<16>(v27, 16 * ((__int64)(*((_QWORD *)&v28 + 1) - (_QWORD)v27) >> 4));
                  v27 = 0;
                  v28 = 0;
                }
                std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v24);
                if ( v26 )
                  std::_Ref_count_base::_Decref(v26);
                result = v14;
                goto LABEL_47;
              }
              v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 104LL))(v30, v31);
              v16 = v15;
              if ( v15 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xFC,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
                  (const char *)(unsigned int)v15,
                  0);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                if ( v27 )
                {
                  std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v27);
                  std::_Deallocate<16>(v27, 16 * ((__int64)(*((_QWORD *)&v28 + 1) - (_QWORD)v27) >> 4));
                  v27 = 0;
                  v28 = 0;
                }
                std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v24);
                if ( v26 )
                  std::_Ref_count_base::_Decref(v26);
                result = v16;
                goto LABEL_47;
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
              v11 = (ConfigurationManagement::Flags::DataModel::InventoryFlag *)((char *)v11 + 240);
            }
            v23 = 0;
            v17 = v30;
            v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 64LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
            v19 = v18(v17, &v23);
            v20 = v19;
            if ( v19 >= 0 )
            {
              v21 = v23;
              v23 = 0;
              *a3 = v21;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
              if ( v27 )
              {
                std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v27);
                std::_Deallocate<16>(v27, 16 * ((__int64)(*((_QWORD *)&v28 + 1) - (_QWORD)v27) >> 4));
                v27 = 0;
                v28 = 0;
              }
              std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v24);
              if ( v26 )
                std::_Ref_count_base::_Decref(v26);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x100,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
                (const char *)(unsigned int)v19,
                v22);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
              if ( v27 )
              {
                std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v27);
                std::_Deallocate<16>(v27, 16 * ((__int64)(*((_QWORD *)&v28 + 1) - (_QWORD)v27) >> 4));
                v27 = 0;
                v28 = 0;
              }
              std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v24);
              if ( v26 )
                std::_Ref_count_base::_Decref(v26);
              result = v20;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF6,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
              (const char *)(unsigned int)v9,
              v22);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
            if ( v27 )
            {
              std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(v27);
              std::_Deallocate<16>(v27, 16 * ((__int64)(*((_QWORD *)&v28 + 1) - (_QWORD)v27) >> 4));
              v27 = 0;
              v28 = 0;
            }
            std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v24);
            if ( v26 )
              std::_Ref_count_base::_Decref(v26);
            result = v10;
          }
        }
      }
      catch ( ... )
      {
        LODWORD(v30) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x104,
                         (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagc"
                                       "onfigurationengine.cpp",
                         v7);
        return (unsigned int)v30;
      }
LABEL_47:
      ;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationengine.cpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800a17a0  mov     [rsp+arg_0], rbx
0x1800a17a5  push    rsi
0x1800a17a6  push    rdi
0x1800a17a7  push    r12
0x1800a17a9  push    r14
0x1800a17ab  push    r15
0x1800a17ad  sub     rsp, 70h
0x1800a17b1  mov     rsi, r8
0x1800a17b4  mov     rbx, rdx
0x1800a17b7  mov     r14, rcx
0x1800a17ba  xor     r12d, r12d
0x1800a17bd  test    rdx, rdx
0x1800a17c0  jnz     short loc_1800A17EA
0x1800a17c2  mov     rcx, [rsp+98h]; this
0x1800a17ca  mov     ebx, 80070057h
0x1800a17cf  mov     r9d, ebx; char *
0x1800a17d2  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a17d9  mov     edx, 0EBh; void *
0x1800a17de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a17e3  mov     eax, ebx
0x1800a17e5  jmp     loc_1800A1CFB
0x1800a17ea  test    rsi, rsi
0x1800a17ed  jnz     short loc_1800A1817
0x1800a17ef  mov     rcx, [rsp+98h]; this
0x1800a17f7  mov     ebx, 80070057h
0x1800a17fc  mov     r9d, ebx; char *
0x1800a17ff  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a1806  mov     edx, 0ECh; void *
0x1800a180b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1810  mov     eax, ebx
0x1800a1812  jmp     loc_1800A1CFB
0x1800a1817  mov     [r8], r12
0x1800a181a  lea     rdx, [rsp+98h+var_50]
0x1800a181f  call    ?GetInventoryFilter@FlagConfigurationEngine@@QEAA?AVInventoryFilter@Flags@ConfigurationManagement@@XZ; FlagConfigurationEngine::GetInventoryFilter(void)
0x1800a1824  nop
0x1800a1825  mov     rdx, rbx
0x1800a1828  lea     rcx, [rsp+98h+var_60]
0x1800a182d  call    ?ConvertHStringMetadataToMap@FlagConfigurationEngine@@CA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; FlagConfigurationEngine::ConvertHStringMetadataToMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x1800a1832  nop
0x1800a1833  lea     r8, [rsp+98h+var_60]
0x1800a1838  lea     rdx, [rsp+98h+var_40]
0x1800a183d  lea     rcx, [rsp+98h+var_50]
0x1800a1842  call    ?FilterFlagsByMetadata@InventoryFilter@Flags@ConfigurationManagement@@QEBA?AV?$vector@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@5@@Z; ConfigurationManagement::Flags::InventoryFilter::FilterFlagsByMetadata(std::map<std::wstring,std::wstring> const &)
0x1800a1847  nop
0x1800a1848  mov     rax, qword ptr [rsp+98h+var_38]
0x1800a184d  cmp     [rsp+98h+var_40], rax
0x1800a1852  jnz     loc_1800A18E8
0x1800a1858  mov     rcx, [rsp+98h]; this
0x1800a1860  mov     ebx, 80070490h
0x1800a1865  mov     r9d, ebx; char *
0x1800a1868  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a186f  mov     edx, 0F3h; void *
0x1800a1874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1879  nop
0x1800a187a  mov     rcx, [rsp+98h+var_40]; this
0x1800a187f  test    rcx, rcx
0x1800a1882  jz      short loc_1800A18C7
0x1800a1884  mov     rdx, qword ptr [rsp+98h+var_38]
0x1800a1889  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a188e  mov     rcx, [rsp+98h+var_40]
0x1800a1893  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a1898  sub     rax, rcx
0x1800a189b  sar     rax, 4
0x1800a189f  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a18a9  imul    rax, rdx
0x1800a18ad  imul    rdx, rax, 0F0h
0x1800a18b4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a18b9  mov     [rsp+98h+var_40], r12
0x1800a18be  xorps   xmm0, xmm0
0x1800a18c1  movdqu  [rsp+98h+var_38], xmm0
0x1800a18c7  lea     rcx, [rsp+98h+var_60]
0x1800a18cc  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800a18d1  nop
0x1800a18d2  mov     rcx, [rsp+98h+var_48]; this
0x1800a18d7  test    rcx, rcx
0x1800a18da  jz      short loc_1800A18E1
0x1800a18dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a18e1  mov     eax, ebx
0x1800a18e3  jmp     loc_1800A1CFB
0x1800a18e8  mov     [rsp+98h+arg_8], r12
0x1800a18f0  lea     rcx, [rsp+98h+arg_8]
0x1800a18f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a18fd  lea     rdx, [rsp+98h+arg_8]
0x1800a1905  call    ??$CreateExternalObjectVector@UIFlag@Flags@ConfigurationManagement@Internal@Windows@@V?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@4785@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ConfigurationManagement::Flags::IFlag,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ConfigurationManagement::Flags::IFlag *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ConfigurationManagement::Flags::IFlag *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ConfigurationManagement::Flags::IFlag *>> * *)
0x1800a190a  mov     ebx, eax
0x1800a190c  test    eax, eax
0x1800a190e  jns     loc_1800A19AD
0x1800a1914  mov     rcx, [rsp+98h]; this
0x1800a191c  mov     r9d, eax; char *
0x1800a191f  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a1926  mov     edx, 0F6h; void *
0x1800a192b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1930  nop
0x1800a1931  lea     rcx, [rsp+98h+arg_8]
0x1800a1939  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a193e  nop
0x1800a193f  mov     rcx, [rsp+98h+var_40]; this
0x1800a1944  test    rcx, rcx
0x1800a1947  jz      short loc_1800A198C
0x1800a1949  mov     rdx, qword ptr [rsp+98h+var_38]
0x1800a194e  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1953  mov     rcx, [rsp+98h+var_40]
0x1800a1958  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a195d  sub     rax, rcx
0x1800a1960  sar     rax, 4
0x1800a1964  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a196e  imul    rax, rdx
0x1800a1972  imul    rdx, rax, 0F0h
0x1800a1979  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a197e  mov     [rsp+98h+var_40], r12
0x1800a1983  xorps   xmm0, xmm0
0x1800a1986  movdqu  [rsp+98h+var_38], xmm0
0x1800a198c  lea     rcx, [rsp+98h+var_60]
0x1800a1991  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800a1996  nop
0x1800a1997  mov     rcx, [rsp+98h+var_48]; this
0x1800a199c  test    rcx, rcx
0x1800a199f  jz      short loc_1800A19A6
0x1800a19a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a19a6  mov     eax, ebx
0x1800a19a8  jmp     loc_1800A1CFB
0x1800a19ad  mov     rbx, [rsp+98h+var_40]
0x1800a19b2  mov     r15, qword ptr [rsp+98h+var_38]
0x1800a19b7  cmp     rbx, r15
0x1800a19ba  jz      loc_1800A1B87
0x1800a19c0  mov     [rsp+98h+arg_18], r12
0x1800a19c8  lea     rcx, [rsp+98h+arg_18]
0x1800a19d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a19d5  mov     [rsp+98h+var_78], r12d; int
0x1800a19da  xor     r9d, r9d
0x1800a19dd  lea     r8, [rsp+98h+arg_18]
0x1800a19e5  mov     rdx, rbx
0x1800a19e8  mov     rcx, r14
0x1800a19eb  call    ?ConvertInventoryFlagToFlag@FlagConfigurationEngine@@AEAAJAEBUInventoryFlag@DataModel@Flags@ConfigurationManagement@@PEAPEAUIFlag@45Internal@Windows@@PEBUFlagStateInformation@45@W4OperationResult@4578@@Z; FlagConfigurationEngine::ConvertInventoryFlagToFlag(ConfigurationManagement::Flags::DataModel::InventoryFlag const &,Windows::Internal::ConfigurationManagement::Flags::IFlag * *,ConfigurationManagement::Flags::FlagStateInformation const *,Windows::Internal::ConfigurationManagement::Flags::OperationResult)
0x1800a19f0  mov     edi, eax
0x1800a19f2  test    eax, eax
0x1800a19f4  jns     loc_1800A1AA1
0x1800a19fa  mov     rcx, [rsp+98h]; this
0x1800a1a02  mov     r9d, eax; char *
0x1800a1a05  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a1a0c  mov     edx, 0FBh; void *
0x1800a1a11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1a16  nop
0x1800a1a17  lea     rcx, [rsp+98h+arg_18]
0x1800a1a1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1a24  nop
0x1800a1a25  lea     rcx, [rsp+98h+arg_8]
0x1800a1a2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1a32  nop
0x1800a1a33  mov     rcx, [rsp+98h+var_40]; this
0x1800a1a38  test    rcx, rcx
0x1800a1a3b  jz      short loc_1800A1A80
0x1800a1a3d  mov     rdx, qword ptr [rsp+98h+var_38]
0x1800a1a42  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1a47  mov     rcx, [rsp+98h+var_40]
0x1800a1a4c  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a1a51  sub     rax, rcx
0x1800a1a54  sar     rax, 4
0x1800a1a58  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a1a62  imul    rax, rdx
0x1800a1a66  imul    rdx, rax, 0F0h
0x1800a1a6d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a1a72  mov     [rsp+98h+var_40], r12
0x1800a1a77  xorps   xmm0, xmm0
0x1800a1a7a  movdqu  [rsp+98h+var_38], xmm0
0x1800a1a80  lea     rcx, [rsp+98h+var_60]
0x1800a1a85  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800a1a8a  nop
0x1800a1a8b  mov     rcx, [rsp+98h+var_48]; this
0x1800a1a90  test    rcx, rcx
0x1800a1a93  jz      short loc_1800A1A9A
0x1800a1a95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1a9a  mov     eax, edi
0x1800a1a9c  jmp     loc_1800A1CFB
0x1800a1aa1  mov     rcx, [rsp+98h+arg_8]
0x1800a1aa9  mov     rax, [rcx]
0x1800a1aac  mov     rdx, [rsp+98h+arg_18]
0x1800a1ab4  mov     rax, [rax+68h]
0x1800a1ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1abd  mov     edi, eax
0x1800a1abf  test    eax, eax
0x1800a1ac1  jns     loc_1800A1B6E
0x1800a1ac7  mov     rcx, [rsp+98h]; this
0x1800a1acf  mov     r9d, eax; char *
0x1800a1ad2  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a1ad9  mov     edx, 0FCh; void *
0x1800a1ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1ae3  nop
0x1800a1ae4  lea     rcx, [rsp+98h+arg_18]
0x1800a1aec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1af1  nop
0x1800a1af2  lea     rcx, [rsp+98h+arg_8]
0x1800a1afa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1aff  nop
0x1800a1b00  mov     rcx, [rsp+98h+var_40]; this
0x1800a1b05  test    rcx, rcx
0x1800a1b08  jz      short loc_1800A1B4D
0x1800a1b0a  mov     rdx, qword ptr [rsp+98h+var_38]
0x1800a1b0f  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1b14  mov     rcx, [rsp+98h+var_40]
0x1800a1b19  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a1b1e  sub     rax, rcx
0x1800a1b21  sar     rax, 4
0x1800a1b25  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a1b2f  imul    rax, rdx
0x1800a1b33  imul    rdx, rax, 0F0h
0x1800a1b3a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a1b3f  mov     [rsp+98h+var_40], r12
0x1800a1b44  xorps   xmm0, xmm0
0x1800a1b47  movdqu  [rsp+98h+var_38], xmm0
0x1800a1b4d  lea     rcx, [rsp+98h+var_60]
0x1800a1b52  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800a1b57  nop
0x1800a1b58  mov     rcx, [rsp+98h+var_48]; this
0x1800a1b5d  test    rcx, rcx
0x1800a1b60  jz      short loc_1800A1B67
0x1800a1b62  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1b67  mov     eax, edi
0x1800a1b69  jmp     loc_1800A1CFB
0x1800a1b6e  lea     rcx, [rsp+98h+arg_18]
0x1800a1b76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1b7b  add     rbx, 0F0h
0x1800a1b82  jmp     loc_1800A19B7
0x1800a1b87  mov     [rsp+98h+var_68], r12
0x1800a1b8c  mov     rdi, [rsp+98h+arg_8]
0x1800a1b94  mov     rax, [rdi]
0x1800a1b97  mov     rbx, [rax+40h]
0x1800a1b9b  lea     rcx, [rsp+98h+var_68]
0x1800a1ba0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1ba5  lea     rdx, [rsp+98h+var_68]
0x1800a1baa  mov     rcx, rdi
0x1800a1bad  mov     rax, rbx
0x1800a1bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bb5  mov     ebx, eax
0x1800a1bb7  test    eax, eax
0x1800a1bb9  jns     loc_1800A1C63
0x1800a1bbf  mov     rcx, [rsp+98h]; this
0x1800a1bc7  mov     r9d, eax; char *
0x1800a1bca  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\featuremanage"...
0x1800a1bd1  mov     edx, 100h; void *
0x1800a1bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1bdb  nop
0x1800a1bdc  lea     rcx, [rsp+98h+var_68]
0x1800a1be1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1be6  nop
0x1800a1be7  lea     rcx, [rsp+98h+arg_8]
0x1800a1bef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1bf4  nop
0x1800a1bf5  mov     rcx, [rsp+98h+var_40]; this
0x1800a1bfa  test    rcx, rcx
0x1800a1bfd  jz      short loc_1800A1C42
0x1800a1bff  mov     rdx, qword ptr [rsp+98h+var_38]
0x1800a1c04  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1c09  mov     rcx, [rsp+98h+var_40]
0x1800a1c0e  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a1c13  sub     rax, rcx
0x1800a1c16  sar     rax, 4
0x1800a1c1a  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a1c24  imul    rax, rdx
0x1800a1c28  imul    rdx, rax, 0F0h
0x1800a1c2f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a1c34  mov     [rsp+98h+var_40], r12
0x1800a1c39  xorps   xmm0, xmm0
0x1800a1c3c  movdqu  [rsp+98h+var_38], xmm0
0x1800a1c42  lea     rcx, [rsp+98h+var_60]
0x1800a1c47  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800a1c4c  nop
0x1800a1c4d  mov     rcx, [rsp+98h+var_48]; this
0x1800a1c52  test    rcx, rcx
0x1800a1c55  jz      short loc_1800A1C5C
0x1800a1c57  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1c5c  mov     eax, ebx
0x1800a1c5e  jmp     loc_1800A1CFB
0x1800a1c63  mov     rax, [rsp+98h+var_68]
0x1800a1c68  mov     [rsp+98h+var_68], r12
0x1800a1c6d  mov     [rsi], rax
0x1800a1c70  lea     rcx, [rsp+98h+var_68]
0x1800a1c75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1c7a  nop
0x1800a1c7b  lea     rcx, [rsp+98h+arg_8]
0x1800a1c83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1c88  nop
0x1800a1c89  mov     rcx, [rsp+98h+var_40]; this
0x1800a1c8e  test    rcx, rcx
0x1800a1c91  jz      short loc_1800A1CD6
0x1800a1c93  mov     rdx, qword ptr [rsp+98h+var_38]
0x1800a1c98  call    ??$_Destroy_range@V?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@std@@@std@@YAXPEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@QEAU1234@AEAV?$allocator@UInventoryFlag@DataModel@Flags@ConfigurationManagement@@@0@@Z; std::_Destroy_range<std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag>>(ConfigurationManagement::Flags::DataModel::InventoryFlag *,ConfigurationManagement::Flags::DataModel::InventoryFlag * const,std::allocator<ConfigurationManagement::Flags::DataModel::InventoryFlag> &)
0x1800a1c9d  mov     rcx, [rsp+98h+var_40]
0x1800a1ca2  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800a1ca7  sub     rax, rcx
0x1800a1caa  sar     rax, 4
0x1800a1cae  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x1800a1cb8  imul    rax, rdx
0x1800a1cbc  imul    rdx, rax, 0F0h
0x1800a1cc3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a1cc8  mov     [rsp+98h+var_40], r12
0x1800a1ccd  xorps   xmm0, xmm0
0x1800a1cd0  movdqu  [rsp+98h+var_38], xmm0
0x1800a1cd6  lea     rcx, [rsp+98h+var_60]
0x1800a1cdb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
  ... truncated ...
```
