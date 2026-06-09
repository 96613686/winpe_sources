# OneCopilotRemediator::CheckAndRemediate(void)

- ea: `0x18002663c`
- end: `0x180026adc`
- name: `?CheckAndRemediate@OneCopilotRemediator@@QEAAXXZ`
- size: `1184`
- prototype: `void __fastcall(OneCopilotRemediator *__hidden this)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800273dc`
- `0x180052c24`

## callees

- `0x18000bdf0`
- `0x1800153fc`
- `0x180018c5c`
- `0x1800206c8`
- `0x1800234ec`
- `0x18002663c`
- `0x180026ae4`
- `0x180026b20`
- `0x180026b98`
- `0x180026bcc`
- `0x180026c04`
- `0x18002a3d0`
- `0x18002a85c`
- `0x18002b980`
- `0x18002b9ec`
- `0x180039bf0`
- `0x18003b5c4`
- `0x18003d0d0`
- `0x18003d128`
- `0x18003d224`
- `0x18003d4f0`
- `0x180050ffc`
- `0x180051d40`
- `0x180051d7c`
- `0x180052128`
- `0x1800522f4`
- `0x18005287c`
- `0x180052e18`
- `0x180053798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800266c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800266c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800269c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026a92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026ab5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800269c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026a92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026ab5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180026954`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180026954`

## string_xrefs

- `0x180026947`: `LastRemediationAttemptTimestamp`
- `0x18002697c`: `OneCopilotRemediationReason::uninstallation_scheduled`
- `0x18002668c`: `OneCopilotRemediationReason::new_remediation_started_before_completing_previous`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
void __fastcall OneCopilotRemediator::CheckAndRemediate(OneCopilotRemediator *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  const char *v4; // rdx
  const char *v5; // rax
  _QWORD *v6; // r10
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rbx
  _QWORD *v9; // rax
  const char *v10; // rdx
  const char *v11; // rax
  _QWORD *v12; // r10
  __int64 v13; // rdx
  const char *v14; // rdx
  const char *v15; // rax
  __int64 v16; // r10
  int InstallationSourceForAumid; // r14d
  int v18; // eax
  __int64 v19; // rcx
  const char *v20; // rdx
  const char *v21; // rax
  __int64 v22; // r10
  unsigned __int16 **v23; // r8
  int v24; // eax
  int v25; // esi
  const char *v26; // rdx
  const char *v27; // rax
  _QWORD *v28; // r9
  const char *v29; // rax
  _QWORD *v30; // r9
  const char *v31; // rdx
  const char *v32; // rax
  _QWORD *v33; // r10
  __int64 v34; // rdx
  const char *v35; // rdx
  const char *v36; // rax
  _QWORD *v37; // r10
  __int64 v38; // rdx
  int lpData; // [rsp+20h] [rbp-E8h]
  _QWORD Data[3]; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v41[3]; // [rsp+48h] [rbp-C0h] BYREF
  bool v42[8]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v43[72]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v44[4]; // [rsp+B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  Data[1] = this;
  v2 = (_QWORD *)((char *)this + 80);
  v3 = *((_QWORD *)this + 10);
  if ( v3 && tip2::details::shared_data<1,0,1>::is_running(v3 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
      v2,
      Data);
    v5 = tip2::details::reason_string(
           (tip2::details *)"OneCopilotRemediationReason::new_remediation_started_before_completing_previous",
           v4);
    LOBYTE(v7) = 2;
    tip2::details::shared_data<1,0,1>::complete_helper(*v6 + 8LL, v7, 2, v5);
    tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
  }
  v8 = (RTL_SRWLOCK *)((char *)this + 88);
  Data[2] = (char *)this + 88;
  AcquireSRWLockExclusive((PSRWLOCK)this + 11);
  v41[2] = (char *)this + 88;
  if ( *v2 && (unsigned __int8)tip2::details::shared_data<0,0,0>::has_ever_started(*v2 + 8LL) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::reset(v2);
  v9 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::ensure_data(v2);
  tip2::details::shared_data<1,0,1>::start(*v9 + 8LL, v41);
  if ( *((_DWORD *)this + 16) > 3u )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
      v2,
      Data);
    v11 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::max_retries_exceeded", v10);
    LOBYTE(v13) = 3;
    tip2::details::shared_data<1,0,1>::complete_helper(*v12 + 8LL, v13, 4, v11);
    tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
    if ( this == (OneCopilotRemediator *)-88LL )
      return;
    goto LABEL_9;
  }
  v41[0] = v2;
  tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
    v2,
    Data);
  v15 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::policy_active", v14);
  tip2::details::shared_data<1,0,1>::set_flag_value<unsigned short const *>(v16 + 8, 7, v15);
  tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
  if ( OneCopilotRemediator::HasRemediationEverSucceeded(this) )
    goto LABEL_29;
  if ( dword_1800ADDC0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800ADDC0);
    if ( dword_1800ADDC0 == -1 )
    {
      OneCopilot::GetMAISignalFuncs();
      atexit(OneCopilotRemediator::CheckAndRemediate_::_12_::_dynamic_atexit_destructor_for__signalFuncs__);
      Init_thread_footer(&dword_1800ADDC0);
    }
  }
  InstallationSourceForAumid = OneCopilot::GetInstallationSourceForAumid(L"Microsoft.Copilot_8wekyb3d8bbwe!App");
  v18 = OneCopilot::GetInstallationSourceForAumid(L"Microsoft.MicrosoftOfficeHub_8wekyb3d8bbwe!App");
  if ( InstallationSourceForAumid != 3 && v18 != 3 )
  {
    OneCopilot::EvaluateForMAI(v42);
    OneCopilotRemediator::StringifySignalResults(v19, v44, v43);
    tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
      v2,
      Data);
    v21 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::evaluate_should_remediate", v20);
    tip2::details::shared_data<1,0,1>::set_flag_value<unsigned short const *>(v22 + 8, 9, v21);
    tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
    v23 = v44;
    if ( v44[3] > (unsigned __int16 *)7 )
      v23 = (unsigned __int16 **)v44[0];
    v24 = OneCopilotRemediator::SaveEvaluationResultToRegistry(
            (HKEY *)this,
            v42[0],
            (wil::reg::reg_view_details::reg_value_type_info *)v23);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
        (const char *)(unsigned int)v24,
        lpData);
    if ( v42[0] )
    {
      OneCopilotRemediator::EnsureCopilotRegistryKeyCreated(this);
      Data[0] = 0;
      RegSetKeyValueW(*((HKEY *)this + 5), 0, L"LastRemediationAttemptTimestamp", 0xBu, Data, 8u);
      v25 = OneCopilotRemediator::ScheduleUninstallation(this, 1u);
      tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
        v2,
        Data);
      if ( v25 >= 0 )
      {
        v27 = tip2::details::reason_string(
                (tip2::details *)"OneCopilotRemediationReason::uninstallation_scheduled",
                v26);
        tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(*v28 + 8LL, 11, v27);
        tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
        std::wstring::~wstring(v44);
        std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v43);
        if ( !v8 )
          return;
LABEL_30:
        ReleaseSRWLockExclusive(v8);
        return;
      }
      v29 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::exception_thrown", v26);
      tip2::details::shared_data<1,0,1>::set_flag_value<long>(*v30 + 8LL, 0, v29, (unsigned int)v25);
    }
    else
    {
      tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
        v2,
        Data);
      v32 = tip2::details::reason_string((tip2::details *)"OneCopilotRemediationReason::no_remediation_necessary", v31);
      LOBYTE(v34) = 1;
      tip2::details::shared_data<1,0,1>::complete_helper(*v33 + 8LL, v34, 5, v32);
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
    std::wstring::~wstring(v44);
    std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v43);
LABEL_29:
    tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::complete(v2);
    if ( !v8 )
      return;
    goto LABEL_30;
  }
  tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(
    v2,
    Data);
  v36 = tip2::details::reason_string(
          (tip2::details *)"OneCopilotRemediationReason::no_remediation_necessary_does_not_have_both_apps",
          v35);
  LOBYTE(v38) = 1;
  tip2::details::shared_data<1,0,1>::complete_helper(*v37 + 8LL, v38, 6, v36);
  tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(Data);
  if ( this != (OneCopilotRemediator *)-88LL )
LABEL_9:
    ReleaseSRWLockExclusive((PSRWLOCK)this + 11);
}

```

