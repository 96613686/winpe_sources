# CUserProfile::CheckNetDefaultProfile(void)

- ea: `0x1800436b0`
- end: `0x1800439b9`
- name: `?CheckNetDefaultProfile@CUserProfile@@MEAAJXZ`
- size: `777`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008200`
- `0x18000a320`
- `0x180010f30`
- `0x1800111a0`
- `0x180021b6c`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002f8e0`
- `0x1800321f4`
- `0x18003a730`
- `0x1800431d0`
- `0x1800433e4`
- `0x1800436b0`
- `0x180045674`
- `0x180045800`
- `0x180047cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004391e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004391e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004380f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043896`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043901`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004380f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043896`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043901`
- `USERENV!__imp_CheckXForestLogon` at `0x18004374c`
- `USERENV!__imp_CheckXForestLogon` at `0x18004374c`

## string_xrefs

- `0x180043762`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800437b1`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800437e7`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18004386c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180043953`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
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
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
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
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v2);
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
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v20);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
      goto LABEL_14;
    }
    v12 = GetFileAttributesW(lpFileName[0]);
    if ( v12 == -1 )
    {
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (byte_18007F7C1 & 2) != 0 )
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
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
    {
      if ( v12 == -1 )
      {
        v16 = GetLastError();
        LastErrorFailHr = v16;
        if ( (byte_18007F7C1 & 2) != 0 )
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v20);
    ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile((ProfileTelemetry::CheckingNetworkDefaultProfile *)v23);
  }
  *((_DWORD *)this + 3) |= 0x200u;
  return 0;
}

