# CUserProfile::RestoreUserProfile(int,int *)

- ea: `0x18002ef18`
- end: `0x18002f6aa`
- name: `?RestoreUserProfile@CUserProfile@@IEAAJHPEAH@Z`
- size: `1938`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `34`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x180003b44`
- `0x180013db0`
- `0x1800177c0`
- `0x180018430`
- `0x18001984c`
- `0x18001dc00`
- `0x180021dd4`
- `0x180024b84`
- `0x180024cb0`
- `0x1800268e0`
- `0x180026908`
- `0x18002729c`
- `0x180027c64`
- `0x180028150`
- `0x180029a04`
- `0x180029f50`
- `0x18002ac64`
- `0x18002e1dc`
- `0x18002e63c`
- `0x18002e864`
- `0x18002ef18`
- `0x18002f6b0`
- `0x18002f6e8`
- `0x180030008`
- `0x1800306b4`
- `0x180030ad0`
- `0x180030af8`
- `0x180030f38`
- `0x180038798`
- `0x18003abac`
- `0x18003bc70`
- `0x180040bcc`
- `0x180047994`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f1c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f578`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f1c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f578`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f127`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f127`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f32c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f32c`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x18002f53d`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x18002f53d`

## string_xrefs

- `0x18002f087`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002f16e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
            v37 = DeleteProfileLite(
                    *((const unsigned __int16 **)this + 6),
                    *((WCHAR **)this + 19),
                    0,
                    *((DWORD **)this + 3));
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
    && (byte_1800828C1 & 2) != 0 )
  {
    McTemplateU0q_EtwEventWriteTransfer(v11, EVENT_RUP_FAILED_CHECK_ROAMING_PROFILE, v10);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl);
  v14 = *((_DWORD *)this + 3) & 0x40000;
  if ( IsEnabled )
  {
    if ( v14 && (byte_1800828C1 & 2) != 0 )
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
    v17 = DeleteProfileLite(*((const unsigned __int16 **)this + 6), *((WCHAR **)this + 19), 0, *((DWORD **)this + 3));
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
0x18002ef18  mov     [rsp-8+arg_18], rbx
0x18002ef1d  push    rbp
0x18002ef1e  push    rsi
0x18002ef1f  push    rdi
0x18002ef20  push    r12
0x18002ef22  push    r13
0x18002ef24  push    r14
0x18002ef26  push    r15
0x18002ef28  lea     rbp, [rsp-100h]
0x18002ef30  sub     rsp, 200h
0x18002ef37  mov     rax, cs:__security_cookie
0x18002ef3e  xor     rax, rsp
0x18002ef41  mov     [rbp+130h+var_40], rax
0x18002ef48  mov     r12, r8
0x18002ef4b  mov     r13d, edx
0x18002ef4e  mov     rdi, rcx
0x18002ef51  lea     rdx, aRestoreuserpro; "RestoreUserProfile"
0x18002ef58  lea     rcx, [rbp+130h+var_1B0]; struct wil::details::IFailureCallback *
0x18002ef5c  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002ef61  lea     rax, ??_7RestoreUserProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::RestoreUserProfile::`vftable'
0x18002ef68  mov     [rbp+130h+var_1B0], rax
0x18002ef6c  lea     rcx, [rbp+130h+var_1B0]; this
0x18002ef70  call    ?StartActivity@RestoreUserProfile@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::RestoreUserProfile::StartActivity(void)
0x18002ef75  xor     r14d, r14d
0x18002ef78  mov     [r12], r14d
0x18002ef7c  mov     rcx, [rdi+18h]; void *
0x18002ef80  call    ?IsUserAGuest@@YAHPEAX@Z; IsUserAGuest(void *)
0x18002ef85  test    eax, eax
0x18002ef87  jz      short loc_18002EF8E
0x18002ef89  bts     dword ptr [rdi+0Ch], 7
0x18002ef8e  mov     rcx, [rdi+18h]; hExistingToken
0x18002ef92  call    ?IsUserAnAdminMember@@YAHPEAX@Z; IsUserAnAdminMember(void *)
0x18002ef97  mov     ebx, eax
0x18002ef99  mov     [rsp+230h+var_200], eax
0x18002ef9d  lea     rdx, [rsp+230h+var_200]
0x18002efa2  lea     rcx, [rbp+130h+var_1B0]
0x18002efa6  call    ??$IsUserAnAdmin@AEBH@RestoreUserProfile@ProfileTelemetry@@QEAAXAEBH@Z; ProfileTelemetry::RestoreUserProfile::IsUserAnAdmin<int const &>(int const &)
0x18002efab  test    ebx, ebx
0x18002efad  jz      short loc_18002EFB9
0x18002efaf  bts     dword ptr [rdi+0Ch], 8
0x18002efb4  btr     dword ptr [rdi+0Ch], 7
0x18002efb9  mov     esi, 1
0x18002efbe  mov     r15d, esi
0x18002efc1  mov     [rsp+230h+var_1F8], r14d
0x18002efc6  mov     rax, [rdi+68h]
0x18002efca  test    rax, rax
0x18002efcd  jz      loc_18002F11E
0x18002efd3  cmp     [rax], r14w
0x18002efd7  jz      loc_18002F11E
0x18002efdd  mov     rcx, [rdi+120h]
0x18002efe4  test    rcx, rcx
0x18002efe7  jz      loc_18002F11E
0x18002efed  mov     rax, [rcx]
0x18002eff0  lea     rdx, [rsp+230h+var_1F8]
0x18002eff5  mov     rax, [rax+8]
0x18002eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002effe  mov     ebx, eax
0x18002f000  test    eax, eax
0x18002f002  jns     loc_18002F11E
0x18002f008  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18002f00f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18002f014  test    al, al
0x18002f016  jz      short loc_18002F030
0x18002f018  test    cs:byte_1800828C1, 2
0x18002f01f  jz      short loc_18002F030
0x18002f021  mov     r8d, ebx
0x18002f024  lea     rdx, EVENT_RUP_FAILED_CHECK_ROAMING_PROFILE
0x18002f02b  call    McTemplateU0q_EtwEventWriteTransfer
0x18002f030  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18002f037  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18002f03c  mov     ecx, [rdi+0Ch]
0x18002f03f  and     ecx, 40000h
0x18002f045  test    al, al
0x18002f047  jz      short loc_18002F079
0x18002f049  test    ecx, ecx
0x18002f04b  jz      short loc_18002F071
0x18002f04d  test    cs:byte_1800828C1, 2
0x18002f054  jz      short loc_18002F071
0x18002f056  lea     rax, [rbp+130h+var_60]
0x18002f05d  mov     qword ptr [rsp+230h+var_210], rax
0x18002f062  mov     r9d, esi
0x18002f065  lea     rdx, EVENT_RUP_PROFILE_FAILED_SUPERMANDATORY
0x18002f06c  call    McGenEventWrite_EtwEventWriteTransfer
0x18002f071  mov     r15d, r14d
0x18002f074  jmp     loc_18002F159
0x18002f079  test    ecx, ecx
0x18002f07b  jz      short loc_18002F071
0x18002f07d  mov     rcx, [rbp+138h]; this
0x18002f084  mov     r9d, ebx; char *
0x18002f087  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f08e  mov     r8, rsi; unsigned int
0x18002f091  mov     edx, 575h; void *
0x18002f096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f09b  call    _IsFirstBoot
0x18002f0a0  test    al, al
0x18002f0a2  jnz     short loc_18002F0C8
0x18002f0a4  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 40h
0x18002f0ab  jz      short loc_18002F0C8
0x18002f0ad  lea     rax, [rbp+130h+var_60]
0x18002f0b4  mov     qword ptr [rsp+230h+var_210], rax; int
0x18002f0b9  mov     r9d, r15d
0x18002f0bc  lea     rdx, ProfSvc_CreateNewProfile_Stop
0x18002f0c3  call    McGenEventWrite_EtwEventWriteTransfer
0x18002f0c8  test    byte ptr [rdi+0Ch], 4
0x18002f0cc  jz      loc_18002F674
0x18002f0d2  mov     rcx, [rdi+30h]; unsigned __int16 *
0x18002f0d6  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002f0db  test    eax, eax
0x18002f0dd  jnz     loc_18002F674
0x18002f0e3  mov     r9, [rdi+18h]
0x18002f0e7  xor     r8d, r8d
0x18002f0ea  mov     rdx, [rdi+98h]
0x18002f0f1  mov     rcx, [rdi+30h]
0x18002f0f5  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x18002f0fa  test    eax, eax
0x18002f0fc  jns     loc_18002F674
0x18002f102  mov     rcx, [rbp+138h]; this
0x18002f109  mov     r9d, eax; char *
0x18002f10c  mov     r8, rsi; unsigned int
0x18002f10f  mov     edx, 552h; void *
0x18002f114  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f119  jmp     loc_18002F674
0x18002f11e  call    _IsFirstBoot
0x18002f123  test    al, al
0x18002f125  jz      short loc_18002F135
0x18002f127  call    cs:__imp_GetTickCount64
0x18002f12e  nop     dword ptr [rax+rax+00h]
0x18002f133  jmp     short loc_18002F159
0x18002f135  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 40h
0x18002f13c  jz      short loc_18002F159
0x18002f13e  lea     rax, [rbp+130h+var_60]
0x18002f145  mov     qword ptr [rsp+230h+var_210], rax; int
0x18002f14a  mov     r9d, esi
0x18002f14d  lea     rdx, ProfSvc_CreateNewProfile_Start
0x18002f154  call    McGenEventWrite_EtwEventWriteTransfer
0x18002f159  mov     [rsp+230h+var_200], r14d
0x18002f15e  lea     r8, [rsp+230h+var_200]; int *
0x18002f163  mov     edx, r15d; int
0x18002f166  mov     rcx, rdi; this
0x18002f169  call    ?CheckLocalProfile@CUserProfile@@IEAAJHPEAH@Z; CUserProfile::CheckLocalProfile(int,int *)
0x18002f16e  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f175  test    eax, eax
0x18002f177  jns     short loc_18002F190
0x18002f179  mov     rcx, [rbp+138h]; this
0x18002f180  mov     r9d, eax; char *
0x18002f183  mov     r8, rsi; unsigned int
0x18002f186  mov     edx, 590h; void *
0x18002f18b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f190  mov     ebx, r14d
0x18002f193  mov     r14d, [rsp+230h+var_200]
0x18002f198  xor     eax, eax
0x18002f19a  test    r14d, r14d
0x18002f19d  setz    bl
0x18002f1a0  mov     [rsp+230h+var_1FC], eax
0x18002f1a4  cmp     [rdi+120h], rax
0x18002f1ab  jz      short loc_18002F20E
0x18002f1ad  test    ebx, ebx
0x18002f1af  jnz     loc_18002F437
0x18002f1b5  cmp     [rsp+230h+var_1F8], eax
0x18002f1b9  jz      short loc_18002F216
0x18002f1bb  lea     rcx, [rdi+100h]; lpSystemTimeAsFileTime
0x18002f1c2  call    cs:__imp_GetSystemTimeAsFileTime
0x18002f1c9  nop     dword ptr [rax+rax+00h]
0x18002f1ce  mov     rcx, [rdi+120h]
0x18002f1d5  mov     rax, [rcx]
0x18002f1d8  mov     r8d, r14d
0x18002f1db  lea     rdx, [rsp+230h+var_1FC]
0x18002f1e0  mov     rax, [rax+10h]
0x18002f1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1e9  test    eax, eax
0x18002f1eb  jns     short loc_18002F216
0x18002f1ed  mov     rcx, [rbp+138h]; this
0x18002f1f4  mov     r9d, eax; char *
0x18002f1f7  mov     r8, rsi; unsigned int
0x18002f1fa  mov     edx, 59Dh; void *
0x18002f1ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f204  mov     ebx, 1
0x18002f209  jmp     loc_18002F437
0x18002f20e  test    ebx, ebx
0x18002f210  jnz     loc_18002F437
0x18002f216  mov     dl, 1
0x18002f218  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::GetImpl(void)'::`2'::impl
0x18002f21f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_Retry_Load_Loop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002f224  mov     qword ptr [rbp+130h+var_60], 0
0x18002f22f  lea     rdx, [rbp+130h+var_50]
0x18002f236  lea     rcx, [rbp+130h+var_60]
0x18002f23d  call    ?start@?$tip_test@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::start(void)
0x18002f242  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::`vftable'
0x18002f249  mov     [rsp+230h+var_1F0], rax
0x18002f24e  mov     r9b, 1; bool
0x18002f251  xor     r8d, r8d; struct wil::CallContextInfo *
0x18002f254  lea     rdx, [rsp+230h+var_1F0]; struct wil::details::IFailureCallback *
0x18002f259  lea     rcx, [rsp+230h+var_1E8]; this
0x18002f25e  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18002f263  mov     rax, qword ptr [rbp+130h+var_60]
0x18002f26a  mov     [rsp+230h+var_1B8], rax
0x18002f26f  test    rax, rax
0x18002f272  jz      short loc_18002F27B
0x18002f274  lock inc dword ptr [rax+120h]
0x18002f27b  lea     rcx, [rbp+130h+var_60]
0x18002f282  call    ??1?$com_ptr_t@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>,wil::err_returncode_policy>(void)
0x18002f287  mov     [rsp+230h+var_200], 32h ; '2'
0x18002f28f  mov     rbx, [rsp+230h+var_1B8]
0x18002f294  mov     qword ptr [rbp+130h+var_60], rbx
0x18002f29b  test    rbx, rbx
0x18002f29e  jz      short loc_18002F2A7
0x18002f2a0  lock inc dword ptr [rbx+120h]
0x18002f2a7  lea     rcx, [rbx+8]
0x18002f2ab  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002f2b0  lea     rdx, [rbx+114h]; unsigned int *
0x18002f2b7  lea     rcx, [rsp+230h+var_200]; unsigned int *
0x18002f2bc  call    ?GetLoopParameters@@YAJPEAK0@Z; GetLoopParameters(ulong *,ulong *)
0x18002f2c1  test    eax, eax
0x18002f2c3  jns     short loc_18002F2DC
0x18002f2c5  mov     rcx, [rbp+138h]; this
0x18002f2cc  mov     r9d, eax; char *
0x18002f2cf  mov     r8, rsi; unsigned int
0x18002f2d2  mov     edx, 5AAh; void *
0x18002f2d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f2dc  lea     rcx, [rbp+130h+var_60]
0x18002f2e3  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x18002f2e8  mov     r9, r12; int *
0x18002f2eb  mov     r8d, r13d; int
0x18002f2ee  mov     edx, [rsp+230h+var_1FC]; int
0x18002f2f2  mov     rcx, rdi; this
0x18002f2f5  call    ?UseLocalProfile@CUserProfile@@IEAAJHHPEAH@Z; CUserProfile::UseLocalProfile(int,int,int *)
0x18002f2fa  mov     r14d, eax
0x18002f2fd  test    eax, eax
0x18002f2ff  jns     loc_18002F3AA
0x18002f305  mov     rbx, [rsp+230h+var_1B8]
0x18002f30a  mov     qword ptr [rbp+130h+var_60], rbx
0x18002f311  test    rbx, rbx
0x18002f314  jz      short loc_18002F31D
0x18002f316  lock inc dword ptr [rbx+120h]
0x18002f31d  lea     rcx, [rbx+8]
0x18002f321  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002f326  mov     ecx, [rbx+114h]; dwMilliseconds
0x18002f32c  call    cs:__imp_Sleep
0x18002f333  nop     dword ptr [rax+rax+00h]
0x18002f338  lea     rcx, [rbp+130h+var_60]
0x18002f33f  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x18002f344  mov     rbx, [rsp+230h+var_1B8]
0x18002f349  mov     qword ptr [rbp+130h+var_60], rbx
0x18002f350  test    rbx, rbx
0x18002f353  jz      short loc_18002F35C
0x18002f355  lock inc dword ptr [rbx+120h]
0x18002f35c  lea     rcx, [rbx+8]
0x18002f360  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002f365  inc     dword ptr [rbx+110h]
0x18002f36b  mov     eax, [rbx+110h]
0x18002f371  cmp     eax, [rsp+230h+var_200]
0x18002f375  setb    bl
0x18002f378  lea     rcx, [rbp+130h+var_60]
0x18002f37f  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x18002f384  test    bl, bl
0x18002f386  jnz     loc_18002F2E8
0x18002f38c  mov     rcx, [rbp+138h]; this
0x18002f393  mov     r9d, r14d; char *
0x18002f396  mov     r8, rsi; unsigned int
0x18002f399  mov     edx, 5BBh; void *
0x18002f39e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f3a3  mov     ebx, 1
0x18002f3a8  jmp     short loc_18002F3AC
0x18002f3aa  xor     ebx, ebx
0x18002f3ac  mov     r14, [rsp+230h+var_1B8]
0x18002f3b1  mov     qword ptr [rbp+130h+var_60], r14
0x18002f3b8  test    r14, r14
0x18002f3bb  jz      short loc_18002F3C5
0x18002f3bd  lock inc dword ptr [r14+120h]
0x18002f3c5  lea     rcx, [r14+8]
0x18002f3c9  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002f3ce  mov     [r14+118h], bl
0x18002f3d5  lea     rcx, [rbp+130h+var_60]
0x18002f3dc  call    ??1?$test_data_control@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_data_control<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x18002f3e1  mov     r14, [rsp+230h+var_1B8]
0x18002f3e6  lea     rdx, [r14+0C8h]
0x18002f3ed  lea     rcx, [rbp+130h+var_60]
0x18002f3f4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002f3f9  or      dword ptr [r14+48h], 300h
0x18002f401  cmp     qword ptr [r14+0F8h], 0
0x18002f409  jz      short loc_18002F419
0x18002f40b  mov     edx, 2
0x18002f410  lea     rcx, [r14+8]
0x18002f414  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18002f419  lea     rcx, [rbp+130h+var_60]
0x18002f420  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18002f425  lea     rcx, [rsp+230h+var_1F0]
0x18002f42a  call    ??1?$test_watcher@V?$merged_data@U_tip_LoopTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>::~test_watcher<tip2::details::merged_data<_tip_LoopTest,_tip_LoopTest>>(void)
0x18002f42f  test    ebx, ebx
0x18002f431  jz      loc_18002F518
0x18002f437  mov     rcx, rdi; this
0x18002f43a  call    ?IssueTempProfile@CUserProfile@@IEAAJXZ; CUserProfile::IssueTempProfile(void)
0x18002f43f  mov     r14d, eax
0x18002f442  test    eax, eax
0x18002f444  jns     loc_18002F506
0x18002f44a  mov     rcx, rdi; this
0x18002f44d  call    ?SaveInfoToRegistry@CUserProfile@@IEAAJXZ; CUserProfile::SaveInfoToRegistry(void)
0x18002f452  test    eax, eax
0x18002f454  jns     short loc_18002F46D
0x18002f456  mov     rcx, [rbp+138h]; this
  ... truncated ...
```
