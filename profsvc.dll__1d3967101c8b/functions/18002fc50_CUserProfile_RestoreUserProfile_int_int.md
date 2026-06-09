# CUserProfile::RestoreUserProfile(int,int *)

- ea: `0x18002fc50`
- end: `0x1800303c3`
- name: `?RestoreUserProfile@CUserProfile@@IEAAJHPEAH@Z`
- size: `1907`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `34`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180003a54`
- `0x180015aa4`
- `0x18001a1e0`
- `0x18001dd04`
- `0x18001e308`
- `0x18001e3c0`
- `0x18001ea10`
- `0x18001f0c0`
- `0x180021b6c`
- `0x180021ca0`
- `0x180023fd4`
- `0x180023ffc`
- `0x180024bf0`
- `0x1800253dc`
- `0x180027ad4`
- `0x180027fdc`
- `0x180028c8c`
- `0x18002b6b8`
- `0x18002bf08`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002f89c`
- `0x18002fb04`
- `0x18002fc50`
- `0x1800303cc`
- `0x180030430`
- `0x1800316b8`
- `0x180032ce0`
- `0x18003735c`
- `0x1800396c0`
- `0x18003a730`
- `0x18003f42c`
- `0x1800458d8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002fef4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030298`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002fef4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030298`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002fe5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002fe5f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030058`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030058`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180030263`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180030263`

## string_xrefs

- `0x18002fdbf`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002fea0`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::RestoreUserProfile(CUserProfile *this, int a2, int *a3)
{
  unsigned int v6; // ebx
  int v7; // r15d
  _WORD *v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  char IsEnabled; // al
  int v13; // r8d
  int v14; // ecx
  int v15; // ecx
  int v16; // r8d
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // r14d
  BOOL v23; // ebx
  int v24; // eax
  __int64 v25; // rbx
  int LoopParameters; // eax
  int v27; // r14d
  __int64 v28; // rbx
  __int64 v29; // rbx
  bool v30; // bl
  __int64 v31; // r14
  __int64 v32; // r14
  int v33; // r14d
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // eax
  int v38; // eax
  unsigned int v39; // eax
  BOOL DirectoryJunctionsForUserProfile; // eax
  int KnownFolders; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  int v46; // ecx
  int v47; // r8d
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  unsigned int v52; // [rsp+30h] [rbp-D0h] BYREF
  int v53; // [rsp+34h] [rbp-CCh] BYREF
  int v54; // [rsp+38h] [rbp-C8h] BYREF
  void **v55; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v56[48]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h]
  _QWORD v58[42]; // [rsp+80h] [rbp-80h] BYREF
  int v59[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v60[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v58);
  v58[0] = &ProfileTelemetry::RestoreUserProfile::`vftable';
  ProfileTelemetry::RestoreUserProfile::StartActivity((ProfileTelemetry::RestoreUserProfile *)v58);
  *a3 = 0;
  if ( (unsigned int)IsUserAGuest(*((void **)this + 3)) )
    *((_DWORD *)this + 3) |= 0x80u;
  v6 = IsUserAnAdminMember(*((HANDLE *)this + 3));
  v52 = v6;
  ProfileTelemetry::RestoreUserProfile::IsUserAnAdmin<int const &>(v58, &v52);
  if ( v6 )
  {
    *((_DWORD *)this + 3) |= 0x100u;
    *((_DWORD *)this + 3) &= ~0x80u;
  }
  v7 = 1;
  v54 = 0;
  v8 = (_WORD *)*((_QWORD *)this + 13);
  if ( !v8
    || !*v8
    || (v9 = *((_QWORD *)this + 36)) == 0
    || (v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 8LL))(v9, &v54), (v10 & 0x80000000) == 0) )
  {
    if ( (unsigned __int8)IsFirstBoot() )
    {
      GetTickCount64();
    }
    else if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x40) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(v18, (unsigned int)ProfSvc_CreateNewProfile_Start, v19, 1, (__int64)v59);
    }
LABEL_29:
    v52 = 0;
    v20 = CUserProfile::CheckLocalProfile(this, v7, (int *)&v52);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x590,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v20,
        v49);
    v22 = v52;
    v23 = v52 == 0;
    v53 = 0;
    if ( *((_QWORD *)this + 36) )
    {
      if ( !v52 )
      {
LABEL_57:
        v33 = CUserProfile::IssueTempProfile(this);
        if ( v33 < 0 )
        {
          v34 = CUserProfile::SaveInfoToRegistry(this);
          if ( v34 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5CD,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)(unsigned int)v34,
              v49);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5CE,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v33,
            v49);
          if ( v7 && !(unsigned __int8)IsFirstBoot() && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x40) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(
              v35,
              (unsigned int)ProfSvc_CreateNewProfile_Stop,
              v36,
              1,
              (__int64)v60);
          if ( (*((_BYTE *)this + 12) & 4) != 0 && !(unsigned int)IsProfileInUse(*((const unsigned __int16 **)this + 6)) )
          {
            v37 = DeleteProfileLite(*((_QWORD *)this + 6), *((_QWORD *)this + 19), 0, *((_QWORD *)this + 3));
            if ( v37 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x552,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v37,
                v51);
          }
          v10 = v33;
          goto LABEL_94;
        }
        *((_DWORD *)this + 68) = 102;
        *a3 = 1;
LABEL_70:
        v38 = *((_DWORD *)this + 3);
        if ( (*((_BYTE *)this + 8) & 4) != 0 )
        {
          if ( (v38 & 4) == 0 )
          {
LABEL_77:
            if ( (*((_BYTE *)this + 12) & 0x10) != 0 && v53 )
              GetSystemTimeAsFileTime((LPFILETIME)this + 30);
            KnownFolders = EnsurePreCreateKnownFolders(*((const unsigned __int16 **)this + 6));
            if ( KnownFolders < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5F0,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)KnownFolders,
                v49);
            v42 = CUserProfile::SaveInfoToRegistry(this);
            if ( v42 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5F3,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v42,
                v49);
            v43 = (*(__int64 (__fastcall **)(CUserProfile *, _QWORD))(*(_QWORD *)this + 200LL))(
                    this,
                    *((_QWORD *)this + 19));
            if ( v43 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5F6,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v43,
                v49);
            v44 = *((_QWORD *)this + 36);
            if ( v44 )
            {
              v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 32LL))(v44);
              if ( v45 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x5FA,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  (const char *)(unsigned int)v45,
                  v49);
            }
            ProfileTelemetry::RestoreUserProfile::Stop((ProfileTelemetry::RestoreUserProfile *)v58, v23);
            if ( v7
              && !(unsigned __int8)IsFirstBoot()
              && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x40) != 0 )
            {
              McGenEventWrite_EtwEventWriteTransfer(
                v46,
                (unsigned int)ProfSvc_CreateNewProfile_Stop,
                v47,
                1,
                (__int64)v60);
            }
            v10 = 0;
            goto LABEL_94;
          }
          v39 = v38 | 0x2000;
        }
        else
        {
          v39 = v38 & 0xFFFFDFFF;
        }
        *((_DWORD *)this + 3) = v39;
        if ( (v39 & 4) != 0 )
        {
          DirectoryJunctionsForUserProfile = CreateDirectoryJunctionsForUserProfile(*((HANDLE *)this + 19));
          if ( DirectoryJunctionsForUserProfile < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5E6,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)DirectoryJunctionsForUserProfile,
              v49);
        }
        goto LABEL_77;
      }
      if ( v54 )
      {
        GetSystemTimeAsFileTime((LPFILETIME)this + 32);
        v24 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD))(**((_QWORD **)this + 36) + 16LL))(
                *((_QWORD *)this + 36),
                &v53,
                v22);
        if ( v24 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x59D,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v24,
            v49);
          v23 = 1;
          goto LABEL_57;
        }
      }
    }
    else if ( !v52 )
    {
      goto LABEL_57;
    }
    LOBYTE(v21) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl'::`2'::impl,
      v21);
    *(_QWORD *)v59 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::start(v59, v60);
    v55 = &tip2::test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::`vftable';
    wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
      (wil::details::ThreadFailureCallbackHolder *)v56,
      (struct wil::details::IFailureCallback *)&v55,
      0,
      1);
    v57 = *(_QWORD *)v59;
    if ( *(_QWORD *)v59 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v59 + 288LL));
    wil::com_ptr_t<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>,wil::err_returncode_policy>(v59);
    v52 = 50;
    v25 = v57;
    *(_QWORD *)v59 = v57;
    if ( v57 )
      _InterlockedIncrement((volatile signed __int32 *)(v57 + 288));
    tip2::details::shared_data<0,0,0>::begin_update(v25 + 8);
    LoopParameters = GetLoopParameters(&v52, (unsigned int *)(v25 + 276));
    if ( LoopParameters < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5AA,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)LoopParameters,
        v49);
    tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(v59);
    while ( 1 )
    {
      v27 = CUserProfile::UseLocalProfile(this, v53, a2, a3);
      if ( v27 >= 0 )
        break;
      v28 = v57;
      *(_QWORD *)v59 = v57;
      if ( v57 )
        _InterlockedIncrement((volatile signed __int32 *)(v57 + 288));
      tip2::details::shared_data<0,0,0>::begin_update(v28 + 8);
      Sleep(*(_DWORD *)(v28 + 276));
      tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(v59);
      v29 = v57;
      *(_QWORD *)v59 = v57;
      if ( v57 )
        _InterlockedIncrement((volatile signed __int32 *)(v57 + 288));
      tip2::details::shared_data<0,0,0>::begin_update(v29 + 8);
      v30 = ++*(_DWORD *)(v29 + 272) < v52;
      tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(v59);
      if ( !v30 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5BB,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v27,
          v49);
        v23 = 1;
        goto LABEL_52;
      }
    }
    v23 = 0;
LABEL_52:
    v31 = v57;
    *(_QWORD *)v59 = v57;
    if ( v57 )
      _InterlockedIncrement((volatile signed __int32 *)(v57 + 288));
    tip2::details::shared_data<0,0,0>::begin_update(v31 + 8);
    *(_BYTE *)(v31 + 280) = v23;
    tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(v59);
    v32 = v57;
    wil::EnterCriticalSection(v59, v57 + 200);
    *(_DWORD *)(v32 + 72) |= 0x300u;
    if ( *(_QWORD *)(v32 + 248) )
      tip2::details::shared_data<0,0,0>::complete_helper(v32 + 8, 2);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v59);
    tip2::test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(&v55);
    if ( !v23 )
      goto LABEL_70;
    goto LABEL_57;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (byte_18007F7C1 & 2) != 0 )
  {
    McTemplateU0q_EtwEventWriteTransfer(v11, EVENT_RUP_FAILED_CHECK_ROAMING_PROFILE, v10);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl);
  v14 = *((_DWORD *)this + 3) & 0x40000;
  if ( IsEnabled )
  {
    if ( v14 && (byte_18007F7C1 & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v14,
        (unsigned int)EVENT_RUP_PROFILE_FAILED_SUPERMANDATORY,
        v13,
        1,
        (__int64)v59);
    goto LABEL_16;
  }
  if ( !v14 )
  {
LABEL_16:
    v7 = 0;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x575,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)v10,
    v49);
  if ( !(unsigned __int8)IsFirstBoot() && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x40) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v15, (unsigned int)ProfSvc_CreateNewProfile_Stop, v16, 1, (__int64)v59);
  if ( (*((_BYTE *)this + 12) & 4) != 0 && !(unsigned int)IsProfileInUse(*((const unsigned __int16 **)this + 6)) )
  {
    v17 = DeleteProfileLite(*((_QWORD *)this + 6), *((_QWORD *)this + 19), 0, *((_QWORD *)this + 3));
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x552,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v17,
        v50);
  }
LABEL_94:
  ProfileTelemetry::RestoreUserProfile::~RestoreUserProfile((ProfileTelemetry::RestoreUserProfile *)v58);
  return v10;
}

```