```

## disassembly

```asm
0x1800436b0  push    rbp
0x1800436b2  push    rbx
0x1800436b3  push    rsi
0x1800436b4  push    rdi
0x1800436b5  push    r14
0x1800436b7  push    r15
0x1800436b9  lea     rbp, [rsp-0C8h]
0x1800436c1  sub     rsp, 1C8h
0x1800436c8  mov     rax, cs:__security_cookie
0x1800436cf  xor     rax, rsp
0x1800436d2  mov     [rbp+0F0h+var_40], rax
0x1800436d9  mov     rdi, rcx
0x1800436dc  lea     rsi, [rcx+0B0h]
0x1800436e3  mov     rbx, [rsi]
0x1800436e6  xor     r14d, r14d
0x1800436e9  test    rbx, rbx
0x1800436ec  jz      loc_180043993
0x1800436f2  cmp     [rbx], r14w
0x1800436f6  jz      loc_180043993
0x1800436fc  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x180043701  call    ??0?$ActivityBase@VProfileLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180043706  lea     rax, ??_7CheckingNetworkDefaultProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::CheckingNetworkDefaultProfile::`vftable'
0x18004370d  mov     [rsp+1F0h+var_190], rax
0x180043712  mov     rdx, rbx; unsigned __int16 *
0x180043715  lea     rcx, [rsp+1F0h+var_190]; this
0x18004371a  call    ?StartActivity@CheckingNetworkDefaultProfile@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::CheckingNetworkDefaultProfile::StartActivity(ushort const *)
0x18004371f  nop
0x180043720  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180043727  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18004372c  test    al, al
0x18004372e  jz      short loc_180043748
0x180043730  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r14b
0x180043737  jge     short loc_180043748
0x180043739  mov     r8, [rsi]
0x18004373c  lea     rdx, EVENT_PROFILE_CHECK_NET_DEFAULT_PROFILE
0x180043743  call    McTemplateU0z_EtwEventWriteTransfer
0x180043748  mov     rcx, [rdi+18h]
0x18004374c  call    cs:__imp_CheckXForestLogon
0x180043752  mov     ebx, eax
0x180043754  test    eax, eax
0x180043756  jns     short loc_180043791
0x180043758  mov     rcx, [rbp+0F8h]; this
0x18004375f  mov     r9d, eax; char *
0x180043762  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043769  mov     edx, 723h; void *
0x18004376e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043773  lea     rcx, [rsp+1F0h+var_190]; this
0x180043778  call    ??1CheckingNetworkDefaultProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile(void)
0x18004377d  mov     rcx, rsi
0x180043780  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180043785  bts     dword ptr [rdi+0Ch], 9
0x18004378a  mov     eax, ebx
0x18004378c  jmp     loc_18004399A
0x180043791  cmp     ebx, 1
0x180043794  jnz     short loc_1800437C4
0x180043796  mov     rcx, [rbp+0F8h]; this
0x18004379d  lea     rax, aCrossForestLog; "Cross forest logon detected, disable ne"...
0x1800437a4  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x1800437a9  mov     ebx, 80070005h
0x1800437ae  mov     r9d, ebx; char *
0x1800437b1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800437b8  mov     edx, 724h; void *
0x1800437bd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800437c2  jmp     short loc_180043773
0x1800437c4  mov     [rsp+1F0h+var_1C0], r14
0x1800437c9  mov     [rsp+1F0h+var_1B8], r14b
0x1800437ce  mov     rdx, [rdi+18h]; void *
0x1800437d2  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800437d7  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800437dc  mov     ebx, eax
0x1800437de  test    eax, eax
0x1800437e0  jns     short loc_18004380C
0x1800437e2  mov     edx, 728h; void *
0x1800437e7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800437ee  mov     r9d, ebx; char *
0x1800437f1  mov     rcx, [rbp+0F8h]; this
0x1800437f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800437fd  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180043802  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180043807  jmp     loc_180043773
0x18004380c  mov     rcx, [rsi]; lpFileName
0x18004380f  call    cs:__imp_GetFileAttributesW
0x180043815  or      r15d, 0FFFFFFFFh
0x180043819  cmp     eax, r15d
0x18004381c  jnz     short loc_180043827
0x18004381e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043823  mov     ebx, eax
0x180043825  jmp     short loc_1800437FD
0x180043827  test    al, 10h
0x180043829  jnz     short loc_180043837
0x18004382b  mov     ebx, 80070002h
0x180043830  mov     edx, 72Fh
0x180043835  jmp     short loc_1800437E7
0x180043837  mov     [rsp+1F0h+lpFileName], r14
0x18004383c  mov     [rsp+1F0h+var_1A8], r14
0x180043841  mov     [rsp+1F0h+var_1A0], r14
0x180043846  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18004384d  mov     r8, [rsi]
0x180043850  lea     rdx, aSS_0; "%s\\%s"
0x180043857  lea     rcx, [rsp+1F0h+lpFileName]
0x18004385c  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180043861  mov     ebx, eax
0x180043863  test    eax, eax
0x180043865  jns     short loc_180043891
0x180043867  mov     edx, 733h; void *
0x18004386c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180043873  mov     r9d, ebx; char *
0x180043876  mov     rcx, [rbp+0F8h]; this
0x18004387d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043882  lea     rcx, [rsp+1F0h+lpFileName]
0x180043887  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004388c  jmp     loc_1800437FD
0x180043891  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x180043896  call    cs:__imp_GetFileAttributesW
0x18004389c  mov     ebx, eax
0x18004389e  cmp     eax, r15d
0x1800438a1  jnz     short loc_180043909
0x1800438a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800438aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800438af  test    al, al
0x1800438b1  jz      short loc_1800438D1
0x1800438b3  test    cs:byte_18007F7C1, 2
0x1800438ba  jz      short loc_1800438D1
0x1800438bc  call    cs:__imp_GetLastError
0x1800438c2  mov     r8d, eax
0x1800438c5  lea     rdx, EVENT_PROFILE_NET_DEFAULT_PROFILE_DAT_NOT_FOUND
0x1800438cc  call    McTemplateU0q_EtwEventWriteTransfer
0x1800438d1  lea     r9, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x1800438d8  mov     r8, [rsi]
0x1800438db  lea     rdx, aSS_0; "%s\\%s"
0x1800438e2  lea     rcx, [rsp+1F0h+lpFileName]
0x1800438e7  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800438ec  mov     ebx, eax
0x1800438ee  test    eax, eax
0x1800438f0  jns     short loc_1800438FC
0x1800438f2  mov     edx, 73Eh
0x1800438f7  jmp     loc_18004386C
0x1800438fc  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x180043901  call    cs:__imp_GetFileAttributesW
0x180043907  mov     ebx, eax
0x180043909  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180043910  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180043915  test    al, al
0x180043917  jz      short loc_180043947
0x180043919  cmp     ebx, r15d
0x18004391c  jnz     short loc_18004396B
0x18004391e  call    cs:__imp_GetLastError
0x180043924  mov     ebx, eax
0x180043926  test    cs:byte_18007F7C1, 2
0x18004392d  jz      loc_180043882
0x180043933  mov     r8d, eax
0x180043936  lea     rdx, EVENT_PROFILE_NET_DEFAULT_PROFILE_MAN_NOT_FOUND
0x18004393d  call    McTemplateU0q_EtwEventWriteTransfer
0x180043942  jmp     loc_180043882
0x180043947  cmp     ebx, r15d
0x18004394a  jnz     short loc_18004396B
0x18004394c  mov     rcx, [rbp+0F8h]; this
0x180043953  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004395a  mov     edx, 750h; void *
0x18004395f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043964  mov     ebx, eax
0x180043966  jmp     loc_180043882
0x18004396b  lea     rcx, [rsp+1F0h+var_190]
0x180043970  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180043975  lea     rcx, [rsp+1F0h+lpFileName]
0x18004397a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004397f  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180043984  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180043989  lea     rcx, [rsp+1F0h+var_190]; this
0x18004398e  call    ??1CheckingNetworkDefaultProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::CheckingNetworkDefaultProfile::~CheckingNetworkDefaultProfile(void)
0x180043993  bts     dword ptr [rdi+0Ch], 9
0x180043998  xor     eax, eax
0x18004399a  mov     rcx, [rbp+0F0h+var_40]
0x1800439a1  xor     rcx, rsp; StackCookie
0x1800439a4  call    __security_check_cookie
0x1800439a9  add     rsp, 1C8h
0x1800439b0  pop     r15
0x1800439b2  pop     r14
0x1800439b4  pop     rdi
0x1800439b5  pop     rsi
0x1800439b6  pop     rbx
0x1800439b7  pop     rbp
0x1800439b8  retn
```
