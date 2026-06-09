# CUserProfile::IssueTempProfile(void)

- ea: `0x180032ce0`
- end: `0x180033137`
- name: `?IssueTempProfile@CUserProfile@@IEAAJXZ`
- size: `1111`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fc50`

## callees

- `0x18000f1b0`
- `0x1800111a0`
- `0x180018bcc`
- `0x18001a8a8`
- `0x18001f060`
- `0x180021ca0`
- `0x1800243a0`
- `0x180026070`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002e648`
- `0x18002f89c`
- `0x18002f8e0`
- `0x18002fb04`
- `0x180032ce0`
- `0x180033140`
- `0x180033308`
- `0x1800336c8`
- `0x1800337dc`
- `0x180039bcc`
- `0x18003a730`
- `0x18003f42c`
- `0x180040e94`
- `0x180043c70`
- `0x180047cbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032fa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800330f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032fa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800330f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032f70`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033038`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033038`

## string_xrefs

- `0x180032dd1`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180032e25`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180032e50`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180032f0c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180032f84`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180033048`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800330c9`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180032d68`: `LITELOAD specified, cannot issue temp profile.`
- `0x180032d9a`: `Temp profiles disabled, cannot issue temp profile.`
- `0x180032db1`: `Mandatory or super mandatory profile specified, cannot issue temp profile.`

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
  bool v25; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  HANDLE v30[3]; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+90h] [rbp-70h]
  __int128 v32; // [rsp+98h] [rbp-68h]
  HANDLE v33[3]; // [rsp+A8h] [rbp-58h] BYREF
  int v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+C8h] [rbp-38h]
  _QWORD v36[42]; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL hMem[2]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v2 = 0;
  LODWORD(hKey) = 0;
  wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v36);
  v36[0] = &ProfileTelemetry::IssueTempProfile::`vftable';
  ProfileTelemetry::IssueTempProfile::StartActivity((ProfileTelemetry::IssueTempProfile *)v36);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (byte_18007F7C1 & 1) != 0 )
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
    goto LABEL_46;
  }
  v25 = 0;
  Profile::GetLocalSetting(3u, &v25);
  if ( (*((_DWORD *)this + 3) & 0x100) == 0 && v25 )
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
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v8);
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
      goto LABEL_46;
    }
    *((_DWORD *)this + 3) |= 0x4000u;
    LODWORD(v33[0]) = 0;
    v33[1] = 0;
    v33[2] = 0;
    v34 = 0;
    v35 = 0;
    if ( (int)CThreadContext::ImpersonateUser((CThreadContext *)v33, *((void **)this + 3)) >= 0
      && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(v10, (unsigned int)EVENT_PROFILE_DIR_BACKEDUP, v11, 1, (__int64)hMem);
    }
    CThreadContext::~CThreadContext(v33);
  }
  lpSubKey = 0;
  v28 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v28 = -1;
  v29 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(*((LPCWCH *)this + 6), (unsigned __int16 **)&lpSubKey, 0);
  LocalProfileImage = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      dwOptions);
LABEL_24:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
    goto LABEL_46;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v13 )
  {
    LocalProfileImage = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x86F,
                          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                          (const char *)v13,
                          dwOptionsa);
    goto LABEL_27;
  }
  LocalProfileImage = CUserProfile::CreateLocalProfileImage(this, hKey, L"TEMP");
  v14 = (void *)*((_QWORD *)this + 3);
  LODWORD(v30[0]) = 0;
  v30[1] = 0;
  v30[2] = 0;
  v31 = 0;
  v32 = 0;
  if ( (LocalProfileImage & 0x80000000) != 0 )
  {
    if ( (int)CThreadContext::ImpersonateUser((CThreadContext *)v30, v14) >= 0 )
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
    CThreadContext::~CThreadContext(v30);
    goto LABEL_27;
  }
  *((_DWORD *)this + 3) = *((_DWORD *)this + 3) & 0xFFFFD7FB | 0x804;
  if ( (int)CThreadContext::ImpersonateUser((CThreadContext *)v30, v14) >= 0
    && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(v18, (unsigned int)EVENT_TEMPPROFILEASSIGNED, v19, 1, (__int64)hMem);
  }
  CThreadContext::~CThreadContext(v30);
  v20 = CUserProfile::IssueDefaultProfile(this);
  LocalProfileImage = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v20,
      dwOptionsa);
LABEL_27:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_24;
  }
  wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v36);
  if ( hKey )
    RegCloseKey(hKey);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  LocalProfileImage = 0;
LABEL_46:
  ProfileTelemetry::IssueTempProfile::~IssueTempProfile((ProfileTelemetry::IssueTempProfile *)v36);
  return LocalProfileImage;
}

```

