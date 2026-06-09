# CUserProfile::CheckExistingLocalImage(HKEY__ *,ulong)

- ea: `0x1800384b8`
- end: `0x180038a1d`
- name: `?CheckExistingLocalImage@CUserProfile@@IEAAJPEAUHKEY__@@K@Z`
- size: `1381`
- prototype: `__int64 __fastcall(CUserProfile *this, HKEY, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b6b8`

## callees

- `0x180006b10`
- `0x180008200`
- `0x18000a320`
- `0x18000a4a0`
- `0x18000adc0`
- `0x180010f30`
- `0x1800111a0`
- `0x1800154e0`
- `0x1800164e0`
- `0x180021b6c`
- `0x180021ca0`
- `0x180026df8`
- `0x180027e8c`
- `0x180027efc`
- `0x180028bf4`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002db38`
- `0x1800384b8`
- `0x18003a730`
- `0x18003f42c`
- `0x180042a08`
- `0x180045298`
- `0x180046ab8`
- `0x180047cbc`
- `0x180047d3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388a3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003869e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800387c9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180038885`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003869e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800387c9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180038885`

## string_xrefs

- `0x18003855c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180038679`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003872b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180038795`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003885d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800388e4`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180038964`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800389a8`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180038538`: `ProfileImagePath`

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
  int v39; // [rsp+20h] [rbp-E0h]
  __int64 v40; // [rsp+30h] [rbp-D0h] BYREF
  char v41; // [rsp+38h] [rbp-C8h]
  LPCWSTR v42[3]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v43[3]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v45[42]; // [rsp+90h] [rbp-70h] BYREF
  int v46[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v45,
    "CUserProfile_CheckExistingLocalImage");
  v45[0] = &ProfileTelemetry::CUserProfile_CheckExistingLocalImage::`vftable';
  ProfileTelemetry::CUserProfile_CheckExistingLocalImage::StartActivity((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v45);
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
      v39);
    goto LABEL_60;
  }
  v9 = lpFileName[0];
  *(LPCWSTR *)v46 = lpFileName[0];
  ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ExpandedLocalImagePath<unsigned short const *>(v45, v46);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0z_EtwEventWriteTransfer(v10, EVENT_CHECKEXISTING_EXPANDED_PATH, v9);
  }
  if ( (a3 & 0x2000) != 0 )
  {
    ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ProfilePartlyLoaded((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v45);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (byte_18007F7C1 & 1) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(
        v11,
        (unsigned int)EVENT_CHECKEXISTING_PARTIALLY_LOADED_PROFILE,
        v12,
        1,
        (__int64)v46);
    }
    *((_DWORD *)this + 3) |= 0x2000u;
    if ( (*((_BYTE *)this + 8) & 4) == 0 )
    {
      ProfileTelemetry::CUserProfile_CheckExistingLocalImage::TreatingProfileAsNew((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v45);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (byte_18007F7C1 & 1) != 0 )
      {
        McGenEventWrite_EtwEventWriteTransfer(v13, (unsigned int)EVENT_CHECKEXISTING_TREAT_AS_NEW, v14, 1, (__int64)v46);
      }
      *((_DWORD *)this + 3) |= 4u;
    }
  }
  if ( (a3 & 0x800) != 0 )
    *((_DWORD *)this + 3) |= a3;
  v40 = 0;
  v41 = 0;
  v15 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v40, *((void **)this + 3));
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
      v39);
LABEL_20:
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v40);
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
    memset(v42, 0, sizeof(v42));
    v24 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v42,
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
        v39);
