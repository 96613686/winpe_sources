# CUserProfile::Unload(void *,void *,ulong)

- ea: `0x18000b540`
- end: `0x18000bdf9`
- name: `?Unload@CUserProfile@@QEAAJPEAX0K@Z`
- size: `2233`
- prototype: `__int64 __fastcall(CUserProfile *this, HANDLE hToken, void *, DWORD)`
- caller_count: `2`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800179fc`
- `0x180018110`

## callees

- `0x180005580`
- `0x180009320`
- `0x18000a2e8`
- `0x18000a320`
- `0x18000a37c`
- `0x18000a428`
- `0x18000a4a0`
- `0x18000a7e8`
- `0x18000a9b8`
- `0x18000a9e0`
- `0x18000aa5c`
- `0x18000aab8`
- `0x18000ab10`
- `0x18000adc0`
- `0x18000ae80`
- `0x18000b4a0`
- `0x18000b540`
- `0x18000be00`
- `0x18000d490`
- `0x1800111a0`
- `0x1800128b0`
- `0x180022780`
- `0x18002356c`
- `0x1800243a0`
- `0x180025134`
- `0x1800254d4`
- `0x180027364`
- `0x1800281a8`
- `0x18002ce38`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002fb04`
- `0x180030624`
- `0x180034794`
- `0x18003a730`
- `0x18003f42c`
- `0x1800420f0`
- `0x180043f9c`
- `0x180043fec`
- `0x18004403c`
- `0x18004439c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b706`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b706`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b5d9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b5d9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b744`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b744`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b5c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b5c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b75c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b75c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b95d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b95d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b975`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000b602`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000b602`

## string_xrefs

- `0x18000b689`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000b6cc`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000b8cd`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ba22`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ba6e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bbcb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bc18`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bc54`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bcb3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bcd3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bcf3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bd22`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000bb31`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000bb6f`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000bc7c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000b673`: `onecore\ds\security\gina\profile\profsvc\profmgr.h`

## pseudocode

```c
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
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // ebx
  unsigned int v24; // r8d
  int v25; // edx
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  RTL_SRWLOCK *v29; // rcx
  CUserProfileManager *v30; // rcx
  int RegKeyHandlesForUser; // eax
  int v32; // eax
  __int64 v33; // rcx
  int v34; // ebx
  unsigned int v35; // ecx
  unsigned int v36; // ebx
  int v37; // eax
  unsigned int v38; // r14d
  int v39; // eax
  int ExclusionListFromRegistry; // eax
  CUserProfile *v41; // rcx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  char v46; // bl
  int v47; // eax
  __int64 v48; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  _BYTE v51[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v54; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Token; // [rsp+50h] [rbp-B0h] BYREF
  char v56; // [rsp+58h] [rbp-A8h]
  _QWORD v57[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  void **v60; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v61[264]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v62; // [rsp+190h] [rbp+90h]
  _DWORD *v63; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v64[48]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v60,
    "CUserProfile_Unload");
  v60 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
  ProfileTelemetry::CUserProfile_Unload::StartActivity((ProfileTelemetry::CUserProfile_Unload *)&v60);
  Token = 0;
  v56 = 0;
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
      v56 = 0;
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
      v60 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v60);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v60);
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
  v56 = 1;
  InfoFromRegistry = CUserProfile::Initialize(this, (WCHAR *)hToken, a3, 0, a4, 0);
  if ( InfoFromRegistry < 0 )
  {
    v16 = 329;
    goto LABEL_15;
  }
  v13 = 0;
  v51[0] = 0;
  TokenHandle = 0;
  v14 = CUserProfileManager::EnterLock(v12, *((_QWORD *)this + 6), &TokenHandle);
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
  v21 = CUserProfile::DecrementRefCount(this, (unsigned int *)&hKey);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v21,
      phkResult);
    v29 = (RTL_SRWLOCK *)TokenHandle;
    if ( !TokenHandle )
    {
LABEL_46:
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&Token);
      v60 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v60);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v64);
      wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v63);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(v61);
      return v22;
    }
