# CLogonTaskFramework::s_LaunchExperienceHostStartWork(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x14007f3f8`
- end: `0x14007f864`
- name: `?s_LaunchExperienceHostStartWork@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007f3e0`
- `0x1400a9950`

## callees

- `0x140012594`
- `0x140023418`
- `0x1400283bc`
- `0x1400690a0`
- `0x14007f3f8`
- `0x14007f86c`
- `0x140085b7c`
- `0x14009ac68`
- `0x14009de4c`
- `0x14009defc`
- `0x1400a99dc`
- `0x1400bb4a4`
- `0x1401551a4`
- `0x1401587f4`
- `0x1401a4734`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007f729`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007f76a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007f729`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007f76a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14007f555`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14007f5ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14007f555`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14007f5ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14007f520`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14007f576`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14007f520`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14007f576`

## string_xrefs

- `0x14007f482`: `shell\lib\logontasks\logontasks.cpp`
- `0x14007f611`: `shell\lib\logontasks\logontasks.cpp`
- `0x14007f6da`: `shell\lib\logontasks\logontasks.cpp`
- `0x14007f742`: `shell\lib\logontasks\logontasks.cpp`
- `0x14007f783`: `shell\lib\logontasks\logontasks.cpp`
- `0x14007f7d7`: `shell\lib\logontasks\logontasks.cpp`
- `0x14007f436`: `ShellStartReadyEvent`
- `0x14007f719`: `ShellStartReadyEvent`
- `0x14007f456`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_ready_event`
- `0x14007f5e5`: `_tip_StartMenuLogonTaskTest_attributes::reason::query_launcher_service`
- `0x14007f649`: `_tip_StartMenuLogonTaskTest_attributes::reason::prelaunch_xaml_launcher`
- `0x14007f6af`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_threadpool_wait`
- `0x14007f688`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_threadpool_wait`
- `0x14007f4c8`: `ShellSearchReadyEvent`
- `0x14007f75a`: `ShellSearchReadyEvent`
- `0x14007f4dd`: `_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_ready_event`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLogonTaskFramework::s_LaunchExperienceHostStartWork(
        HANDLE *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  const char *v2; // rax
  const char *v3; // r8
  char v4; // dl
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  const char *v8; // rdx
  const char *v9; // rax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v11; // rdx
  struct _TP_WAIT *v12; // rcx
  PTP_WAIT v13; // rax
  const char *v14; // rdx
  struct _TP_WAIT *v15; // rcx
  const char *v16; // rdx
  const char *v17; // rax
  __int64 v18; // rdx
  const char *v19; // rdx
  const char *v20; // rax
  const char *v22; // rax
  __int64 v23; // r9
  __int64 v24; // rdx
  const char *v25; // rax
  __int64 v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // eax
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+10h]
  void *v34; // [rsp+68h] [rbp+20h] BYREF
  HANDLE v35; // [rsp+70h] [rbp+28h] BYREF
  HANDLE EventW; // [rsp+78h] [rbp+30h] BYREF

  v34 = a2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest>::GetImpl'::`2'::impl) )
  {
    EventW = CreateEventW(0, 1, 0, L"ShellStartReadyEvent");
    if ( EventW )
    {
      v35 = CreateEventW(0, 1, 0, L"ShellSearchReadyEvent");
      if ( v35 )
      {
        v34 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        v29 = CLogonTaskFramework::s_QueryServiceImmersiveShell(
                (const struct _GUID *)&SID_ImmersiveLauncher,
                &GUID_d8d60399_a0f1_f987_5551_321fd1b49864,
                &v34);
        LastError = v29;
        if ( v29 >= 0 )
        {
          v29 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v34 + 104LL))(v34);
          LastError = v29;
          if ( v29 >= 0 )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::swap(
              a1 + 54,
              &EventW);
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::swap(
              a1 + 55,
              &v35);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
            LastError = 0;
            goto LABEL_37;
          }
          v30 = 7132;
        }
        else
        {
          v30 = 7131;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v29,
          v31);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1BD8,
                      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                      v28);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1BD5,
                    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                    v27);
    }