## disassembly

```asm
0x18002fc50  mov     [rsp-8+arg_18], rbx
0x18002fc55  push    rbp
0x18002fc56  push    rsi
0x18002fc57  push    rdi
0x18002fc58  push    r12
0x18002fc5a  push    r13
0x18002fc5c  push    r14
0x18002fc5e  push    r15
0x18002fc60  lea     rbp, [rsp-100h]
0x18002fc68  sub     rsp, 200h
0x18002fc6f  mov     rax, cs:__security_cookie
0x18002fc76  xor     rax, rsp
0x18002fc79  mov     [rbp+130h+var_40], rax
0x18002fc80  mov     r12, r8
0x18002fc83  mov     r13d, edx
0x18002fc86  mov     rdi, rcx
0x18002fc89  lea     rdx, aRestoreuserpro; "RestoreUserProfile"
0x18002fc90  lea     rcx, [rbp+130h+var_1B0]; struct wil::details::IFailureCallback *
0x18002fc94  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002fc99  lea     rax, ??_7RestoreUserProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::RestoreUserProfile::`vftable'
0x18002fca0  mov     [rbp+130h+var_1B0], rax
0x18002fca4  lea     rcx, [rbp+130h+var_1B0]; this
0x18002fca8  call    ?StartActivity@RestoreUserProfile@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::RestoreUserProfile::StartActivity(void)
0x18002fcad  xor     r14d, r14d
0x18002fcb0  mov     [r12], r14d
0x18002fcb4  mov     rcx, [rdi+18h]; void *
0x18002fcb8  call    ?IsUserAGuest@@YAHPEAX@Z; IsUserAGuest(void *)
0x18002fcbd  test    eax, eax
0x18002fcbf  jz      short loc_18002FCC6
0x18002fcc1  bts     dword ptr [rdi+0Ch], 7
0x18002fcc6  mov     rcx, [rdi+18h]; hExistingToken
0x18002fcca  call    ?IsUserAnAdminMember@@YAHPEAX@Z; IsUserAnAdminMember(void *)
0x18002fccf  mov     ebx, eax
0x18002fcd1  mov     [rsp+230h+var_200], eax
0x18002fcd5  lea     rdx, [rsp+230h+var_200]
0x18002fcda  lea     rcx, [rbp+130h+var_1B0]
0x18002fcde  call    ??$IsUserAnAdmin@AEBH@RestoreUserProfile@ProfileTelemetry@@QEAAXAEBH@Z; ProfileTelemetry::RestoreUserProfile::IsUserAnAdmin<int const &>(int const &)
0x18002fce3  test    ebx, ebx
0x18002fce5  jz      short loc_18002FCF1
0x18002fce7  bts     dword ptr [rdi+0Ch], 8
0x18002fcec  btr     dword ptr [rdi+0Ch], 7
0x18002fcf1  mov     esi, 1
0x18002fcf6  mov     r15d, esi
0x18002fcf9  mov     [rsp+230h+var_1F8], r14d
0x18002fcfe  mov     rax, [rdi+68h]
0x18002fd02  test    rax, rax
0x18002fd05  jz      loc_18002FE56
0x18002fd0b  cmp     [rax], r14w
0x18002fd0f  jz      loc_18002FE56
0x18002fd15  mov     rcx, [rdi+120h]
0x18002fd1c  test    rcx, rcx
0x18002fd1f  jz      loc_18002FE56
0x18002fd25  mov     rax, [rcx]
0x18002fd28  lea     rdx, [rsp+230h+var_1F8]
0x18002fd2d  mov     rax, [rax+8]
0x18002fd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd36  mov     ebx, eax
0x18002fd38  test    eax, eax
0x18002fd3a  jns     loc_18002FE56
0x18002fd40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18002fd47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18002fd4c  test    al, al
0x18002fd4e  jz      short loc_18002FD68
0x18002fd50  test    cs:byte_18007F7C1, 2
0x18002fd57  jz      short loc_18002FD68
0x18002fd59  mov     r8d, ebx
0x18002fd5c  lea     rdx, EVENT_RUP_FAILED_CHECK_ROAMING_PROFILE
0x18002fd63  call    McTemplateU0q_EtwEventWriteTransfer
0x18002fd68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18002fd6f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18002fd74  mov     ecx, [rdi+0Ch]
0x18002fd77  and     ecx, 40000h
0x18002fd7d  test    al, al
0x18002fd7f  jz      short loc_18002FDB1
0x18002fd81  test    ecx, ecx
0x18002fd83  jz      short loc_18002FDA9
0x18002fd85  test    cs:byte_18007F7C1, 2
0x18002fd8c  jz      short loc_18002FDA9
0x18002fd8e  lea     rax, [rbp+130h+var_60]
0x18002fd95  mov     qword ptr [rsp+230h+var_210], rax
0x18002fd9a  mov     r9d, esi
0x18002fd9d  lea     rdx, EVENT_RUP_PROFILE_FAILED_SUPERMANDATORY
0x18002fda4  call    McGenEventWrite_EtwEventWriteTransfer
0x18002fda9  mov     r15d, r14d
0x18002fdac  jmp     loc_18002FE8B
0x18002fdb1  test    ecx, ecx
0x18002fdb3  jz      short loc_18002FDA9
0x18002fdb5  mov     rcx, [rbp+138h]; this
0x18002fdbc  mov     r9d, ebx; char *
0x18002fdbf  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fdc6  mov     r8, rsi; unsigned int
0x18002fdc9  mov     edx, 575h; void *
0x18002fdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fdd3  call    _IsFirstBoot
0x18002fdd8  test    al, al
0x18002fdda  jnz     short loc_18002FE00
0x18002fddc  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 40h
0x18002fde3  jz      short loc_18002FE00
0x18002fde5  lea     rax, [rbp+130h+var_60]
0x18002fdec  mov     qword ptr [rsp+230h+var_210], rax; int
0x18002fdf1  mov     r9d, r15d
0x18002fdf4  lea     rdx, ProfSvc_CreateNewProfile_Stop
0x18002fdfb  call    McGenEventWrite_EtwEventWriteTransfer
0x18002fe00  test    byte ptr [rdi+0Ch], 4
0x18002fe04  jz      loc_18003038E
0x18002fe0a  mov     rcx, [rdi+30h]; unsigned __int16 *
0x18002fe0e  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002fe13  test    eax, eax
0x18002fe15  jnz     loc_18003038E
0x18002fe1b  mov     r9, [rdi+18h]
0x18002fe1f  xor     r8d, r8d
0x18002fe22  mov     rdx, [rdi+98h]
0x18002fe29  mov     rcx, [rdi+30h]
0x18002fe2d  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x18002fe32  test    eax, eax
0x18002fe34  jns     loc_18003038E
0x18002fe3a  mov     rcx, [rbp+138h]; this
0x18002fe41  mov     r9d, eax; char *
0x18002fe44  mov     r8, rsi; unsigned int
0x18002fe47  mov     edx, 552h; void *
0x18002fe4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fe51  jmp     loc_18003038E
0x18002fe56  call    _IsFirstBoot
0x18002fe5b  test    al, al
0x18002fe5d  jz      short loc_18002FE67
0x18002fe5f  call    cs:__imp_GetTickCount64
0x18002fe65  jmp     short loc_18002FE8B
0x18002fe67  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 40h
0x18002fe6e  jz      short loc_18002FE8B
0x18002fe70  lea     rax, [rbp+130h+var_60]
0x18002fe77  mov     qword ptr [rsp+230h+var_210], rax; int
0x18002fe7c  mov     r9d, esi
0x18002fe7f  lea     rdx, ProfSvc_CreateNewProfile_Start
0x18002fe86  call    McGenEventWrite_EtwEventWriteTransfer
0x18002fe8b  mov     [rsp+230h+var_200], r14d
0x18002fe90  lea     r8, [rsp+230h+var_200]; int *
0x18002fe95  mov     edx, r15d; int
0x18002fe98  mov     rcx, rdi; this
0x18002fe9b  call    ?CheckLocalProfile@CUserProfile@@IEAAJHPEAH@Z; CUserProfile::CheckLocalProfile(int,int *)
0x18002fea0  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fea7  test    eax, eax
0x18002fea9  jns     short loc_18002FEC2
0x18002feab  mov     rcx, [rbp+138h]; this
0x18002feb2  mov     r9d, eax; char *
0x18002feb5  mov     r8, rsi; unsigned int
0x18002feb8  mov     edx, 590h; void *
0x18002febd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fec2  mov     ebx, r14d
0x18002fec5  mov     r14d, [rsp+230h+var_200]
0x18002feca  xor     eax, eax
0x18002fecc  test    r14d, r14d
0x18002fecf  setz    bl
0x18002fed2  mov     [rsp+230h+var_1FC], eax
0x18002fed6  cmp     [rdi+120h], rax
0x18002fedd  jz      short loc_18002FF3A
0x18002fedf  test    ebx, ebx
0x18002fee1  jnz     loc_18003015D
0x18002fee7  cmp     [rsp+230h+var_1F8], eax
0x18002feeb  jz      short loc_18002FF42
0x18002feed  lea     rcx, [rdi+100h]; lpSystemTimeAsFileTime
0x18002fef4  call    cs:__imp_GetSystemTimeAsFileTime
0x18002fefa  mov     rcx, [rdi+120h]
0x18002ff01  mov     rax, [rcx]
0x18002ff04  mov     r8d, r14d
0x18002ff07  lea     rdx, [rsp+230h+var_1FC]
0x18002ff0c  mov     rax, [rax+10h]
0x18002ff10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff15  test    eax, eax
0x18002ff17  jns     short loc_18002FF42
0x18002ff19  mov     rcx, [rbp+138h]; this
0x18002ff20  mov     r9d, eax; char *
0x18002ff23  mov     r8, rsi; unsigned int
0x18002ff26  mov     edx, 59Dh; void *
0x18002ff2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ff30  mov     ebx, 1
0x18002ff35  jmp     loc_18003015D
0x18002ff3a  test    ebx, ebx
0x18002ff3c  jnz     loc_18003015D
0x18002ff42  mov     dl, 1
0x18002ff44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl(void)'::`2'::impl
0x18002ff4b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002ff50  mov     qword ptr [rbp+130h+var_60], 0
0x18002ff5b  lea     rdx, [rbp+130h+var_50]
0x18002ff62  lea     rcx, [rbp+130h+var_60]
0x18002ff69  call    ?start@?$tip_test@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::start(void)
0x18002ff6e  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::`vftable'
0x18002ff75  mov     [rsp+230h+var_1F0], rax
0x18002ff7a  mov     r9b, 1; bool
0x18002ff7d  xor     r8d, r8d; struct wil::CallContextInfo *
0x18002ff80  lea     rdx, [rsp+230h+var_1F0]; struct wil::details::IFailureCallback *
0x18002ff85  lea     rcx, [rsp+230h+var_1E8]; this
0x18002ff8a  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18002ff8f  mov     rax, qword ptr [rbp+130h+var_60]
0x18002ff96  mov     [rsp+230h+var_1B8], rax
0x18002ff9b  test    rax, rax
0x18002ff9e  jz      short loc_18002FFA7
0x18002ffa0  lock inc dword ptr [rax+120h]
0x18002ffa7  lea     rcx, [rbp+130h+var_60]
0x18002ffae  call    ??1?$com_ptr_t@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>,wil::err_returncode_policy>(void)
0x18002ffb3  mov     [rsp+230h+var_200], 32h ; '2'
0x18002ffbb  mov     rbx, [rsp+230h+var_1B8]
0x18002ffc0  mov     qword ptr [rbp+130h+var_60], rbx
0x18002ffc7  test    rbx, rbx
0x18002ffca  jz      short loc_18002FFD3
0x18002ffcc  lock inc dword ptr [rbx+120h]
0x18002ffd3  lea     rcx, [rbx+8]
0x18002ffd7  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002ffdc  lea     rdx, [rbx+114h]; unsigned int *
0x18002ffe3  lea     rcx, [rsp+230h+var_200]; unsigned int *
0x18002ffe8  call    ?GetLoopParameters@@YAJPEAK0@Z; GetLoopParameters(ulong *,ulong *)
0x18002ffed  test    eax, eax
0x18002ffef  jns     short loc_180030008
0x18002fff1  mov     rcx, [rbp+138h]; this
0x18002fff8  mov     r9d, eax; char *
0x18002fffb  mov     r8, rsi; unsigned int
0x18002fffe  mov     edx, 5AAh; void *
0x180030003  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030008  lea     rcx, [rbp+130h+var_60]
0x18003000f  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x180030014  mov     r9, r12; int *
0x180030017  mov     r8d, r13d; int
0x18003001a  mov     edx, [rsp+230h+var_1FC]; int
0x18003001e  mov     rcx, rdi; this
0x180030021  call    ?UseLocalProfile@CUserProfile@@IEAAJHHPEAH@Z; CUserProfile::UseLocalProfile(int,int,int *)
0x180030026  mov     r14d, eax
0x180030029  test    eax, eax
0x18003002b  jns     loc_1800300D0
0x180030031  mov     rbx, [rsp+230h+var_1B8]
0x180030036  mov     qword ptr [rbp+130h+var_60], rbx
0x18003003d  test    rbx, rbx
0x180030040  jz      short loc_180030049
0x180030042  lock inc dword ptr [rbx+120h]
0x180030049  lea     rcx, [rbx+8]
0x18003004d  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180030052  mov     ecx, [rbx+114h]; dwMilliseconds
0x180030058  call    cs:__imp_Sleep
0x18003005e  lea     rcx, [rbp+130h+var_60]
0x180030065  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x18003006a  mov     rbx, [rsp+230h+var_1B8]
0x18003006f  mov     qword ptr [rbp+130h+var_60], rbx
0x180030076  test    rbx, rbx
0x180030079  jz      short loc_180030082
0x18003007b  lock inc dword ptr [rbx+120h]
0x180030082  lea     rcx, [rbx+8]
0x180030086  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18003008b  inc     dword ptr [rbx+110h]
0x180030091  mov     eax, [rbx+110h]
0x180030097  cmp     eax, [rsp+230h+var_200]
0x18003009b  setb    bl
0x18003009e  lea     rcx, [rbp+130h+var_60]
0x1800300a5  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x1800300aa  test    bl, bl
0x1800300ac  jnz     loc_180030014
0x1800300b2  mov     rcx, [rbp+138h]; this
0x1800300b9  mov     r9d, r14d; char *
0x1800300bc  mov     r8, rsi; unsigned int
0x1800300bf  mov     edx, 5BBh; void *
0x1800300c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800300c9  mov     ebx, 1
0x1800300ce  jmp     short loc_1800300D2
0x1800300d0  xor     ebx, ebx
0x1800300d2  mov     r14, [rsp+230h+var_1B8]
0x1800300d7  mov     qword ptr [rbp+130h+var_60], r14
0x1800300de  test    r14, r14
0x1800300e1  jz      short loc_1800300EB
0x1800300e3  lock inc dword ptr [r14+120h]
0x1800300eb  lea     rcx, [r14+8]
0x1800300ef  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800300f4  mov     [r14+118h], bl
0x1800300fb  lea     rcx, [rbp+130h+var_60]
0x180030102  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x180030107  mov     r14, [rsp+230h+var_1B8]
0x18003010c  lea     rdx, [r14+0C8h]
0x180030113  lea     rcx, [rbp+130h+var_60]
0x18003011a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003011f  or      dword ptr [r14+48h], 300h
0x180030127  cmp     qword ptr [r14+0F8h], 0
0x18003012f  jz      short loc_18003013F
0x180030131  mov     edx, 2
0x180030136  lea     rcx, [r14+8]
0x18003013a  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003013f  lea     rcx, [rbp+130h+var_60]
0x180030146  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18003014b  lea     rcx, [rsp+230h+var_1F0]
0x180030150  call    ??1?$test_watcher@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x180030155  test    ebx, ebx
0x180030157  jz      loc_18003023E
0x18003015d  mov     rcx, rdi; this
0x180030160  call    ?IssueTempProfile@CUserProfile@@IEAAJXZ; CUserProfile::IssueTempProfile(void)
0x180030165  mov     r14d, eax
0x180030168  test    eax, eax
0x18003016a  jns     loc_18003022C
0x180030170  mov     rcx, rdi; this
0x180030173  call    ?SaveInfoToRegistry@CUserProfile@@IEAAJXZ; CUserProfile::SaveInfoToRegistry(void)
0x180030178  test    eax, eax
0x18003017a  jns     short loc_180030193
0x18003017c  mov     rcx, [rbp+138h]; this
0x180030183  mov     r9d, eax; char *
0x180030186  mov     r8, rsi; unsigned int
0x180030189  mov     edx, 5CDh; void *
  ... truncated ...
```