LABEL_45:
    ReleaseSRWLockExclusive(v29);
    goto LABEL_46;
  }
  v23 = (int)hKey;
  v57[2] = 0;
  v57[0] = *((_QWORD *)this + 6);
  v57[1] = *((_QWORD *)this + 19);
  v24 = *((_DWORD *)this + 3);
  v25 = (v24 >> 7) & 1 | 4;
  if ( (v24 & 1) == 0 )
    v25 = (*((_DWORD *)this + 3) >> 7) & 1;
  v26 = v25 | 4;
  if ( (v24 & 0x10000) == 0 )
    v26 = v25;
  if ( (v24 & 0x18) != 0 )
  {
    v26 |= 2u;
    if ( (v24 & 8) == 0 )
      v26 |= 8u;
  }
  v27 = v26 | 1;
  if ( (v24 & 0x800) == 0 )
    v27 = v26;
  v58 = v27;
  v59 = (int)hKey;
  v28 = SendNotification(64, v57, *((unsigned int *)this + 5), *((_QWORD *)this + 3));
  if ( v28 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x919,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v28,
      phkResult);
  if ( v23 )
  {
    ProfileTelemetry::CUserProfile_Unload::RefCountDecremented<unsigned long &>(&v60, &hKey);
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
        phkResulta);
    CUserProfile::GetProfileQuotaFromRegistry(v41, hKey, (unsigned __int64 *)this + 35);
  }
  v30 = (CUserProfileManager *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  RegKeyHandlesForUser = CUserProfileManager::RetrieveRegKeyHandlesForUser(
                           v30,
                           *((const unsigned __int16 **)this + 6),
                           (void **)this + 28,
                           (void **)this + 29);
  if ( RegKeyHandlesForUser < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)RegKeyHandlesForUser,
      phkResulta);
  LODWORD(hKey) = 0;
  v32 = CUserProfile::UnloadHives(this, (int *)&hKey);
  v22 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v32,
      phkResulta);
    v29 = (RTL_SRWLOCK *)TokenHandle;
    if ( !TokenHandle )
      goto LABEL_46;
    goto LABEL_45;
  }
  v54 = 0;
  v33 = *((_QWORD *)this + 36);
  v34 = (int)hKey;
  if ( !v33
    || (v37 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v33 + 24LL))(
                v33,
                (unsigned int)hKey,
                &v54),
        v38 = v37,
        v37 >= 0) )
  {
    v35 = *((_DWORD *)this + 5);
    if ( v35 != -1 )
      GetUserChoiceForSlowLink(v35, 1);
    if ( v34 )
    {
      v39 = CUserProfile::DeleteTempHive(this);
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v39,
          phkResulta);
      ProfileTelemetry::CUserProfile_Unload::HiveStillBeingLoadedNoDelete((ProfileTelemetry::CUserProfile_Unload *)&v60);
    }
    else
    {
      v36 = *((_DWORD *)this + 3);
      if ( (v36 & 0x80u) != 0 )
      {
        LODWORD(hKey) = 0;
        if ( (unsigned int)GetMachineRole((int *)&hKey) )
        {
          if ( (_DWORD)hKey )
          {
            ProfileTelemetry::CUserProfile_Unload::DeletingGuestProfile((ProfileTelemetry::CUserProfile_Unload *)&v60);
            v42 = DeleteProfileP(*((const unsigned __int16 **)this + 6), 0);
            if ( v42 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x19C,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v42,
                phkResulta);
          }
        }
      }
      else if ( (v36 & 0x800) != 0 )
      {
        ProfileTelemetry::CUserProfile_Unload::DeletingTempProfile((ProfileTelemetry::CUserProfile_Unload *)&v60);
        v43 = DeleteProfileLite(*((_QWORD *)this + 6), *((_QWORD *)this + 19), (v36 >> 13) & 2, a3);
        if ( v43 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1A7,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v43,
            phkResulta);
      }
      else if ( (int)Profile::GetLocalSetting(4, v51) >= 0
             && (v13 = v51[0]) != 0
             && (v45 = *((_DWORD *)this + 3), (v45 & 2) == 0)
             && (v54 || (v45 & 0x40001) != 0) )
      {
        ProfileTelemetry::CUserProfile_Unload::DeletingCachedProfile((ProfileTelemetry::CUserProfile_Unload *)&v60);
        v44 = DeleteProfileP(*((const unsigned __int16 **)this + 6), 0);
        if ( v44 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B7,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v44,
            phkResulta);
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
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v60);
    if ( !v56 )
      goto LABEL_24;
    if ( SetThreadToken(0, Token) )
    {
      v20 = Token;
      if ( !Token )
      {
LABEL_23:
        Token = 0;
        v56 = 0;
LABEL_24:
        v60 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
        if ( !v63 )
          goto LABEL_25;
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          &v60,
          &TokenHandle);
        if ( v63 && *v63 == 1 )
        {
          v46 = 1;
        }
        else
        {
          v46 = 0;
          wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v63);
        }
        if ( TokenHandle )
          ReleaseSRWLockExclusive((PSRWLOCK)TokenHandle);
        if ( v46 )
        {
LABEL_25:
          if ( *v62 == 1 )
          {
            v47 = v62[22];
            v54 = v47;
            v48 = 2147942974LL;
            if ( v47 < 0 )
              v48 = (unsigned int)v47;
            wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
              v62,
              v48,
              &v54);
            wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
              &v60,
              v54);
          }
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v64);
        wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v63);
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(v61);
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
    (const char *)(unsigned int)v37,
    phkResulta);
  if ( TokenHandle )
    ReleaseSRWLockExclusive((PSRWLOCK)TokenHandle);
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&Token);
  v60 = &ProfileTelemetry::CUserProfile_Unload::`vftable';
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v60);
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v60);
  return v38;
}

```

