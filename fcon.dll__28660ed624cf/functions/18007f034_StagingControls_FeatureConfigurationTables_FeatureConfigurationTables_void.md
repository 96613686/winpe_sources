# StagingControls::FeatureConfigurationTables::FeatureConfigurationTables(void)

- ea: `0x18007f034`
- end: `0x18007f1eb`
- name: `??0FeatureConfigurationTables@StagingControls@@QEAA@XZ`
- size: `439`
- prototype: `__int64 __fastcall(StagingControls::FeatureConfigurationTables *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18006b1f4`
- `0x18006c8f8`
- `0x1800aecb0`

## callees

- `0x1800036fc`
- `0x18001974c`
- `0x180035f4c`
- `0x18004b4dc`
- `0x18004c08c`
- `0x18007ee8c`
- `0x18007ef38`
- `0x18007f034`
- `0x18007f2a4`
- `0x18007f38c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007f082`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007f082`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f0a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f0b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f0a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f0b6`

## string_xrefs

- `0x18007f07b`: `ntdll.dll`
- `0x18007f0ac`: `RtlQueryAllInternalFeatureConfigurations`
- `0x18007f1d9`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\featureconfigurationtables.cpp`
- `0x18007f098`: `RtlQueryAllInternalRuntimeFeatureConfigurations`

## pseudocode

```c
StagingControls::FeatureConfigurationTables *__fastcall StagingControls::FeatureConfigurationTables::FeatureConfigurationTables(
        StagingControls::FeatureConfigurationTables *this)
{
  HMODULE ModuleHandleW; // rax
  const char *v3; // r9
  HMODULE v4; // r14
  __int64 v5; // rax
  void *v6; // rax
  __int64 v7; // rax
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // rax
  std::_Ref_count_base *v11[2]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v12[8]; // [rsp+40h] [rbp-30h] BYREF
  std::_Ref_count_base *v13; // [rsp+48h] [rbp-28h]
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v17; // [rsp+90h] [rbp+20h] BYREF
  __int64 v18; // [rsp+98h] [rbp+28h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v4 = ModuleHandleW;
  if ( !ModuleHandleW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)8,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\featureconfigurationtables.cpp",
      v3);
  *((_QWORD *)this + 6) = GetProcAddress(ModuleHandleW, "RtlQueryAllInternalRuntimeFeatureConfigurations");
  *((_QWORD *)this + 7) = GetProcAddress(v4, "RtlQueryAllInternalFeatureConfigurations");
  v14 = 0;
  v15 = 0;
  *(_OWORD *)v11 = 0;
  v18 = 0;
  v17 = 0;
  if ( (unsigned __int8)StagingControls::FeatureConfigurationTables::GetAllRuntimeConfigurations(
                          (_DWORD)this,
                          (unsigned int)&v17,
                          (unsigned int)v11,
                          (unsigned int)&v18,
                          (__int64)&v14) )
  {
    v5 = std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(
           v12,
           &v14,
           &v17);
    std::shared_ptr<ITreatmentsProvider>::operator=((char *)this + 16, v5);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    v6 = operator new(0x58u);
    v7 = std::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>(
           v6,
           &v18,
           v11,
           &v17);
    *(_QWORD *)this = v7 + 16;
    v8 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v7;
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  if ( (unsigned __int8)StagingControls::FeatureConfigurationTables::GetAllBootConfigurations(this, &v17, &v14) )
  {
    v9 = std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(
           v12,
           &v14,
           &v17);
    std::shared_ptr<ITreatmentsProvider>::operator=((char *)this + 32, v9);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
  }
  if ( v11[1] )
    std::_Ref_count_base::_Decref(v11[1]);
  std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v14);
  return this;
}

