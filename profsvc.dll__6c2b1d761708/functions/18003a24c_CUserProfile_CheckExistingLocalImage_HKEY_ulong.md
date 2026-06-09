# CUserProfile::CheckExistingLocalImage(HKEY__ *,ulong)

- ea: `0x18003a24c`
- end: `0x18003a7d0`
- name: `?CheckExistingLocalImage@CUserProfile@@IEAAJPEAUHKEY__@@K@Z`
- size: `1412`
- prototype: `int(CUserProfile *__hidden this, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e63c`

## callees

- `0x180005dd0`
- `0x180007b58`
- `0x180007d40`
- `0x1800087e8`
- `0x18000d030`
- `0x18000e1a0`
- `0x1800146f0`
- `0x180019260`
- `0x180022440`
- `0x180024b84`
- `0x180024cb0`
- `0x180028ef4`
- `0x180029e00`
- `0x180029e70`
- `0x18002abc8`
- `0x18002df48`
- `0x180030ad0`
- `0x180030af8`
- `0x18003a24c`
- `0x18003bc70`
- `0x180040bcc`
- `0x180044518`
- `0x1800471c8`
- `0x180048ba4`
- `0x180049e10`
- `0x180049e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a64f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a64f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a432`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a569`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a62b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a432`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a569`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a62b`

## string_xrefs

- `0x18003a2f0`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a40d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a4cb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a535`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a603`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a696`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a716`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a75a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a2cc`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall CUserProfile::CheckExistingLocalImage(CUserProfile *this, HKEY a2, int a3)
{
  __int64 v6; // r9
  int v7; // eax
  unsigned int LastError; // ebx
  const WCHAR *v9; // r14
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // r8d
  int v13; // ecx
  int v14; // r8d
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  DWORD FileAttributesW; // esi
  int v19; // ecx
  int v20; // r8d
  const char *v21; // r9
  DWORD v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // esi
  LPCWSTR v26; // rsi
  __int64 v27; // rcx
  int v28; // eax
  LPCWSTR v29; // rsi
  DWORD v30; // r15d
  const char *v31; // r9
  DWORD v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  _WORD *v35; // rax
  int DWORD; // eax
  int v37; // eax
  const struct wil::FailureInfo *v38; // rdx
  int v40; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+30h] [rbp-D0h] BYREF
  char v42; // [rsp+38h] [rbp-C8h]
  LPCWSTR v43[3]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v44[3]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v46[42]; // [rsp+90h] [rbp-70h] BYREF
  int v47[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "CUserProfile_CheckExistingLocalImage");
  v46[0] = &ProfileTelemetry::CUserProfile_CheckExistingLocalImage::`vftable';
  ProfileTelemetry::CUserProfile_CheckExistingLocalImage::StartActivity((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v46);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((char *)this + 152);
  memset(lpFileName, 0, 24);
  LOBYTE(v6) = 1;
  v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
         lpFileName,
         a2,
         L"ProfileImagePath",
         v6);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v7,
      v40);
    goto LABEL_60;
  }
  v9 = lpFileName[0];
  *(LPCWSTR *)v47 = lpFileName[0];
  ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ExpandedLocalImagePath<unsigned short const *>(v46, v47);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0z_EtwEventWriteTransfer(v10, EVENT_CHECKEXISTING_EXPANDED_PATH, v9);
  }
  if ( (a3 & 0x2000) != 0 )
  {
    ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ProfilePartlyLoaded((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v46);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (byte_1800828C1 & 1) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(
        v11,
        (unsigned int)EVENT_CHECKEXISTING_PARTIALLY_LOADED_PROFILE,
        v12,
        1,
        (__int64)v47);
    }
    *((_DWORD *)this + 3) |= 0x2000u;
    if ( (*((_BYTE *)this + 8) & 4) == 0 )
    {
      ProfileTelemetry::CUserProfile_CheckExistingLocalImage::TreatingProfileAsNew((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v46);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (byte_1800828C1 & 1) != 0 )
      {
        McGenEventWrite_EtwEventWriteTransfer(v13, (unsigned int)EVENT_CHECKEXISTING_TREAT_AS_NEW, v14, 1, (__int64)v47);
      }
      *((_DWORD *)this + 3) |= 4u;
    }
  }
  if ( (a3 & 0x800) != 0 )
    *((_DWORD *)this + 3) |= a3;
  v41 = 0;
  v42 = 0;
  v15 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v41, *((void **)this + 3));
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = (unsigned int)v15;
    v17 = 969;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)v16,
      v40);