## disassembly

```asm
0x18000b540  mov     [rsp-8+arg_18], rbx
0x18000b545  push    rbp
0x18000b546  push    rsi
0x18000b547  push    rdi
0x18000b548  push    r12
0x18000b54a  push    r13
0x18000b54c  push    r14
0x18000b54e  push    r15
0x18000b550  lea     rbp, [rsp-0E0h]
0x18000b558  sub     rsp, 1E0h
0x18000b55f  mov     rax, cs:__security_cookie
0x18000b566  xor     rax, rsp
0x18000b569  mov     [rbp+110h+var_40], rax
0x18000b570  mov     r14d, r9d
0x18000b573  mov     r15, r8
0x18000b576  mov     rsi, rdx
0x18000b579  mov     rdi, rcx
0x18000b57c  lea     rdx, aCuserprofileUn; "CUserProfile_Unload"
0x18000b583  lea     rcx, [rbp+110h+var_190]
0x18000b587  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000b58c  lea     r13, ??_7CUserProfile_Unload@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_Unload::`vftable'
0x18000b593  mov     [rbp+110h+var_190], r13
0x18000b597  lea     rcx, [rbp+110h+var_190]; this
0x18000b59b  call    ?StartActivity@CUserProfile_Unload@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_Unload::StartActivity(void)
0x18000b5a0  xor     r12d, r12d
0x18000b5a3  mov     [rsp+210h+Token], r12
0x18000b5a8  mov     [rsp+210h+var_1B8], r12b
0x18000b5ad  mov     ebx, 80004005h
0x18000b5b2  test    rsi, rsi
0x18000b5b5  jz      loc_18000B6C4
0x18000b5bb  mov     [rsp+210h+TokenHandle], r12
0x18000b5c0  call    cs:__imp_GetCurrentThread
0x18000b5c6  lea     r9, [rsp+210h+TokenHandle]; TokenHandle
0x18000b5cb  mov     edx, 2000Ch; DesiredAccess
0x18000b5d0  mov     r8d, 1; OpenAsSelf
0x18000b5d6  mov     rcx, rax; ThreadHandle
0x18000b5d9  call    cs:__imp_OpenThreadToken
0x18000b5df  test    eax, eax
0x18000b5e1  jnz     short loc_18000B5FF
0x18000b5e3  call    cs:__imp_GetLastError
0x18000b5e9  mov     ebx, eax
0x18000b5eb  test    eax, eax
0x18000b5ed  jg      loc_18000B6B1
0x18000b5f3  cmp     ebx, 800703F0h
0x18000b5f9  jnz     loc_18000BC6A
0x18000b5ff  mov     rcx, rsi; hToken
0x18000b602  call    cs:__imp_ImpersonateLoggedOnUser
0x18000b608  test    eax, eax
0x18000b60a  jz      loc_18000BB2A
0x18000b610  mov     rax, [rsp+210h+TokenHandle]
0x18000b615  mov     [rsp+210h+Token], rax
0x18000b61a  mov     [rsp+210h+var_1B8], 1
0x18000b61f  mov     [rsp+210h+var_1E8], r12; unsigned __int16 *
0x18000b624  mov     dword ptr [rsp+210h+phkResult], r14d; int
0x18000b629  xor     r9d, r9d; struct _PROFILEINFOW *
0x18000b62c  mov     r8, r15; void *
0x18000b62f  mov     rdx, rsi; void *
0x18000b632  mov     rcx, rdi; this
0x18000b635  call    ?Initialize@CUserProfile@@IEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z; CUserProfile::Initialize(void *,void *,_PROFILEINFOW *,ulong,ushort const *)
0x18000b63a  mov     ebx, eax
0x18000b63c  test    eax, eax
0x18000b63e  js      loc_18000BC9C
0x18000b644  xor     sil, sil
0x18000b647  mov     [rsp+210h+var_1E0], sil
0x18000b64c  mov     [rsp+210h+TokenHandle], r12
0x18000b651  lea     r8, [rsp+210h+TokenHandle]
0x18000b656  mov     rdx, [rdi+30h]
0x18000b65a  call    ?EnterLock@CUserProfileManager@@QEAAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CUserProfileManager::EnterLock(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &)
0x18000b65f  mov     ebx, eax
0x18000b661  test    eax, eax
0x18000b663  jns     loc_18000B7DB
0x18000b669  mov     rcx, [rbp+118h]; this
0x18000b670  mov     r9d, eax; char *
0x18000b673  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b67a  mov     edx, 0B4h; void *
0x18000b67f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b684  mov     edx, 14Fh; void *
0x18000b689  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b690  mov     r9d, ebx; char *
0x18000b693  mov     rcx, [rbp+118h]; this
0x18000b69a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b69f  mov     rcx, [rsp+210h+TokenHandle]; SRWLock
0x18000b6a4  test    rcx, rcx
0x18000b6a7  jz      short loc_18000B6DF
0x18000b6a9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b6af  jmp     short loc_18000B6DF
0x18000b6b1  movzx   ebx, ax
0x18000b6b4  or      ebx, 80070000h
0x18000b6ba  jmp     loc_18000B5F3
0x18000b6bf  mov     [rsp+210h+var_1B8], r12b
0x18000b6c4  mov     edx, 146h; void *
0x18000b6c9  mov     r9d, ebx; char *
0x18000b6cc  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b6d3  mov     rcx, [rbp+118h]; this
0x18000b6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6df  lea     rcx, [rsp+210h+Token]; this
0x18000b6e4  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18000b6e9  mov     [rbp+110h+var_190], r13
0x18000b6ed  lea     rcx, [rbp+110h+var_190]
0x18000b6f1  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000b6f6  lea     rcx, [rbp+110h+var_190]
0x18000b6fa  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000b6ff  mov     eax, ebx
0x18000b701  jmp     loc_18000B7B1
0x18000b706  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b70c  mov     rcx, [rdi+120h]
0x18000b713  test    rcx, rcx
0x18000b716  jz      short loc_18000B72D
0x18000b718  mov     rax, [rcx]
0x18000b71b  mov     edx, r12d
0x18000b71e  test    sil, sil
0x18000b721  setnz   dl
0x18000b724  mov     rax, [rax+38h]
0x18000b728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b72d  lea     rcx, [rbp+110h+var_190]
0x18000b731  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000b736  cmp     [rsp+210h+var_1B8], 0
0x18000b73b  jz      short loc_18000B76C
0x18000b73d  mov     rdx, [rsp+210h+Token]; Token
0x18000b742  xor     ecx, ecx; Thread
0x18000b744  call    cs:__imp_SetThreadToken
0x18000b74a  test    eax, eax
0x18000b74c  jz      loc_18000BB68
0x18000b752  mov     rcx, [rsp+210h+Token]; hObject
0x18000b757  test    rcx, rcx
0x18000b75a  jz      short loc_18000B762
0x18000b75c  call    cs:__imp_CloseHandle
0x18000b762  mov     [rsp+210h+Token], r12
0x18000b767  mov     [rsp+210h+var_1B8], 0
0x18000b76c  mov     [rbp+110h+var_190], r13
0x18000b770  cmp     [rbp+110h+var_78], 0
0x18000b778  jnz     loc_18000BD93
0x18000b77e  mov     rcx, [rbp+110h+var_80]
0x18000b785  cmp     dword ptr [rcx], 1
0x18000b788  jz      loc_18000BDCC
0x18000b78e  lea     rcx, [rbp+110h+var_70]; this
0x18000b795  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000b79a  lea     rcx, [rbp+110h+var_78]
0x18000b7a1  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000b7a6  lea     rcx, [rbp+110h+var_188]
0x18000b7aa  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000b7af  xor     eax, eax
0x18000b7b1  mov     rcx, [rbp+110h+var_40]
0x18000b7b8  xor     rcx, rsp; StackCookie
0x18000b7bb  call    __security_check_cookie
0x18000b7c0  mov     rbx, [rsp+210h+arg_18]
0x18000b7c8  add     rsp, 1E0h
0x18000b7cf  pop     r15
0x18000b7d1  pop     r14
0x18000b7d3  pop     r13
0x18000b7d5  pop     r12
0x18000b7d7  pop     rdi
0x18000b7d8  pop     rsi
0x18000b7d9  pop     rbp
0x18000b7da  retn
0x18000b7db  mov     rcx, rdi; this
0x18000b7de  call    ?LoadInfoFromRegistry@CUserProfile@@IEAAJXZ; CUserProfile::LoadInfoFromRegistry(void)
0x18000b7e3  mov     ebx, eax
0x18000b7e5  test    eax, eax
0x18000b7e7  js      loc_18000BCA6
0x18000b7ed  mov     dword ptr [rsp+210h+hKey], r12d
0x18000b7f2  lea     rdx, [rsp+210h+hKey]; unsigned int *
0x18000b7f7  mov     rcx, rdi; this
0x18000b7fa  call    ?DecrementRefCount@CUserProfile@@IEAAJPEAK@Z; CUserProfile::DecrementRefCount(ulong *)
0x18000b7ff  mov     ebx, eax
0x18000b801  test    eax, eax
0x18000b803  js      loc_18000B8C3
0x18000b809  mov     ebx, dword ptr [rsp+210h+hKey]
0x18000b80d  mov     [rsp+210h+var_1A0], r12
0x18000b812  mov     rax, [rdi+30h]
0x18000b816  mov     [rsp+210h+var_1B0], rax
0x18000b81b  mov     rax, [rdi+98h]
0x18000b822  mov     [rsp+210h+var_1A8], rax
0x18000b827  mov     r8d, [rdi+0Ch]
0x18000b82b  mov     ecx, r8d
0x18000b82e  shr     ecx, 7
0x18000b831  and     ecx, 1
0x18000b834  mov     edx, ecx
0x18000b836  or      edx, 4
0x18000b839  test    r8b, 1
0x18000b83d  cmovz   edx, ecx
0x18000b840  mov     ecx, edx
0x18000b842  or      ecx, 4
0x18000b845  bt      r8d, 10h
0x18000b84a  cmovnb  ecx, edx
0x18000b84d  test    r8b, 18h
0x18000b851  jz      short loc_18000B85F
0x18000b853  or      ecx, 2
0x18000b856  test    r8b, 8
0x18000b85a  jnz     short loc_18000B85F
0x18000b85c  or      ecx, 8
0x18000b85f  mov     eax, ecx
0x18000b861  or      eax, 1
0x18000b864  bt      r8d, 0Bh
0x18000b869  cmovnb  eax, ecx
0x18000b86c  mov     [rsp+210h+var_198], eax
0x18000b870  mov     [rsp+210h+var_194], ebx
0x18000b874  mov     r9, [rdi+18h]
0x18000b878  mov     r8d, [rdi+14h]
0x18000b87c  lea     rdx, [rsp+210h+var_1B0]
0x18000b881  mov     ecx, 40h ; '@'
0x18000b886  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x18000b88b  mov     rcx, [rbp+118h]; this
0x18000b892  test    eax, eax
0x18000b894  js      loc_18000BCB0
0x18000b89a  test    ebx, ebx
0x18000b89c  jz      loc_18000B92D
0x18000b8a2  lea     rdx, [rsp+210h+hKey]
0x18000b8a7  lea     rcx, [rbp+110h+var_190]
0x18000b8ab  call    ??$RefCountDecremented@AEAK@CUserProfile_Unload@ProfileTelemetry@@QEAAXAEAK@Z; ProfileTelemetry::CUserProfile_Unload::RefCountDecremented<ulong &>(ulong &)
0x18000b8b0  mov     rcx, [rsp+210h+TokenHandle]; SRWLock
0x18000b8b5  test    rcx, rcx
0x18000b8b8  jz      loc_18000B70C
0x18000b8be  jmp     loc_18000B706
0x18000b8c3  mov     rcx, [rbp+118h]; this
0x18000b8ca  mov     r9d, ebx; char *
0x18000b8cd  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b8d4  mov     edx, 156h; void *
0x18000b8d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8de  mov     rcx, [rsp+210h+TokenHandle]; SRWLock
0x18000b8e3  test    rcx, rcx
0x18000b8e6  jz      short loc_18000B8EE
0x18000b8e8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8ee  lea     rcx, [rsp+210h+Token]; this
0x18000b8f3  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18000b8f8  mov     [rbp+110h+var_190], r13
0x18000b8fc  lea     rcx, [rbp+110h+var_190]
0x18000b900  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000b905  lea     rcx, [rbp+110h+var_70]; this
0x18000b90c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000b911  lea     rcx, [rbp+110h+var_78]
0x18000b918  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000b91d  lea     rcx, [rbp+110h+var_188]
0x18000b921  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000b926  mov     eax, ebx
0x18000b928  jmp     loc_18000B7B1
0x18000b92d  xor     r8d, r8d; int
0x18000b930  xor     edx, edx; int
0x18000b932  mov     rcx, rdi; this
0x18000b935  call    ?NotifyCredMan@CUserProfile@@IEAAXHH@Z; CUserProfile::NotifyCredMan(int,int)
0x18000b93a  mov     [rsp+210h+hKey], r12
0x18000b93f  lea     rax, [rsp+210h+hKey]
0x18000b944  mov     [rsp+210h+phkResult], rax; int
0x18000b949  mov     r9d, 20019h; samDesired
0x18000b94f  xor     r8d, r8d; ulOptions
0x18000b952  mov     rdx, [rdi+30h]; lpSubKey
0x18000b956  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000b95d  call    cs:__imp_RegOpenKeyExW
0x18000b963  test    eax, eax
0x18000b965  jz      loc_18000BAD5
0x18000b96b  mov     rcx, [rsp+210h+hKey]; hKey
0x18000b970  test    rcx, rcx
0x18000b973  jz      short loc_18000B97B
0x18000b975  call    cs:__imp_RegCloseKey
0x18000b97b  lea     r9, [rdi+0E8h]; void **
0x18000b982  lea     r8, [rdi+0E0h]; void **
0x18000b989  mov     rdx, [rdi+30h]; unsigned __int16 *
0x18000b98d  call    ?RetrieveRegKeyHandlesForUser@CUserProfileManager@@QEAAJPEBGPEAPEAX1@Z; CUserProfileManager::RetrieveRegKeyHandlesForUser(ushort const *,void * *,void * *)
0x18000b992  test    eax, eax
0x18000b994  js      loc_18000BCE9
0x18000b99a  mov     dword ptr [rsp+210h+hKey], r12d
0x18000b99f  lea     rdx, [rsp+210h+hKey]; int *
0x18000b9a4  mov     rcx, rdi; this
0x18000b9a7  call    ?UnloadHives@CUserProfile@@IEAAJPEAH@Z; CUserProfile::UnloadHives(int *)
0x18000b9ac  mov     ebx, eax
0x18000b9ae  test    eax, eax
0x18000b9b0  js      short loc_18000BA18
0x18000b9b2  mov     [rsp+210h+var_1C8], r12d
0x18000b9b7  mov     rcx, [rdi+120h]
0x18000b9be  mov     ebx, dword ptr [rsp+210h+hKey]
0x18000b9c2  test    rcx, rcx
0x18000b9c5  jnz     short loc_18000BA46
0x18000b9c7  mov     ecx, [rdi+14h]; unsigned int
0x18000b9ca  cmp     ecx, 0FFFFFFFFh
0x18000b9cd  jnz     loc_18000BD09
0x18000b9d3  test    ebx, ebx
0x18000b9d5  jnz     loc_18000BAB7
0x18000b9db  mov     ebx, [rdi+0Ch]
0x18000b9de  test    bl, bl
0x18000b9e0  js      loc_18000BD38
0x18000b9e6  bt      ebx, 0Bh
0x18000b9ea  jb      loc_18000BBE1
0x18000b9f0  lea     rdx, [rsp+210h+var_1E0]
0x18000b9f5  mov     ecx, 4
0x18000b9fa  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x18000b9ff  test    eax, eax
0x18000ba01  jns     loc_18000BD5F
0x18000ba07  xor     sil, sil
0x18000ba0a  mov     rcx, [rdi+30h]; lpString1
0x18000ba0e  call    ?WriteUnloadTime@@YAJPEBG@Z; WriteUnloadTime(ushort const *)
0x18000ba13  jmp     loc_18000B8B0
0x18000ba18  mov     rcx, [rbp+118h]; this
0x18000ba1f  mov     r9d, ebx; char *
0x18000ba22  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ba29  mov     edx, 171h; void *
0x18000ba2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba33  mov     rcx, [rsp+210h+TokenHandle]
0x18000ba38  test    rcx, rcx
0x18000ba3b  jz      loc_18000B8EE
0x18000ba41  jmp     loc_18000B8E8
  ... truncated ...
```