## disassembly

```asm
0x18002663c  push    rbx
0x18002663e  push    rsi
0x18002663f  push    rdi
0x180026640  push    r14
0x180026642  sub     rsp, 0E8h
0x180026649  mov     rax, cs:__security_cookie
0x180026650  xor     rax, rsp
0x180026653  mov     [rsp+108h+var_38], rax
0x18002665b  mov     rsi, rcx
0x18002665e  mov     [rsp+108h+var_D0], rcx
0x180026663  lea     rdi, [rcx+50h]
0x180026667  mov     rcx, [rdi]
0x18002666a  test    rcx, rcx
0x18002666d  jz      short loc_1800266BA
0x18002666f  add     rcx, 8
0x180026673  call    ?is_running@?$shared_data@$00$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,1>::is_running(void)
0x180026678  test    al, al
0x18002667a  jz      short loc_1800266BA
0x18002667c  lea     rdx, [rsp+108h+Data]
0x180026681  mov     rcx, rdi
0x180026684  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180026689  mov     r10, rax
0x18002668c  lea     rcx, aOnecopilotreme_12; "OneCopilotRemediationReason::new_remedi"...
0x180026693  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026698  mov     r9, rax
0x18002669b  mov     r8d, 2
0x1800266a1  mov     rcx, [r10]
0x1800266a4  add     rcx, 8
0x1800266a8  mov     dl, r8b
0x1800266ab  call    ?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,1>::complete_helper(TestCompletionKind,ushort,char const *)
0x1800266b0  lea     rcx, [rsp+108h+Data]
0x1800266b5  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x1800266ba  lea     rbx, [rsi+58h]
0x1800266be  mov     [rsp+108h+var_C8], rbx
0x1800266c3  mov     rcx, rbx; SRWLock
0x1800266c6  call    cs:__imp_AcquireSRWLockExclusive
0x1800266cc  mov     [rsp+108h+var_B0], rbx
0x1800266d1  mov     rcx, [rdi]
0x1800266d4  test    rcx, rcx
0x1800266d7  jz      short loc_1800266EE
0x1800266d9  add     rcx, 8
0x1800266dd  call    ?has_ever_started@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::has_ever_started(void)
0x1800266e2  test    al, al
0x1800266e4  jz      short loc_1800266EE
0x1800266e6  mov     rcx, rdi
0x1800266e9  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::reset(void)
0x1800266ee  mov     rcx, rdi
0x1800266f1  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::ensure_data(void)
0x1800266f6  mov     rcx, [rax]
0x1800266f9  add     rcx, 8
0x1800266fd  lea     rdx, [rsp+108h+var_C0]
0x180026702  call    ?start@?$shared_data@$00$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,1>::start(void)
0x180026707  lea     rdx, [rsp+108h+Data]
0x18002670c  mov     rcx, rdi
0x18002670f  cmp     dword ptr [rsi+40h], 3
0x180026713  jbe     short loc_18002675E
0x180026715  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x18002671a  mov     r10, rax
0x18002671d  lea     rcx, aOnecopilotreme_4; "OneCopilotRemediationReason::max_retrie"...
0x180026724  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026729  mov     r9, rax
0x18002672c  mov     r8d, 4
0x180026732  mov     rcx, [r10]
0x180026735  add     rcx, 8
0x180026739  mov     dl, 3
0x18002673b  call    ?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,1>::complete_helper(TestCompletionKind,ushort,char const *)
0x180026740  lea     rcx, [rsp+108h+Data]
0x180026745  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x18002674a  nop
0x18002674b  test    rbx, rbx
0x18002674e  jz      short loc_180026759
0x180026750  mov     rcx, rbx; SRWLock
0x180026753  call    cs:__imp_ReleaseSRWLockExclusive
0x180026759  jmp     loc_180026ABE
0x18002675e  mov     [rsp+108h+var_C0], rdi
0x180026763  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180026768  mov     r10, [rax]
0x18002676b  mov     ecx, [rsi+30h]
0x18002676e  sub     ecx, 1
0x180026771  jz      short loc_180026798
0x180026773  sub     ecx, 1
0x180026776  jz      short loc_18002678F
0x180026778  cmp     ecx, 1
0x18002677b  jz      short loc_180026786
0x18002677d  lea     r9, aNone_0; "None"
0x180026784  jmp     short loc_18002679F
0x180026786  lea     r9, aBoth; "Both"
0x18002678d  jmp     short loc_18002679F
0x18002678f  lea     r9, aMachine; "Machine"
0x180026796  jmp     short loc_18002679F
0x180026798  lea     r9, aUser; "User"
0x18002679f  lea     rcx, aOnecopilotreme_3; "OneCopilotRemediationReason::policy_act"...
0x1800267a6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800267ab  mov     r8, rax
0x1800267ae  mov     edx, 7
0x1800267b3  lea     rcx, [r10+8]
0x1800267b7  call    ??$set_flag_value@PEBG@?$shared_data@$00$0A@$00@details@tip2@@QEAAXGPEBDPEBG@Z; tip2::details::shared_data<1,0,1>::set_flag_value<ushort const *>(ushort,char const *,ushort const *)
0x1800267bc  lea     rcx, [rsp+108h+Data]
0x1800267c1  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x1800267c6  mov     rcx, rsi; this
0x1800267c9  call    ?HasRemediationEverSucceeded@OneCopilotRemediator@@AEAA_NXZ; OneCopilotRemediator::HasRemediationEverSucceeded(void)
0x1800267ce  test    al, al
0x1800267d0  jnz     loc_180026AA4
0x1800267d6  mov     ecx, cs:_tls_index
0x1800267dc  mov     rax, gs:58h
0x1800267e5  mov     edx, 4
0x1800267ea  mov     rax, [rax+rcx*8]
0x1800267ee  mov     ecx, [rdx+rax]
0x1800267f1  cmp     cs:dword_1800ADDC0, ecx
0x1800267f7  jle     short loc_18002682D
0x1800267f9  lea     rcx, dword_1800ADDC0
0x180026800  call    _Init_thread_header
0x180026805  cmp     cs:dword_1800ADDC0, 0FFFFFFFFh
0x18002680c  jnz     short loc_18002682D
0x18002680e  call    ?GetMAISignalFuncs@OneCopilot@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@P6A_NXZU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@P6A_NXZ@std@@@2@@std@@XZ; OneCopilot::GetMAISignalFuncs(void)
0x180026813  lea     rcx, _OneCopilotRemediator__CheckAndRemediate____12____dynamic_atexit_destructor_for__signalFuncs__; void (__cdecl *)()
0x18002681a  call    atexit
0x18002681f  nop
0x180026820  lea     rcx, dword_1800ADDC0
0x180026827  call    _Init_thread_footer
0x18002682c  nop
0x18002682d  lea     rcx, applicationUserModelId; "Microsoft.Copilot_8wekyb3d8bbwe!App"
0x180026834  call    ?GetInstallationSourceForAumid@OneCopilot@@YA?AW4InstallationSource@1@PEBG@Z; OneCopilot::GetInstallationSourceForAumid(ushort const *)
0x180026839  mov     r14d, eax
0x18002683c  lea     rcx, aMicrosoftMicro; "Microsoft.MicrosoftOfficeHub_8wekyb3d8b"...
0x180026843  call    ?GetInstallationSourceForAumid@OneCopilot@@YA?AW4InstallationSource@1@PEBG@Z; OneCopilot::GetInstallationSourceForAumid(ushort const *)
0x180026848  cmp     r14d, 3
0x18002684c  jz      loc_180026A4C
0x180026852  cmp     eax, 3
0x180026855  jz      loc_180026A4C
0x18002685b  lea     rcx, [rsp+108h+var_A8]
0x180026860  call    ?EvaluateForMAI@OneCopilot@@YA?AU?$pair@_NV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@P6A_NXZU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@P6A_NXZ@std@@@2@@3@@Z; OneCopilot::EvaluateForMAI(std::map<std::wstring,bool (*)(void)> const &)
0x180026865  nop
0x180026866  lea     r8, [rsp+108h+var_A0]
0x18002686b  lea     rdx, [rsp+108h+var_58]
0x180026873  call    ?StringifySignalResults@OneCopilotRemediator@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@3@@Z; OneCopilotRemediator::StringifySignalResults(std::unordered_map<std::wstring,bool> const &)
0x180026878  nop
0x180026879  lea     rdx, [rsp+108h+Data]
0x18002687e  mov     rcx, rdi
0x180026881  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180026886  mov     r10, [rax]
0x180026889  lea     r9, [rsp+108h+var_58]
0x180026891  cmp     [rsp+108h+var_40], 7
0x18002689a  cmova   r9, [rsp+108h+var_58]
0x1800268a3  lea     rcx, aOnecopilotreme_0; "OneCopilotRemediationReason::evaluate_s"...
0x1800268aa  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800268af  mov     r8, rax
0x1800268b2  mov     edx, 9
0x1800268b7  lea     rcx, [r10+8]
0x1800268bb  call    ??$set_flag_value@PEBG@?$shared_data@$00$0A@$00@details@tip2@@QEAAXGPEBDPEBG@Z; tip2::details::shared_data<1,0,1>::set_flag_value<ushort const *>(ushort,char const *,ushort const *)
0x1800268c0  lea     rcx, [rsp+108h+Data]
0x1800268c5  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x1800268ca  lea     r8, [rsp+108h+var_58]
0x1800268d2  cmp     [rsp+108h+var_40], 7
0x1800268db  cmova   r8, [rsp+108h+var_58]; unsigned __int16 *
0x1800268e4  mov     dl, [rsp+108h+var_A8]; bool
0x1800268e8  mov     rcx, rsi; this
0x1800268eb  call    ?SaveEvaluationResultToRegistry@OneCopilotRemediator@@AEAAJ_NPEBG@Z; OneCopilotRemediator::SaveEvaluationResultToRegistry(bool,ushort const *)
0x1800268f0  mov     rcx, [rsp+108h]; this
0x1800268f8  test    eax, eax
0x1800268fa  jns     short loc_180026910
0x1800268fc  mov     r9d, eax; char *
0x1800268ff  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180026906  mov     edx, 124h; void *
0x18002690b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026910  cmp     [rsp+108h+var_A8], 0
0x180026915  jz      loc_1800269F3
0x18002691b  mov     rcx, rsi; this
0x18002691e  call    ?EnsureCopilotRegistryKeyCreated@OneCopilotRemediator@@AEAAXXZ; OneCopilotRemediator::EnsureCopilotRegistryKeyCreated(void)
0x180026923  mov     [rsp+108h+Data], 0
0x18002692c  mov     [rsp+108h+cbData], 8; cbData
0x180026934  lea     rax, [rsp+108h+Data]
0x180026939  mov     [rsp+108h+lpData], rax; lpData
0x18002693e  mov     r14d, 0Bh
0x180026944  mov     r9d, r14d; dwType
0x180026947  lea     r8, aLastremediatio; "LastRemediationAttemptTimestamp"
0x18002694e  xor     edx, edx; lpSubKey
0x180026950  mov     rcx, [rsi+28h]; hKey
0x180026954  call    cs:__imp_RegSetKeyValueW
0x18002695a  lea     edx, [r14-0Ah]; unsigned int
0x18002695e  mov     rcx, rsi; this
0x180026961  call    ?ScheduleUninstallation@OneCopilotRemediator@@AEAAJI@Z; OneCopilotRemediator::ScheduleUninstallation(uint)
0x180026966  mov     esi, eax
0x180026968  lea     rdx, [rsp+108h+Data]
0x18002696d  mov     rcx, rdi
0x180026970  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180026975  mov     r9, rax
0x180026978  test    esi, esi
0x18002697a  js      short loc_1800269D1
0x18002697c  lea     rcx, aOnecopilotreme_2; "OneCopilotRemediationReason::uninstalla"...
0x180026983  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026988  mov     r8, rax
0x18002698b  mov     edx, r14d
0x18002698e  mov     rcx, [r9]
0x180026991  add     rcx, 8
0x180026995  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,1>::get_or_add_flag_under_lock(ushort,char const *)
0x18002699a  lea     rcx, [rsp+108h+Data]
0x18002699f  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x1800269a4  nop
0x1800269a5  lea     rcx, [rsp+108h+var_58]
0x1800269ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800269b2  nop
0x1800269b3  lea     rcx, [rsp+108h+var_A0]
0x1800269b8  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800269bd  nop
0x1800269be  test    rbx, rbx
0x1800269c1  jz      short loc_1800269CC
0x1800269c3  mov     rcx, rbx; SRWLock
0x1800269c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800269cc  jmp     loc_180026ABE
0x1800269d1  lea     rcx, aOnecopilotreme_6; "OneCopilotRemediationReason::exception_"...
0x1800269d8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800269dd  mov     r8, rax
0x1800269e0  xor     edx, edx
0x1800269e2  mov     rcx, [r9]
0x1800269e5  add     rcx, 8
0x1800269e9  mov     r9d, esi
0x1800269ec  call    ??$set_flag_value@J@?$shared_data@$00$0A@$00@details@tip2@@QEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,1>::set_flag_value<long>(ushort,char const *,long)
0x1800269f1  jmp     short loc_180026A26
0x1800269f3  lea     rdx, [rsp+108h+Data]
0x1800269f8  mov     rcx, rdi
0x1800269fb  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180026a00  mov     r10, rax
0x180026a03  lea     rcx, aOnecopilotreme_5; "OneCopilotRemediationReason::no_remedia"...
0x180026a0a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026a0f  mov     r9, rax
0x180026a12  mov     r8d, 5
0x180026a18  mov     rcx, [r10]
0x180026a1b  add     rcx, 8
0x180026a1f  mov     dl, 1
0x180026a21  call    ?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,1>::complete_helper(TestCompletionKind,ushort,char const *)
0x180026a26  lea     rcx, [rsp+108h+Data]
0x180026a2b  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x180026a30  nop
0x180026a31  lea     rcx, [rsp+108h+var_58]
0x180026a39  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026a3e  nop
0x180026a3f  lea     rcx, [rsp+108h+var_A0]
0x180026a44  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180026a49  nop
0x180026a4a  jmp     short loc_180026AA4
0x180026a4c  lea     rdx, [rsp+108h+Data]
0x180026a51  mov     rcx, rdi
0x180026a54  call    ??C?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::operator->(void)
0x180026a59  mov     r10, rax
0x180026a5c  lea     rcx, aOnecopilotreme_13; "OneCopilotRemediationReason::no_remedia"...
0x180026a63  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026a68  mov     r9, rax
0x180026a6b  mov     r8d, 6
0x180026a71  mov     rcx, [r10]
0x180026a74  add     rcx, 8
0x180026a78  mov     dl, 1
0x180026a7a  call    ?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,1>::complete_helper(TestCompletionKind,ushort,char const *)
0x180026a7f  lea     rcx, [rsp+108h+Data]
0x180026a84  call    ??1?$test_data_control@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::~test_data_control<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>(void)
0x180026a89  nop
0x180026a8a  test    rbx, rbx
0x180026a8d  jz      short loc_180026A98
0x180026a8f  mov     rcx, rbx; SRWLock
0x180026a92  call    cs:__imp_ReleaseSRWLockExclusive
0x180026a98  jmp     short loc_180026ABE
0x180026a9a  mov     rdi, [rsp+108h+var_C0]
0x180026a9f  mov     rbx, [rsp+108h+var_C8]
0x180026aa4  mov     rcx, rdi
0x180026aa7  call    ?complete@?$tip_test@V?$merged_data@U_tip_OneCopilotRemediationTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_OneCopilotRemediationTest_attributes,tip2::test_data_basic>>::complete(void)
0x180026aac  nop
0x180026aad  test    rbx, rbx
0x180026ab0  jz      short loc_180026ABC
0x180026ab2  mov     rcx, rbx; SRWLock
0x180026ab5  call    cs:__imp_ReleaseSRWLockExclusive
0x180026abb  nop
0x180026abc  jmp     short $+2
0x180026abe  mov     rcx, [rsp+108h+var_38]
0x180026ac6  xor     rcx, rsp; StackCookie
0x180026ac9  call    __security_check_cookie
0x180026ace  add     rsp, 0E8h
0x180026ad5  pop     r14
0x180026ad7  pop     rdi
0x180026ad8  pop     rsi
0x180026ad9  pop     rbx
0x180026ada  retn
```