LABEL_37:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&EventW);
    return LastError;
  }
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           a1 + 56,
                           1,
                           L"ShellStartReadyEvent") )
  {
    v2 = "_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_ready_event";
    v3 = "_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_ready_event";
    v4 = 95;
    do
    {
      ++v2;
      if ( v4 == 58 )
        v3 = v2;
      v4 = *v2;
    }
    while ( *v2 );
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      a1 + 58,
      3,
      v3);
    v6 = 7050;
    goto LABEL_8;
  }
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           a1 + 57,
                           1,
                           L"ShellSearchReadyEvent") )
  {
    v9 = tip2::details::reason_string(
           (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_ready_event",
           v8);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      a1 + 58,
      4,
      v9);
    v6 = 7057;
LABEL_8:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                  v5);
LABEL_9:
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(a1 + 58) )
      tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::complete(a1 + 58);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(CLogonTaskFramework::s_StartOrSearchSignalledReadyCallback, a1, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    a1 + 59,
    ThreadpoolWait);
  v12 = (struct _TP_WAIT *)a1[59];
  if ( v12 )
  {
    SetThreadpoolWait(v12, a1[56], 0);
    v13 = CreateThreadpoolWait(CLogonTaskFramework::s_StartOrSearchSignalledReadyCallback, a1, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      a1 + 60,
      v13);
    v15 = (struct _TP_WAIT *)a1[60];
    if ( v15 )
    {
      SetThreadpoolWait(v15, a1[57], 0);
      v34 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      LastError = CLogonTaskFramework::s_QueryServiceImmersiveShell(
                    (const struct _GUID *)&SID_ImmersiveLauncher,
                    &GUID_d8d60399_a0f1_f987_5551_321fd1b49864,
                    &v34);
      if ( (LastError & 0x80000000) == 0 )
      {
        LastError = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v34 + 104LL))(v34);
        if ( (LastError & 0x80000000) == 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          return 0;
        }
        v20 = tip2::details::reason_string(
                (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::prelaunch_xaml_launcher",
                v19);
        tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<unsigned long>(
          a1 + 58,
          6,
          v20,
          LastError);
        v18 = 7113;
      }
      else
      {
        v17 = tip2::details::reason_string(
                (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::query_launcher_service",
                v16);
        tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<unsigned long>(
          a1 + 58,
          5,
          v17,
          LastError);
        v18 = 7104;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)LastError,
        v31);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      goto LABEL_9;
    }
    v22 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_search_threadpool_wait",
            v14);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      v23 + 464,
      8,
      v22);
    v24 = 7094;
  }
  else
  {
    v25 = tip2::details::reason_string(
            (tip2::details *)"_tip_StartMenuLogonTaskTest_attributes::reason::allocate_start_threadpool_wait",
            v11);
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(
      v26 + 464,
      7,
      v25);
    v24 = 7077;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v24,
    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
    (const char *)0x80070006LL,
    v31);
  if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(a1 + 58) )
    tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::complete(a1 + 58);
  return 2147942406LL;
}

