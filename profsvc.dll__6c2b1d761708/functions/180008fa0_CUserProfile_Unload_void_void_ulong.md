# CUserProfile::Unload(void *,void *,ulong)

- ea: `0x180008fa0`
- end: `0x180009828`
- name: `?Unload@CUserProfile@@QEAAJPEAX0K@Z`
- size: `2184`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, HANDLE hToken, void *, unsigned int)`
- caller_count: `2`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001afd0`
- `0x18001c980`

## callees

- `0x1800066cc`
- `0x180007b58`
- `0x180007bc0`
- `0x180007c2c`
- `0x180007cd0`
- `0x180007d40`
- `0x1800080d0`
- `0x180008154`
- `0x1800081b0`
- `0x1800081f0`
- `0x180008250`
- `0x1800082b8`
- `0x1800084bc`
- `0x1800084e0`
- `0x1800087e8`
- `0x1800088b0`
- `0x180008f00`
- `0x180008fa0`
- `0x180009830`
- `0x18000b0a0`
- `0x18000e1a0`
- `0x180012b14`
- `0x180013aa0`
- `0x180014e90`
- `0x180025570`
- `0x180025e54`
- `0x180026c7c`
- `0x1800277fc`
- `0x180027e50`
- `0x18002a120`
- `0x18002df48`
- `0x18002eae0`
- `0x18002f6e8`
- `0x18003057c`
- `0x180030ad0`
- `0x180034e10`
- `0x18003bc70`
- `0x180040bcc`
- `0x180043b20`
- `0x180045a9c`
- `0x180045aec`
- `0x180045b3c`
- `0x1800462dc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009121`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009184`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800094ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800095c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009121`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009184`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800094ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800095c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000904f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000904f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000903f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000903f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800091c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800091c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009020`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000939c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000939c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180009074`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180009074`

## string_xrefs