```

## disassembly

```asm
0x18007f034  mov     [rsp-18h+arg_10], rbx
0x18007f039  mov     [rsp-18h+arg_18], rsi
0x18007f03e  push    rbp
0x18007f03f  push    rdi
0x18007f040  push    r14
0x18007f042  mov     rbp, rsp
0x18007f045  sub     rsp, 70h
0x18007f049  mov     rbx, rcx
0x18007f04c  mov     qword ptr [rcx], 0
0x18007f053  mov     qword ptr [rcx+8], 0
0x18007f05b  mov     qword ptr [rcx+10h], 0
0x18007f063  mov     qword ptr [rcx+18h], 0
0x18007f06b  mov     qword ptr [rcx+20h], 0
0x18007f073  mov     qword ptr [rcx+28h], 0
0x18007f07b  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18007f082  call    cs:__imp_GetModuleHandleW
0x18007f088  mov     r14, rax
0x18007f08b  mov     rcx, [rbp+18h]; this
0x18007f08f  test    rax, rax
0x18007f092  jz      loc_18007F1D9
0x18007f098  lea     rdx, aRtlqueryallint_0; "RtlQueryAllInternalRuntimeFeatureConfig"...
0x18007f09f  mov     rcx, rax; hModule
0x18007f0a2  call    cs:__imp_GetProcAddress
0x18007f0a8  mov     [rbx+30h], rax
0x18007f0ac  lea     rdx, aRtlqueryallint; "RtlQueryAllInternalFeatureConfiguration"...
0x18007f0b3  mov     rcx, r14; hModule
0x18007f0b6  call    cs:__imp_GetProcAddress
0x18007f0bc  mov     [rbx+38h], rax
0x18007f0c0  xorps   xmm0, xmm0
0x18007f0c3  movdqu  [rbp+var_20], xmm0
0x18007f0c8  mov     [rbp+var_10], 0
0x18007f0d0  xorps   xmm1, xmm1
0x18007f0d3  movdqu  xmmword ptr [rbp+var_40], xmm1
0x18007f0d8  mov     [rbp+arg_8], 0
0x18007f0e0  mov     [rbp+arg_0], 0
0x18007f0e8  lea     rax, [rbp+var_20]
0x18007f0ec  mov     [rsp+70h+var_50], rax
0x18007f0f1  lea     r9, [rbp+arg_8]
0x18007f0f5  lea     r8, [rbp+var_40]
0x18007f0f9  lea     rdx, [rbp+arg_0]
0x18007f0fd  mov     rcx, rbx
0x18007f100  call    ?GetAllRuntimeConfigurations@FeatureConfigurationTables@StagingControls@@AEAA_NAEA_KAEAV?$shared_ptr@E@std@@0AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@4@@Z; StagingControls::FeatureConfigurationTables::GetAllRuntimeConfigurations(unsigned __int64 &,std::shared_ptr<uchar> &,unsigned __int64 &,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x18007f105  test    al, al
0x18007f107  jz      short loc_18007F16B
0x18007f109  lea     r8, [rbp+arg_0]
0x18007f10d  lea     rdx, [rbp+var_20]
0x18007f111  lea     rcx, [rbp+var_30]
0x18007f115  call    ??$make_shared@VFeatureOverrides@StagingControls@@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEA_K@std@@YA?AV?$shared_ptr@VFeatureOverrides@StagingControls@@@0@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@0@AEA_K@Z; std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &)
0x18007f11a  mov     rdx, rax
0x18007f11d  lea     rcx, [rbx+10h]
0x18007f121  call    ??4?$shared_ptr@VITreatmentsProvider@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ITreatmentsProvider>::operator=(std::shared_ptr<ITreatmentsProvider> &&)
0x18007f126  mov     rcx, [rbp+var_28]; this
0x18007f12a  test    rcx, rcx
0x18007f12d  jz      short loc_18007F134
0x18007f12f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007f134  mov     ecx, 58h ; 'X'; Size
0x18007f139  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007f13e  lea     r9, [rbp+arg_0]
0x18007f142  lea     r8, [rbp+var_40]
0x18007f146  lea     rdx, [rbp+arg_8]
0x18007f14a  mov     rcx, rax
0x18007f14d  call    ??$?0AEA_KAEAV?$shared_ptr@E@std@@AEA_K@?$_Ref_count_obj2@VGovernedFeaturesTable@StagingControls@@@std@@QEAA@AEA_KAEAV?$shared_ptr@E@1@0@Z; std::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>(unsigned __int64 &,std::shared_ptr<uchar> &,unsigned __int64 &)
0x18007f152  lea     rcx, [rax+10h]
0x18007f156  mov     [rbx], rcx
0x18007f159  mov     rcx, [rbx+8]; this
0x18007f15d  mov     [rbx+8], rax
0x18007f161  test    rcx, rcx
0x18007f164  jz      short loc_18007F16B
0x18007f166  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007f16b  lea     r8, [rbp+var_20]
0x18007f16f  lea     rdx, [rbp+arg_0]
0x18007f173  mov     rcx, rbx
0x18007f176  call    ?GetAllBootConfigurations@FeatureConfigurationTables@StagingControls@@AEAA_NAEA_KAEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@Z; StagingControls::FeatureConfigurationTables::GetAllBootConfigurations(unsigned __int64 &,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x18007f17b  test    al, al
0x18007f17d  jz      short loc_18007F1AA
0x18007f17f  lea     r8, [rbp+arg_0]
0x18007f183  lea     rdx, [rbp+var_20]
0x18007f187  lea     rcx, [rbp+var_30]
0x18007f18b  call    ??$make_shared@VFeatureOverrides@StagingControls@@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEA_K@std@@YA?AV?$shared_ptr@VFeatureOverrides@StagingControls@@@0@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@0@AEA_K@Z; std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &)
0x18007f190  mov     rdx, rax
0x18007f193  lea     rcx, [rbx+20h]
0x18007f197  call    ??4?$shared_ptr@VITreatmentsProvider@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ITreatmentsProvider>::operator=(std::shared_ptr<ITreatmentsProvider> &&)
0x18007f19c  mov     rcx, [rbp+var_28]; this
0x18007f1a0  test    rcx, rcx
0x18007f1a3  jz      short loc_18007F1AA
0x18007f1a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007f1aa  mov     rcx, [rbp+var_40+8]; this
0x18007f1ae  test    rcx, rcx
0x18007f1b1  jz      short loc_18007F1B8
0x18007f1b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007f1b8  lea     rcx, [rbp+var_20]
0x18007f1bc  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x18007f1c1  mov     rax, rbx
0x18007f1c4  lea     r11, [rsp+70h+var_s0]
0x18007f1c9  mov     rbx, [r11+30h]
0x18007f1cd  mov     rsi, [r11+38h]
0x18007f1d1  mov     rsp, r11
0x18007f1d4  pop     r14
0x18007f1d6  pop     rdi
0x18007f1d7  pop     rbp
0x18007f1d8  retn
0x18007f1d9  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\featuremanage"...
0x18007f1e0  mov     edx, 8; void *
0x18007f1e5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
