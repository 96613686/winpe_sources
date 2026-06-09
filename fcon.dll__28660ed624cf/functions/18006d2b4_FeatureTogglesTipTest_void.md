# FeatureTogglesTipTest(void)

- ea: `0x18006d2b4`
- end: `0x18006d3fe`
- name: `?FeatureTogglesTipTest@@YAXXZ`
- size: `330`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006e1d0`

## callees

- `0x180023dd0`
- `0x180023fc8`
- `0x180024064`
- `0x1800247e4`
- `0x180025634`
- `0x18006d2b4`
- `0x18006e46c`
- `0x18006e4b8`
- `0x18006e55c`

## import_xrefs

- `api-ms-win-core-featuretoggles-l1-1-0!GetFeatureTogglesChangeToken` at `0x18006d32b`
- `api-ms-win-core-featuretoggles-l1-1-0!GetFeatureTogglesChangeToken` at `0x18006d356`
- `api-ms-win-core-featuretoggles-l1-1-0!GetFeatureTogglesChangeToken` at `0x18006d32b`
- `api-ms-win-core-featuretoggles-l1-1-0!GetFeatureTogglesChangeToken` at `0x18006d356`

## string_xrefs

- `0x18006d391`: `FeatureExperimentsTIP::reason::CompletedSuccessfully`
- `0x18006d3be`: `FeatureExperimentsTIP::reason::PayloadCommitted`

## pseudocode

```c
void FeatureTogglesTipTest(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  int v2; // edi
  unsigned int v3; // ebx
  unsigned int v4; // eax
  const char *v5; // rdx
  char *v6; // rcx
  const char *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r10
  __int64 v11; // [rsp+20h] [rbp-58h] BYREF
  void **v12; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v13[48]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v14; // [rsp+68h] [rbp-10h]
  __int64 v15; // [rsp+80h] [rbp+8h] BYREF

  v15 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_FCON_FeatureTogglesUsageTest_attributes,tip2::test_data_basic>>::start(
    &v15,
    &v11);
  v12 = &tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v13,
    (struct wil::details::IFailureCallback *)&v12,
    0,
    1);
  v14 = v15;
  if ( v15 )
    _InterlockedAdd((volatile signed __int32 *)(v15 + 336), 1u);
  wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v15);
  v0 = `ft::key<57371640,ft::details::always_enabled_key,_ft_57371640,0>::_cache'::`2'::s_cache;
  v1 = GetFeatureTogglesChangeToken();
  if ( (v0 & 0x7FF) == v1 )
    v0 >>= 31;
  else
    LOBYTE(v0) = ft::key<57371640,ft::details::always_enabled_key,_ft_57371640,0>::traits::_is_enabled(v0, v1);
  v2 = (unsigned __int8)v0;
  v3 = `ft::key<57373206,ft::details::always_enabled_key,_ft_57373206,0>::_cache'::`2'::s_cache;
  v4 = GetFeatureTogglesChangeToken();
  if ( (v3 & 0x7FF) == v4 )
    v3 >>= 31;
  else
    LOBYTE(v3) = ft::key<57373206,ft::details::always_enabled_key,_ft_57373206,0>::traits::_is_enabled(v3, v4);
  switch ( v2 | (2 * (unsigned __int8)v3) )
  {
    case 0:
      goto LABEL_16;
    case 1:
      v6 = "FeatureExperimentsTIP::reason::ExperimentReconcileIgnored";
      goto LABEL_17;
    case 2:
      v6 = "FeatureExperimentsTIP::reason::IgnoredByPolicy";
      goto LABEL_17;
  }
  if ( (v2 | (2 * (unsigned __int8)v3)) != 3 )
  {
LABEL_16:
    v6 = "FeatureExperimentsTIP::reason::PayloadCommitted";
    goto LABEL_17;
  }
  v6 = "FeatureExperimentsTIP::reason::CompletedSuccessfully";
LABEL_17:
  v7 = tip2::details::reason_string((tip2::details *)v6, v5);
  LOBYTE(v8) = 1;
  tip2::details::shared_data<0,0,1>::complete_without_lock(v10, v8, v9, v7);
  tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v12);
}

