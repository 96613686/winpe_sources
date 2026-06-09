# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ApplyFlagConfigurationsViaBroker(Windows::Foundation::Collections::IVectorView<Windows::Internal::ConfigurationManagement::Flags::IFlag *> *,Windows::Foundation::Collections::IVector<Windows::Internal::ConfigurationManagement::Flags::IFlag *> * *)

- ea: `0x1800985c0`
- end: `0x1800988c7`
- name: `?ApplyFlagConfigurationsViaBroker@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@UEAAJPEAU?$IVectorView@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@Collections@Foundation@5@PEAPEAU?$IVector@PEAUIFlag@Flags@ConfigurationManagement@Internal@Windows@@@785@@Z`
- size: `775`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000796c`
- `0x18000949c`
- `0x180010154`
- `0x1800107b0`
- `0x180035660`
- `0x180096ac4`
- `0x180096f50`
- `0x18009761c`
- `0x1800985c0`
- `0x1800989c4`
- `0x1800b7010`

## string_xrefs

- `0x1800985f5`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180098622`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180098674`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180098717`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009877e`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x18009882b`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ApplyFlagConfigurationsViaBroker(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 result; // rax
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // [rsp+20h] [rbp-78h]
  __int64 v12; // [rsp+30h] [rbp-68h] BYREF
  __int128 v13; // [rsp+38h] [rbp-60h] BYREF
  __int64 v14; // [rsp+48h] [rbp-50h]
  _QWORD v15[4]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a2 )
  {
    if ( a3 )
    {
      *a3 = 0;
      try
      {
        v6 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 56LL))();
        v7 = v6;
        if ( v6 >= 0 )
        {
          v13 = 0;
          v14 = 0;
          std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Construct_n<>(&v13, 0);
          std::vector<unsigned int>::vector<unsigned int>(v15, 0);
          wil::CoCreateInstance<IFlagConfigurationBroker,wil::err_exception_policy>(&v12);
          v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v12 + 32LL))(
                 v12,
                 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v13 + 1) - v13) >> 2));
          v10 = v9;
          if ( v9 >= 0 )
            v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD *))(**(_QWORD **)(a1 + 32) + 136LL))(
                    *(_QWORD *)(a1 + 32),
                    v15,
                    0,
                    a3);
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23D,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
              (const char *)(unsigned int)v9,
              v11);
          wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v12);
          std::vector<unsigned int>::_Tidy(v15);
          std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Tidy(&v13);
          result = v10;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x230,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
            (const char *)(unsigned int)v6,
            v11);
          result = v7;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x242,
                               (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\"
                                             "flagconfigurationmanager.cpp",
                               v8);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
        (const char *)0x80070057LL,
        v11);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v11);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800985c0  mov     [rsp+arg_0], rbx