LABEL_20:
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v41);
    goto LABEL_60;
  }
  FileAttributesW = GetFileAttributesW(v9);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
  {
    if ( FileAttributesW == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3DF,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                    v21);
      goto LABEL_20;
    }
    if ( (FileAttributesW & 0x10) == 0 )
    {
      LastError = -2147024894;
      v16 = 2147942402LL;
      v17 = 994;
      goto LABEL_19;
    }
LABEL_33:
    memset(v43, 0, sizeof(v43));
    v24 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v43,
            L"%s\\%s",
            v9,
            L"ntuser.man");
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E7,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v24,
        v40);
LABEL_35:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v43);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v41);
      LastError = v25;
      goto LABEL_60;
    }
    v26 = v43[0];
    if ( GetFileAttributesW(v43[0]) != -1 )
    {
      *(_QWORD *)v47 = v26;
      ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalMandatoryImage<unsigned short const *>(v46, v47);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
      {
        McTemplateU0z_EtwEventWriteTransfer(v27, EVENT_CHECKEXISTING_MANDATORY_PROFILE_FOUND, v26);
      }
      *((_DWORD *)this + 3) |= 0x20000u;
      *((_QWORD *)this + 31) = 0;
LABEL_57:
      v37 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
              (char *)this + 152,
              v9,
              -1);
      LastError = v37;
      if ( v37 >= 0 )
      {
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v46, v38);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v43);
        CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v41);
        LastError = 0;
        goto LABEL_60;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v37,
        v40);
      goto LABEL_48;
    }
    memset(v44, 0, sizeof(v44));
    v28 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v44,
            L"%s\\%s",
            v9,
            L"ntuser.dat");
    v25 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v28,
        v40);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v44);
      goto LABEL_35;
    }
    v29 = v44[0];
    v30 = GetFileAttributesW(v44[0]);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
    {
      if ( v30 == -1 )
      {
        v32 = GetLastError();
        LastError = v32;
        if ( (byte_1800828C1 & 2) != 0 )
          McTemplateU0zd_EtwEventWriteTransfer(v34, v33, v29, v32);
        goto LABEL_47;
      }
    }
    else if ( v30 == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x40D,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                    v31);