- `0x180009101`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000914a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009491`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800095fa`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009647`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009683`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800096e2`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009702`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009722`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009751`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000955a`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180009598`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x1800096ab`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x1800090eb`: `onecore\ds\security\gina\profile\profsvc\profmgr.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserProfile::Unload(CUserProfile *this, HANDLE hToken, void *a3, DWORD a4)
{
  int InfoFromRegistry; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v11; // r9
  __int64 v12; // rcx
  char v13; // si
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v18; // rcx
  const char *v19; // r9
  HANDLE v20; // rcx
  int v21; // ebx
  unsigned int v22; // r8d
  int v23; // edx
  int v24; // ecx
  int v25; // eax
  int v26; // eax
  CUserProfileManager *v27; // rcx
  int RegKeyHandlesForUser; // eax
  __int64 v29; // rcx
  int v30; // ebx
  unsigned int v31; // ecx
  unsigned int v32; // ebx
  int v33; // eax
  unsigned int v34; // r14d
  int v35; // eax
  int ExclusionListFromRegistry; // eax
  CUserProfile *v37; // rcx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  char v42; // bl
  int v43; // eax
  __int64 v44; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  _BYTE v46[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Token; // [rsp+50h] [rbp-B0h] BYREF
  char v51; // [rsp+58h] [rbp-A8h]
  _QWORD v52[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  void **v55; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v56[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v57[192]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v58[32]; // [rsp+170h] [rbp+70h] BYREF
  _DWORD *v59; // [rsp+190h] [rbp+90h]
  _DWORD *v60; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v61[48]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v55,
    "CUserProfile_Unload");
  v55 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
  ProfileTelemetry::CUserProfile_Unload::StartActivity((ProfileTelemetry::CUserProfile_Unload *)&v55);
  Token = 0;
  v51 = 0;
  InfoFromRegistry = -2147467259;
  if ( !hToken )
    goto LABEL_14;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    InfoFromRegistry = LastError;
    if ( LastError > 0 )
      InfoFromRegistry = (unsigned __int16)LastError | 0x80070000;
    if ( InfoFromRegistry != -2147023888 && InfoFromRegistry < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        (const char *)(unsigned int)InfoFromRegistry,
        phkResult);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_13:
      v51 = 0;
LABEL_14:
      v16 = 326;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)InfoFromRegistry,
        phkResult);
LABEL_16:
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&Token);
      v55 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v55);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v55);
      return (unsigned int)InfoFromRegistry;
    }
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    Token = TokenHandle;
  }
  else
  {
    InfoFromRegistry = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x2D,
                         (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                         v11);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( InfoFromRegistry < 0 )
      goto LABEL_13;
  }
  v51 = 1;
  InfoFromRegistry = CUserProfile::Initialize(this, (WCHAR *)hToken, a3, 0, a4, 0);
  if ( InfoFromRegistry < 0 )
  {
    v16 = 329;
    goto LABEL_15;
  }
  v13 = 0;
  v46[0] = 0;
  TokenHandle = 0;
  v14 = CUserProfileManager::EnterLock(v12, *((_WORD **)this + 6), (RTL_SRWLOCK **)&TokenHandle);
  InfoFromRegistry = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.h",
      (const char *)(unsigned int)v14,
      phkResult);
    v15 = 335;
    goto LABEL_11;
  }
  InfoFromRegistry = CUserProfile::LoadInfoFromRegistry(this);
  if ( InfoFromRegistry < 0 )
  {
    v15 = 338;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)InfoFromRegistry,
      phkResult);
    if ( TokenHandle )
      ReleaseSRWLockExclusive((PSRWLOCK)TokenHandle);
    goto LABEL_16;
  }
  LODWORD(hKey) = 0;
  InfoFromRegistry = CUserProfile::DecrementRefCount(this, (unsigned int *)&hKey);
  if ( InfoFromRegistry < 0 )
  {
    v15 = 342;
    goto LABEL_11;
  }
  v21 = (int)hKey;
  v52[2] = 0;
  v52[0] = *((_QWORD *)this + 6);
  v52[1] = *((_QWORD *)this + 19);
  v22 = *((_DWORD *)this + 3);
  v23 = (v22 >> 7) & 1 | 4;
  if ( (v22 & 1) == 0 )
    v23 = (*((_DWORD *)this + 3) >> 7) & 1;
  v24 = v23 | 4;
  if ( (v22 & 0x10000) == 0 )
    v24 = v23;
  if ( (v22 & 0x18) != 0 )
  {
    v24 |= 2u;
    if ( (v22 & 8) == 0 )
      v24 |= 8u;
  }
  v25 = v24 | 1;
  if ( (v22 & 0x800) == 0 )
    v25 = v24;
  v53 = v25;
  v54 = (int)hKey;
  v26 = SendNotification(64, v52, *((unsigned int *)this + 5));
  if ( v26 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x919,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v26,
      phkResult);
  if ( v21 )
  {
    ProfileTelemetry::CUserProfile_Unload::RefCountDecremented<unsigned long &>(&v55, &hKey);
    goto LABEL_42;
  }
  CUserProfile::NotifyCredMan(this, 0, 0);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_USERS, *((LPCWSTR *)this + 6), 0, 0x20019u, &hKey) )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((char *)this + 200);
    *((_QWORD *)this + 26) = -1;
    *((_QWORD *)this + 27) = -1;
    ExclusionListFromRegistry = GetExclusionListFromRegistry(
                                  hKey,
                                  *((const unsigned __int16 **)this + 6),
                                  (unsigned __int16 **)this + 25);
    if ( ExclusionListFromRegistry < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)ExclusionListFromRegistry,
        phkResult);
    CUserProfile::GetProfileQuotaFromRegistry(v37, hKey, (unsigned __int64 *)this + 35);
  }
  v27 = (CUserProfileManager *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  RegKeyHandlesForUser = CUserProfileManager::RetrieveRegKeyHandlesForUser(
                           v27,
                           *((const unsigned __int16 **)this + 6),
                           (void **)this + 28,
                           (void **)this + 29);
  if ( RegKeyHandlesForUser < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)RegKeyHandlesForUser,
      phkResult);
  LODWORD(hKey) = 0;
  InfoFromRegistry = CUserProfile::UnloadHives(this, (int *)&hKey);
  if ( InfoFromRegistry < 0 )
  {
    v15 = 369;
    goto LABEL_11;
  }
  v49 = 0;
  v29 = *((_QWORD *)this + 36);
  v30 = (int)hKey;
  if ( !v29
    || (v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v29 + 24LL))(
                v29,
                (unsigned int)hKey,
                &v49),
        v34 = v33,
        v33 >= 0) )
  {
    v31 = *((_DWORD *)this + 5);
    if ( v31 != -1 )
      GetUserChoiceForSlowLink(v31, 1);
    if ( v30 )
    {
      v35 = CUserProfile::DeleteTempHive(this);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v35,
          phkResult);
      ProfileTelemetry::CUserProfile_Unload::HiveStillBeingLoadedNoDelete((ProfileTelemetry::CUserProfile_Unload *)&v55);
    }
    else
    {
      v32 = *((_DWORD *)this + 3);
      if ( (v32 & 0x80u) != 0 )
      {
        LODWORD(hKey) = 0;
        if ( (unsigned int)GetMachineRole((int *)&hKey) )
        {
          if ( (_DWORD)hKey )
          {
            ProfileTelemetry::CUserProfile_Unload::DeletingGuestProfile((ProfileTelemetry::CUserProfile_Unload *)&v55);
            v38 = DeleteProfileP(*((const unsigned __int16 **)this + 6), 0);
            if ( v38 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x19C,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v38,
                phkResult);
          }
        }
      }
      else if ( (v32 & 0x800) != 0 )
      {
        ProfileTelemetry::CUserProfile_Unload::DeletingTempProfile((ProfileTelemetry::CUserProfile_Unload *)&v55);
        v39 = DeleteProfileLite(
                *((const unsigned __int16 **)this + 6),
                *((WCHAR **)this + 19),
                (v32 >> 13) & 2,
                (DWORD *)a3);
        if ( v39 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1A7,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v39,
            phkResult);
      }
      else if ( (int)Profile::GetLocalSetting(4, v46) >= 0
             && (v13 = v46[0]) != 0
             && (v41 = *((_DWORD *)this + 3), (v41 & 2) == 0)
             && (v49 || (v41 & 0x40001) != 0) )
      {
        ProfileTelemetry::CUserProfile_Unload::DeletingCachedProfile((ProfileTelemetry::CUserProfile_Unload *)&v55);
        v40 = DeleteProfileP(*((const unsigned __int16 **)this + 6), 0);
        if ( v40 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B7,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v40,
            phkResult);
      }
      else
      {
        v13 = 0;
        WriteUnloadTime(*((LPCWCH *)this + 6));
      }
    }
LABEL_42:
    if ( TokenHandle )
      ReleaseSRWLockExclusive((PSRWLOCK)TokenHandle);
    v18 = *((_QWORD *)this + 36);
    if ( v18 )
      (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v18 + 56LL))(v18, v13 != 0);
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v55);
    if ( !v51 )
      goto LABEL_24;
    if ( SetThreadToken(0, Token) )
    {
      v20 = Token;
      if ( !Token )
      {
LABEL_23:
        Token = 0;
        v51 = 0;
LABEL_24:
        v55 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
        if ( !v60 )
          goto LABEL_25;
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          &v55,
          &TokenHandle);
        if ( v60 && *v60 == 1 )
        {
          v42 = 1;
        }
        else
        {
          v42 = 0;
          wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v60);
        }
        if ( TokenHandle )
          ReleaseSRWLockExclusive((PSRWLOCK)TokenHandle);
        if ( v42 )
        {
LABEL_25:
          if ( *v59 == 1 )
          {
            v43 = v59[22];
            v49 = v43;
            v44 = 2147942974LL;
            if ( v43 < 0 )
              v44 = (unsigned int)v43;
            wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
              v59,
              v44,
              &v49);
            wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
              &v55,
              v49);
          }
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v61);
        wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v60);
        wil::details::shared_buffer::reset((wil::details::shared_buffer *)v58);
        wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)v57);
        _TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>::~_TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>(v56);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        v19);
      v20 = Token;
      if ( !Token )
        goto LABEL_23;
    }
    CloseHandle(v20);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x177,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v33,
    phkResult);
  if ( TokenHandle )
    ReleaseSRWLockExclusive((PSRWLOCK)TokenHandle);
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&Token);
  v55 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v55);
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v55);
  return v34;
}

```