```

## disassembly

```asm
0x14007f3f8  mov     [rsp-10h+arg_8], rdx
0x14007f3fd  mov     [rsp-10h+pv], rcx
0x14007f402  push    rbp
0x14007f403  push    rbx
0x14007f404  mov     rbp, rsp
0x14007f407  sub     rsp, 48h
0x14007f40b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest> `wil::Feature<__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest>::GetImpl(void)'::`2'::impl
0x14007f412  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StartMenuLogonTaskTipTest>::__private_IsEnabled(void)
0x14007f417  test    al, al
0x14007f419  jz      loc_14007F719
0x14007f41f  lea     rax, [rbp+pv]
0x14007f423  mov     [rbp+var_18], rax
0x14007f427  mov     [rbp+var_10], 1
0x14007f42b  mov     rcx, [rbp+pv]
0x14007f42f  add     rcx, 1C0h
0x14007f436  lea     r8, aShellstartread; "ShellStartReadyEvent"
0x14007f43d  mov     edx, 1
0x14007f442  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14007f447  mov     rcx, [rbp+pv]
0x14007f44b  test    al, al
0x14007f44d  jnz     short loc_14007F4C1
0x14007f44f  add     rcx, 1D0h
0x14007f456  lea     rax, aTipStartmenulo_2; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14007f45d  mov     r8, rax
0x14007f460  mov     dl, 5Fh ; '_'
0x14007f462  inc     rax
0x14007f465  cmp     dl, 3Ah ; ':'
0x14007f468  jnz     short loc_14007F46D
0x14007f46a  mov     r8, rax
0x14007f46d  mov     dl, [rax]
0x14007f46f  test    dl, dl
0x14007f471  jnz     short loc_14007F462
0x14007f473  mov     edx, 3
0x14007f478  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x14007f47d  mov     edx, 1B8Ah; void *
0x14007f482  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14007f489  mov     rcx, [rbp+10h]; this
0x14007f48d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007f492  mov     ebx, eax
0x14007f494  mov     rcx, [rbp+pv]
0x14007f498  add     rcx, 1D0h
0x14007f49f  call    ??B?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(void)
0x14007f4a4  test    al, al
0x14007f4a6  jz      loc_14007F85A
0x14007f4ac  mov     rcx, [rbp+pv]
0x14007f4b0  add     rcx, 1D0h
0x14007f4b7  call    ?complete@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::complete(void)
0x14007f4bc  jmp     loc_14007F85A
0x14007f4c1  add     rcx, 1C8h
0x14007f4c8  lea     r8, aShellsearchrea; "ShellSearchReadyEvent"
0x14007f4cf  mov     edx, 1
0x14007f4d4  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14007f4d9  test    al, al
0x14007f4db  jnz     short loc_14007F50B
0x14007f4dd  lea     rcx, aTipStartmenulo_0; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14007f4e4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14007f4e9  mov     r8, rax
0x14007f4ec  mov     edx, 4
0x14007f4f1  mov     rcx, [rbp+pv]
0x14007f4f5  add     rcx, 1D0h
0x14007f4fc  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x14007f501  mov     edx, 1B91h
0x14007f506  jmp     loc_14007F482
0x14007f50b  mov     rdx, [rbp+pv]; pv
0x14007f50f  lea     rbx, [rdx+1D8h]
0x14007f516  xor     r8d, r8d; pcbe
0x14007f519  lea     rcx, ?s_StartOrSearchSignalledReadyCallback@CLogonTaskFramework@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14007f520  call    cs:__imp_CreateThreadpoolWait
0x14007f527  nop     dword ptr [rax+rax+00h]
0x14007f52c  mov     rdx, rax
0x14007f52f  mov     rcx, rbx
0x14007f532  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14007f537  mov     r9, [rbp+pv]
0x14007f53b  mov     rcx, [r9+1D8h]; pwa
0x14007f542  test    rcx, rcx
0x14007f545  jz      loc_14007F6AF
0x14007f54b  xor     r8d, r8d; pftTimeout
0x14007f54e  mov     rdx, [r9+1C0h]; h
0x14007f555  call    cs:__imp_SetThreadpoolWait
0x14007f55c  nop     dword ptr [rax+rax+00h]
0x14007f561  mov     rdx, [rbp+pv]; pv
0x14007f565  lea     rbx, [rdx+1E0h]
0x14007f56c  xor     r8d, r8d; pcbe
0x14007f56f  lea     rcx, ?s_StartOrSearchSignalledReadyCallback@CLogonTaskFramework@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14007f576  call    cs:__imp_CreateThreadpoolWait
0x14007f57d  nop     dword ptr [rax+rax+00h]
0x14007f582  mov     rdx, rax
0x14007f585  mov     rcx, rbx
0x14007f588  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14007f58d  mov     r9, [rbp+pv]
0x14007f591  mov     rcx, [r9+1E0h]; pwa
0x14007f598  test    rcx, rcx
0x14007f59b  jz      loc_14007F688
0x14007f5a1  xor     r8d, r8d; pftTimeout
0x14007f5a4  mov     rdx, [r9+1C8h]; h
0x14007f5ab  call    cs:__imp_SetThreadpoolWait
0x14007f5b2  nop     dword ptr [rax+rax+00h]
0x14007f5b7  mov     [rbp+arg_8], 0
0x14007f5bf  lea     rcx, [rbp+arg_8]
0x14007f5c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14007f5c8  lea     r8, [rbp+arg_8]; void **
0x14007f5cc  lea     rdx, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864; struct _GUID *
0x14007f5d3  lea     rcx, SID_ImmersiveLauncher; struct _GUID *
0x14007f5da  call    ?s_QueryServiceImmersiveShell@CLogonTaskFramework@@CAJAEBU_GUID@@0PEAPEAX@Z; CLogonTaskFramework::s_QueryServiceImmersiveShell(_GUID const &,_GUID const &,void * *)
0x14007f5df  mov     ebx, eax
0x14007f5e1  test    eax, eax
0x14007f5e3  jns     short loc_14007F633
0x14007f5e5  lea     rcx, aTipStartmenulo_6; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14007f5ec  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14007f5f1  mov     r8, rax
0x14007f5f4  mov     edx, 5
0x14007f5f9  mov     rcx, [rbp+pv]
0x14007f5fd  add     rcx, 1D0h
0x14007f604  mov     r9d, ebx
0x14007f607  call    ??$set_flag_value@K@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBDK@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<ulong>(ushort,char const *,ulong)
0x14007f60c  mov     edx, 1BC0h; void *
0x14007f611  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14007f618  mov     r9d, ebx; char *
0x14007f61b  mov     rcx, [rbp+10h]; this
0x14007f61f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f624  nop
0x14007f625  lea     rcx, [rbp+arg_8]
0x14007f629  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14007f62e  jmp     loc_14007F494
0x14007f633  mov     rcx, [rbp+arg_8]
0x14007f637  mov     rax, [rcx]
0x14007f63a  mov     rax, [rax+68h]
0x14007f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f643  mov     ebx, eax
0x14007f645  test    eax, eax
0x14007f647  jns     short loc_14007F677
0x14007f649  lea     rcx, aTipStartmenulo_3; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14007f650  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14007f655  mov     r8, rax
0x14007f658  mov     edx, 6
0x14007f65d  mov     rcx, [rbp+pv]
0x14007f661  add     rcx, 1D0h
0x14007f668  mov     r9d, ebx
0x14007f66b  call    ??$set_flag_value@K@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBDK@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag_value<ulong>(ushort,char const *,ulong)
0x14007f670  mov     edx, 1BC9h
0x14007f675  jmp     short loc_14007F611
0x14007f677  lea     rcx, [rbp+arg_8]
0x14007f67b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14007f680  nop
0x14007f681  xor     eax, eax
0x14007f683  jmp     loc_14007F85C
0x14007f688  lea     rcx, aTipStartmenulo; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14007f68f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14007f694  mov     r8, rax
0x14007f697  mov     edx, 8
0x14007f69c  lea     rcx, [r9+1D0h]
0x14007f6a3  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x14007f6a8  mov     edx, 1BB6h
0x14007f6ad  jmp     short loc_14007F6D4
0x14007f6af  lea     rcx, aTipStartmenulo_4; "_tip_StartMenuLogonTaskTest_attributes:"...
0x14007f6b6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14007f6bb  mov     r8, rax
0x14007f6be  mov     edx, 7
0x14007f6c3  lea     rcx, [r9+1D0h]
0x14007f6ca  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::set_flag(ushort,char const *)
0x14007f6cf  mov     edx, 1BA5h; void *
0x14007f6d4  mov     r9d, 80070006h; char *
0x14007f6da  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14007f6e1  mov     rcx, [rbp+10h]; this
0x14007f6e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f6ea  nop
0x14007f6eb  mov     rcx, [rbp+pv]
0x14007f6ef  add     rcx, 1D0h
0x14007f6f6  call    ??B?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::operator bool(void)
0x14007f6fb  test    al, al
0x14007f6fd  jz      short loc_14007F70F
0x14007f6ff  mov     rcx, [rbp+pv]
0x14007f703  add     rcx, 1D0h
0x14007f70a  call    ?complete@?$tip_test@V?$merged_data@U_tip_StartMenuLogonTaskTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_StartMenuLogonTaskTest_attributes,tip2::test_data_basic>>::complete(void)
0x14007f70f  mov     eax, 80070006h
0x14007f714  jmp     loc_14007F85C
0x14007f719  lea     r9, aShellstartread; "ShellStartReadyEvent"
0x14007f720  xor     r8d, r8d; bInitialState
0x14007f723  lea     edx, [r8+1]; bManualReset
0x14007f727  xor     ecx, ecx; lpEventAttributes
0x14007f729  call    cs:__imp_CreateEventW
0x14007f730  nop     dword ptr [rax+rax+00h]
0x14007f735  mov     [rbp+arg_18], rax
0x14007f739  test    rax, rax
0x14007f73c  jnz     short loc_14007F75A
0x14007f73e  mov     rcx, [rbp+10h]; this
0x14007f742  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14007f749  mov     edx, 1BD5h; void *
0x14007f74e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007f753  mov     ebx, eax
0x14007f755  jmp     loc_14007F851
0x14007f75a  lea     r9, aShellsearchrea; "ShellSearchReadyEvent"
0x14007f761  xor     r8d, r8d; bInitialState
0x14007f764  lea     edx, [r8+1]; bManualReset
0x14007f768  xor     ecx, ecx; lpEventAttributes
0x14007f76a  call    cs:__imp_CreateEventW
0x14007f771  nop     dword ptr [rax+rax+00h]
0x14007f776  mov     [rbp+arg_10], rax
0x14007f77a  test    rax, rax
0x14007f77d  jnz     short loc_14007F7A4
0x14007f77f  mov     rcx, [rbp+10h]; this
0x14007f783  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14007f78a  mov     edx, 1BD8h; void *
0x14007f78f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007f794  mov     ebx, eax
0x14007f796  lea     rcx, [rbp+arg_10]
0x14007f79a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14007f79f  jmp     loc_14007F851
0x14007f7a4  mov     [rbp+arg_8], 0
0x14007f7ac  lea     rcx, [rbp+arg_8]
0x14007f7b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14007f7b5  lea     r8, [rbp+arg_8]; void **
0x14007f7b9  lea     rdx, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864; struct _GUID *
0x14007f7c0  lea     rcx, SID_ImmersiveLauncher; struct _GUID *
0x14007f7c7  call    ?s_QueryServiceImmersiveShell@CLogonTaskFramework@@CAJAEBU_GUID@@0PEAPEAX@Z; CLogonTaskFramework::s_QueryServiceImmersiveShell(_GUID const &,_GUID const &,void * *)
0x14007f7cc  mov     ebx, eax
0x14007f7ce  test    eax, eax
0x14007f7d0  jns     short loc_14007F7F6
0x14007f7d2  mov     edx, 1BDBh; void *
0x14007f7d7  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14007f7de  mov     r9d, eax; char *
0x14007f7e1  mov     rcx, [rbp+10h]; this
0x14007f7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f7ea  nop
0x14007f7eb  lea     rcx, [rbp+arg_8]
0x14007f7ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14007f7f4  jmp     short loc_14007F796
0x14007f7f6  mov     rcx, [rbp+arg_8]
0x14007f7fa  mov     rax, [rcx]
0x14007f7fd  mov     rax, [rax+68h]
0x14007f801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f806  mov     ebx, eax
0x14007f808  test    eax, eax
0x14007f80a  jns     short loc_14007F813
0x14007f80c  mov     edx, 1BDCh
0x14007f811  jmp     short loc_14007F7D7
0x14007f813  mov     rcx, [rbp+pv]
0x14007f817  add     rcx, 1B0h
0x14007f81e  lea     rdx, [rbp+arg_18]
0x14007f822  call    ?swap@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x14007f827  mov     rcx, [rbp+pv]
0x14007f82b  add     rcx, 1B8h
0x14007f832  lea     rdx, [rbp+arg_10]
0x14007f836  call    ?swap@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x14007f83b  nop
0x14007f83c  lea     rcx, [rbp+arg_8]
0x14007f840  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14007f845  nop
0x14007f846  lea     rcx, [rbp+arg_10]
0x14007f84a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14007f84f  xor     ebx, ebx
0x14007f851  lea     rcx, [rbp+arg_18]
0x14007f855  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14007f85a  mov     eax, ebx
0x14007f85c  add     rsp, 48h
0x14007f860  pop     rbx
0x14007f861  pop     rbp
0x14007f862  retn
```