## disassembly

```asm
0x180032ce0  mov     [rsp-8+arg_8], rbx
0x180032ce5  mov     [rsp-8+arg_10], rsi
0x180032cea  push    rbp
0x180032ceb  push    rdi
0x180032cec  push    r14
0x180032cee  lea     rbp, [rsp-150h]
0x180032cf6  sub     rsp, 250h
0x180032cfd  mov     rax, cs:__security_cookie
0x180032d04  xor     rax, rsp
0x180032d07  mov     [rbp+160h+var_20], rax
0x180032d0e  mov     rdi, rcx
0x180032d11  xor     r14d, r14d
0x180032d14  mov     esi, r14d
0x180032d17  mov     dword ptr [rsp+260h+hKey], r14d
0x180032d1c  lea     rcx, [rbp+160h+var_180]; struct wil::details::IFailureCallback *
0x180032d20  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180032d25  lea     rax, ??_7IssueTempProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::IssueTempProfile::`vftable'
0x180032d2c  mov     [rbp+160h+var_180], rax
0x180032d30  lea     rcx, [rbp+160h+var_180]; this
0x180032d34  call    ?StartActivity@IssueTempProfile@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::IssueTempProfile::StartActivity(void)
0x180032d39  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180032d40  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180032d45  test    al, al
0x180032d47  jz      short loc_180032D62
0x180032d49  test    cs:byte_18007F7C1, 1
0x180032d50  jz      short loc_180032D62
0x180032d52  mov     r8, [rdi+30h]
0x180032d56  lea     rdx, EVENT_ISSUE_TEMP_PROFILE
0x180032d5d  call    McTemplateU0z_EtwEventWriteTransfer
0x180032d62  test    byte ptr [rdi+8], 4
0x180032d66  jz      short loc_180032D76
0x180032d68  lea     rax, aLiteloadSpecif; "LITELOAD specified, cannot issue temp p"...
0x180032d6f  mov     edx, 846h
0x180032d74  jmp     short loc_180032DBD
0x180032d76  mov     [rsp+260h+var_210], r14b
0x180032d7b  lea     rdx, [rsp+260h+var_210]
0x180032d80  mov     ecx, 3
0x180032d85  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180032d8a  test    dword ptr [rdi+0Ch], 100h
0x180032d91  jnz     short loc_180032DA8
0x180032d93  cmp     [rsp+260h+var_210], r14b
0x180032d98  jz      short loc_180032DA8
0x180032d9a  lea     rax, aTempProfilesDi; "Temp profiles disabled, cannot issue te"...
0x180032da1  mov     edx, 84Eh
0x180032da6  jmp     short loc_180032DBD
0x180032da8  test    dword ptr [rdi+0Ch], 40001h
0x180032daf  jz      short loc_180032DE2
0x180032db1  lea     rax, aMandatoryOrSup; "Mandatory or super mandatory profile sp"...
0x180032db8  mov     edx, 851h; void *
0x180032dbd  mov     ebx, 80004005h
0x180032dc2  mov     rcx, [rbp+168h]; this
0x180032dc9  mov     qword ptr [rsp+260h+dwOptions], rax; int
0x180032dce  mov     r9d, ebx; char *
0x180032dd1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180032dd8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032ddd  jmp     loc_180033105
0x180032de2  mov     rcx, [rdi+30h]; lpString1
0x180032de6  test    dword ptr [rdi+0Ch], 804h
0x180032ded  jz      short loc_180032E3B
0x180032def  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x180032df4  test    eax, eax
0x180032df6  jnz     loc_180032EC4
0x180032dfc  mov     r9, [rdi+18h]
0x180032e00  xor     r8d, r8d
0x180032e03  mov     rdx, [rdi+98h]
0x180032e0a  mov     rcx, [rdi+30h]
0x180032e0e  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x180032e13  test    eax, eax
0x180032e15  jns     loc_180032EC4
0x180032e1b  mov     rcx, [rbp+168h]; this
0x180032e22  mov     r9d, eax; char *
0x180032e25  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180032e2c  mov     edx, 85Bh; void *
0x180032e31  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032e36  jmp     loc_180032EC4
0x180032e3b  call    ?BackupProfileListEntry@@YAJPEBG@Z; BackupProfileListEntry(ushort const *)
0x180032e40  mov     ebx, eax
0x180032e42  test    eax, eax
0x180032e44  jns     short loc_180032E66
0x180032e46  mov     rcx, [rbp+168h]; this
0x180032e4d  mov     r9d, eax; char *
0x180032e50  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180032e57  mov     edx, 860h; void *
0x180032e5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e61  jmp     loc_180033105
0x180032e66  bts     dword ptr [rdi+0Ch], 0Eh
0x180032e6b  mov     [rbp+160h+var_1B8], r14d
0x180032e6f  mov     [rbp+160h+var_1B0], r14
0x180032e73  mov     [rbp+160h+var_1A8], r14
0x180032e77  mov     [rbp+160h+var_1A0], r14d
0x180032e7b  xorps   xmm0, xmm0
0x180032e7e  movdqu  [rbp+160h+var_198], xmm0
0x180032e83  mov     rdx, [rdi+18h]; void *
0x180032e87  lea     rcx, [rbp+160h+var_1B8]; this
0x180032e8b  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180032e90  test    eax, eax
0x180032e92  js      short loc_180032EBB
0x180032e94  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180032e9b  jz      short loc_180032EBB
0x180032e9d  lea     rax, [rbp+160h+hMem]
0x180032ea4  mov     qword ptr [rsp+260h+dwOptions], rax; int
0x180032ea9  mov     r9d, 1
0x180032eaf  lea     rdx, EVENT_PROFILE_DIR_BACKEDUP
0x180032eb6  call    McGenEventWrite_EtwEventWriteTransfer
0x180032ebb  lea     rcx, [rbp+160h+var_1B8]; this
0x180032ebf  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180032ec4  mov     [rsp+260h+lpSubKey], r14
0x180032ec9  mov     [rsp+260h+var_1F8], r14
0x180032ece  mov     [rsp+260h+var_1F0], r14
0x180032ed3  lea     rcx, [rsp+260h+lpSubKey]
0x180032ed8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180032edd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032ee1  mov     [rsp+260h+var_1F8], rax
0x180032ee6  mov     [rsp+260h+var_1F0], rax
0x180032eeb  xor     r8d, r8d; int *
0x180032eee  lea     rdx, [rsp+260h+lpSubKey]; unsigned __int16 **
0x180032ef3  mov     rcx, [rdi+30h]; lpString1
0x180032ef7  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180032efc  mov     ebx, eax
0x180032efe  test    eax, eax
0x180032f00  jns     short loc_180032F2C
0x180032f02  mov     rcx, [rbp+168h]; this
0x180032f09  mov     r9d, eax; char *
0x180032f0c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180032f13  mov     edx, 86Ch; void *
0x180032f18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032f1d  lea     rcx, [rsp+260h+lpSubKey]
0x180032f22  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180032f27  jmp     loc_180033105
0x180032f2c  mov     [rsp+260h+hKey], r14
0x180032f31  xor     edx, edx
0x180032f33  lea     rcx, [rsp+260h+hKey]
0x180032f38  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180032f3d  mov     [rsp+260h+lpdwDisposition], r14; lpdwDisposition
0x180032f42  lea     rax, [rsp+260h+hKey]
0x180032f47  mov     [rsp+260h+phkResult], rax; phkResult
0x180032f4c  mov     [rsp+260h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180032f51  mov     dword ptr [rsp+260h+samDesired], 2001Fh; samDesired
0x180032f59  mov     [rsp+260h+dwOptions], r14d; int
0x180032f5e  xor     r9d, r9d; lpClass
0x180032f61  xor     r8d, r8d; Reserved
0x180032f64  mov     rdx, [rsp+260h+lpSubKey]; lpSubKey
0x180032f69  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032f70  call    cs:__imp_RegCreateKeyExW
0x180032f76  test    eax, eax
0x180032f78  jz      short loc_180032FB0
0x180032f7a  mov     rcx, [rbp+168h]; this
0x180032f81  mov     r9d, eax; char *
0x180032f84  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180032f8b  mov     edx, 86Fh; void *
0x180032f90  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032f95  mov     ebx, eax
0x180032f97  mov     rcx, [rsp+260h+hKey]; hKey
0x180032f9c  test    rcx, rcx
0x180032f9f  jz      loc_180032F1D
0x180032fa5  call    cs:__imp_RegCloseKey
0x180032fab  jmp     loc_180032F1D
0x180032fb0  lea     r8, aTemp; "TEMP"
0x180032fb7  mov     rdx, [rsp+260h+hKey]; HKEY
0x180032fbc  mov     rcx, rdi; this
0x180032fbf  call    ?CreateLocalProfileImage@CUserProfile@@IEAAJPEAUHKEY__@@PEBG@Z; CUserProfile::CreateLocalProfileImage(HKEY__ *,ushort const *)
0x180032fc4  mov     ebx, eax
0x180032fc6  mov     rdx, [rdi+18h]; void *
0x180032fca  mov     [rsp+260h+var_1E8], r14d
0x180032fcf  mov     [rbp+160h+var_1E0], r14
0x180032fd3  mov     [rbp+160h+var_1D8], r14
0x180032fd7  mov     [rbp+160h+var_1D0], r14d
0x180032fdb  xorps   xmm0, xmm0
0x180032fde  lea     rcx, [rsp+260h+var_1E8]; this
0x180032fe3  movdqu  [rbp+160h+var_1C8], xmm0
0x180032fe8  test    eax, eax
0x180032fea  jns     short loc_180033068
0x180032fec  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180032ff1  test    eax, eax
0x180032ff3  js      short loc_18003303E
0x180032ff5  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180032ffc  jz      short loc_18003302B
0x180032ffe  mov     edx, ebx; dwMessageId
0x180033000  lea     rcx, [rbp+160h+hMem]; lpBuffer
0x180033007  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18003300c  lea     r8, asc_180060EA8; "???"
0x180033013  cmp     [rax], r14
0x180033016  cmovnz  r8, [rax]
0x18003301a  lea     rdx, EVENT_TEMP_DIR_FAILED
0x180033021  call    McTemplateU0z_EtwEventWriteTransfer
0x180033026  mov     esi, 1
0x18003302b  test    sil, 1
0x18003302f  jz      short loc_18003303E
0x180033031  mov     rcx, [rbp+160h+hMem]; hMem
0x180033038  call    cs:__imp_LocalFree
0x18003303e  mov     rcx, [rbp+168h]; this
0x180033045  mov     r9d, ebx; char *
0x180033048  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003304f  mov     edx, 879h; void *
0x180033054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033059  lea     rcx, [rsp+260h+var_1E8]; this
0x18003305e  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180033063  jmp     loc_180032F97
0x180033068  mov     eax, [rdi+0Ch]
0x18003306b  btr     eax, 0Dh
0x18003306f  or      eax, 804h
0x180033074  mov     [rdi+0Ch], eax
0x180033077  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18003307c  test    eax, eax
0x18003307e  js      short loc_1800330A7
0x180033080  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180033087  jz      short loc_1800330A7
0x180033089  lea     rax, [rbp+160h+hMem]
0x180033090  mov     qword ptr [rsp+260h+dwOptions], rax; int
0x180033095  mov     r9d, 1
0x18003309b  lea     rdx, EVENT_TEMPPROFILEASSIGNED
0x1800330a2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800330a7  lea     rcx, [rsp+260h+var_1E8]; this
0x1800330ac  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x1800330b1  mov     rcx, rdi; this
0x1800330b4  call    ?IssueDefaultProfile@CUserProfile@@IEAAJXZ; CUserProfile::IssueDefaultProfile(void)
0x1800330b9  mov     ebx, eax
0x1800330bb  test    eax, eax
0x1800330bd  jns     short loc_1800330DF
0x1800330bf  mov     rcx, [rbp+168h]; this
0x1800330c6  mov     r9d, eax; char *
0x1800330c9  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800330d0  mov     edx, 88Ch; void *
0x1800330d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800330da  jmp     loc_180032F97
0x1800330df  lea     rcx, [rbp+160h+var_180]
0x1800330e3  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800330e8  mov     rcx, [rsp+260h+hKey]; hKey
0x1800330ed  test    rcx, rcx
0x1800330f0  jz      short loc_1800330F8
0x1800330f2  call    cs:__imp_RegCloseKey
0x1800330f8  lea     rcx, [rsp+260h+lpSubKey]
0x1800330fd  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180033102  mov     ebx, r14d
0x180033105  lea     rcx, [rbp+160h+var_180]; this
0x180033109  call    ??1IssueTempProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::IssueTempProfile::~IssueTempProfile(void)
0x18003310e  mov     eax, ebx
0x180033110  mov     rcx, [rbp+160h+var_20]
0x180033117  xor     rcx, rsp; StackCookie
0x18003311a  call    __security_check_cookie
0x18003311f  lea     r11, [rsp+260h+var_10]
0x180033127  mov     rbx, [r11+28h]
0x18003312b  mov     rsi, [r11+30h]
0x18003312f  mov     rsp, r11
0x180033132  pop     r14
0x180033134  pop     rdi
0x180033135  pop     rbp
0x180033136  retn
```