0x1800985c5  mov     [rsp+arg_10], rsi
0x1800985ca  push    rdi
0x1800985cb  push    r12
0x1800985cd  push    r13
0x1800985cf  push    r14
0x1800985d1  push    r15
0x1800985d3  sub     rsp, 70h
0x1800985d7  mov     r14, r8
0x1800985da  mov     rsi, rdx
0x1800985dd  mov     r13, rcx
0x1800985e0  test    rdx, rdx
0x1800985e3  jnz     short loc_18009860D
0x1800985e5  mov     rcx, [rsp+98h]; this
0x1800985ed  mov     ebx, 80070057h
0x1800985f2  mov     r9d, ebx; char *
0x1800985f5  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800985fc  mov     edx, 22Ah; void *
0x180098601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098606  mov     eax, ebx
0x180098608  jmp     loc_1800988AC
0x18009860d  test    r14, r14
0x180098610  jnz     short loc_18009863A
0x180098612  mov     rcx, [rsp+98h]; this
0x18009861a  mov     ebx, 80070057h
0x18009861f  mov     r9d, ebx; char *
0x180098622  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098629  mov     edx, 22Bh; void *
0x18009862e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098633  mov     eax, ebx
0x180098635  jmp     loc_1800988AC
0x18009863a  mov     qword ptr [r8], 0
0x180098641  mov     [rsp+98h+arg_8], 0
0x18009864c  mov     rax, [rdx]
0x18009864f  lea     rdx, [rsp+98h+arg_8]
0x180098657  mov     rcx, rsi
0x18009865a  mov     rax, [rax+38h]
0x18009865e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098663  mov     ebx, eax
0x180098665  test    eax, eax
0x180098667  jns     short loc_18009868C
0x180098669  mov     rcx, [rsp+98h]; this
0x180098671  mov     r9d, eax; char *
0x180098674  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009867b  mov     edx, 230h; void *
0x180098680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098685  mov     eax, ebx
0x180098687  jmp     loc_1800988AC
0x18009868c  xorps   xmm0, xmm0
0x18009868f  movdqu  [rsp+98h+var_60], xmm0
0x180098695  mov     [rsp+98h+var_50], 0
0x18009869e  mov     edx, [rsp+98h+arg_8]
0x1800986a5  lea     rcx, [rsp+98h+var_60]
0x1800986aa  call    ??$_Construct_n@$$V@?$vector@U__MIDL_IFlagConfigurationBroker_0001@@V?$allocator@U__MIDL_IFlagConfigurationBroker_0001@@@std@@@std@@AEAAX_K@Z; std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Construct_n<>(unsigned __int64)
0x1800986af  nop
0x1800986b0  mov     edx, [rsp+98h+arg_8]
0x1800986b7  lea     rcx, [rsp+98h+var_48]
0x1800986bc  call    ??0?$vector@IV?$allocator@I@std@@@std@@QEAA@_KAEBV?$allocator@I@1@@Z; std::vector<uint>::vector<uint>(unsigned __int64,std::allocator<uint> const &)
0x1800986c1  nop
0x1800986c2  xor     edi, edi
0x1800986c4  cmp     edi, [rsp+98h+arg_8]
0x1800986cb  jnb     loc_1800987DF
0x1800986d1  mov     [rsp+98h+arg_18], 0
0x1800986dd  mov     rax, [rsi]
0x1800986e0  mov     rbx, [rax+30h]
0x1800986e4  lea     rcx, [rsp+98h+arg_18]
0x1800986ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800986f1  lea     r8, [rsp+98h+arg_18]
0x1800986f9  mov     edx, edi
0x1800986fb  mov     rcx, rsi
0x1800986fe  mov     rax, rbx
0x180098701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098706  mov     ebx, eax
0x180098708  test    eax, eax
0x18009870a  jns     short loc_180098753
0x18009870c  mov     rcx, [rsp+98h]; this
0x180098714  mov     r9d, eax; char *
0x180098717  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009871e  mov     edx, 236h; void *
0x180098723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098728  nop
0x180098729  lea     rcx, [rsp+98h+arg_18]
0x180098731  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098736  nop
0x180098737  lea     rcx, [rsp+98h+var_48]
0x18009873c  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180098741  nop
0x180098742  lea     rcx, [rsp+98h+var_60]
0x180098747  call    ?_Tidy@?$vector@U__MIDL_IFlagConfigurationBroker_0001@@V?$allocator@U__MIDL_IFlagConfigurationBroker_0001@@@std@@@std@@AEAAXXZ; std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Tidy(void)
0x18009874c  mov     eax, ebx
0x18009874e  jmp     loc_1800988AC
0x180098753  lea     r12, [rdi+rdi*2]
0x180098757  mov     rax, qword ptr [rsp+98h+var_60]
0x18009875c  lea     rdx, [rax+r12*4]
0x180098760  mov     rcx, [rsp+98h+arg_18]
0x180098768  call    _anonymous_namespace___ConvertFlagToComDef
0x18009876d  mov     ebx, eax
0x18009876f  test    eax, eax
0x180098771  jns     short loc_1800987BA
0x180098773  mov     rcx, [rsp+98h]; this
0x18009877b  mov     r9d, eax; char *
0x18009877e  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098785  mov     edx, 237h; void *
0x18009878a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009878f  nop
0x180098790  lea     rcx, [rsp+98h+arg_18]
0x180098798  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009879d  nop
0x18009879e  lea     rcx, [rsp+98h+var_48]
0x1800987a3  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x1800987a8  nop
0x1800987a9  lea     rcx, [rsp+98h+var_60]
0x1800987ae  call    ?_Tidy@?$vector@U__MIDL_IFlagConfigurationBroker_0001@@V?$allocator@U__MIDL_IFlagConfigurationBroker_0001@@@std@@@std@@AEAAXXZ; std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Tidy(void)
0x1800987b3  mov     eax, ebx
0x1800987b5  jmp     loc_1800988AC
0x1800987ba  mov     rax, qword ptr [rsp+98h+var_60]
0x1800987bf  mov     ecx, [rax+r12*4]
0x1800987c3  mov     rax, [rsp+98h+var_48]
0x1800987c8  mov     [rax+rdi*4], ecx
0x1800987cb  lea     rcx, [rsp+98h+arg_18]
0x1800987d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800987d8  inc     edi
0x1800987da  jmp     loc_1800986C4
0x1800987df  lea     rcx, [rsp+98h+var_68]
0x1800987e4  call    ??$CoCreateInstance@UIFlagConfigurationBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIFlagConfigurationBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IFlagConfigurationBroker,wil::err_exception_policy>(_GUID const &,ulong)
0x1800987e9  nop
0x1800987ea  mov     rcx, [rsp+98h+var_68]
0x1800987ef  mov     r8, qword ptr [rsp+98h+var_60]
0x1800987f4  mov     rax, [rcx]
0x1800987f7  mov     rdx, qword ptr [rsp+98h+var_60+8]
0x1800987fc  sub     rdx, r8
0x1800987ff  sar     rdx, 2
0x180098803  mov     r9, 0AAAAAAAAAAAAAAABh
0x18009880d  imul    rdx, r9
0x180098811  mov     rax, [rax+20h]
0x180098815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009881a  mov     ebx, eax
0x18009881c  test    eax, eax
0x18009881e  jns     short loc_180098861
0x180098820  mov     rcx, [rsp+98h]; this
0x180098828  mov     r9d, eax; char *
0x18009882b  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098832  mov     edx, 23Dh; void *
0x180098837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009883c  nop
0x18009883d  lea     rcx, [rsp+98h+var_68]
0x180098842  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180098847  nop
0x180098848  lea     rcx, [rsp+98h+var_48]
0x18009884d  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180098852  nop
0x180098853  lea     rcx, [rsp+98h+var_60]
0x180098858  call    ?_Tidy@?$vector@U__MIDL_IFlagConfigurationBroker_0001@@V?$allocator@U__MIDL_IFlagConfigurationBroker_0001@@@std@@@std@@AEAAXXZ; std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Tidy(void)
0x18009885d  mov     eax, ebx
0x18009885f  jmp     short loc_1800988AC
0x180098861  mov     rcx, [r13+20h]
0x180098865  mov     rax, [rcx]
0x180098868  mov     r9, r14
0x18009886b  xor     r8d, r8d
0x18009886e  lea     rdx, [rsp+98h+var_48]
0x180098873  mov     rax, [rax+88h]
0x18009887a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009887f  mov     ebx, eax
0x180098881  lea     rcx, [rsp+98h+var_68]
0x180098886  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18009888b  nop
0x18009888c  lea     rcx, [rsp+98h+var_48]
0x180098891  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180098896  nop
0x180098897  lea     rcx, [rsp+98h+var_60]
0x18009889c  call    ?_Tidy@?$vector@U__MIDL_IFlagConfigurationBroker_0001@@V?$allocator@U__MIDL_IFlagConfigurationBroker_0001@@@std@@@std@@AEAAXXZ; std::vector<__MIDL_IFlagConfigurationBroker_0001>::_Tidy(void)
0x1800988a1  mov     eax, ebx
0x1800988a3  jmp     short loc_1800988AC
0x1800988a5  mov     eax, [rsp+98h+arg_8]
0x1800988ac  lea     r11, [rsp+98h+var_28]
0x1800988b1  mov     rbx, [r11+30h]
0x1800988b5  mov     rsi, [r11+40h]
0x1800988b9  mov     rsp, r11
0x1800988bc  pop     r15
0x1800988be  pop     r14
0x1800988c0  pop     r13
0x1800988c2  pop     r12
0x1800988c4  pop     rdi
0x1800988c5  retn
```