LABEL_35:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v42);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v40);
      LastError = v25;
      goto LABEL_60;
    }
    v26 = v42[0];
    if ( GetFileAttributesW(v42[0]) != -1 )
    {
      *(_QWORD *)v46 = v26;
      ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalMandatoryImage<unsigned short const *>(v45, v46);
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
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v42);
        CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v40);
        LastError = 0;
        goto LABEL_60;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v37,
        v39);
      goto LABEL_48;
    }
    memset(v43, 0, sizeof(v43));
    v28 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v43,
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
        v39);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v43);
      goto LABEL_35;
    }
    v29 = v43[0];
    v30 = GetFileAttributesW(v43[0]);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
    {
      if ( v30 == -1 )
      {
        v32 = GetLastError();
        LastError = v32;
        if ( (byte_18007F7C1 & 2) != 0 )
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v43);
LABEL_48:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v42);
      goto LABEL_20;
    }
    *(_QWORD *)v46 = v29;
    ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalProfileImage<unsigned short const *>(v45, v46);
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
            v39);
          *((_DWORD *)this + 62) = 0;
          *((_DWORD *)this + 63) = 0;
        }
      }
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v43);
    goto LABEL_57;
  }
  if ( FileAttributesW == -1 )
  {
    v22 = GetLastError();
    LastError = v22;
    if ( (byte_18007F7C1 & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v23, EVENT_CHECKEXISTING_GETFILEATTRIBUTES_PATH_FAILED, v22);
    goto LABEL_20;
  }
  if ( (FileAttributesW & 0x10) != 0 )
    goto LABEL_33;
  if ( (byte_18007F7C1 & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v19,
      (unsigned int)EVENT_CHECKEXISTING_PATH_NOT_DIRECTORY,
      v20,
      1,
      (__int64)v46);
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v40);
  LastError = -2147024894;
LABEL_60:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  ProfileTelemetry::CUserProfile_CheckExistingLocalImage::~CUserProfile_CheckExistingLocalImage((ProfileTelemetry::CUserProfile_CheckExistingLocalImage *)v45);
  return LastError;
}