```

## disassembly

```asm
0x18006d2b4  mov     rax, rsp
0x18006d2b7  mov     [rax+10h], rbx
0x18006d2bb  mov     [rax+18h], rsi
0x18006d2bf  push    rdi
0x18006d2c0  sub     rsp, 70h
0x18006d2c4  mov     qword ptr [rax+8], 0
0x18006d2cc  lea     rdx, [rax-58h]
0x18006d2d0  lea     rcx, [rax+8]
0x18006d2d4  call    ?start@?$tip_test@V?$merged_data@U_tip_FCON_FeatureTogglesUsageTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FCON_FeatureTogglesUsageTest_attributes,tip2::test_data_basic>>::start(void)
0x18006d2d9  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_FCON_WinCSApplyFlagsByKeys_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable'
0x18006d2e0  mov     [rsp+78h+var_48], rax
0x18006d2e5  mov     esi, 1
0x18006d2ea  mov     r9b, sil; bool
0x18006d2ed  xor     r8d, r8d; struct wil::CallContextInfo *
0x18006d2f0  lea     rdx, [rsp+78h+var_48]; struct wil::details::IFailureCallback *
0x18006d2f5  lea     rcx, [rsp+78h+var_40]; this
0x18006d2fa  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18006d2ff  mov     rax, [rsp+78h+arg_0]
0x18006d307  mov     [rsp+78h+var_10], rax
0x18006d30c  test    rax, rax
0x18006d30f  jz      short loc_18006D318
0x18006d311  lock add [rax+150h], esi
0x18006d318  lea     rcx, [rsp+78h+arg_0]
0x18006d320  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FCON_ProcessGovernedFeatureUsage_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x18006d325  mov     ebx, cs:?s_cache@?1??_cache@?$key@$0DGLGLPI@Ualways_enabled_key@details@ft@@U_ft_57371640@@$0A@@ft@@CAAEATft_key_cache@@XZ@4T4@A; ft_key_cache `ft::key<57371640,ft::details::always_enabled_key,_ft_57371640,0>::_cache(void)'::`2'::s_cache
0x18006d32b  call    cs:__imp_GetFeatureTogglesChangeToken
0x18006d331  mov     ecx, ebx
0x18006d333  and     ecx, 7FFh
0x18006d339  cmp     ecx, eax
0x18006d33b  jnz     short loc_18006D342
0x18006d33d  shr     ebx, 1Fh
0x18006d340  jmp     short loc_18006D34D
0x18006d342  mov     edx, eax
0x18006d344  mov     ecx, ebx
0x18006d346  call    ?_is_enabled@traits@?$key@$0DGLGLPI@Ualways_enabled_key@details@ft@@U_ft_57371640@@$0A@@ft@@KA_NTft_key_cache@@I@Z; ft::key<57371640,ft::details::always_enabled_key,_ft_57371640,0>::traits::_is_enabled(ft_key_cache,uint)
0x18006d34b  mov     bl, al
0x18006d34d  movzx   edi, bl
0x18006d350  mov     ebx, cs:?s_cache@?1??_cache@?$key@$0DGLHCBG@Ualways_enabled_key@details@ft@@U_ft_57373206@@$0A@@ft@@CAAEATft_key_cache@@XZ@4T4@A; ft_key_cache `ft::key<57373206,ft::details::always_enabled_key,_ft_57373206,0>::_cache(void)'::`2'::s_cache
0x18006d356  call    cs:__imp_GetFeatureTogglesChangeToken
0x18006d35c  mov     ecx, ebx
0x18006d35e  and     ecx, 7FFh
0x18006d364  cmp     ecx, eax
0x18006d366  jnz     short loc_18006D36D
0x18006d368  shr     ebx, 1Fh
0x18006d36b  jmp     short loc_18006D378
0x18006d36d  mov     edx, eax
0x18006d36f  mov     ecx, ebx
0x18006d371  call    ?_is_enabled@traits@?$key@$0DGLHCBG@Ualways_enabled_key@details@ft@@U_ft_57373206@@$0A@@ft@@KA_NTft_key_cache@@I@Z; ft::key<57373206,ft::details::always_enabled_key,_ft_57373206,0>::traits::_is_enabled(ft_key_cache,uint)
0x18006d376  mov     bl, al
0x18006d378  movzx   ecx, bl
0x18006d37b  add     ecx, ecx
0x18006d37d  or      ecx, edi
0x18006d37f  jz      short loc_18006D3B8
0x18006d381  sub     ecx, esi
0x18006d383  jz      short loc_18006D3A9
0x18006d385  sub     ecx, esi
0x18006d387  jz      short loc_18006D39A
0x18006d389  cmp     ecx, esi
0x18006d38b  jnz     short loc_18006D3B8
0x18006d38d  movzx   r8d, si
0x18006d391  lea     rcx, aFeatureexperim_0; "FeatureExperimentsTIP::reason::Complete"...
0x18006d398  jmp     short loc_18006D3C5
0x18006d39a  mov     r8d, 3
0x18006d3a0  lea     rcx, aFeatureexperim_2; "FeatureExperimentsTIP::reason::IgnoredB"...
0x18006d3a7  jmp     short loc_18006D3C5
0x18006d3a9  mov     r8d, 2
0x18006d3af  lea     rcx, aFeatureexperim_11; "FeatureExperimentsTIP::reason::Experime"...
0x18006d3b6  jmp     short loc_18006D3C5
0x18006d3b8  mov     r8d, 4
0x18006d3be  lea     rcx, aFeatureexperim_7; "FeatureExperimentsTIP::reason::PayloadC"...
0x18006d3c5  mov     r10, [rsp+78h+var_10]
0x18006d3ca  add     r10, 8
0x18006d3ce  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18006d3d3  mov     r9, rax
0x18006d3d6  mov     dl, sil
0x18006d3d9  mov     rcx, r10
0x18006d3dc  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x18006d3e1  lea     rcx, [rsp+78h+var_48]
0x18006d3e6  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x18006d3eb  nop
0x18006d3ec  lea     r11, [rsp+78h+var_8]
0x18006d3f1  mov     rbx, [r11+18h]
0x18006d3f5  mov     rsi, [r11+20h]
0x18006d3f9  mov     rsp, r11
0x18006d3fc  pop     rdi
0x18006d3fd  retn
```
