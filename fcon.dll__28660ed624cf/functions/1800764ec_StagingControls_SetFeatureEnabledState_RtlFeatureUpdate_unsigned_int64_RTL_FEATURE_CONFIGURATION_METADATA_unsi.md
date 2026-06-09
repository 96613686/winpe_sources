# StagingControls_SetFeatureEnabledState(RtlFeatureUpdate *,unsigned __int64,_RTL_FEATURE_CONFIGURATION_METADATA *,unsigned __int64,unsigned __int64 &,bool)

- ea: `0x1800764ec`
- end: `0x18007686e`
- name: `?StagingControls_SetFeatureEnabledState@@YAJPEAURtlFeatureUpdate@@_KPEAU_RTL_FEATURE_CONFIGURATION_METADATA@@1AEA_K_N@Z`
- size: `898`
- prototype: `__int64 __usercall@<rax>(struct RtlFeatureUpdate *@<rcx>, unsigned __int64@<rdx>, struct _RTL_FEATURE_CONFIGURATION_METADATA *@<r8>, unsigned __int64@<r9>, unsigned __int64 *, bool)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180038708`

## callees

- `0x18000fef0`
- `0x180023dd0`
- `0x180023fc8`
- `0x180024064`
- `0x1800247e4`
- `0x180025634`
- `0x1800613fc`
- `0x180073bf4`
- `0x180074440`
- `0x1800744ac`
- `0x180075608`
- `0x1800761c0`
- `0x1800764ec`
- `0x180076ed0`
- `0x1800771d8`
- `0x180077484`
- `0x18007c98c`
- `0x18007cacc`

## import_xrefs

- `ntdll!RtlSetFeatureConfigurations` at `0x1800767b6`
- `ntdll!RtlSetFeatureConfigurations` at `0x1800767b6`

## string_xrefs

