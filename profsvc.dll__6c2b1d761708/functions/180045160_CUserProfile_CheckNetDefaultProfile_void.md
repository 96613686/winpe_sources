# CUserProfile::CheckNetDefaultProfile(void)

- ea: `0x180045160`
- end: `0x18004548e`
- name: `?CheckNetDefaultProfile@CUserProfile@@MEAAJXZ`
- size: `814`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180005dd0`
- `0x180007b58`
- `0x18000d030`
- `0x18000e1a0`
- `0x180024b84`
- `0x18002df48`
- `0x180030ad0`
- `0x180030af8`
- `0x180032e60`
- `0x180035860`
- `0x18003bc70`
- `0x180044c44`
- `0x180044e5c`
- `0x180045160`
- `0x18004763c`
- `0x1800477d4`
- `0x180049e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004537e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004537e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453ec`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800452c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180045352`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800453c9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800452c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180045352`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800453c9`
- `USERENV!__imp_CheckXForestLogon` at `0x1800451fc`
- `USERENV!__imp_CheckXForestLogon` at `0x1800451fc`

## string_xrefs

- `0x180045218`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180045267`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18004529d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180045328`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180045427`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserProfile::CheckNetDefaultProfile(CUserProfile *this)
{
  LPCWSTR *v2; // rsi
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rcx
  int v5; // eax
  int LastErrorFailHr; // ebx
  __int64 v8; // rdx
  DWORD FileAttributesW; // eax
  wil::details *v10; // rcx
  __int64 v11; // rdx
  DWORD v12; // ebx
  DWORD LastError; // eax
  __int64 v14; // rcx
  const char *v15; // r9
  DWORD v16; // eax
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  HANDLE v20; // [rsp+30h] [rbp-D0h] BYREF
  char v21; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpFileName[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v2 = (LPCWSTR *)((char *)this + 176);
  v3 = (const unsigned __int16 *)*((_QWORD *)this + 22);
  if ( v3 && *v3 )
  {
    wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v23);
    v23[0] = &ProfileTelemetry::CheckingNetworkDefaultProfile::`vftable';
    ProfileTelemetry::CheckingNetworkDefaultProfile::StartActivity(
      (ProfileTelemetry::CheckingNetworkDefaultProfile *)v23,
      v3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
    {
      McTemplateU0z_EtwEventWriteTransfer(v4, EVENT_PROFILE_CHECK_NET_DEFAULT_PROFILE, *v2);
    }
    v5 = CheckXForestLogon(*((_QWORD *)this + 3));
    LastErrorFailHr = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x723,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v5,
        v18);
LABEL_8:
      ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile((ProfileTelemetry::CheckingNetworkDefaultProfile *)v23);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v2);
      *((_DWORD *)this + 3) |= 0x200u;
      return (unsigned int)LastErrorFailHr;
    }
    if ( v5 == 1 )
    {
      LastErrorFailHr = -2147024891;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x724,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)0x80070005LL,
        (int)"Cross forest logon detected, disable network default profile.",
        v19);
      goto LABEL_8;
    }
    v20 = 0;
    v21 = 0;
    LastErrorFailHr = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v20, *((void **)this + 3));
    if ( LastErrorFailHr < 0 )
    {
      v8 = 1832;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v18);
LABEL_14:
      CAutoImpersonate::ResetImpersonation(&v20);
      goto LABEL_8;
    }
    FileAttributesW = GetFileAttributesW(*v2);
    if ( FileAttributesW == -1 )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
      goto LABEL_14;
    }
    if ( (FileAttributesW & 0x10) == 0 )
    {
      LastErrorFailHr = -2147024894;
      v8 = 1839;
      goto LABEL_13;
    }
    memset(lpFileName, 0, 24);
    LastErrorFailHr = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                        lpFileName,
                        L"%s\\%s",
                        *v2,
                        L"ntuser.dat");
    if ( LastErrorFailHr < 0 )
    {
      v11 = 1843;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v18);
LABEL_22:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
      goto LABEL_14;
    }
    v12 = GetFileAttributesW(lpFileName[0]);
    if ( v12 == -1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (byte_1800828C1 & 2) != 0 )
      {
        LastError = GetLastError();
        McTemplateU0q_EtwEventWriteTransfer(v14, EVENT_PROFILE_NET_DEFAULT_PROFILE_DAT_NOT_FOUND, LastError);
      }
      LastErrorFailHr = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                          lpFileName,
                          L"%s\\%s",
                          *v2,
                          L"ntuser.man");
      if ( LastErrorFailHr < 0 )
      {
        v11 = 1854;
        goto LABEL_21;
      }
      v12 = GetFileAttributesW(lpFileName[0]);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
    {
      if ( v12 == -1 )
      {
        v16 = GetLastError();
        LastErrorFailHr = v16;
        if ( (byte_1800828C1 & 2) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v17, EVENT_PROFILE_NET_DEFAULT_PROFILE_MAN_NOT_FOUND, v16);
        goto LABEL_22;
      }
    }
    else if ( v12 == -1 )
    {
      LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x750,
                          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                          v15);
      goto LABEL_22;
    }
    wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v23);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
    CAutoImpersonate::ResetImpersonation(&v20);
    ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile((ProfileTelemetry::CheckingNetworkDefaultProfile *)v23);
  }
  *((_DWORD *)this + 3) |= 0x200u;
  return 0;
}

