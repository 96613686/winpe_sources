# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsFlagEnabled(HSTRING__ *,Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration * *,Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration * *,Windows::Internal::ConfigurationManagement::Flags::PendingAction *,uchar *)

- ea: `0x1800990a0`
- end: `0x18009933c`
- name: `?IsFlagEnabled@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIFlagConfiguration@2345@1PEAW4PendingAction@2345@PEAE@Z`
- size: `668`
- prototype: `__int64 __fastcall(Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager *__hidden this, HSTRING, struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration **, struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration **, enum Windows::Internal::ConfigurationManagement::Flags::PendingAction *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000949c`
- `0x180023dd0`
- `0x180023fc8`
- `0x180024064`
- `0x1800247e4`
- `0x180025634`
- `0x1800990a0`
- `0x18009ab74`
- `0x18009acf0`
- `0x1800b7010`

## string_xrefs

- `0x1800992e0`: `FeatureExperimentsTIP::reason::CompletedSuccessfully`
- `0x18009913b`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180099172`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800991a9`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800991e8`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180099227`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180099261`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x1800992c1`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsFlagEnabled(
        Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager *this,
        HSTRING a2,
        struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration **a3,
        struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration **a4,
        enum Windows::Internal::ConfigurationManagement::Flags::PendingAction *a5,
        unsigned __int8 *a6)
{
  enum Windows::Internal::ConfigurationManagement::Flags::PendingAction *v11; // rdi
  unsigned __int8 *v12; // rsi
  int v13; // ebx
  int v14; // eax
  const char *v15; // rdx
  unsigned int v16; // ebx
  const char *v17; // rax
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-98h]
  __int64 v20; // [rsp+40h] [rbp-78h] BYREF
  void **v21; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v22[48]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v23; // [rsp+88h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int64 v25; // [rsp+C8h] [rbp+10h] BYREF

  v25 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_FCON_WinCSIsEnabled_attributes,tip2::test_data_basic>>::start(
    &v25,
    &v20);
  v21 = &tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v22,
    (struct wil::details::IFailureCallback *)&v21,
    0,
    1);
  v23 = v25;
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 336));
  wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v25);
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        v11 = a5;
        if ( a5 )
        {
          v12 = a6;
          if ( a6 )
          {
            v13 = Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ValidateCallerPrivileges();
            if ( v13 >= 0 )
            {
              *a3 = 0;
              *a4 = 0;
              *(_DWORD *)v11 = 0;
              *v12 = 0;
              v14 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration **, struct Windows::Internal::ConfigurationManagement::Flags::IFlagConfiguration **))(**((_QWORD **)this + 8) + 48LL))(
                      *((_QWORD *)this + 8),
                      a2,
                      a3,
                      a4);
              v16 = v14;
              if ( v14 >= 0 )
              {
                v17 = tip2::details::reason_string(
                        (tip2::details *)"FeatureExperimentsTIP::reason::CompletedSuccessfully",
                        v15);
                LOBYTE(v18) = 1;
                tip2::details::shared_data<0,0,1>::complete_without_lock(v23 + 8, v18, 1, v17);
                tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xCE,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigur"
                                "ationmanager.cpp",
                  (const char *)(unsigned int)v14,
                  (int)v11);
                tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
                return v16;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC7,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
                (const char *)(unsigned int)v13,
                v19);
              tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
              return (unsigned int)v13;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC5,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
              (const char *)0x80070057LL,
              v19);
            tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
            return 2147942487LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
            (const char *)0x80070057LL,
            v19);
          tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC3,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
          (const char *)0x80070057LL,
          v19);
        tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
        (const char *)0x80070057LL,
        v19);
      tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v19);
    tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v21);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800990a0  mov     rax, rsp
