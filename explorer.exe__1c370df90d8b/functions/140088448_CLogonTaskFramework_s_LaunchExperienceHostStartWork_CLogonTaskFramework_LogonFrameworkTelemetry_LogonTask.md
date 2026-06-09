# CLogonTaskFramework::s_LaunchExperienceHostStartWork(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140088448`
- end: `0x1400887a2`
- name: `?s_LaunchExperienceHostStartWork@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140088430`
- `0x1401ac360`

## callees

- `0x14000edcc`
- `0x140030c1c`
- `0x1400655ec`
- `0x14007a7cc`
- `0x140088448`
- `0x1400954e0`
- `0x1400987b8`
- `0x140098864`
- `0x1400a35a8`
- `0x1400a9ef0`
- `0x14014aa48`
- `0x14014e70c`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140088555`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14008859f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140088555`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14008859f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140088584`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400885ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140088584`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400885ce`

## string_xrefs

- `0x1400884af`: `shell\lib\logontasks\logontasks.cpp`
- `0x14008862e`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400886f6`: `shell\lib\logontasks\logontasks.cpp`
- `0x140088753`: `shell\lib\logontasks\logontasks.cpp`
- `0x140088500`: `ShellSearchReadyEvent`
- `0x140088512`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_ready_event`
- `0x140088476`: `ShellStartReadyEvent`
- `0x140088488`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_ready_event`
- `0x140088602`: `_tip_StartMenuLogonTaskTest_attributes::reason::query_launcher_service`
- `0x14008868a`: `_tip_StartMenuLogonTaskTest_attributes::reason::prelaunch_xaml_launcher`
- `0x140088729`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_threadpool_wait`
- `0x1400886cc`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_threadpool_wait`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLogonTaskFramework::s_LaunchExperienceHostStartWork(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  const char *v2; // rdx
  const char *v3; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // rcx
  const char *v9; // rdx
  const char *v10; // rax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v12; // rdx
  struct _TP_WAIT *v13; // rcx
  PTP_WAIT v14; // rax
  const char *v15; // rdx
  struct _TP_WAIT *v16; // rcx
  const char *v17; // rdx
  const char *v18; // rax
  __int64 v19; // rdx
  const char *v20; // rdx
  const char *v21; // rax
  const char *v22; // rax
  __int64 v23; // r9
  __int64 v24; // rcx
  const char *v25; // rax
  __int64 v26; // r9
  int v27; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  void *v30; // [rsp+58h] [rbp+18h] BYREF

  v30 = a2;
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           (char *)a1 + 432,
                           1,
                           L"ShellStartReadyEvent") )
  {
    v3 = tip2::details::reason_string(
           (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_ready_event",
           v2);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      (char *)a1 + 448,
      3,
      v3);
    v5 = 7055;
    goto LABEL_3;
  }
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           (char *)a1 + 440,
                           1,
                           L"ShellSearchReadyEvent") )
  {
    v10 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_ready_event",
            v9);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      (char *)a1 + 448,
      4,
      v10);
    v5 = 7062;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                  v4);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool((char *)a1 + 448) )
    {
      v7 = *((_QWORD *)a1 + 56);
      goto LABEL_5;
    }
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(CLogonTaskFramework::s_StartOrSearchSignalledReadyCallback, a1, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)a1 + 456,
    ThreadpoolWait);
  v13 = (struct _TP_WAIT *)*((_QWORD *)a1 + 57);
  if ( !v13 )
  {
    v25 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_threadpool_wait",
            v12);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      v26 + 448,
      7,
      v25);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BAA,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)0x80070006LL,
      v27);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool((char *)a1 + 448) )
    {
      v24 = *((_QWORD *)a1 + 56);
LABEL_23:
      if ( v24 )
        tip2::details::shared_data<0,0,1>::complete_without_lock(v24 + 8);
    }
    return 2147942406LL;
  }
  SetThreadpoolWait(v13, *((HANDLE *)a1 + 54), 0);
  v14 = CreateThreadpoolWait(CLogonTaskFramework::s_StartOrSearchSignalledReadyCallback, a1, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)a1 + 464,
    v14);
  v16 = (struct _TP_WAIT *)*((_QWORD *)a1 + 58);
  if ( !v16 )
  {
    v22 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_threadpool_wait",
            v15);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      v23 + 448,
      8,
      v22);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BBB,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)0x80070006LL,
      v27);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool((char *)a1 + 448) )
    {
      v24 = *((_QWORD *)a1 + 56);
      goto LABEL_23;
    }
    return 2147942406LL;
  }
  SetThreadpoolWait(v16, *((HANDLE *)a1 + 55), 0);
  v30 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  LastError = CLogonTaskFramework::s_QueryServiceImmersiveShell(
                (const struct _GUID *)&SID_ImmersiveLauncher,
                &GUID_d8d60399_a0f1_f987_5551_321fd1b49864,
                &v30);
  if ( (LastError & 0x80000000) != 0 )
  {
    v18 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::query_launcher_service",
            v17);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<unsigned long>(
      (char *)a1 + 448,
      5,
      v18,
      LastError);
    v19 = 7109;
    goto LABEL_14;
  }
  LastError = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v30 + 104LL))(v30);
  if ( (LastError & 0x80000000) != 0 )
  {
    v21 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::prelaunch_xaml_launcher",
            v20);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<unsigned long>(
      (char *)a1 + 448,
      6,
      v21,
      LastError);
    v19 = 7118;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)LastError,
      v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool((char *)a1 + 448) )
    {
      v7 = *((_QWORD *)a1 + 56);
LABEL_5:
      if ( v7 )
        tip2::details::shared_data<0,0,1>::complete_without_lock(v7 + 8);
    }
    return LastError;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  return 0;
}