```

## disassembly

```asm
0x180045160  push    rbp
0x180045162  push    rbx
0x180045163  push    rsi
0x180045164  push    rdi
0x180045165  push    r14
0x180045167  push    r15
0x180045169  lea     rbp, [rsp-0C8h]
0x180045171  sub     rsp, 1C8h
0x180045178  mov     rax, cs:__security_cookie
0x18004517f  xor     rax, rsp
0x180045182  mov     [rbp+0F0h+var_40], rax
0x180045189  mov     rdi, rcx
0x18004518c  lea     rsi, [rcx+0B0h]
0x180045193  mov     rbx, [rsi]
0x180045196  xor     r14d, r14d
0x180045199  test    rbx, rbx
0x18004519c  jz      loc_180045467
0x1800451a2  cmp     [rbx], r14w
0x1800451a6  jz      loc_180045467
0x1800451ac  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x1800451b1  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800451b6  lea     rax, ??_7CheckingNetworkDefaultProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::CheckingNetworkDefaultProfile::`vftable'
0x1800451bd  mov     [rsp+1F0h+var_190], rax
0x1800451c2  mov     rdx, rbx; unsigned __int16 *
0x1800451c5  lea     rcx, [rsp+1F0h+var_190]; this
0x1800451ca  call    ?StartActivity@CheckingNetworkDefaultProfile@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::CheckingNetworkDefaultProfile::StartActivity(ushort const *)
0x1800451cf  nop
0x1800451d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800451d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800451dc  test    al, al
0x1800451de  jz      short loc_1800451F8
0x1800451e0  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r14b
0x1800451e7  jge     short loc_1800451F8
0x1800451e9  mov     r8, [rsi]
0x1800451ec  lea     rdx, EVENT_PROFILE_CHECK_NET_DEFAULT_PROFILE
0x1800451f3  call    McTemplateU0z_EtwEventWriteTransfer
0x1800451f8  mov     rcx, [rdi+18h]
0x1800451fc  call    cs:__imp_CheckXForestLogon
0x180045203  nop     dword ptr [rax+rax+00h]
0x180045208  mov     ebx, eax
0x18004520a  test    eax, eax
0x18004520c  jns     short loc_180045247
0x18004520e  mov     rcx, [rbp+0F8h]; this
0x180045215  mov     r9d, eax; char *
0x180045218  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004521f  mov     edx, 723h; void *
0x180045224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045229  lea     rcx, [rsp+1F0h+var_190]; this
0x18004522e  call    ??1CheckingNetworkDefaultProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile(void)
0x180045233  mov     rcx, rsi
0x180045236  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004523b  bts     dword ptr [rdi+0Ch], 9
0x180045240  mov     eax, ebx
0x180045242  jmp     loc_18004546E
0x180045247  cmp     ebx, 1
0x18004524a  jnz     short loc_18004527A
0x18004524c  mov     rcx, [rbp+0F8h]; this
0x180045253  lea     rax, aCrossForestLog; "Cross forest logon detected, disable ne"...
0x18004525a  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004525f  mov     ebx, 80070005h
0x180045264  mov     r9d, ebx; char *
0x180045267  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004526e  mov     edx, 724h; void *
0x180045273  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045278  jmp     short loc_180045229
0x18004527a  mov     [rsp+1F0h+var_1C0], r14
0x18004527f  mov     [rsp+1F0h+var_1B8], r14b
0x180045284  mov     rdx, [rdi+18h]; void *
0x180045288  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18004528d  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180045292  mov     ebx, eax
0x180045294  test    eax, eax
0x180045296  jns     short loc_1800452C2
0x180045298  mov     edx, 728h; void *
0x18004529d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800452a4  mov     r9d, ebx; char *
0x1800452a7  mov     rcx, [rbp+0F8h]; this
0x1800452ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800452b3  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800452b8  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800452bd  jmp     loc_180045229
0x1800452c2  mov     rcx, [rsi]; lpFileName
0x1800452c5  call    cs:__imp_GetFileAttributesW
0x1800452cc  nop     dword ptr [rax+rax+00h]
0x1800452d1  or      r15d, 0FFFFFFFFh
0x1800452d5  cmp     eax, r15d
0x1800452d8  jnz     short loc_1800452E3
0x1800452da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800452df  mov     ebx, eax
0x1800452e1  jmp     short loc_1800452B3
0x1800452e3  test    al, 10h
0x1800452e5  jnz     short loc_1800452F3
0x1800452e7  mov     ebx, 80070002h
0x1800452ec  mov     edx, 72Fh
0x1800452f1  jmp     short loc_18004529D
0x1800452f3  mov     [rsp+1F0h+lpFileName], r14
0x1800452f8  mov     [rsp+1F0h+var_1A8], r14
0x1800452fd  mov     [rsp+1F0h+var_1A0], r14
0x180045302  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180045309  mov     r8, [rsi]
0x18004530c  lea     rdx, aSS_0; "%s\\%s"
0x180045313  lea     rcx, [rsp+1F0h+lpFileName]
0x180045318  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004531d  mov     ebx, eax
0x18004531f  test    eax, eax
0x180045321  jns     short loc_18004534D
0x180045323  mov     edx, 733h; void *
0x180045328  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004532f  mov     r9d, ebx; char *
0x180045332  mov     rcx, [rbp+0F8h]; this
0x180045339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004533e  lea     rcx, [rsp+1F0h+lpFileName]
0x180045343  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180045348  jmp     loc_1800452B3
0x18004534d  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x180045352  call    cs:__imp_GetFileAttributesW
0x180045359  nop     dword ptr [rax+rax+00h]
0x18004535e  mov     ebx, eax
0x180045360  cmp     eax, r15d
0x180045363  jnz     short loc_1800453D7
0x180045365  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18004536c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180045371  test    al, al
0x180045373  jz      short loc_180045399
0x180045375  test    cs:byte_1800828C1, 2
0x18004537c  jz      short loc_180045399
0x18004537e  call    cs:__imp_GetLastError
0x180045385  nop     dword ptr [rax+rax+00h]
0x18004538a  mov     r8d, eax
0x18004538d  lea     rdx, EVENT_PROFILE_NET_DEFAULT_PROFILE_DAT_NOT_FOUND
0x180045394  call    McTemplateU0q_EtwEventWriteTransfer
0x180045399  lea     r9, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x1800453a0  mov     r8, [rsi]
0x1800453a3  lea     rdx, aSS_0; "%s\\%s"
0x1800453aa  lea     rcx, [rsp+1F0h+lpFileName]
0x1800453af  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800453b4  mov     ebx, eax
0x1800453b6  test    eax, eax
0x1800453b8  jns     short loc_1800453C4
0x1800453ba  mov     edx, 73Eh
0x1800453bf  jmp     loc_180045328
0x1800453c4  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x1800453c9  call    cs:__imp_GetFileAttributesW
0x1800453d0  nop     dword ptr [rax+rax+00h]
0x1800453d5  mov     ebx, eax
0x1800453d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800453de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800453e3  test    al, al
0x1800453e5  jz      short loc_18004541B
0x1800453e7  cmp     ebx, r15d
0x1800453ea  jnz     short loc_18004543F
0x1800453ec  call    cs:__imp_GetLastError
0x1800453f3  nop     dword ptr [rax+rax+00h]
0x1800453f8  mov     ebx, eax
0x1800453fa  test    cs:byte_1800828C1, 2
0x180045401  jz      loc_18004533E
0x180045407  mov     r8d, eax
0x18004540a  lea     rdx, EVENT_PROFILE_NET_DEFAULT_PROFILE_MAN_NOT_FOUND
0x180045411  call    McTemplateU0q_EtwEventWriteTransfer
0x180045416  jmp     loc_18004533E
0x18004541b  cmp     ebx, r15d
0x18004541e  jnz     short loc_18004543F
0x180045420  mov     rcx, [rbp+0F8h]; this
0x180045427  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004542e  mov     edx, 750h; void *
0x180045433  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045438  mov     ebx, eax
0x18004543a  jmp     loc_18004533E
0x18004543f  lea     rcx, [rsp+1F0h+var_190]
0x180045444  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180045449  lea     rcx, [rsp+1F0h+lpFileName]
0x18004544e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180045453  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180045458  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18004545d  lea     rcx, [rsp+1F0h+var_190]; this
0x180045462  call    ??1CheckingNetworkDefaultProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile(void)
0x180045467  bts     dword ptr [rdi+0Ch], 9
0x18004546c  xor     eax, eax
0x18004546e  mov     rcx, [rbp+0F0h+var_40]
0x180045475  xor     rcx, rsp; StackCookie
0x180045478  call    __security_check_cookie
0x18004547d  add     rsp, 1C8h
0x180045484  pop     r15
0x180045486  pop     r14
0x180045488  pop     rdi
0x180045489  pop     rsi
0x18004548a  pop     rbx
0x18004548b  pop     rbp
0x18004548c  retn
```