- `0x180076800`: `FeatureExperimentsTIP::reason::CompletedSuccessfully`
- `0x1800766ad`: `FeatureExperimentsTIP::reason::StorageConfigWriteFeatureStateFailure`
- `0x180076701`: `FeatureExperimentsTIP::reason::StorageConfigWriteFeatureMetadataFailure`
- `0x1800767df`: `FeatureExperimentsTIP::reason::RtlSetFeatureConfigurationsFailure`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StagingControls_SetFeatureEnabledState(
        struct RtlFeatureUpdate *a1,
        unsigned __int64 a2,
        struct _RTL_FEATURE_CONFIGURATION_METADATA *a3,
        unsigned __int64 a4,
        unsigned __int64 *a5,
        int a6)
{
  const char *v10; // rdx
  const char *v11; // rax
  __int64 v12; // rdx
  int v13; // ebx
  char v14; // r14
  unsigned __int64 i; // rsi
  char *v16; // rbx
  struct _RTL_FEATURE_CONFIGURATION_UPDATE *v17; // rdx
  unsigned __int64 j; // rbx
  char *v19; // rsi
  struct _RTL_FEATURE_CONFIGURATION_UPDATE *v20; // rdx
  unsigned int v21; // r8d
  const char *v22; // rdx
  const char *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // r8d
  const char *v27; // rdx
  __int64 v28; // rcx
  struct _RTL_FEATURE_CONFIGURATION_UPDATE *v29; // r8
  struct _RTL_FEATURE_CONFIGURATION_UPDATE *v30; // r9
  unsigned __int64 v31; // rbx
  char *v32; // r8
  int v33; // ecx
  int v34; // eax
  const char *v35; // rdx
  unsigned int v36; // r8d
  const char *v37; // rdx
  __int64 v39; // [rsp+20h] [rbp-69h] BYREF
  _BYTE v40[16]; // [rsp+28h] [rbp-61h] BYREF
  struct _RTL_FEATURE_CONFIGURATION_UPDATE *v41[2]; // [rsp+38h] [rbp-51h] BYREF
  struct _RTL_FEATURE_CONFIGURATION_UPDATE *v42; // [rsp+48h] [rbp-41h]
  void **v43; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v44[48]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v45; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  v39 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::start(
    &v39,
    v40);
  v43 = &tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v44,
    (struct wil::details::IFailureCallback *)&v43,
    0,
    1);
  v45 = v39;
  if ( v39 )
    _InterlockedIncrement((volatile signed __int32 *)(v39 + 336));
  wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v39);
  if ( !AreFeatureUpdatesValid(a1, a2) )
  {
    v11 = tip2::details::reason_string((tip2::details *)"FeatureExperimentsTIP::reason::InvalidStatus", v10);
    LOBYTE(v12) = 3;
    tip2::details::shared_data<0,0,1>::complete_without_lock(v45 + 8, v12, 6, v11);
    v13 = -1073741811;
    goto LABEL_49;
  }
  *(_OWORD *)v41 = 0;
  v42 = 0;
  v14 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag>::GetImpl'::`2'::impl) )
  {
    for ( i = 0; i < a2; ++i )
    {
      v16 = (char *)a1 + 44 * i;
      if ( (v16[32] & 2) != 0 )
      {
        v17 = v41[1];
        if ( v41[1] == v42 )
        {
          std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_UPDATE>(
            v41,
            v41[1],
            (char *)a1 + 44 * i);
        }
        else
        {
          *(_OWORD *)v41[1] = *(_OWORD *)v16;
          *((_OWORD *)v17 + 1) = *((_OWORD *)v16 + 1);
          v41[1] = (struct _RTL_FEATURE_CONFIGURATION_UPDATE *)((char *)v41[1] + 32);
        }
        v14 |= *((_DWORD *)v16 + 9) == 1;
      }
    }
  }
  else
  {
    for ( j = 0; j < a2; ++j )
    {
      v19 = (char *)a1 + 44 * j;
      v20 = v41[1];
      if ( v41[1] == v42 )
      {
        std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_UPDATE>(
          v41,
          v41[1],
          (char *)a1 + 44 * j);
      }
      else
      {
        *(_OWORD *)v41[1] = *(_OWORD *)v19;
        *((_OWORD *)v20 + 1) = *((_OWORD *)v19 + 1);
        v41[1] = (struct _RTL_FEATURE_CONFIGURATION_UPDATE *)((char *)v41[1] + 32);
      }
      v14 |= *((_DWORD *)v19 + 9) == 1;
    }
  }
  v13 = (unsigned __int16)StorageWriter::WriteFeatureStates(v41[0], (v41[1] - v41[0]) >> 5, 1);
  if ( v13 )
    v13 |= 0xC0070000;
  if ( v13 >= 0 )
  {
    v13 = (unsigned __int16)StorageWriter::WriteFeatureMetadatas(a3, a4, 0);
    if ( v13 )
      v13 |= 0xC0070000;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x7B, v26, (const char *)(unsigned int)v13, v39);
      a6 = v13;
      FeatureExperimentTelemetry::StorageConfigWriteFeatureMetadataFailure<unsigned int>(&a6);
      v23 = tip2::details::reason_string(
              (tip2::details *)"FeatureExperimentsTIP::reason::StorageConfigWriteFeatureMetadataFailure",
              v27);
      v25 = 8;
      v28 = v45 + 8;
      LOBYTE(v24) = 3;
      goto LABEL_47;
    }
    v29 = v41[0];
    v30 = v41[1];
    if ( v41[0] != v41[1] )
    {
      v30 = v41[0];
      v41[1] = v41[0];
    }
    v31 = 0;
    if ( a2 )
    {
      do
      {
        v32 = (char *)a1 + 44 * v31;
        if ( (v32[32] & 1) != 0 )
        {
          v33 = *((_DWORD *)v32 + 10);
          if ( (v33 & 1) != 0 )
            *((_DWORD *)v32 + 4) |= 0x100u;
          if ( (v33 & 2) != 0 )
            *((_DWORD *)v32 + 4) |= 0x200u;
          if ( v30 == v42 )
          {
            std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_UPDATE>(
              v41,
              v30,
              v32);
            v30 = v41[1];
          }
          else
          {
            *(_OWORD *)v30 = *(_OWORD *)v32;
            *((_OWORD *)v30 + 1) = *((_OWORD *)v32 + 1);
            v30 = (struct _RTL_FEATURE_CONFIGURATION_UPDATE *)((char *)v41[1] + 32);
            v41[1] = (struct _RTL_FEATURE_CONFIGURATION_UPDATE *)((char *)v41[1] + 32);
          }
        }
        ++v31;
      }
      while ( v31 < a2 );
      v29 = v41[0];
    }
    v34 = RtlSetFeatureConfigurations(a5, 1, v29, (v30 - v29) >> 5);
    v13 = v34;
    if ( v34 >= 0 )
    {
      if ( v14 )
        StagingControls_NotifyPendingFeatureConfigsChanged();
      v23 = tip2::details::reason_string((tip2::details *)"FeatureExperimentsTIP::reason::CompletedSuccessfully", v35);
      v25 = 1;
      LOBYTE(v24) = 1;
      goto LABEL_46;
    }
    wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x98, v36, (const char *)(unsigned int)v34, v39);
    a6 = v13;
    FeatureExperimentTelemetry::RtlSetFeatureConfigurationsFailure<unsigned int>(&a6);
    v23 = tip2::details::reason_string(
            (tip2::details *)"FeatureExperimentsTIP::reason::RtlSetFeatureConfigurationsFailure",
            v37);
    v25 = 9;
  }
  else
  {
    wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x70, v21, (const char *)(unsigned int)v13, v39);
    a6 = v13;
    FeatureExperimentTelemetry::StorageConfigWriteFeatureStateFailure<unsigned int>(&a6);
    v23 = tip2::details::reason_string(
            (tip2::details *)"FeatureExperimentsTIP::reason::StorageConfigWriteFeatureStateFailure",
            v22);
    v25 = 7;
  }
  LOBYTE(v24) = 3;
