# CUserProfile::IssueTempProfile(void)

- ea: `0x18002e1dc`
- end: `0x18002e634`
- name: `?IssueTempProfile@CUserProfile@@IEAAJXZ`
- size: `1112`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ef18`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x180012ca0`
- `0x1800130d0`
- `0x180013770`
- `0x18001378c`
- `0x18001c358`
- `0x180024cb0`
- `0x180026c7c`
- `0x18002e1dc`
- `0x18002f6e8`
- `0x180030008`
- `0x180030ad0`
- `0x180030af8`
- `0x180031060`
- `0x180033928`
- `0x180033d80`
- `0x180033e98`
- `0x180035860`
- `0x18003b0c4`
- `0x18003bc70`
- `0x180040bcc`
- `0x180042880`
- `0x180045750`
- `0x1800478a8`
- `0x180049e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e46c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e46c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e534`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e534`

## string_xrefs

- `0x18002e2cd`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e321`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e34c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e408`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e486`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e54a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e5cb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e264`: `LITELOAD specified, cannot issue temp profile.`
- `0x18002e296`: `Temp profiles disabled, cannot issue temp profile.`
- `0x18002e2ad`: `Mandatory or super mandatory profile specified, cannot issue temp profile.`

## pseudocode

```c
__int64 __fastcall CUserProfile::IssueTempProfile(CUserProfile *this)
{
  char v2; // si
  __int64 v3; // rcx
  const char *v4; // rax
  __int64 v5; // rdx
  DWORD LocalProfileImage; // ebx
  const unsigned __int16 *v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int ProfileListKeyNameFromSid; // eax
  unsigned int v13; // eax
  void *v14; // rdx
  const wchar_t **v15; // rax
  __int64 v16; // rcx
  const wchar_t *v17; // r8
  int v18; // ecx
  int v19; // r8d
  int v20; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  _BYTE v25[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  __int128 v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+C0h] [rbp-40h]
  __int128 v39; // [rsp+C8h] [rbp-38h]
  _QWORD v40[42]; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL hMem[2]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v2 = 0;
  LODWORD(phkResult) = 0;
  wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &ProfileTelemetry::IssueTempProfile::`vftable';
  ProfileTelemetry::IssueTempProfile::StartActivity((ProfileTelemetry::IssueTempProfile *)v40);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (byte_1800828C1 & 1) != 0 )
  {
    McTemplateU0z_EtwEventWriteTransfer(v3, EVENT_ISSUE_TEMP_PROFILE, *((_QWORD *)this + 6));
  }
  if ( (*((_BYTE *)this + 8) & 4) != 0 )
  {
    v4 = "LITELOAD specified, cannot issue temp profile.";
    v5 = 2118;
LABEL_11:
    LocalProfileImage = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)0x80004005LL,
      (int)v4,
      samDesired);
    goto LABEL_43;
  }
  v25[0] = 0;
  Profile::GetLocalSetting(3, v25);
  if ( (*((_DWORD *)this + 3) & 0x100) == 0 && v25[0] )
  {
    v4 = "Temp profiles disabled, cannot issue temp profile.";
    v5 = 2126;
    goto LABEL_11;
  }
  if ( (*((_DWORD *)this + 3) & 0x40001) != 0 )
  {
    v4 = "Mandatory or super mandatory profile specified, cannot issue temp profile.";
    v5 = 2129;
    goto LABEL_11;
  }
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 6);
  if ( (*((_DWORD *)this + 3) & 0x804) != 0 )
  {
    if ( !(unsigned int)IsProfileInUse(v7) )
    {
      v8 = DeleteProfileLite(*((const unsigned __int16 **)this + 6), *((WCHAR **)this + 19), 0, *((DWORD **)this + 3));
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x85B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v8,
          dwOptions);
    }
  }
  else
  {
    v9 = BackupProfileListEntry(v7);
    LocalProfileImage = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x860,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v9,
        dwOptions);
      goto LABEL_43;
    }
    *((_DWORD *)this + 3) |= 0x4000u;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    if ( CThreadContext::ImpersonateUser((CThreadContext *)&v35, *((void **)this + 3)) >= 0
      && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(v10, (unsigned int)EVENT_PROFILE_DIR_BACKEDUP, v11, 1, (__int64)hMem);
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v35);
  }
  lpSubKey = 0;
  v28 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v28 = -1;
  v29 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(*((LPCWCH *)this + 6), (unsigned __int16 **)&lpSubKey, 0);
  LocalProfileImage = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    if ( v13 )
    {
      LocalProfileImage = wil::details::in1diag3::Return_Win32(
                            retaddr,
                            (void *)0x86F,
                            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                            (const char *)v13,
                            dwOptionsa);
    }
    else
    {
      LocalProfileImage = CUserProfile::CreateLocalProfileImage(this, phkResult, L"TEMP");
      v14 = (void *)*((_QWORD *)this + 3);
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      if ( (LocalProfileImage & 0x80000000) == 0 )
      {
        *((_DWORD *)this + 3) = *((_DWORD *)this + 3) & 0xFFFFD7FB | 0x804;
        if ( CThreadContext::ImpersonateUser((CThreadContext *)&v30, v14) >= 0
          && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
        {
          McGenEventWrite_EtwEventWriteTransfer(v18, (unsigned int)EVENT_TEMPPROFILEASSIGNED, v19, 1, (__int64)hMem);
        }
        CThreadContext::~CThreadContext((CThreadContext *)&v30);
        v20 = CUserProfile::IssueDefaultProfile(this);
        LocalProfileImage = v20;
        if ( v20 >= 0 )
        {
          wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v40);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
          LocalProfileImage = 0;
          goto LABEL_43;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x88C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v20,
          dwOptionsa);
      }
      else
      {
        if ( CThreadContext::ImpersonateUser((CThreadContext *)&v30, v14) >= 0 )
        {
          if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
          {
            v15 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)hMem, LocalProfileImage);
            v17 = L"???";
            if ( *v15 )
              v17 = *v15;
            McTemplateU0z_EtwEventWriteTransfer(v16, EVENT_TEMP_DIR_FAILED, v17);
            v2 = 1;
          }
          if ( (v2 & 1) != 0 )
            LocalFree(hMem[0]);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x879,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)LocalProfileImage,
          dwOptionsa);
        CThreadContext::~CThreadContext((CThreadContext *)&v30);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      dwOptions);
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
LABEL_43:
  ProfileTelemetry::IssueTempProfile::~IssueTempProfile((ProfileTelemetry::IssueTempProfile *)v40);
  return LocalProfileImage;
}

```

## disassembly

```asm
0x18002e1dc  mov     [rsp-8+arg_8], rbx
0x18002e1e1  mov     [rsp-8+arg_10], rsi
0x18002e1e6  push    rbp
0x18002e1e7  push    rdi
0x18002e1e8  push    r14
0x18002e1ea  lea     rbp, [rsp-150h]
0x18002e1f2  sub     rsp, 250h
0x18002e1f9  mov     rax, cs:__security_cookie
0x18002e200  xor     rax, rsp
0x18002e203  mov     [rbp+160h+var_20], rax
0x18002e20a  mov     rdi, rcx
0x18002e20d  xor     r14d, r14d
0x18002e210  mov     esi, r14d
0x18002e213  mov     dword ptr [rsp+260h+var_208], r14d
0x18002e218  lea     rcx, [rbp+160h+var_180]; struct wil::details::IFailureCallback *
0x18002e21c  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002e221  lea     rax, ??_7IssueTempProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::IssueTempProfile::`vftable'
0x18002e228  mov     [rbp+160h+var_180], rax
0x18002e22c  lea     rcx, [rbp+160h+var_180]; this
0x18002e230  call    ?StartActivity@IssueTempProfile@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::IssueTempProfile::StartActivity(void)
0x18002e235  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18002e23c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18002e241  test    al, al
0x18002e243  jz      short loc_18002E25E
0x18002e245  test    cs:byte_1800828C1, 1
0x18002e24c  jz      short loc_18002E25E
0x18002e24e  mov     r8, [rdi+30h]
0x18002e252  lea     rdx, EVENT_ISSUE_TEMP_PROFILE
0x18002e259  call    McTemplateU0z_EtwEventWriteTransfer
0x18002e25e  test    byte ptr [rdi+8], 4
0x18002e262  jz      short loc_18002E272
0x18002e264  lea     rax, aLiteloadSpecif; "LITELOAD specified, cannot issue temp p"...
0x18002e26b  mov     edx, 846h
0x18002e270  jmp     short loc_18002E2B9
0x18002e272  mov     [rsp+260h+var_210], r14b
0x18002e277  lea     rdx, [rsp+260h+var_210]
0x18002e27c  mov     ecx, 3
0x18002e281  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x18002e286  test    dword ptr [rdi+0Ch], 100h
0x18002e28d  jnz     short loc_18002E2A4
0x18002e28f  cmp     [rsp+260h+var_210], r14b
0x18002e294  jz      short loc_18002E2A4
0x18002e296  lea     rax, aTempProfilesDi; "Temp profiles disabled, cannot issue te"...
0x18002e29d  mov     edx, 84Eh
0x18002e2a2  jmp     short loc_18002E2B9
0x18002e2a4  test    dword ptr [rdi+0Ch], 40001h
0x18002e2ab  jz      short loc_18002E2DE
0x18002e2ad  lea     rax, aMandatoryOrSup; "Mandatory or super mandatory profile sp"...
0x18002e2b4  mov     edx, 851h; void *
0x18002e2b9  mov     ebx, 80004005h
0x18002e2be  mov     rcx, [rbp+168h]; this
0x18002e2c5  mov     qword ptr [rsp+260h+dwOptions], rax; int
0x18002e2ca  mov     r9d, ebx; char *
0x18002e2cd  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e2d4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002e2d9  jmp     loc_18002E601
0x18002e2de  mov     rcx, [rdi+30h]; lpString1
0x18002e2e2  test    dword ptr [rdi+0Ch], 804h
0x18002e2e9  jz      short loc_18002E337
0x18002e2eb  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002e2f0  test    eax, eax
0x18002e2f2  jnz     loc_18002E3C0
0x18002e2f8  mov     r9, [rdi+18h]
0x18002e2fc  xor     r8d, r8d
0x18002e2ff  mov     rdx, [rdi+98h]
0x18002e306  mov     rcx, [rdi+30h]
0x18002e30a  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x18002e30f  test    eax, eax
0x18002e311  jns     loc_18002E3C0
0x18002e317  mov     rcx, [rbp+168h]; this
0x18002e31e  mov     r9d, eax; char *
0x18002e321  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e328  mov     edx, 85Bh; void *
0x18002e32d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e332  jmp     loc_18002E3C0
0x18002e337  call    ?BackupProfileListEntry@@YAJPEBG@Z; BackupProfileListEntry(ushort const *)
0x18002e33c  mov     ebx, eax
0x18002e33e  test    eax, eax
0x18002e340  jns     short loc_18002E362
0x18002e342  mov     rcx, [rbp+168h]; this
0x18002e349  mov     r9d, eax; char *
0x18002e34c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e353  mov     edx, 860h; void *
0x18002e358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e35d  jmp     loc_18002E601
0x18002e362  bts     dword ptr [rdi+0Ch], 0Eh
0x18002e367  mov     [rbp+160h+var_1B8], r14d
0x18002e36b  mov     [rbp+160h+var_1B0], r14
0x18002e36f  mov     [rbp+160h+var_1A8], r14
0x18002e373  mov     [rbp+160h+var_1A0], r14d
0x18002e377  xorps   xmm0, xmm0
0x18002e37a  movdqu  [rbp+160h+var_198], xmm0
0x18002e37f  mov     rdx, [rdi+18h]; void *
0x18002e383  lea     rcx, [rbp+160h+var_1B8]; this
0x18002e387  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18002e38c  test    eax, eax
0x18002e38e  js      short loc_18002E3B7
0x18002e390  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18002e397  jz      short loc_18002E3B7
0x18002e399  lea     rax, [rbp+160h+hMem]
0x18002e3a0  mov     qword ptr [rsp+260h+dwOptions], rax; int
0x18002e3a5  mov     r9d, 1
0x18002e3ab  lea     rdx, EVENT_PROFILE_DIR_BACKEDUP
0x18002e3b2  call    McGenEventWrite_EtwEventWriteTransfer
0x18002e3b7  lea     rcx, [rbp+160h+var_1B8]; this
0x18002e3bb  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18002e3c0  mov     [rsp+260h+lpSubKey], r14
0x18002e3c5  mov     [rsp+260h+var_1F8], r14
0x18002e3ca  mov     [rsp+260h+var_1F0], r14
0x18002e3cf  lea     rcx, [rsp+260h+lpSubKey]
0x18002e3d4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002e3d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e3dd  mov     [rsp+260h+var_1F8], rax
0x18002e3e2  mov     [rsp+260h+var_1F0], rax
0x18002e3e7  xor     r8d, r8d; int *
0x18002e3ea  lea     rdx, [rsp+260h+lpSubKey]; unsigned __int16 **
0x18002e3ef  mov     rcx, [rdi+30h]; lpString1
0x18002e3f3  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002e3f8  mov     ebx, eax
0x18002e3fa  test    eax, eax
0x18002e3fc  jns     short loc_18002E428
0x18002e3fe  mov     rcx, [rbp+168h]; this
0x18002e405  mov     r9d, eax; char *
0x18002e408  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e40f  mov     edx, 86Ch; void *
0x18002e414  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e419  lea     rcx, [rsp+260h+lpSubKey]
0x18002e41e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002e423  jmp     loc_18002E601
0x18002e428  mov     [rsp+260h+var_208], r14
0x18002e42d  xor     edx, edx
0x18002e42f  lea     rcx, [rsp+260h+var_208]
0x18002e434  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002e439  mov     [rsp+260h+lpdwDisposition], r14; lpdwDisposition
0x18002e43e  lea     rax, [rsp+260h+var_208]
0x18002e443  mov     [rsp+260h+phkResult], rax; phkResult
0x18002e448  mov     [rsp+260h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002e44d  mov     dword ptr [rsp+260h+samDesired], 2001Fh; samDesired
0x18002e455  mov     [rsp+260h+dwOptions], r14d; int
0x18002e45a  xor     r9d, r9d; lpClass
0x18002e45d  xor     r8d, r8d; Reserved
0x18002e460  mov     rdx, [rsp+260h+lpSubKey]; lpSubKey
0x18002e465  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e46c  call    cs:__imp_RegCreateKeyExW
0x18002e473  nop     dword ptr [rax+rax+00h]
0x18002e478  test    eax, eax
0x18002e47a  jz      short loc_18002E4A8
0x18002e47c  mov     rcx, [rbp+168h]; this
0x18002e483  mov     r9d, eax; char *
0x18002e486  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e48d  mov     edx, 86Fh; void *
0x18002e492  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e497  mov     ebx, eax
0x18002e499  lea     rcx, [rsp+260h+var_208]
0x18002e49e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002e4a3  jmp     loc_18002E419
0x18002e4a8  lea     r8, aTemp; "TEMP"
0x18002e4af  mov     rdx, [rsp+260h+var_208]; HKEY
0x18002e4b4  mov     rcx, rdi; this
0x18002e4b7  call    ?CreateLocalProfileImage@CUserProfile@@IEAAJPEAUHKEY__@@PEBG@Z; CUserProfile::CreateLocalProfileImage(HKEY__ *,ushort const *)
0x18002e4bc  mov     ebx, eax
0x18002e4be  mov     rdx, [rdi+18h]; void *
0x18002e4c2  mov     [rsp+260h+var_1E8], r14d
0x18002e4c7  mov     [rbp+160h+var_1E0], r14
0x18002e4cb  mov     [rbp+160h+var_1D8], r14
0x18002e4cf  mov     [rbp+160h+var_1D0], r14d
0x18002e4d3  xorps   xmm0, xmm0
0x18002e4d6  lea     rcx, [rsp+260h+var_1E8]; this
0x18002e4db  movdqu  [rbp+160h+var_1C8], xmm0
0x18002e4e0  test    eax, eax
0x18002e4e2  jns     loc_18002E56A
0x18002e4e8  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18002e4ed  test    eax, eax
0x18002e4ef  js      short loc_18002E540
0x18002e4f1  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18002e4f8  jz      short loc_18002E527
0x18002e4fa  mov     edx, ebx; dwMessageId
0x18002e4fc  lea     rcx, [rbp+160h+hMem]; lpBuffer
0x18002e503  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18002e508  lea     r8, asc_180063710; "???"
0x18002e50f  cmp     [rax], r14
0x18002e512  cmovnz  r8, [rax]
0x18002e516  lea     rdx, EVENT_TEMP_DIR_FAILED
0x18002e51d  call    McTemplateU0z_EtwEventWriteTransfer
0x18002e522  mov     esi, 1
0x18002e527  test    sil, 1
0x18002e52b  jz      short loc_18002E540
0x18002e52d  mov     rcx, [rbp+160h+hMem]; hMem
0x18002e534  call    cs:__imp_LocalFree
0x18002e53b  nop     dword ptr [rax+rax+00h]
0x18002e540  mov     rcx, [rbp+168h]; this
0x18002e547  mov     r9d, ebx; char *
0x18002e54a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e551  mov     edx, 879h; void *
0x18002e556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e55b  lea     rcx, [rsp+260h+var_1E8]; this
0x18002e560  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18002e565  jmp     loc_18002E499
0x18002e56a  mov     eax, [rdi+0Ch]
0x18002e56d  btr     eax, 0Dh
0x18002e571  or      eax, 804h
0x18002e576  mov     [rdi+0Ch], eax
0x18002e579  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18002e57e  test    eax, eax
0x18002e580  js      short loc_18002E5A9
0x18002e582  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18002e589  jz      short loc_18002E5A9
0x18002e58b  lea     rax, [rbp+160h+hMem]
0x18002e592  mov     qword ptr [rsp+260h+dwOptions], rax; int
0x18002e597  mov     r9d, 1
0x18002e59d  lea     rdx, EVENT_TEMPPROFILEASSIGNED
0x18002e5a4  call    McGenEventWrite_EtwEventWriteTransfer
0x18002e5a9  lea     rcx, [rsp+260h+var_1E8]; this
0x18002e5ae  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18002e5b3  mov     rcx, rdi; this
0x18002e5b6  call    ?IssueDefaultProfile@CUserProfile@@IEAAJXZ; CUserProfile::IssueDefaultProfile(void)
0x18002e5bb  mov     ebx, eax
0x18002e5bd  test    eax, eax
0x18002e5bf  jns     short loc_18002E5E1
0x18002e5c1  mov     rcx, [rbp+168h]; this
0x18002e5c8  mov     r9d, eax; char *
0x18002e5cb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e5d2  mov     edx, 88Ch; void *
0x18002e5d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e5dc  jmp     loc_18002E499
0x18002e5e1  lea     rcx, [rbp+160h+var_180]
0x18002e5e5  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002e5ea  lea     rcx, [rsp+260h+var_208]
0x18002e5ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002e5f4  lea     rcx, [rsp+260h+lpSubKey]
0x18002e5f9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002e5fe  mov     ebx, r14d
0x18002e601  lea     rcx, [rbp+160h+var_180]; this
0x18002e605  call    ??1IssueTempProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::IssueTempProfile::~IssueTempProfile(void)
0x18002e60a  mov     eax, ebx
0x18002e60c  mov     rcx, [rbp+160h+var_20]
0x18002e613  xor     rcx, rsp; StackCookie
0x18002e616  call    __security_check_cookie
0x18002e61b  lea     r11, [rsp+260h+var_10]
0x18002e623  mov     rbx, [r11+28h]
0x18002e627  mov     rsi, [r11+30h]
0x18002e62b  mov     rsp, r11
0x18002e62e  pop     r14
0x18002e630  pop     rdi
0x18002e631  pop     rbp
0x18002e632  retn
```