0x1800990a3  mov     [rax+8], rbx
0x1800990a7  mov     [rax+18h], rsi
0x1800990ab  push    rdi
0x1800990ac  push    r12
0x1800990ae  push    r13
0x1800990b0  push    r14
0x1800990b2  push    r15
0x1800990b4  sub     rsp, 90h
0x1800990bb  mov     r14, r9
0x1800990be  mov     r15, r8
0x1800990c1  mov     r12, rdx
0x1800990c4  mov     r13, rcx
0x1800990c7  mov     qword ptr [rax+10h], 0
0x1800990cf  lea     rdx, [rax-78h]
0x1800990d3  lea     rcx, [rax+10h]
0x1800990d7  call    ?start@?$tip_test@V?$merged_data@U_tip_FCON_WinCSIsEnabled_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FCON_WinCSIsEnabled_attributes,tip2::test_data_basic>>::start(void)
0x1800990dc  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_FCON_WinCSApplyFlagsByKeys_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable'
0x1800990e3  mov     [rsp+0B8h+var_68], rax
0x1800990e8  mov     r9b, 1; bool
0x1800990eb  xor     r8d, r8d; struct wil::CallContextInfo *
0x1800990ee  lea     rdx, [rsp+0B8h+var_68]; struct wil::details::IFailureCallback *
0x1800990f3  lea     rcx, [rsp+0B8h+var_60]; this
0x1800990f8  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800990fd  mov     rax, [rsp+0B8h+arg_8]
0x180099105  mov     [rsp+0B8h+var_30], rax
0x18009910d  test    rax, rax
0x180099110  jz      short loc_180099119
0x180099112  lock inc dword ptr [rax+150h]
0x180099119  lea     rcx, [rsp+0B8h+arg_8]
0x180099121  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FCON_ProcessGovernedFeatureUsage_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x180099126  test    r12, r12
0x180099129  jnz     short loc_18009915D
0x18009912b  mov     rcx, [rsp+0B8h]; this
0x180099133  mov     ebx, 80070057h
0x180099138  mov     r9d, ebx; char *
0x18009913b  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180099142  mov     edx, 0C1h; void *
0x180099147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009914c  lea     rcx, [rsp+0B8h+var_68]
0x180099151  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180099156  mov     eax, ebx
0x180099158  jmp     loc_18009931E
0x18009915d  test    r15, r15
0x180099160  jnz     short loc_180099194
0x180099162  mov     rcx, [rsp+0B8h]; this
0x18009916a  mov     ebx, 80070057h
0x18009916f  mov     r9d, ebx; char *
0x180099172  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180099179  mov     edx, 0C2h; void *
0x18009917e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099183  lea     rcx, [rsp+0B8h+var_68]
0x180099188  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x18009918d  mov     eax, ebx
0x18009918f  jmp     loc_18009931E
0x180099194  test    r14, r14
0x180099197  jnz     short loc_1800991CB
0x180099199  mov     rcx, [rsp+0B8h]; this
0x1800991a1  mov     ebx, 80070057h
0x1800991a6  mov     r9d, ebx; char *
0x1800991a9  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800991b0  mov     edx, 0C3h; void *
0x1800991b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800991ba  lea     rcx, [rsp+0B8h+var_68]
0x1800991bf  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x1800991c4  mov     eax, ebx
0x1800991c6  jmp     loc_18009931E
0x1800991cb  mov     rdi, [rsp+0B8h+arg_20]
0x1800991d3  test    rdi, rdi
0x1800991d6  jnz     short loc_18009920A
0x1800991d8  mov     rcx, [rsp+0B8h]; this
0x1800991e0  mov     ebx, 80070057h
0x1800991e5  mov     r9d, ebx; char *
0x1800991e8  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800991ef  mov     edx, 0C4h; void *
0x1800991f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800991f9  lea     rcx, [rsp+0B8h+var_68]
0x1800991fe  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180099203  mov     eax, ebx
0x180099205  jmp     loc_18009931E
0x18009920a  mov     rsi, [rsp+0B8h+arg_28]
0x180099212  test    rsi, rsi
0x180099215  jnz     short loc_180099249
0x180099217  mov     rcx, [rsp+0B8h]; this
0x18009921f  mov     ebx, 80070057h
0x180099224  mov     r9d, ebx; char *
0x180099227  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009922e  mov     edx, 0C5h; void *
0x180099233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099238  lea     rcx, [rsp+0B8h+var_68]
0x18009923d  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180099242  mov     eax, ebx
0x180099244  jmp     loc_18009931E
0x180099249  call    ?ValidateCallerPrivileges@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJXZ; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::ValidateCallerPrivileges(void)
0x18009924e  mov     ebx, eax
0x180099250  xor     eax, eax
0x180099252  test    ebx, ebx
0x180099254  jns     short loc_180099283
0x180099256  mov     rcx, [rsp+0B8h]; this
0x18009925e  mov     r9d, ebx; char *
0x180099261  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180099268  mov     edx, 0C7h; void *
0x18009926d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099272  lea     rcx, [rsp+0B8h+var_68]
0x180099277  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x18009927c  mov     eax, ebx
0x18009927e  jmp     loc_18009931E
0x180099283  mov     [r15], rax
0x180099286  mov     [r14], rax
0x180099289  mov     [rdi], eax
0x18009928b  mov     [rsi], al
0x18009928d  mov     rcx, [r13+40h]
0x180099291  mov     rax, [rcx]
0x180099294  mov     [rsp+0B8h+var_90], rsi
0x180099299  mov     qword ptr [rsp+0B8h+var_98], rdi; int
0x18009929e  mov     r9, r14
0x1800992a1  mov     r8, r15
0x1800992a4  mov     rdx, r12
0x1800992a7  mov     rax, [rax+30h]
0x1800992ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992b0  mov     ebx, eax
0x1800992b2  test    eax, eax
0x1800992b4  jns     short loc_1800992E0
0x1800992b6  mov     rcx, [rsp+0B8h]; this
0x1800992be  mov     r9d, eax; char *
0x1800992c1  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x1800992c8  mov     edx, 0CEh; void *
0x1800992cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800992d2  lea     rcx, [rsp+0B8h+var_68]
0x1800992d7  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x1800992dc  mov     eax, ebx
0x1800992de  jmp     short loc_18009931E
0x1800992e0  lea     rcx, aFeatureexperim_0; "FeatureExperimentsTIP::reason::Complete"...
0x1800992e7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800992ec  mov     r9, rax
0x1800992ef  mov     r8d, 1
0x1800992f5  mov     rcx, [rsp+0B8h+var_30]
0x1800992fd  add     rcx, 8
0x180099301  mov     dl, r8b
0x180099304  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180099309  lea     rcx, [rsp+0B8h+var_68]
0x18009930e  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180099313  xor     eax, eax
0x180099315  jmp     short loc_18009931E
0x180099317  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18009931e  lea     r11, [rsp+0B8h+var_28]
0x180099326  mov     rbx, [r11+30h]
0x18009932a  mov     rsi, [r11+40h]
0x18009932e  mov     rsp, r11
0x180099331  pop     r15
0x180099333  pop     r14
0x180099335  pop     r13
0x180099337  pop     r12
0x180099339  pop     rdi
0x18009933a  retn
```