LABEL_47:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v44);
LABEL_48:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v43);
      goto LABEL_20;
    }
    *(_QWORD *)v47 = v29;
    ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalProfileImage<unsigned short const *>(v46, v47);
    v35 = (_WORD *)*((_QWORD *)this + 13);
    if ( v35 )
    {
      if ( *v35 )
      {
        DWORD = SHRegGetDWORD(a2, 0, L"ProfileUnloadTimeLow", (unsigned int *)this + 62);
        if ( DWORD < 0 || (DWORD = SHRegGetDWORD(a2, 0, L"ProfileUnloadTimeHigh", (unsigned int *)this + 63), DWORD < 0) )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x41C,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)DWORD,
            v40);
          *((_DWORD *)this + 62) = 0;
          *((_DWORD *)this + 63) = 0;
        }
      }
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v44);
    goto LABEL_57;
  }
  if ( FileAttributesW == -1 )
  {
    v22 = GetLastError();
    LastError = v22;
    if ( (byte_1800828C1 & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v23, EVENT_CHECKEXISTING_GETFILEATTRIBUTES_PATH_FAILED, v22);
    goto LABEL_20;
  }
  if ( (FileAttributesW & 0x10) != 0 )
    goto LABEL_33;
  if ( (byte_1800828C1 & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v19,
      (unsigned int)EVENT_CHECKEXISTING_PATH_NOT_DIRECTORY,
      v20,
      1,
      (__int64)v47);
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v41);
  LastError = -2147024894;
LABEL_60:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  ProfileTelemetry::CUserProfile_CheckExistingLocalImage::~CUserProfile_CheckExistingLocalImage((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v46);
  return LastError;
}

```

## disassembly

```asm
0x18003a24c  mov     [rsp-8+arg_10], rbx
0x18003a251  push    rbp
0x18003a252  push    rsi
0x18003a253  push    rdi
0x18003a254  push    r12
0x18003a256  push    r13
0x18003a258  push    r14
0x18003a25a  push    r15
0x18003a25c  lea     rbp, [rsp-100h]
0x18003a264  sub     rsp, 200h
0x18003a26b  mov     rax, cs:__security_cookie
0x18003a272  xor     rax, rsp
0x18003a275  mov     [rbp+130h+var_40], rax
0x18003a27c  mov     esi, r8d
0x18003a27f  mov     r12, rdx
0x18003a282  mov     rdi, rcx
0x18003a285  lea     rdx, aCuserprofileCh; "CUserProfile_CheckExistingLocalImage"
0x18003a28c  lea     rcx, [rbp+130h+var_1A0]
0x18003a290  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003a295  lea     rax, ??_7CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_CheckExistingLocalImage::`vftable'
0x18003a29c  mov     [rbp+130h+var_1A0], rax
0x18003a2a0  lea     rcx, [rbp+130h+var_1A0]; this
0x18003a2a4  call    ?StartActivity@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::StartActivity(void)
0x18003a2a9  lea     r13, [rdi+98h]
0x18003a2b0  mov     rcx, r13
0x18003a2b3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a2b8  xor     r15d, r15d
0x18003a2bb  mov     [rsp+230h+lpFileName], r15
0x18003a2c0  mov     [rsp+230h+var_1B8], r15
0x18003a2c5  mov     [rbp+130h+var_1B0], r15
0x18003a2c9  mov     r9b, 1
0x18003a2cc  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18003a2d3  mov     rdx, r12
0x18003a2d6  lea     rcx, [rsp+230h+lpFileName]
0x18003a2db  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18003a2e0  mov     ebx, eax
0x18003a2e2  test    eax, eax
0x18003a2e4  jns     short loc_18003A306
0x18003a2e6  mov     rcx, [rbp+138h]; this
0x18003a2ed  mov     r9d, eax; char *
0x18003a2f0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a2f7  mov     edx, 39Ah; void *
0x18003a2fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a301  jmp     loc_18003A790
0x18003a306  mov     r14, [rsp+230h+lpFileName]
0x18003a30b  mov     qword ptr [rbp+130h+var_50], r14
0x18003a312  lea     rdx, [rbp+130h+var_50]
0x18003a319  lea     rcx, [rbp+130h+var_1A0]
0x18003a31d  call    ??$ExpandedLocalImagePath@PEBG@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAX$$QEAPEBG@Z; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ExpandedLocalImagePath<ushort const *>(ushort const * &&)
0x18003a322  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003a329  mov     rcx, rbx
0x18003a32c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a331  test    al, al
0x18003a333  jz      short loc_18003A34D
0x18003a335  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r15b
0x18003a33c  jge     short loc_18003A34D
0x18003a33e  mov     r8, r14
0x18003a341  lea     rdx, EVENT_CHECKEXISTING_EXPANDED_PATH
0x18003a348  call    McTemplateU0z_EtwEventWriteTransfer
0x18003a34d  bt      esi, 0Dh
0x18003a351  jnb     loc_18003A3DE
0x18003a357  lea     rcx, [rbp+130h+var_1A0]; this
0x18003a35b  call    ?ProfilePartlyLoaded@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ProfilePartlyLoaded(void)
0x18003a360  mov     rcx, rbx
0x18003a363  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a368  test    al, al
0x18003a36a  jz      short loc_18003A393
0x18003a36c  test    cs:byte_1800828C1, 1
0x18003a373  jz      short loc_18003A393
0x18003a375  lea     rax, [rbp+130h+var_50]
0x18003a37c  mov     qword ptr [rsp+230h+var_210], rax
0x18003a381  mov     r9d, 1
0x18003a387  lea     rdx, EVENT_CHECKEXISTING_PARTIALLY_LOADED_PROFILE
0x18003a38e  call    McGenEventWrite_EtwEventWriteTransfer
0x18003a393  bts     dword ptr [rdi+0Ch], 0Dh
0x18003a398  test    byte ptr [rdi+8], 4
0x18003a39c  jnz     short loc_18003A3DE
0x18003a39e  lea     rcx, [rbp+130h+var_1A0]; this
0x18003a3a2  call    ?TreatingProfileAsNew@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::TreatingProfileAsNew(void)
0x18003a3a7  mov     rcx, rbx
0x18003a3aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a3af  test    al, al
0x18003a3b1  jz      short loc_18003A3DA
0x18003a3b3  test    cs:byte_1800828C1, 1
0x18003a3ba  jz      short loc_18003A3DA
0x18003a3bc  lea     rax, [rbp+130h+var_50]
0x18003a3c3  mov     qword ptr [rsp+230h+var_210], rax; int
0x18003a3c8  mov     r9d, 1
0x18003a3ce  lea     rdx, EVENT_CHECKEXISTING_TREAT_AS_NEW
0x18003a3d5  call    McGenEventWrite_EtwEventWriteTransfer
0x18003a3da  or      dword ptr [rdi+0Ch], 4
0x18003a3de  bt      esi, 0Bh
0x18003a3e2  jnb     short loc_18003A3E7
0x18003a3e4  or      [rdi+0Ch], esi
0x18003a3e7  mov     [rsp+230h+var_200], r15
0x18003a3ec  mov     [rsp+230h+var_1F8], r15b
0x18003a3f1  mov     rdx, [rdi+18h]; void *
0x18003a3f5  lea     rcx, [rsp+230h+var_200]; this
0x18003a3fa  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18003a3ff  mov     ebx, eax
0x18003a401  test    eax, eax
0x18003a403  jns     short loc_18003A42F
0x18003a405  mov     r9d, eax; char *
0x18003a408  mov     edx, 3C9h; void *
0x18003a40d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a414  mov     rcx, [rbp+138h]; this
0x18003a41b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a420  lea     rcx, [rsp+230h+var_200]; this
0x18003a425  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003a42a  jmp     loc_18003A790
0x18003a42f  mov     rcx, r14; lpFileName
0x18003a432  call    cs:__imp_GetFileAttributesW
0x18003a439  nop     dword ptr [rax+rax+00h]
0x18003a43e  mov     esi, eax
0x18003a440  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003a447  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a44c  or      ebx, 0FFFFFFFFh
0x18003a44f  test    al, al
0x18003a451  jz      short loc_18003A4C0
0x18003a453  cmp     esi, ebx
0x18003a455  jnz     short loc_18003A47F
0x18003a457  call    cs:__imp_GetLastError
0x18003a45e  nop     dword ptr [rax+rax+00h]
0x18003a463  mov     ebx, eax
0x18003a465  test    cs:byte_1800828C1, 2
0x18003a46c  jz      short loc_18003A420
0x18003a46e  mov     r8d, eax
0x18003a471  lea     rdx, EVENT_CHECKEXISTING_GETFILEATTRIBUTES_PATH_FAILED
0x18003a478  call    McTemplateU0q_EtwEventWriteTransfer
0x18003a47d  jmp     short loc_18003A420
0x18003a47f  test    sil, 10h
0x18003a483  jnz     short loc_18003A4FB
0x18003a485  test    cs:byte_1800828C1, 2
0x18003a48c  jz      short loc_18003A4AC
0x18003a48e  lea     rax, [rbp+130h+var_50]
0x18003a495  mov     qword ptr [rsp+230h+var_210], rax
0x18003a49a  mov     r9d, 1
0x18003a4a0  lea     rdx, EVENT_CHECKEXISTING_PATH_NOT_DIRECTORY
0x18003a4a7  call    McGenEventWrite_EtwEventWriteTransfer
0x18003a4ac  lea     rcx, [rsp+230h+var_200]; this
0x18003a4b1  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003a4b6  mov     ebx, 80070002h
0x18003a4bb  jmp     loc_18003A790
0x18003a4c0  cmp     esi, ebx
0x18003a4c2  jnz     short loc_18003A4E3
0x18003a4c4  mov     rcx, [rbp+138h]; this
0x18003a4cb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a4d2  mov     edx, 3DFh; void *
0x18003a4d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a4dc  mov     ebx, eax
0x18003a4de  jmp     loc_18003A420
0x18003a4e3  test    sil, 10h
0x18003a4e7  jnz     short loc_18003A4FB
0x18003a4e9  mov     ebx, 80070002h
0x18003a4ee  mov     r9d, ebx
0x18003a4f1  mov     edx, 3E2h
0x18003a4f6  jmp     loc_18003A40D
0x18003a4fb  mov     [rsp+230h+var_1F0], r15
0x18003a500  mov     [rsp+230h+var_1E8], r15
0x18003a505  mov     [rsp+230h+var_1E0], r15
0x18003a50a  lea     r9, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x18003a511  mov     r8, r14
0x18003a514  lea     rdx, aSS_0; "%s\\%s"
0x18003a51b  lea     rcx, [rsp+230h+var_1F0]
0x18003a520  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003a525  mov     esi, eax
0x18003a527  test    eax, eax
0x18003a529  jns     short loc_18003A561
0x18003a52b  mov     rcx, [rbp+138h]; this
0x18003a532  mov     r9d, eax; char *
0x18003a535  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a53c  mov     edx, 3E7h; void *
0x18003a541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a546  lea     rcx, [rsp+230h+var_1F0]
0x18003a54b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a550  lea     rcx, [rsp+230h+var_200]; this
0x18003a555  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003a55a  mov     ebx, esi
0x18003a55c  jmp     loc_18003A790
0x18003a561  mov     rsi, [rsp+230h+var_1F0]
0x18003a566  mov     rcx, rsi; lpFileName
0x18003a569  call    cs:__imp_GetFileAttributesW
0x18003a570  nop     dword ptr [rax+rax+00h]
0x18003a575  cmp     eax, ebx
0x18003a577  jz      short loc_18003A5C9
0x18003a579  mov     qword ptr [rbp+130h+var_50], rsi
0x18003a580  lea     rdx, [rbp+130h+var_50]
0x18003a587  lea     rcx, [rbp+130h+var_1A0]
0x18003a58b  call    ??$FoundLocalMandatoryImage@PEBG@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAX$$QEAPEBG@Z; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalMandatoryImage<ushort const *>(ushort const * &&)
0x18003a590  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003a597  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a59c  test    al, al
0x18003a59e  jz      short loc_18003A5B8
0x18003a5a0  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r15b
0x18003a5a7  jge     short loc_18003A5B8
0x18003a5a9  mov     r8, rsi
0x18003a5ac  lea     rdx, EVENT_CHECKEXISTING_MANDATORY_PROFILE_FOUND
0x18003a5b3  call    McTemplateU0z_EtwEventWriteTransfer
0x18003a5b8  bts     dword ptr [rdi+0Ch], 11h
0x18003a5bd  mov     [rdi+0F8h], r15
0x18003a5c4  jmp     loc_18003A73B
0x18003a5c9  mov     [rsp+230h+var_1D8], r15
0x18003a5ce  mov     [rsp+230h+var_1D0], r15
0x18003a5d3  mov     [rsp+230h+var_1C8], r15
0x18003a5d8  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18003a5df  mov     r8, r14
0x18003a5e2  lea     rdx, aSS_0; "%s\\%s"
0x18003a5e9  lea     rcx, [rsp+230h+var_1D8]
0x18003a5ee  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003a5f3  mov     esi, eax
0x18003a5f5  test    eax, eax
0x18003a5f7  jns     short loc_18003A623
0x18003a5f9  mov     rcx, [rbp+138h]; this
0x18003a600  mov     r9d, eax; char *
0x18003a603  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a60a  mov     edx, 3FFh; void *
0x18003a60f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a614  lea     rcx, [rsp+230h+var_1D8]
0x18003a619  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a61e  jmp     loc_18003A546
0x18003a623  mov     rsi, [rsp+230h+var_1D8]
0x18003a628  mov     rcx, rsi; lpFileName
0x18003a62b  call    cs:__imp_GetFileAttributesW
0x18003a632  nop     dword ptr [rax+rax+00h]
0x18003a637  mov     r15d, eax
0x18003a63a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003a641  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a646  test    al, al
0x18003a648  jz      short loc_18003A68A
0x18003a64a  cmp     r15d, ebx
0x18003a64d  jnz     short loc_18003A6AB
0x18003a64f  call    cs:__imp_GetLastError
0x18003a656  nop     dword ptr [rax+rax+00h]
0x18003a65b  mov     ebx, eax
0x18003a65d  test    cs:byte_1800828C1, 2
0x18003a664  jz      short loc_18003A671
0x18003a666  mov     r9d, eax
0x18003a669  mov     r8, rsi
0x18003a66c  call    McTemplateU0zd_EtwEventWriteTransfer
0x18003a671  lea     rcx, [rsp+230h+var_1D8]
0x18003a676  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a67b  lea     rcx, [rsp+230h+var_1F0]
0x18003a680  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a685  jmp     loc_18003A420
0x18003a68a  cmp     r15d, ebx
0x18003a68d  jnz     short loc_18003A6AB
0x18003a68f  mov     rcx, [rbp+138h]; this
0x18003a696  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a69d  mov     edx, 40Dh; void *
0x18003a6a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a6a7  mov     ebx, eax
0x18003a6a9  jmp     short loc_18003A671
0x18003a6ab  mov     qword ptr [rbp+130h+var_50], rsi
0x18003a6b2  lea     rdx, [rbp+130h+var_50]
0x18003a6b9  lea     rcx, [rbp+130h+var_1A0]
0x18003a6bd  call    ??$FoundLocalProfileImage@PEBG@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAX$$QEAPEBG@Z; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalProfileImage<ushort const *>(ushort const * &&)
0x18003a6c2  mov     rax, [rdi+68h]
0x18003a6c6  xor     r15d, r15d
0x18003a6c9  test    rax, rax
0x18003a6cc  jz      short loc_18003A731
0x18003a6ce  cmp     [rax], r15w
0x18003a6d2  jz      short loc_18003A731
0x18003a6d4  lea     rbx, [rdi+0F8h]
0x18003a6db  mov     r9, rbx; unsigned int *
0x18003a6de  lea     r8, aProfileunloadt; "ProfileUnloadTimeLow"
0x18003a6e5  xor     edx, edx; unsigned __int16 *
0x18003a6e7  mov     rcx, r12; HKEY
0x18003a6ea  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18003a6ef  test    eax, eax
0x18003a6f1  js      short loc_18003A70C
0x18003a6f3  lea     r9, [rbx+4]; unsigned int *
0x18003a6f7  lea     r8, aProfileunloadt_0; "ProfileUnloadTimeHigh"
0x18003a6fe  xor     edx, edx; unsigned __int16 *
0x18003a700  mov     rcx, r12; HKEY
0x18003a703  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18003a708  test    eax, eax
0x18003a70a  jns     short loc_18003A731
0x18003a70c  mov     rcx, [rbp+138h]; this
0x18003a713  mov     r9d, eax; char *
0x18003a716  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a71d  mov     edx, 41Ch; void *
0x18003a722  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a727  mov     [rbx], r15d
0x18003a72a  mov     [rdi+0FCh], r15d
0x18003a731  lea     rcx, [rsp+230h+var_1D8]
0x18003a736  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a73b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a73f  mov     rdx, r14
0x18003a742  mov     rcx, r13
0x18003a745  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003a74a  mov     ebx, eax
0x18003a74c  test    eax, eax
0x18003a74e  jns     short loc_18003A770
0x18003a750  mov     rcx, [rbp+138h]; this
0x18003a757  mov     r9d, eax; char *
0x18003a75a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a761  mov     edx, 425h; void *
0x18003a766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a76b  jmp     loc_18003A67B
0x18003a770  lea     rcx, [rbp+130h+var_1A0]
  ... truncated ...
```