LABEL_46:
  v28 = v45 + 8;
LABEL_47:
  tip2::details::shared_data<0,0,1>::complete_without_lock(v28, v24, v25, v23);
  if ( v41[0] )
  {
    std::_Deallocate<16>(v41[0], (v42 - v41[0]) & 0xFFFFFFFFFFFFFFE0uLL);
    v42 = 0;
    *(_OWORD *)v41 = 0;
  }
LABEL_49:
  tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v43);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800764ec  push    rbp
0x1800764ee  push    rbx
0x1800764ef  push    rsi
0x1800764f0  push    rdi
0x1800764f1  push    r12
0x1800764f3  push    r13
0x1800764f5  push    r14
0x1800764f7  push    r15
0x1800764f9  lea     rbp, [rsp-0Fh]
0x1800764fe  sub     rsp, 98h
0x180076505  mov     r12, r9
0x180076508  mov     r13, r8
0x18007650b  mov     rdi, rdx
0x18007650e  mov     r15, rcx
0x180076511  mov     [rbp+47h+var_B0], 0
0x180076519  lea     rdx, [rbp+47h+var_A8]
0x18007651d  lea     rcx, [rbp+47h+var_B0]
0x180076521  call    ?start@?$tip_test@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::start(void)
0x180076526  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_FCON_WinCSApplyFlagsByKeys_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable'
0x18007652d  mov     [rbp+47h+var_80], rax
0x180076531  mov     r9b, 1; bool
0x180076534  xor     r8d, r8d; struct wil::CallContextInfo *
0x180076537  lea     rdx, [rbp+47h+var_80]; struct wil::details::IFailureCallback *
0x18007653b  lea     rcx, [rbp+47h+var_78]; this
0x18007653f  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180076544  mov     rax, [rbp+47h+var_B0]
0x180076548  mov     [rbp+47h+var_48], rax
0x18007654c  test    rax, rax
0x18007654f  jz      short loc_180076558
0x180076551  lock inc dword ptr [rax+150h]
0x180076558  lea     rcx, [rbp+47h+var_B0]
0x18007655c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FCON_ProcessGovernedFeatureUsage_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x180076561  nop
0x180076562  mov     rdx, rdi; unsigned __int64
0x180076565  mov     rcx, r15; struct RtlFeatureUpdate *
0x180076568  call    ?AreFeatureUpdatesValid@@YA_NPEAURtlFeatureUpdate@@_K@Z; AreFeatureUpdatesValid(RtlFeatureUpdate *,unsigned __int64)
0x18007656d  test    al, al
0x18007656f  jnz     short loc_18007659F
0x180076571  lea     rcx, aFeatureexperim_6; "FeatureExperimentsTIP::reason::InvalidS"...
0x180076578  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18007657d  mov     r9, rax
0x180076580  mov     r8d, 6
0x180076586  mov     rcx, [rbp+47h+var_48]
0x18007658a  add     rcx, 8
0x18007658e  mov     dl, 3
0x180076590  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180076595  mov     ebx, 0C000000Dh
0x18007659a  jmp     loc_18007684F
0x18007659f  xorps   xmm0, xmm0
0x1800765a2  movdqu  xmmword ptr [rbp+47h+var_98], xmm0
0x1800765a7  mov     [rbp+47h+var_88], 0
0x1800765af  xor     r14b, r14b
0x1800765b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag> `wil::Feature<__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag>::GetImpl(void)'::`2'::impl
0x1800765b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckFeatureConfigStoragePersistentFlag>::__private_IsEnabled(void)
0x1800765be  test    al, al
0x1800765c0  jz      short loc_180076619
0x1800765c2  xor     esi, esi
0x1800765c4  test    rdi, rdi
0x1800765c7  jz      loc_180076664
0x1800765cd  imul    rbx, rsi, 2Ch ; ','
0x1800765d1  add     rbx, r15
0x1800765d4  test    byte ptr [rbx+20h], 2
0x1800765d8  jz      short loc_18007660F
0x1800765da  mov     rdx, [rbp+47h+var_98+8]
0x1800765de  cmp     rdx, [rbp+47h+var_88]
0x1800765e2  jz      short loc_1800765F9
0x1800765e4  movups  xmm0, xmmword ptr [rbx]
0x1800765e7  movups  xmmword ptr [rdx], xmm0
0x1800765ea  movups  xmm1, xmmword ptr [rbx+10h]
0x1800765ee  movups  xmmword ptr [rdx+10h], xmm1
0x1800765f2  add     [rbp+47h+var_98+8], 20h ; ' '
0x1800765f7  jmp     short loc_180076605
0x1800765f9  mov     r8, rbx
0x1800765fc  lea     rcx, [rbp+47h+var_98]
0x180076600  call    ??$_Emplace_reallocate@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@?$vector@U_RTL_FEATURE_CONFIGURATION_UPDATE@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@std@@@std@@AEAAPEAU_RTL_FEATURE_CONFIGURATION_UPDATE@@QEAU2@$$QEAU2@@Z; std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_UPDATE>(_RTL_FEATURE_CONFIGURATION_UPDATE * const,_RTL_FEATURE_CONFIGURATION_UPDATE &&)
0x180076605  cmp     dword ptr [rbx+24h], 1
0x180076609  setz    al
0x18007660c  or      r14b, al
0x18007660f  inc     rsi
0x180076612  cmp     rsi, rdi
0x180076615  jb      short loc_1800765CD
0x180076617  jmp     short loc_180076664
0x180076619  xor     ebx, ebx
0x18007661b  test    rdi, rdi
0x18007661e  jz      short loc_180076664
0x180076620  imul    rsi, rbx, 2Ch ; ','
0x180076624  add     rsi, r15
0x180076627  mov     rdx, [rbp+47h+var_98+8]
0x18007662b  cmp     rdx, [rbp+47h+var_88]
0x18007662f  jz      short loc_180076646
0x180076631  movups  xmm0, xmmword ptr [rsi]
0x180076634  movups  xmmword ptr [rdx], xmm0
0x180076637  movups  xmm1, xmmword ptr [rsi+10h]
0x18007663b  movups  xmmword ptr [rdx+10h], xmm1
0x18007663f  add     [rbp+47h+var_98+8], 20h ; ' '
0x180076644  jmp     short loc_180076652
0x180076646  mov     r8, rsi
0x180076649  lea     rcx, [rbp+47h+var_98]
0x18007664d  call    ??$_Emplace_reallocate@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@?$vector@U_RTL_FEATURE_CONFIGURATION_UPDATE@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@std@@@std@@AEAAPEAU_RTL_FEATURE_CONFIGURATION_UPDATE@@QEAU2@$$QEAU2@@Z; std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_UPDATE>(_RTL_FEATURE_CONFIGURATION_UPDATE * const,_RTL_FEATURE_CONFIGURATION_UPDATE &&)
0x180076652  cmp     dword ptr [rsi+24h], 1
0x180076656  setz    al
0x180076659  or      r14b, al
0x18007665c  inc     rbx
0x18007665f  cmp     rbx, rdi
0x180076662  jb      short loc_180076620
0x180076664  mov     rcx, [rbp+47h+var_98]; struct _RTL_FEATURE_CONFIGURATION_UPDATE *
0x180076668  mov     rdx, [rbp+47h+var_98+8]
0x18007666c  sub     rdx, rcx
0x18007666f  sar     rdx, 5; unsigned __int64
0x180076673  mov     r8b, 1; bool
0x180076676  call    ?WriteFeatureStates@StorageWriter@@SAJPEAU_RTL_FEATURE_CONFIGURATION_UPDATE@@_K_N@Z; StorageWriter::WriteFeatureStates(_RTL_FEATURE_CONFIGURATION_UPDATE *,unsigned __int64,bool)
0x18007667b  movzx   ebx, ax
0x18007667e  mov     eax, ebx
0x180076680  mov     esi, 0C0070000h
0x180076685  or      eax, esi
0x180076687  test    ebx, ebx
0x180076689  cmovnz  ebx, eax
0x18007668c  mov     rcx, [rbp+4Fh]; this
0x180076690  test    ebx, ebx
0x180076692  jns     short loc_1800766C6
0x180076694  mov     r9d, ebx; char *
0x180076697  mov     edx, 70h ; 'p'; void *
0x18007669c  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800766a1  mov     [rbp+47h+arg_28], ebx
0x1800766a4  lea     rcx, [rbp+47h+arg_28]
0x1800766a8  call    ??$StorageConfigWriteFeatureStateFailure@I@FeatureExperimentTelemetry@@SAX$$QEAI@Z; FeatureExperimentTelemetry::StorageConfigWriteFeatureStateFailure<uint>(uint &&)
0x1800766ad  lea     rcx, aFeatureexperim_1; "FeatureExperimentsTIP::reason::StorageC"...
0x1800766b4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800766b9  mov     r8d, 7
0x1800766bf  mov     dl, 3
0x1800766c1  jmp     loc_180076815
0x1800766c6  xor     r8d, r8d; unsigned __int16 *
0x1800766c9  mov     rdx, r12; unsigned __int64
0x1800766cc  mov     rcx, r13; struct _RTL_FEATURE_CONFIGURATION_METADATA *
0x1800766cf  call    ?WriteFeatureMetadatas@StorageWriter@@SAJPEBU_RTL_FEATURE_CONFIGURATION_METADATA@@_KPEBG@Z; StorageWriter::WriteFeatureMetadatas(_RTL_FEATURE_CONFIGURATION_METADATA const *,unsigned __int64,ushort const *)
0x1800766d4  movzx   ebx, ax
0x1800766d7  mov     eax, ebx
0x1800766d9  or      eax, esi
0x1800766db  test    ebx, ebx
0x1800766dd  cmovnz  ebx, eax
0x1800766e0  mov     rcx, [rbp+4Fh]; this
0x1800766e4  test    ebx, ebx
0x1800766e6  jns     short loc_180076721
0x1800766e8  mov     r9d, ebx; char *
0x1800766eb  mov     edx, 7Bh ; '{'; void *
0x1800766f0  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800766f5  mov     [rbp+47h+arg_28], ebx
0x1800766f8  lea     rcx, [rbp+47h+arg_28]
0x1800766fc  call    ??$StorageConfigWriteFeatureMetadataFailure@I@FeatureExperimentTelemetry@@SAX$$QEAI@Z; FeatureExperimentTelemetry::StorageConfigWriteFeatureMetadataFailure<uint>(uint &&)
0x180076701  lea     rcx, aFeatureexperim_5; "FeatureExperimentsTIP::reason::StorageC"...
0x180076708  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18007670d  mov     r8d, 8
0x180076713  mov     rcx, [rbp+47h+var_48]
0x180076717  add     rcx, r8
0x18007671a  mov     dl, 3
0x18007671c  jmp     loc_18007681D
0x180076721  mov     r8, [rbp+47h+var_98]
0x180076725  mov     r9, [rbp+47h+var_98+8]
0x180076729  cmp     r8, r9
0x18007672c  jz      short loc_180076735
0x18007672e  mov     r9, r8
0x180076731  mov     [rbp+47h+var_98+8], r8
0x180076735  xor     ebx, ebx
0x180076737  test    rdi, rdi
0x18007673a  jz      short loc_1800767A6
0x18007673c  imul    r8, rbx, 2Ch ; ','
0x180076740  add     r8, r15
0x180076743  test    byte ptr [r8+20h], 1
0x180076748  jz      short loc_18007679A
0x18007674a  mov     ecx, [r8+28h]
0x18007674e  test    cl, 1
0x180076751  jz      short loc_180076759
0x180076753  bts     dword ptr [r8+10h], 8
0x180076759  test    cl, 2
0x18007675c  jz      short loc_180076764
0x18007675e  bts     dword ptr [r8+10h], 9
0x180076764  cmp     r9, [rbp+47h+var_88]
0x180076768  jz      short loc_18007678A
0x18007676a  movups  xmm0, xmmword ptr [r8]
0x18007676e  movups  xmmword ptr [r9], xmm0
0x180076772  movups  xmm1, xmmword ptr [r8+10h]
0x180076777  movups  xmmword ptr [r9+10h], xmm1
0x18007677c  mov     r9, [rbp+47h+var_98+8]
0x180076780  add     r9, 20h ; ' '
0x180076784  mov     [rbp+47h+var_98+8], r9
0x180076788  jmp     short loc_18007679A
0x18007678a  mov     rdx, r9
0x18007678d  lea     rcx, [rbp+47h+var_98]
0x180076791  call    ??$_Emplace_reallocate@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@?$vector@U_RTL_FEATURE_CONFIGURATION_UPDATE@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@std@@@std@@AEAAPEAU_RTL_FEATURE_CONFIGURATION_UPDATE@@QEAU2@$$QEAU2@@Z; std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_UPDATE>(_RTL_FEATURE_CONFIGURATION_UPDATE * const,_RTL_FEATURE_CONFIGURATION_UPDATE &&)
0x180076796  mov     r9, [rbp+47h+var_98+8]
0x18007679a  inc     rbx
0x18007679d  cmp     rbx, rdi
0x1800767a0  jb      short loc_18007673C
0x1800767a2  mov     r8, [rbp+47h+var_98]
0x1800767a6  sub     r9, r8
0x1800767a9  sar     r9, 5
0x1800767ad  mov     edx, 1
0x1800767b2  mov     rcx, [rbp+47h+arg_20]
0x1800767b6  call    cs:__imp_RtlSetFeatureConfigurations
0x1800767bc  mov     ebx, eax
0x1800767be  mov     rcx, [rbp+4Fh]; this
0x1800767c2  test    eax, eax
0x1800767c4  jns     short loc_1800767F6
0x1800767c6  mov     r9d, eax; char *
0x1800767c9  mov     edx, 98h; void *
0x1800767ce  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800767d3  mov     [rbp+47h+arg_28], ebx
0x1800767d6  lea     rcx, [rbp+47h+arg_28]
0x1800767da  call    ??$RtlSetFeatureConfigurationsFailure@I@FeatureExperimentTelemetry@@SAX$$QEAI@Z; FeatureExperimentTelemetry::RtlSetFeatureConfigurationsFailure<uint>(uint &&)
0x1800767df  lea     rcx, aFeatureexperim_10; "FeatureExperimentsTIP::reason::RtlSetFe"...
0x1800767e6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800767eb  mov     r8d, 9
0x1800767f1  jmp     loc_1800766BF
0x1800767f6  test    r14b, r14b
0x1800767f9  jz      short loc_180076800
0x1800767fb  call    ?StagingControls_NotifyPendingFeatureConfigsChanged@@YAXXZ; StagingControls_NotifyPendingFeatureConfigsChanged(void)
0x180076800  lea     rcx, aFeatureexperim_0; "FeatureExperimentsTIP::reason::Complete"...
0x180076807  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18007680c  mov     r8d, 1
0x180076812  mov     dl, r8b
0x180076815  mov     rcx, [rbp+47h+var_48]
0x180076819  add     rcx, 8
0x18007681d  mov     r9, rax
0x180076820  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180076825  nop
0x180076826  mov     rcx, [rbp+47h+var_98]
0x18007682a  test    rcx, rcx
0x18007682d  jz      short loc_18007684F
0x18007682f  mov     rdx, [rbp+47h+var_88]
0x180076833  sub     rdx, rcx
0x180076836  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18007683a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007683f  xorps   xmm0, xmm0
0x180076842  mov     [rbp+47h+var_88], 0
0x18007684a  movdqu  xmmword ptr [rbp+47h+var_98], xmm0
0x18007684f  lea     rcx, [rbp+47h+var_80]
0x180076853  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180076858  mov     eax, ebx
0x18007685a  add     rsp, 98h
0x180076861  pop     r15
0x180076863  pop     r14
0x180076865  pop     r13
0x180076867  pop     r12
0x180076869  pop     rdi
0x18007686a  pop     rsi
0x18007686b  pop     rbx
0x18007686c  pop     rbp
0x18007686d  retn
```