```

## disassembly

```asm
0x140088448  mov     [rsp-8+arg_10], rbx
0x14008844d  mov     [rsp-8+arg_8], rdx
0x140088452  mov     [rsp-8+pv], rcx
0x140088457  push    rbp
0x140088458  mov     rbp, rsp
0x14008845b  sub     rsp, 40h
0x14008845f  lea     rax, [rbp+pv]
0x140088463  mov     [rbp+var_10], rax
0x140088467  mov     ebx, 1
0x14008846c  mov     [rbp+var_8], bl
0x14008846f  add     rcx, 1B0h
0x140088476  lea     r8, aShellstartread; "ShellStartReadyEvent"
0x14008847d  mov     edx, ebx
0x14008847f  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140088484  test    al, al
0x140088486  jnz     short loc_1400884F5
0x140088488  lea     rcx, aTipStartmenulo_2; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14008848f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140088494  mov     r8, rax
0x140088497  lea     edx, [rbx+2]
0x14008849a  mov     rcx, [rbp+pv]
0x14008849e  add     rcx, 1C0h
0x1400884a5  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x1400884aa  mov     edx, 1B8Fh; void *
0x1400884af  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400884b6  mov     rcx, [rbp+8]; this
0x1400884ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400884bf  mov     ebx, eax
0x1400884c1  mov     rcx, [rbp+pv]
0x1400884c5  add     rcx, 1C0h
0x1400884cc  call    ??B?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(void)
0x1400884d1  test    al, al
0x1400884d3  jz      short loc_1400884EE
0x1400884d5  mov     rcx, [rbp+pv]
0x1400884d9  mov     rcx, [rcx+1C0h]
0x1400884e0  test    rcx, rcx
0x1400884e3  jz      short loc_1400884EE
0x1400884e5  add     rcx, 8
0x1400884e9  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,1>::complete_without_lock(void)
0x1400884ee  mov     eax, ebx
0x1400884f0  jmp     loc_140088797
0x1400884f5  mov     rcx, [rbp+pv]
0x1400884f9  add     rcx, 1B8h
0x140088500  lea     r8, aShellsearchrea; "ShellSearchReadyEvent"
0x140088507  mov     edx, ebx
0x140088509  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14008850e  test    al, al
0x140088510  jnz     short loc_140088540
0x140088512  lea     rcx, aTipStartmenulo_0; "_tip_StartMenuLogonTaskTest_attributes:"...
0x140088519  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14008851e  mov     r8, rax
0x140088521  mov     edx, 4
0x140088526  mov     rcx, [rbp+pv]
0x14008852a  add     rcx, 1C0h
0x140088531  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x140088536  mov     edx, 1B96h
0x14008853b  jmp     loc_1400884AF
0x140088540  mov     rdx, [rbp+pv]; pv
0x140088544  lea     rbx, [rdx+1C8h]
0x14008854b  xor     r8d, r8d; pcbe
0x14008854e  lea     rcx, ?s_StartOrSearchSignalledReadyCallback@CLogonTaskFramework@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140088555  call    cs:__imp_CreateThreadpoolWait
0x14008855b  mov     rdx, rax
0x14008855e  mov     rcx, rbx
0x140088561  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x140088566  mov     r9, [rbp+pv]
0x14008856a  mov     rcx, [r9+1C8h]; pwa
0x140088571  test    rcx, rcx
0x140088574  jz      loc_140088729
0x14008857a  xor     r8d, r8d; pftTimeout
0x14008857d  mov     rdx, [r9+1B0h]; h
0x140088584  call    cs:__imp_SetThreadpoolWait
0x14008858a  mov     rdx, [rbp+pv]; pv
0x14008858e  lea     rbx, [rdx+1D0h]
0x140088595  xor     r8d, r8d; pcbe
0x140088598  lea     rcx, ?s_StartOrSearchSignalledReadyCallback@CLogonTaskFramework@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14008859f  call    cs:__imp_CreateThreadpoolWait
0x1400885a5  mov     rdx, rax
0x1400885a8  mov     rcx, rbx
0x1400885ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1400885b0  mov     r9, [rbp+pv]
0x1400885b4  mov     rcx, [r9+1D0h]; pwa
0x1400885bb  test    rcx, rcx
0x1400885be  jz      loc_1400886CC
0x1400885c4  xor     r8d, r8d; pftTimeout
0x1400885c7  mov     rdx, [r9+1B8h]; h
0x1400885ce  call    cs:__imp_SetThreadpoolWait
0x1400885d4  mov     [rbp+arg_8], 0
0x1400885dc  lea     rcx, [rbp+arg_8]
0x1400885e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400885e5  lea     r8, [rbp+arg_8]; void **
0x1400885e9  lea     rdx, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864; struct _GUID *
0x1400885f0  lea     rcx, SID_ImmersiveLauncher; struct _GUID *
0x1400885f7  call    ?s_QueryServiceImmersiveShell@CLogonTaskFramework@@CAJAEBU_GUID@@0PEAPEAX@Z; CLogonTaskFramework::s_QueryServiceImmersiveShell(_GUID const &,_GUID const &,void * *)
0x1400885fc  mov     ebx, eax
0x1400885fe  test    eax, eax
0x140088600  jns     short loc_140088674
0x140088602  lea     rcx, aTipStartmenulo_6; "_tip_StartMenuLogonTaskTest_attributes:"...
0x140088609  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14008860e  mov     r8, rax
0x140088611  mov     edx, 5
0x140088616  mov     rcx, [rbp+pv]
0x14008861a  add     rcx, 1C0h
0x140088621  mov     r9d, ebx
0x140088624  call    ??$set_flag_value@K@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBDK@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<ulong>(ushort,char const *,ulong)
0x140088629  mov     edx, 1BC5h; void *
0x14008862e  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140088635  mov     r9d, ebx; char *
0x140088638  mov     rcx, [rbp+8]; this
0x14008863c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140088641  nop
0x140088642  lea     rcx, [rbp+arg_8]
0x140088646  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14008864b  nop
0x14008864c  mov     rcx, [rbp+pv]
0x140088650  add     rcx, 1C0h
0x140088657  call    ??B?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(void)
0x14008865c  test    al, al
0x14008865e  jz      loc_1400884EE
0x140088664  mov     rax, [rbp+pv]
0x140088668  mov     rcx, [rax+1C0h]
0x14008866f  jmp     loc_1400884E0
0x140088674  mov     rcx, [rbp+arg_8]
0x140088678  mov     rax, [rcx]
0x14008867b  mov     rax, [rax+68h]
0x14008867f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088684  mov     ebx, eax
0x140088686  test    eax, eax
0x140088688  jns     short loc_1400886BB
0x14008868a  lea     rcx, aTipStartmenulo_3; "_tip_StartMenuLogonTaskTest_attributes:"...
0x140088691  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140088696  mov     r8, rax
0x140088699  mov     edx, 6
0x14008869e  mov     rcx, [rbp+pv]
0x1400886a2  add     rcx, 1C0h
0x1400886a9  mov     r9d, ebx
0x1400886ac  call    ??$set_flag_value@K@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBDK@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<ulong>(ushort,char const *,ulong)
0x1400886b1  mov     edx, 1BCEh
0x1400886b6  jmp     loc_14008862E
0x1400886bb  lea     rcx, [rbp+arg_8]
0x1400886bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400886c4  nop
0x1400886c5  xor     eax, eax
0x1400886c7  jmp     loc_140088797
0x1400886cc  lea     rcx, aTipStartmenulo; "_tip_StartMenuLogonTaskTest_attributes:"...
0x1400886d3  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400886d8  mov     r8, rax
0x1400886db  mov     edx, 8
0x1400886e0  lea     rcx, [r9+1C0h]
0x1400886e7  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x1400886ec  mov     rcx, [rbp+8]; this
0x1400886f0  mov     r9d, 80070006h; char *
0x1400886f6  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400886fd  mov     edx, 1BBBh; void *
0x140088702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140088707  nop
0x140088708  mov     rcx, [rbp+pv]
0x14008870c  add     rcx, 1C0h
0x140088713  call    ??B?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(void)
0x140088718  test    al, al
0x14008871a  jz      short loc_140088792
0x14008871c  mov     rax, [rbp+pv]
0x140088720  mov     rcx, [rax+1C0h]
0x140088727  jmp     short loc_140088784
0x140088729  lea     rcx, aTipStartmenulo_4; "_tip_StartMenuLogonTaskTest_attributes:"...
0x140088730  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140088735  mov     r8, rax
0x140088738  mov     edx, 7
0x14008873d  lea     rcx, [r9+1C0h]
0x140088744  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x140088749  mov     rcx, [rbp+8]; this
0x14008874d  mov     r9d, 80070006h; char *
0x140088753  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14008875a  mov     edx, 1BAAh; void *
0x14008875f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140088764  nop
0x140088765  mov     rcx, [rbp+pv]
0x140088769  add     rcx, 1C0h
0x140088770  call    ??B?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(void)
0x140088775  test    al, al
0x140088777  jz      short loc_140088792
0x140088779  mov     rcx, [rbp+pv]
0x14008877d  mov     rcx, [rcx+1C0h]
0x140088784  test    rcx, rcx
0x140088787  jz      short loc_140088792
0x140088789  add     rcx, 8
0x14008878d  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,1>::complete_without_lock(void)
0x140088792  mov     eax, 80070006h
0x140088797  mov     rbx, [rsp+40h+arg_10]
0x14008879c  add     rsp, 40h
0x1400887a0  pop     rbp
0x1400887a1  retn
```