## disassembly

```asm
0x180008fa0  mov     [rsp-8+arg_18], rbx
0x180008fa5  push    rbp
0x180008fa6  push    rsi
0x180008fa7  push    rdi
0x180008fa8  push    r12
0x180008faa  push    r13
0x180008fac  push    r14
0x180008fae  push    r15
0x180008fb0  lea     rbp, [rsp-0E0h]
0x180008fb8  sub     rsp, 1E0h
0x180008fbf  mov     rax, cs:__security_cookie
0x180008fc6  xor     rax, rsp
0x180008fc9  mov     [rbp+110h+var_40], rax
0x180008fd0  mov     r14d, r9d
0x180008fd3  mov     r15, r8
0x180008fd6  mov     rsi, rdx
0x180008fd9  mov     rdi, rcx
0x180008fdc  lea     rdx, aCuserprofileUn; "CUserProfile_Unload"
0x180008fe3  lea     rcx, [rbp+110h+var_190]
0x180008fe7  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180008fec  lea     r13, ??_7CUserProfile_Unload@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_Unload::`vftable'
0x180008ff3  mov     [rbp+110h+var_190], r13
0x180008ff7  lea     rcx, [rbp+110h+var_190]; this
0x180008ffb  call    ?StartActivity@CUserProfile_Unload@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_Unload::StartActivity(void)
0x180009000  xor     r12d, r12d
0x180009003  mov     [rsp+210h+Token], r12
0x180009008  mov     [rsp+210h+var_1B8], r12b
0x18000900d  mov     ebx, 80004005h
0x180009012  test    rsi, rsi
0x180009015  jz      loc_180009142
0x18000901b  mov     [rsp+210h+TokenHandle], r12
0x180009020  call    cs:__imp_GetCurrentThread
0x180009027  nop     dword ptr [rax+rax+00h]
0x18000902c  lea     r9, [rsp+210h+TokenHandle]; TokenHandle
0x180009031  mov     edx, 2000Ch; DesiredAccess
0x180009036  mov     r8d, 1; OpenAsSelf
0x18000903c  mov     rcx, rax; ThreadHandle
0x18000903f  call    cs:__imp_OpenThreadToken
0x180009046  nop     dword ptr [rax+rax+00h]
0x18000904b  test    eax, eax
0x18000904d  jnz     short loc_180009071
0x18000904f  call    cs:__imp_GetLastError
0x180009056  nop     dword ptr [rax+rax+00h]
0x18000905b  mov     ebx, eax
0x18000905d  test    eax, eax
0x18000905f  jg      loc_18000912F
0x180009065  cmp     ebx, 800703F0h
0x18000906b  jnz     loc_180009699
0x180009071  mov     rcx, rsi; hToken
0x180009074  call    cs:__imp_ImpersonateLoggedOnUser
0x18000907b  nop     dword ptr [rax+rax+00h]
0x180009080  test    eax, eax
0x180009082  jz      loc_180009553
0x180009088  mov     rax, [rsp+210h+TokenHandle]
0x18000908d  mov     [rsp+210h+Token], rax
0x180009092  mov     [rsp+210h+var_1B8], 1
0x180009097  mov     [rsp+210h+var_1E8], r12; unsigned __int16 *
0x18000909c  mov     dword ptr [rsp+210h+phkResult], r14d; int
0x1800090a1  xor     r9d, r9d; struct _PROFILEINFOW *
0x1800090a4  mov     r8, r15; void *
0x1800090a7  mov     rdx, rsi; void *
0x1800090aa  mov     rcx, rdi; this
0x1800090ad  call    ?Initialize@CUserProfile@@IEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z; CUserProfile::Initialize(void *,void *,_PROFILEINFOW *,ulong,ushort const *)
0x1800090b2  mov     ebx, eax
0x1800090b4  test    eax, eax
0x1800090b6  js      loc_1800096CB
0x1800090bc  xor     sil, sil
0x1800090bf  mov     [rsp+210h+var_1E0], sil
0x1800090c4  mov     [rsp+210h+TokenHandle], r12
0x1800090c9  lea     r8, [rsp+210h+TokenHandle]
0x1800090ce  mov     rdx, [rdi+30h]
0x1800090d2  call    ?EnterLock@CUserProfileManager@@QEAAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CUserProfileManager::EnterLock(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &)
0x1800090d7  mov     ebx, eax
0x1800090d9  test    eax, eax
0x1800090db  jns     loc_18000927E
0x1800090e1  mov     rcx, [rbp+118h]; this
0x1800090e8  mov     r9d, eax; char *
0x1800090eb  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800090f2  mov     edx, 0B4h; void *
0x1800090f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090fc  mov     edx, 14Fh; void *
0x180009101  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009108  mov     r9d, ebx; char *
0x18000910b  mov     rcx, [rbp+118h]; this
0x180009112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009117  mov     rcx, [rsp+210h+TokenHandle]; SRWLock
0x18000911c  test    rcx, rcx
0x18000911f  jz      short loc_18000915D
0x180009121  call    cs:__imp_ReleaseSRWLockExclusive
0x180009128  nop     dword ptr [rax+rax+00h]
0x18000912d  jmp     short loc_18000915D
0x18000912f  movzx   ebx, ax
0x180009132  or      ebx, 80070000h
0x180009138  jmp     loc_180009065
0x18000913d  mov     [rsp+210h+var_1B8], r12b
0x180009142  mov     edx, 146h; void *
0x180009147  mov     r9d, ebx; char *
0x18000914a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009151  mov     rcx, [rbp+118h]; this
0x180009158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000915d  lea     rcx, [rsp+210h+Token]; this
0x180009162  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180009167  mov     [rbp+110h+var_190], r13
0x18000916b  lea     rcx, [rbp+110h+var_190]
0x18000916f  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180009174  lea     rcx, [rbp+110h+var_190]
0x180009178  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000917d  mov     eax, ebx
0x18000917f  jmp     loc_180009253
0x180009184  call    cs:__imp_ReleaseSRWLockExclusive
0x18000918b  nop     dword ptr [rax+rax+00h]
0x180009190  mov     rcx, [rdi+120h]
0x180009197  test    rcx, rcx
0x18000919a  jz      short loc_1800091B1
0x18000919c  mov     rax, [rcx]
0x18000919f  mov     edx, r12d
0x1800091a2  test    sil, sil
0x1800091a5  setnz   dl
0x1800091a8  mov     rax, [rax+38h]
0x1800091ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b1  lea     rcx, [rbp+110h+var_190]
0x1800091b5  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800091ba  cmp     [rsp+210h+var_1B8], 0
0x1800091bf  jz      short loc_1800091FC
0x1800091c1  mov     rdx, [rsp+210h+Token]; Token
0x1800091c6  xor     ecx, ecx; Thread
0x1800091c8  call    cs:__imp_SetThreadToken
0x1800091cf  nop     dword ptr [rax+rax+00h]
0x1800091d4  test    eax, eax
0x1800091d6  jz      loc_180009591
0x1800091dc  mov     rcx, [rsp+210h+Token]; hObject
0x1800091e1  test    rcx, rcx
0x1800091e4  jz      short loc_1800091F2
0x1800091e6  call    cs:__imp_CloseHandle
0x1800091ed  nop     dword ptr [rax+rax+00h]
0x1800091f2  mov     [rsp+210h+Token], r12
0x1800091f7  mov     [rsp+210h+var_1B8], 0
0x1800091fc  mov     [rbp+110h+var_190], r13
0x180009200  cmp     [rbp+110h+var_78], 0
0x180009208  jnz     loc_1800097C2
0x18000920e  mov     rcx, [rbp+110h+var_80]
0x180009215  cmp     dword ptr [rcx], 1
0x180009218  jz      loc_1800097FB
0x18000921e  lea     rcx, [rbp+110h+var_70]; this
0x180009225  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000922a  lea     rcx, [rbp+110h+var_78]
0x180009231  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180009236  lea     rcx, [rbp+110h+var_A0]; this
0x18000923a  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000923f  lea     rcx, [rbp+110h+var_160]; this
0x180009243  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x180009248  lea     rcx, [rbp+110h+var_188]
0x18000924c  call    ??1?$_TlgActivityBase@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0A@$03@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>::~_TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>(void)
0x180009251  xor     eax, eax
0x180009253  mov     rcx, [rbp+110h+var_40]
0x18000925a  xor     rcx, rsp; StackCookie
0x18000925d  call    __security_check_cookie
0x180009262  mov     rbx, [rsp+210h+arg_18]
0x18000926a  add     rsp, 1E0h
0x180009271  pop     r15
0x180009273  pop     r14
0x180009275  pop     r13
0x180009277  pop     r12
0x180009279  pop     rdi
0x18000927a  pop     rsi
0x18000927b  pop     rbp
0x18000927c  retn
0x18000927e  mov     rcx, rdi; this
0x180009281  call    ?LoadInfoFromRegistry@CUserProfile@@IEAAJXZ; CUserProfile::LoadInfoFromRegistry(void)
0x180009286  mov     ebx, eax
0x180009288  test    eax, eax
0x18000928a  js      loc_1800096D5
0x180009290  mov     dword ptr [rsp+210h+hKey], r12d
0x180009295  lea     rdx, [rsp+210h+hKey]; unsigned int *
0x18000929a  mov     rcx, rdi; this
0x18000929d  call    ?DecrementRefCount@CUserProfile@@IEAAJPEAK@Z; CUserProfile::DecrementRefCount(ulong *)
0x1800092a2  mov     ebx, eax
0x1800092a4  test    eax, eax
0x1800092a6  js      loc_180009362
0x1800092ac  mov     ebx, dword ptr [rsp+210h+hKey]
0x1800092b0  mov     [rsp+210h+var_1A0], r12
0x1800092b5  mov     rax, [rdi+30h]
0x1800092b9  mov     [rsp+210h+var_1B0], rax
0x1800092be  mov     rax, [rdi+98h]
0x1800092c5  mov     [rsp+210h+var_1A8], rax
0x1800092ca  mov     r8d, [rdi+0Ch]
0x1800092ce  mov     ecx, r8d
0x1800092d1  shr     ecx, 7
0x1800092d4  and     ecx, 1
0x1800092d7  mov     edx, ecx
0x1800092d9  or      edx, 4
0x1800092dc  test    r8b, 1
0x1800092e0  cmovz   edx, ecx
0x1800092e3  mov     ecx, edx
0x1800092e5  or      ecx, 4
0x1800092e8  bt      r8d, 10h
0x1800092ed  cmovnb  ecx, edx
0x1800092f0  test    r8b, 18h
0x1800092f4  jz      short loc_180009302
0x1800092f6  or      ecx, 2
0x1800092f9  test    r8b, 8
0x1800092fd  jnz     short loc_180009302
0x1800092ff  or      ecx, 8
0x180009302  mov     eax, ecx
0x180009304  or      eax, 1
0x180009307  bt      r8d, 0Bh
0x18000930c  cmovnb  eax, ecx
0x18000930f  mov     [rsp+210h+var_198], eax
0x180009313  mov     [rsp+210h+var_194], ebx
0x180009317  mov     r9, [rdi+18h]
0x18000931b  mov     r8d, [rdi+14h]
0x18000931f  lea     rdx, [rsp+210h+var_1B0]
0x180009324  mov     ecx, 40h ; '@'
0x180009329  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x18000932e  mov     rcx, [rbp+118h]; this
0x180009335  test    eax, eax
0x180009337  js      loc_1800096DF
0x18000933d  test    ebx, ebx
0x18000933f  jz      short loc_18000936C
0x180009341  lea     rdx, [rsp+210h+hKey]
0x180009346  lea     rcx, [rbp+110h+var_190]
0x18000934a  call    ??$RefCountDecremented@AEAK@CUserProfile_Unload@ProfileTelemetry@@QEAAXAEAK@Z; ProfileTelemetry::CUserProfile_Unload::RefCountDecremented<ulong &>(ulong &)
0x18000934f  mov     rcx, [rsp+210h+TokenHandle]; SRWLock
0x180009354  test    rcx, rcx
0x180009357  jz      loc_180009190
0x18000935d  jmp     loc_180009184
0x180009362  mov     edx, 156h
0x180009367  jmp     loc_180009101
0x18000936c  xor     r8d, r8d; int
0x18000936f  xor     edx, edx; int
0x180009371  mov     rcx, rdi; this
0x180009374  call    ?NotifyCredMan@CUserProfile@@IEAAXHH@Z; CUserProfile::NotifyCredMan(int,int)
0x180009379  mov     [rsp+210h+hKey], r12
0x18000937e  lea     rax, [rsp+210h+hKey]
0x180009383  mov     [rsp+210h+phkResult], rax; int
0x180009388  mov     r9d, 20019h; samDesired
0x18000938e  xor     r8d, r8d; ulOptions
0x180009391  mov     rdx, [rdi+30h]; lpSubKey
0x180009395  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000939c  call    cs:__imp_RegOpenKeyExW
0x1800093a3  nop     dword ptr [rax+rax+00h]
0x1800093a8  test    eax, eax
0x1800093aa  jz      loc_1800094FE
0x1800093b0  mov     rcx, [rsp+210h+hKey]; hKey
0x1800093b5  test    rcx, rcx
0x1800093b8  jz      short loc_1800093C6
0x1800093ba  call    cs:__imp_RegCloseKey
0x1800093c1  nop     dword ptr [rax+rax+00h]
0x1800093c6  lea     r9, [rdi+0E8h]; void **
0x1800093cd  lea     r8, [rdi+0E0h]; void **
0x1800093d4  mov     rdx, [rdi+30h]; unsigned __int16 *
0x1800093d8  call    ?RetrieveRegKeyHandlesForUser@CUserProfileManager@@QEAAJPEBGPEAPEAX1@Z; CUserProfileManager::RetrieveRegKeyHandlesForUser(ushort const *,void * *,void * *)
0x1800093dd  test    eax, eax
0x1800093df  js      loc_180009718
0x1800093e5  mov     dword ptr [rsp+210h+hKey], r12d
0x1800093ea  lea     rdx, [rsp+210h+hKey]; int *
0x1800093ef  mov     rcx, rdi; this
0x1800093f2  call    ?UnloadHives@CUserProfile@@IEAAJPEAH@Z; CUserProfile::UnloadHives(int *)
0x1800093f7  mov     ebx, eax
0x1800093f9  test    eax, eax
0x1800093fb  js      short loc_180009463
0x1800093fd  mov     [rsp+210h+var_1C8], r12d
0x180009402  mov     rcx, [rdi+120h]
0x180009409  mov     ebx, dword ptr [rsp+210h+hKey]
0x18000940d  test    rcx, rcx
0x180009410  jnz     short loc_18000946D
0x180009412  mov     ecx, [rdi+14h]; unsigned int
0x180009415  cmp     ecx, 0FFFFFFFFh
0x180009418  jnz     loc_180009738
0x18000941e  test    ebx, ebx
0x180009420  jnz     loc_1800094E0
0x180009426  mov     ebx, [rdi+0Ch]
0x180009429  test    bl, bl
0x18000942b  js      loc_180009767
0x180009431  bt      ebx, 0Bh
0x180009435  jb      loc_180009610
0x18000943b  lea     rdx, [rsp+210h+var_1E0]
0x180009440  mov     ecx, 4
0x180009445  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x18000944a  test    eax, eax
0x18000944c  jns     loc_18000978E
0x180009452  xor     sil, sil
0x180009455  mov     rcx, [rdi+30h]; lpString1
0x180009459  call    ?WriteUnloadTime@@YAJPEBG@Z; WriteUnloadTime(ushort const *)
0x18000945e  jmp     loc_18000934F
0x180009463  mov     edx, 171h
0x180009468  jmp     loc_180009101
0x18000946d  mov     rax, [rcx]
0x180009470  lea     r8, [rsp+210h+var_1C8]
0x180009475  mov     edx, ebx
0x180009477  mov     rax, [rax+18h]
0x18000947b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009480  mov     r14d, eax
0x180009483  test    eax, eax
0x180009485  jns     short loc_180009412
0x180009487  mov     rcx, [rbp+118h]; this
0x18000948e  mov     r9d, eax; char *
0x180009491  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009498  mov     edx, 177h; void *
0x18000949d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