```

## disassembly

```asm
0x1800384b8  mov     [rsp-8+arg_10], rbx
0x1800384bd  push    rbp
0x1800384be  push    rsi
0x1800384bf  push    rdi
0x1800384c0  push    r12
0x1800384c2  push    r13
0x1800384c4  push    r14
0x1800384c6  push    r15
0x1800384c8  lea     rbp, [rsp-100h]
0x1800384d0  sub     rsp, 200h
0x1800384d7  mov     rax, cs:__security_cookie
0x1800384de  xor     rax, rsp
0x1800384e1  mov     [rbp+130h+var_40], rax
0x1800384e8  mov     esi, r8d
0x1800384eb  mov     r12, rdx
0x1800384ee  mov     rdi, rcx
0x1800384f1  lea     rdx, aCuserprofileCh; "CUserProfile_CheckExistingLocalImage"
0x1800384f8  lea     rcx, [rbp+130h+var_1A0]
0x1800384fc  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180038501  lea     rax, ??_7CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@6B@; const ProfileTelemetry::CUserProfile_CheckExistingLocalImage::`vftable'
0x180038508  mov     [rbp+130h+var_1A0], rax
0x18003850c  lea     rcx, [rbp+130h+var_1A0]; this
0x180038510  call    ?StartActivity@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::StartActivity(void)
0x180038515  lea     r13, [rdi+98h]
0x18003851c  mov     rcx, r13
0x18003851f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180038524  xor     r15d, r15d
0x180038527  mov     [rsp+230h+lpFileName], r15
0x18003852c  mov     [rsp+230h+var_1B8], r15
0x180038531  mov     [rbp+130h+var_1B0], r15
0x180038535  mov     r9b, 1
0x180038538  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18003853f  mov     rdx, r12
0x180038542  lea     rcx, [rsp+230h+lpFileName]
0x180038547  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18003854c  mov     ebx, eax
0x18003854e  test    eax, eax
0x180038550  jns     short loc_180038572
0x180038552  mov     rcx, [rbp+138h]; this
0x180038559  mov     r9d, eax; char *
0x18003855c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038563  mov     edx, 39Ah; void *
0x180038568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003856d  jmp     loc_1800389DE
0x180038572  mov     r14, [rsp+230h+lpFileName]
0x180038577  mov     qword ptr [rbp+130h+var_50], r14
0x18003857e  lea     rdx, [rbp+130h+var_50]
0x180038585  lea     rcx, [rbp+130h+var_1A0]
0x180038589  call    ??$ExpandedLocalImagePath@PEBG@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAX$$QEAPEBG@Z; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ExpandedLocalImagePath<ushort const *>(ushort const * &&)
0x18003858e  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180038595  mov     rcx, rbx
0x180038598  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003859d  test    al, al
0x18003859f  jz      short loc_1800385B9
0x1800385a1  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r15b
0x1800385a8  jge     short loc_1800385B9
0x1800385aa  mov     r8, r14
0x1800385ad  lea     rdx, EVENT_CHECKEXISTING_EXPANDED_PATH
0x1800385b4  call    McTemplateU0z_EtwEventWriteTransfer
0x1800385b9  bt      esi, 0Dh
0x1800385bd  jnb     loc_18003864A
0x1800385c3  lea     rcx, [rbp+130h+var_1A0]; this
0x1800385c7  call    ?ProfilePartlyLoaded@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::ProfilePartlyLoaded(void)
0x1800385cc  mov     rcx, rbx
0x1800385cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800385d4  test    al, al
0x1800385d6  jz      short loc_1800385FF
0x1800385d8  test    cs:byte_18007F7C1, 1
0x1800385df  jz      short loc_1800385FF
0x1800385e1  lea     rax, [rbp+130h+var_50]
0x1800385e8  mov     qword ptr [rsp+230h+var_210], rax
0x1800385ed  mov     r9d, 1
0x1800385f3  lea     rdx, EVENT_CHECKEXISTING_PARTIALLY_LOADED_PROFILE
0x1800385fa  call    McGenEventWrite_EtwEventWriteTransfer
0x1800385ff  bts     dword ptr [rdi+0Ch], 0Dh
0x180038604  test    byte ptr [rdi+8], 4
0x180038608  jnz     short loc_18003864A
0x18003860a  lea     rcx, [rbp+130h+var_1A0]; this
0x18003860e  call    ?TreatingProfileAsNew@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::TreatingProfileAsNew(void)
0x180038613  mov     rcx, rbx
0x180038616  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003861b  test    al, al
0x18003861d  jz      short loc_180038646
0x18003861f  test    cs:byte_18007F7C1, 1
0x180038626  jz      short loc_180038646
0x180038628  lea     rax, [rbp+130h+var_50]
0x18003862f  mov     qword ptr [rsp+230h+var_210], rax; int
0x180038634  mov     r9d, 1
0x18003863a  lea     rdx, EVENT_CHECKEXISTING_TREAT_AS_NEW
0x180038641  call    McGenEventWrite_EtwEventWriteTransfer
0x180038646  or      dword ptr [rdi+0Ch], 4
0x18003864a  bt      esi, 0Bh
0x18003864e  jnb     short loc_180038653
0x180038650  or      [rdi+0Ch], esi
0x180038653  mov     [rsp+230h+var_200], r15
0x180038658  mov     [rsp+230h+var_1F8], r15b
0x18003865d  mov     rdx, [rdi+18h]; void *
0x180038661  lea     rcx, [rsp+230h+var_200]; this
0x180038666  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18003866b  mov     ebx, eax
0x18003866d  test    eax, eax
0x18003866f  jns     short loc_18003869B
0x180038671  mov     r9d, eax; char *
0x180038674  mov     edx, 3C9h; void *
0x180038679  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038680  mov     rcx, [rbp+138h]; this
0x180038687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003868c  lea     rcx, [rsp+230h+var_200]; this
0x180038691  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180038696  jmp     loc_1800389DE
0x18003869b  mov     rcx, r14; lpFileName
0x18003869e  call    cs:__imp_GetFileAttributesW
0x1800386a4  mov     esi, eax
0x1800386a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800386ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800386b2  or      ebx, 0FFFFFFFFh
0x1800386b5  test    al, al
0x1800386b7  jz      short loc_180038720
0x1800386b9  cmp     esi, ebx
0x1800386bb  jnz     short loc_1800386DF
0x1800386bd  call    cs:__imp_GetLastError
0x1800386c3  mov     ebx, eax
0x1800386c5  test    cs:byte_18007F7C1, 2
0x1800386cc  jz      short loc_18003868C
0x1800386ce  mov     r8d, eax
0x1800386d1  lea     rdx, EVENT_CHECKEXISTING_GETFILEATTRIBUTES_PATH_FAILED
0x1800386d8  call    McTemplateU0q_EtwEventWriteTransfer
0x1800386dd  jmp     short loc_18003868C
0x1800386df  test    sil, 10h
0x1800386e3  jnz     short loc_18003875B
0x1800386e5  test    cs:byte_18007F7C1, 2
0x1800386ec  jz      short loc_18003870C
0x1800386ee  lea     rax, [rbp+130h+var_50]
0x1800386f5  mov     qword ptr [rsp+230h+var_210], rax
0x1800386fa  mov     r9d, 1
0x180038700  lea     rdx, EVENT_CHECKEXISTING_PATH_NOT_DIRECTORY
0x180038707  call    McGenEventWrite_EtwEventWriteTransfer
0x18003870c  lea     rcx, [rsp+230h+var_200]; this
0x180038711  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180038716  mov     ebx, 80070002h
0x18003871b  jmp     loc_1800389DE
0x180038720  cmp     esi, ebx
0x180038722  jnz     short loc_180038743
0x180038724  mov     rcx, [rbp+138h]; this
0x18003872b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038732  mov     edx, 3DFh; void *
0x180038737  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003873c  mov     ebx, eax
0x18003873e  jmp     loc_18003868C
0x180038743  test    sil, 10h
0x180038747  jnz     short loc_18003875B
0x180038749  mov     ebx, 80070002h
0x18003874e  mov     r9d, ebx
0x180038751  mov     edx, 3E2h
0x180038756  jmp     loc_180038679
0x18003875b  mov     [rsp+230h+var_1F0], r15
0x180038760  mov     [rsp+230h+var_1E8], r15
0x180038765  mov     [rsp+230h+var_1E0], r15
0x18003876a  lea     r9, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x180038771  mov     r8, r14
0x180038774  lea     rdx, aSS_0; "%s\\%s"
0x18003877b  lea     rcx, [rsp+230h+var_1F0]
0x180038780  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180038785  mov     esi, eax
0x180038787  test    eax, eax
0x180038789  jns     short loc_1800387C1
0x18003878b  mov     rcx, [rbp+138h]; this
0x180038792  mov     r9d, eax; char *
0x180038795  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003879c  mov     edx, 3E7h; void *
0x1800387a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800387a6  lea     rcx, [rsp+230h+var_1F0]
0x1800387ab  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800387b0  lea     rcx, [rsp+230h+var_200]; this
0x1800387b5  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800387ba  mov     ebx, esi
0x1800387bc  jmp     loc_1800389DE
0x1800387c1  mov     rsi, [rsp+230h+var_1F0]
0x1800387c6  mov     rcx, rsi; lpFileName
0x1800387c9  call    cs:__imp_GetFileAttributesW
0x1800387cf  cmp     eax, ebx
0x1800387d1  jz      short loc_180038823
0x1800387d3  mov     qword ptr [rbp+130h+var_50], rsi
0x1800387da  lea     rdx, [rbp+130h+var_50]
0x1800387e1  lea     rcx, [rbp+130h+var_1A0]
0x1800387e5  call    ??$FoundLocalMandatoryImage@PEBG@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAX$$QEAPEBG@Z; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalMandatoryImage<ushort const *>(ushort const * &&)
0x1800387ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800387f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800387f6  test    al, al
0x1800387f8  jz      short loc_180038812
0x1800387fa  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r15b
0x180038801  jge     short loc_180038812
0x180038803  mov     r8, rsi
0x180038806  lea     rdx, EVENT_CHECKEXISTING_MANDATORY_PROFILE_FOUND
0x18003880d  call    McTemplateU0z_EtwEventWriteTransfer
0x180038812  bts     dword ptr [rdi+0Ch], 11h
0x180038817  mov     [rdi+0F8h], r15
0x18003881e  jmp     loc_180038989
0x180038823  mov     [rsp+230h+var_1D8], r15
0x180038828  mov     [rsp+230h+var_1D0], r15
0x18003882d  mov     [rsp+230h+var_1C8], r15
0x180038832  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180038839  mov     r8, r14
0x18003883c  lea     rdx, aSS_0; "%s\\%s"
0x180038843  lea     rcx, [rsp+230h+var_1D8]
0x180038848  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003884d  mov     esi, eax
0x18003884f  test    eax, eax
0x180038851  jns     short loc_18003887D
0x180038853  mov     rcx, [rbp+138h]; this
0x18003885a  mov     r9d, eax; char *
0x18003885d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038864  mov     edx, 3FFh; void *
0x180038869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003886e  lea     rcx, [rsp+230h+var_1D8]
0x180038873  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180038878  jmp     loc_1800387A6
0x18003887d  mov     rsi, [rsp+230h+var_1D8]
0x180038882  mov     rcx, rsi; lpFileName
0x180038885  call    cs:__imp_GetFileAttributesW
0x18003888b  mov     r15d, eax
0x18003888e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180038895  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003889a  test    al, al
0x18003889c  jz      short loc_1800388D8
0x18003889e  cmp     r15d, ebx
0x1800388a1  jnz     short loc_1800388F9
0x1800388a3  call    cs:__imp_GetLastError
0x1800388a9  mov     ebx, eax
0x1800388ab  test    cs:byte_18007F7C1, 2
0x1800388b2  jz      short loc_1800388BF
0x1800388b4  mov     r9d, eax
0x1800388b7  mov     r8, rsi
0x1800388ba  call    McTemplateU0zd_EtwEventWriteTransfer
0x1800388bf  lea     rcx, [rsp+230h+var_1D8]
0x1800388c4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800388c9  lea     rcx, [rsp+230h+var_1F0]
0x1800388ce  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800388d3  jmp     loc_18003868C
0x1800388d8  cmp     r15d, ebx
0x1800388db  jnz     short loc_1800388F9
0x1800388dd  mov     rcx, [rbp+138h]; this
0x1800388e4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800388eb  mov     edx, 40Dh; void *
0x1800388f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800388f5  mov     ebx, eax
0x1800388f7  jmp     short loc_1800388BF
0x1800388f9  mov     qword ptr [rbp+130h+var_50], rsi
0x180038900  lea     rdx, [rbp+130h+var_50]
0x180038907  lea     rcx, [rbp+130h+var_1A0]
0x18003890b  call    ??$FoundLocalProfileImage@PEBG@CUserProfile_CheckExistingLocalImage@ProfileTelemetry@@QEAAX$$QEAPEBG@Z; ProfileTelemetry::CUserProfile_CheckExistingLocalImage::FoundLocalProfileImage<ushort const *>(ushort const * &&)
0x180038910  mov     rax, [rdi+68h]
0x180038914  xor     r15d, r15d
0x180038917  test    rax, rax
0x18003891a  jz      short loc_18003897F
0x18003891c  cmp     [rax], r15w
0x180038920  jz      short loc_18003897F
0x180038922  lea     rbx, [rdi+0F8h]
0x180038929  mov     r9, rbx; unsigned int *
0x18003892c  lea     r8, aProfileunloadt; "ProfileUnloadTimeLow"
0x180038933  xor     edx, edx; unsigned __int16 *
0x180038935  mov     rcx, r12; HKEY
0x180038938  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18003893d  test    eax, eax
0x18003893f  js      short loc_18003895A
0x180038941  lea     r9, [rbx+4]; unsigned int *
0x180038945  lea     r8, aProfileunloadt_0; "ProfileUnloadTimeHigh"
0x18003894c  xor     edx, edx; unsigned __int16 *
0x18003894e  mov     rcx, r12; HKEY
0x180038951  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180038956  test    eax, eax
0x180038958  jns     short loc_18003897F
0x18003895a  mov     rcx, [rbp+138h]; this
0x180038961  mov     r9d, eax; char *
0x180038964  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003896b  mov     edx, 41Ch; void *
0x180038970  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038975  mov     [rbx], r15d
0x180038978  mov     [rdi+0FCh], r15d
0x18003897f  lea     rcx, [rsp+230h+var_1D8]
0x180038984  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180038989  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003898d  mov     rdx, r14
0x180038990  mov     rcx, r13
0x180038993  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180038998  mov     ebx, eax
0x18003899a  test    eax, eax
0x18003899c  jns     short loc_1800389BE
0x18003899e  mov     rcx, [rbp+138h]; this
0x1800389a5  mov     r9d, eax; char *
0x1800389a8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800389af  mov     edx, 425h; void *
0x1800389b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389b9  jmp     loc_1800388C9
0x1800389be  lea     rcx, [rbp+130h+var_1A0]
0x1800389c2  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800389c7  lea     rcx, [rsp+230h+var_1F0]
0x1800389cc  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800389d1  lea     rcx, [rsp+230h+var_200]; this
0x1800389d6  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
  ... truncated ...
```
