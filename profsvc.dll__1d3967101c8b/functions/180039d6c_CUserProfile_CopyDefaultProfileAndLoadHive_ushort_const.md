# CUserProfile::CopyDefaultProfileAndLoadHive(ushort const *)

- ea: `0x180039d6c`
- end: `0x18003a30b`
- name: `?CopyDefaultProfileAndLoadHive@CUserProfile@@IEAAJPEBG@Z`
- size: `1439`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180039bcc`

## callees

- `0x180008200`
- `0x1800085cc`
- `0x180008ef4`
- `0x1800099f8`
- `0x18000a320`
- `0x180010f30`
- `0x1800111a0`
- `0x180011200`
- `0x180018bcc`
- `0x18001a8a8`
- `0x180021b6c`
- `0x180021ca0`
- `0x18002c324`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002f8e0`
- `0x180038de4`
- `0x180039d6c`
- `0x18003a730`
- `0x18003c118`
- `0x18003fd6c`
- `0x180040e94`
- `0x180042924`
- `0x180047cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a05e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a2bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a2bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039e0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039e74`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a045`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039e0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039e74`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a045`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180039f59`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180039f59`
- `ext-ms-win-profile-profsvc-l1-1-0!ConnectToRoamingVhdProfile` at `0x180039fa4`
- `ext-ms-win-profile-profsvc-l1-1-0!ConnectToRoamingVhdProfile` at `0x180039fa4`

## string_xrefs

- `0x180039e51`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180039e83`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180039ee4`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180039f2e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180039f67`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180039ff5`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a0ce`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a183`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a21c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003a0ba`: `User does not have privileges on registry hive`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfile::CopyDefaultProfileAndLoadHive(CUserProfile *this, const unsigned __int16 *a2)
{
  char v4; // r15
  __int64 v5; // rcx
  int v6; // eax
  unsigned int LastError; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  CAutoImpersonate *v11; // rcx
  const char *v12; // r9
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // esi
  signed int v16; // eax
  const char *v17; // r9
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  char IsEnabled; // al
  __int64 v24; // rcx
  const WCHAR *v25; // rbx
  DWORD FileAttributesW; // esi
  DWORD v27; // eax
  __int64 v28; // rcx
  HKEY v29; // rcx
  int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // ecx
  int v34; // r8d
  char v35; // al
  HKEY v36; // rdx
  const unsigned __int16 *v37; // rcx
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  signed int v42; // eax
  const wchar_t **v43; // rax
  __int64 v44; // rcx
  const wchar_t *v45; // r8
  int v47; // [rsp+20h] [rbp-89h]
  int v48; // [rsp+20h] [rbp-89h]
  int v49; // [rsp+20h] [rbp-89h]
  void **v50; // [rsp+28h] [rbp-81h]
  HLOCAL hMem; // [rsp+30h] [rbp-79h] BYREF
  LPCWSTR v52[3]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v53; // [rsp+50h] [rbp-59h] BYREF
  char v54; // [rsp+58h] [rbp-51h]
  __int64 v55; // [rsp+60h] [rbp-49h] BYREF
  char v56; // [rsp+68h] [rbp-41h]
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-39h] BYREF
  HANDLE v58[3]; // [rsp+88h] [rbp-21h] BYREF
  int v59; // [rsp+A0h] [rbp-9h]
  __int128 v60; // [rsp+A8h] [rbp-1h]
  int v61[4]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = 0;
  LODWORD(hMem) = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0z_EtwEventWriteTransfer(v5, EVENT_COPY_DEFAULT_PROFILE_START, a2);
  }
  memset(lpFileName, 0, sizeof(lpFileName));
  v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         a2,
         L"ntuser.dat");
  LastError = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 1905;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)v8,
      v47);
    goto LABEL_75;
  }
  if ( GetFileAttributesW(lpFileName[0]) != -1 )
    goto LABEL_15;
  if ( GetLastError() == 1326 )
  {
    v53 = 0;
    v54 = 0;
    v10 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v53, *((void **)this + 3));
    LastError = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v10,
        v47);
LABEL_10:
      v11 = (CAutoImpersonate *)&v53;
LABEL_11:
      CAutoImpersonate::ResetImpersonation(v11);
      goto LABEL_75;
    }
    if ( GetFileAttributesW(lpFileName[0]) == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x77B,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                    v12);
      goto LABEL_10;
    }
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v53);
LABEL_15:
    v13 = (*((_DWORD *)this + 2) & 0xC) != 0 ? 692482 : 819458;
    if ( (*((_DWORD *)this + 3) & 0x2000) == 0 )
      v13 |= 0x31u;
    v55 = 0;
    v56 = 0;
    v14 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v55, *((void **)this + 3));
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x792,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v14,
        v47);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v55);
LABEL_19:
      LastError = v15;
      goto LABEL_75;
    }
    v47 = 0;
    if ( !(unsigned int)CopyProfileDirectoryEx2(a2, *((_QWORD *)this + 19), v13, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x794,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                    v17);
      v11 = (CAutoImpersonate *)&v55;
      goto LABEL_11;
    }
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v55);
    if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent(v18) )
    {
      v19 = ConnectToRoamingVhdProfile(*((_QWORD *)this + 19), *((_QWORD *)this + 3), *((unsigned int *)this + 3));
      LastError = v19;
      if ( v19 < 0 )
      {
        v8 = (unsigned int)v19;
        v9 = 1946;
        goto LABEL_24;
      }
    }
    memset(v52, 0, sizeof(v52));
    v20 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v52,
            L"%s\\%s",
            *((_QWORD *)this + 19),
            L"ntuser.dat",
            0,
            0,
            hMem);
    LastError = v20;
    if ( v20 < 0 )
    {
      v21 = (unsigned int)v20;
      v22 = 1951;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)v21,
        v48);
LABEL_33:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v52);
      goto LABEL_75;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl);
    v25 = v52[0];
    if ( IsEnabled && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
      McTemplateU0z_EtwEventWriteTransfer(v24, EVENT_COPY_DEFAULT_PROFILE_NEWHIVE, v52[0]);
    FileAttributesW = GetFileAttributesW(v25);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
    {
      if ( FileAttributesW == -1 )
      {
        v27 = GetLastError();
        if ( (byte_18007F7C1 & 2) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v28, EVENT_COPY_DEFAULT_PROFILE_HIVE_NOT_FOUND, v27);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v52);
        LastError = -2147019873;
        goto LABEL_75;
      }
    }
    else if ( FileAttributesW == -1 )
    {
      LastError = -2147019873;
      v21 = 2147947423LL;
      v22 = 1973;
      goto LABEL_32;
    }
    if ( !(unsigned int)CheckFullAccessOnFile(*((HANDLE *)this + 3), v25) )
    {
      LastError = -2147467259;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x7BE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)0x80004005LL,
        (int)"User does not have privileges on registry hive",
        (const char *)v50);
      goto LABEL_33;
    }
    v30 = MountRegHive(v29, *((const unsigned __int16 **)this + 6), v25, 0, *((HANDLE *)this + 3), (void **)this + 28);
    v15 = v30;
    LODWORD(hMem) = v30;
    if ( v30 < 0 )
    {
      if ( v30 == -2147023887 )
      {
        LODWORD(v58[0]) = 0;
        v58[1] = 0;
        v58[2] = 0;
        v59 = 0;
        v60 = 0;
        if ( (int)CThreadContext::ImpersonateUser((CThreadContext *)v58, *((void **)this + 3)) >= 0
          && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
        {
          McGenEventWrite_EtwEventWriteTransfer(v31, (unsigned int)EVENT_FAILED_LOAD_1009, v32, 1, (__int64)v61);
        }
        CThreadContext::~CThreadContext(v58);
      }
      ProfileTelemetry::DefaultHiveLoadFailure<long const &>(&hMem);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7CE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v15,
        v49);
      goto LABEL_53;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(
        v33,
        (unsigned int)EVENT_COPY_DEFAULT_PROFILE_HIVE_LOADED,
        v34,
        1,
        (__int64)v61);
    }
    VerifyCriticalKeysInUserHive(*((LPCWSTR *)this + 6));
    v35 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl);
    v37 = (const unsigned __int16 *)*((_QWORD *)this + 6);
    if ( v35 )
    {
      v38 = SetDefaultUserHiveSecurity(v37, v36);
      v15 = v38;
      if ( v38 < 0 )
      {
        if ( (byte_18007F7C1 & 2) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(
            v39,
            EVENT_COPY_DEFAULT_PROFILE_SET_DEFAULT_SECURITY_FAILED,
            (unsigned int)v38);
        v40 = 2022;
        goto LABEL_62;
      }
    }
    else
    {
      v15 = SetDefaultUserHiveSecurity(v37, v36);
      if ( v15 < 0 )
      {
        v40 = 2027;
LABEL_62:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v15,
          v49);
        UnmountRegHive(v41, *((_QWORD *)this + 6), 0, (char *)this + 224);
LABEL_53:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v52);
        goto LABEL_19;
      }
    }
    if ( (*((_BYTE *)this + 8) & 4) != 0
      || (v42 = LoadChangeUserClasses(
                  *((const unsigned __int16 **)this + 6),
                  0,
                  1,
                  0,
                  (void **)this + 29,
                  *((HANDLE *)this + 3)),
          v15 = v42,
          v42 >= 0) )
    {
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v52);
      LastError = 0;
      goto LABEL_75;
    }
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
    {
      v43 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v42);
      v45 = L"???";
      if ( *v43 )
        v45 = *v43;
      McTemplateU0z_EtwEventWriteTransfer(v44, EVENT_FAIL_LOAD_CLASSES_HIVE, v45);
      v4 = 1;
    }
    if ( (v4 & 1) != 0 )
      LocalFree(hMem);
    v40 = 2037;
    goto LABEL_62;
  }
  v16 = GetLastError();
  LastError = v16;
  if ( v16 > 0 )
    LastError = (unsigned __int16)v16 | 0x80070000;
  if ( (LastError & 0x80000000) != 0 )
  {
    v8 = LastError;
    v9 = 1920;
    goto LABEL_24;
  }
LABEL_75:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x180039d6c  mov     [rsp-8+arg_10], rbx
0x180039d71  push    rbp
0x180039d72  push    rsi
0x180039d73  push    rdi
0x180039d74  push    r12
0x180039d76  push    r13
0x180039d78  push    r14
0x180039d7a  push    r15
0x180039d7c  lea     rbp, [rsp-27h]
0x180039d81  sub     rsp, 0D0h
0x180039d88  mov     rax, cs:__security_cookie
0x180039d8f  xor     rax, rsp
0x180039d92  mov     [rbp+57h+var_38], rax
0x180039d96  mov     r14, rdx
0x180039d99  mov     rdi, rcx
0x180039d9c  xor     r12d, r12d
0x180039d9f  mov     r15d, r12d
0x180039da2  mov     dword ptr [rbp+57h+hMem], r12d
0x180039da6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180039dad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180039db2  test    al, al
0x180039db4  jz      short loc_180039DCE
0x180039db6  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x180039dbd  jge     short loc_180039DCE
0x180039dbf  mov     r8, r14
0x180039dc2  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_START
0x180039dc9  call    McTemplateU0z_EtwEventWriteTransfer
0x180039dce  mov     [rbp+57h+lpFileName], r12
0x180039dd2  mov     [rbp+57h+var_88], r12
0x180039dd6  mov     [rbp+57h+var_80], r12
0x180039dda  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180039de1  mov     r8, r14
0x180039de4  lea     rdx, aSS_0; "%s\\%s"
0x180039deb  lea     rcx, [rbp+57h+lpFileName]
0x180039def  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180039df4  mov     ebx, eax
0x180039df6  test    eax, eax
0x180039df8  jns     short loc_180039E07
0x180039dfa  mov     r9d, eax
0x180039dfd  mov     edx, 771h
0x180039e02  jmp     loc_180039F2A
0x180039e07  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180039e0b  call    cs:__imp_GetFileAttributesW
0x180039e11  or      r13d, 0FFFFFFFFh
0x180039e15  cmp     eax, r13d
0x180039e18  jnz     loc_180039EA1
0x180039e1e  call    cs:__imp_GetLastError
0x180039e24  cmp     eax, 52Eh
0x180039e29  jnz     loc_180039F05
0x180039e2f  mov     [rbp+57h+var_B0], r12
0x180039e33  mov     [rbp+57h+var_A8], r12b
0x180039e37  mov     rdx, [rdi+18h]; void *
0x180039e3b  lea     rcx, [rbp+57h+var_B0]; this
0x180039e3f  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180039e44  mov     ebx, eax
0x180039e46  test    eax, eax
0x180039e48  jns     short loc_180039E70
0x180039e4a  mov     rcx, [rbp+5Fh]; this
0x180039e4e  mov     r9d, eax; char *
0x180039e51  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039e58  mov     edx, 77Ah; void *
0x180039e5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e62  lea     rcx, [rbp+57h+var_B0]; this
0x180039e66  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180039e6b  jmp     loc_18003A2D9
0x180039e70  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180039e74  call    cs:__imp_GetFileAttributesW
0x180039e7a  cmp     eax, r13d
0x180039e7d  jnz     short loc_180039E98
0x180039e7f  mov     rcx, [rbp+5Fh]; this
0x180039e83  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039e8a  mov     edx, 77Bh; void *
0x180039e8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039e94  mov     ebx, eax
0x180039e96  jmp     short loc_180039E62
0x180039e98  lea     rcx, [rbp+57h+var_B0]; this
0x180039e9c  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180039ea1  mov     eax, [rdi+8]
0x180039ea4  and     al, 0Ch
0x180039ea6  neg     al
0x180039ea8  sbb     ebx, ebx
0x180039eaa  and     ebx, 0FFFE1000h
0x180039eb0  add     ebx, 0C8102h
0x180039eb6  test    dword ptr [rdi+0Ch], 2000h
0x180039ebd  jnz     short loc_180039EC2
0x180039ebf  or      ebx, 31h
0x180039ec2  mov     [rbp+57h+var_A0], r12
0x180039ec6  mov     [rbp+57h+var_98], r12b
0x180039eca  mov     rdx, [rdi+18h]; void *
0x180039ece  lea     rcx, [rbp+57h+var_A0]; this
0x180039ed2  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180039ed7  mov     esi, eax
0x180039ed9  test    eax, eax
0x180039edb  jns     short loc_180039F3F
0x180039edd  mov     rcx, [rbp+5Fh]; this
0x180039ee1  mov     r9d, eax; char *
0x180039ee4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039eeb  mov     edx, 792h; void *
0x180039ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ef5  lea     rcx, [rbp+57h+var_A0]; this
0x180039ef9  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180039efe  mov     ebx, esi
0x180039f00  jmp     loc_18003A2D9
0x180039f05  call    cs:__imp_GetLastError
0x180039f0b  mov     ebx, eax
0x180039f0d  test    eax, eax
0x180039f0f  jle     short loc_180039F1A
0x180039f11  movzx   ebx, ax
0x180039f14  or      ebx, 80070000h
0x180039f1a  test    ebx, ebx
0x180039f1c  jns     loc_18003A2D9
0x180039f22  mov     r9d, ebx; char *
0x180039f25  mov     edx, 780h; void *
0x180039f2a  mov     rcx, [rbp+5Fh]; this
0x180039f2e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039f35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f3a  jmp     loc_18003A2D9
0x180039f3f  mov     [rsp+100h+var_D8], r12; char *
0x180039f44  mov     [rsp+100h+var_E0], r12; int
0x180039f49  xor     r9d, r9d
0x180039f4c  mov     r8d, ebx
0x180039f4f  mov     rdx, [rdi+98h]
0x180039f56  mov     rcx, r14
0x180039f59  call    cs:__imp_CopyProfileDirectoryEx2
0x180039f5f  test    eax, eax
0x180039f61  jnz     short loc_180039F83
0x180039f63  mov     rcx, [rbp+5Fh]; this
0x180039f67  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039f6e  mov     edx, 794h; void *
0x180039f73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039f78  mov     ebx, eax
0x180039f7a  lea     rcx, [rbp+57h+var_A0]
0x180039f7e  jmp     loc_180039E66
0x180039f83  lea     rcx, [rbp+57h+var_A0]; this
0x180039f87  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180039f8c  call    IsWaitForNetworkForRoamingProfilePresent
0x180039f91  test    al, al
0x180039f93  jz      short loc_180039FBD
0x180039f95  mov     r8d, [rdi+0Ch]
0x180039f99  mov     rdx, [rdi+18h]
0x180039f9d  mov     rcx, [rdi+98h]
0x180039fa4  call    cs:__imp_ConnectToRoamingVhdProfile
0x180039faa  mov     ebx, eax
0x180039fac  test    eax, eax
0x180039fae  jns     short loc_180039FBD
0x180039fb0  mov     r9d, eax
0x180039fb3  mov     edx, 79Ah
0x180039fb8  jmp     loc_180039F2A
0x180039fbd  mov     [rbp+57h+var_C8], r12
0x180039fc1  mov     [rbp+57h+var_C0], r12
0x180039fc5  mov     [rbp+57h+var_B8], r12
0x180039fc9  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180039fd0  mov     r8, [rdi+98h]
0x180039fd7  lea     rdx, aSS_0; "%s\\%s"
0x180039fde  lea     rcx, [rbp+57h+var_C8]
0x180039fe2  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180039fe7  mov     ebx, eax
0x180039fe9  test    eax, eax
0x180039feb  jns     short loc_18003A013
0x180039fed  mov     r9d, eax; char *
0x180039ff0  mov     edx, 79Fh; void *
0x180039ff5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039ffc  mov     rcx, [rbp+5Fh]; this
0x18003a000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a005  lea     rcx, [rbp+57h+var_C8]
0x18003a009  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a00e  jmp     loc_18003A2D9
0x18003a013  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003a01a  mov     rcx, r14
0x18003a01d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a022  mov     rbx, [rbp+57h+var_C8]
0x18003a026  test    al, al
0x18003a028  jz      short loc_18003A042
0x18003a02a  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18003a031  jge     short loc_18003A042
0x18003a033  mov     r8, rbx
0x18003a036  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_NEWHIVE
0x18003a03d  call    McTemplateU0z_EtwEventWriteTransfer
0x18003a042  mov     rcx, rbx; lpFileName
0x18003a045  call    cs:__imp_GetFileAttributesW
0x18003a04b  mov     esi, eax
0x18003a04d  mov     rcx, r14
0x18003a050  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a055  test    al, al
0x18003a057  jz      short loc_18003A08F
0x18003a059  cmp     esi, r13d
0x18003a05c  jnz     short loc_18003A0A6
0x18003a05e  call    cs:__imp_GetLastError
0x18003a064  test    cs:byte_18007F7C1, 2
0x18003a06b  jz      short loc_18003A07C
0x18003a06d  mov     r8d, eax
0x18003a070  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_HIVE_NOT_FOUND
0x18003a077  call    McTemplateU0q_EtwEventWriteTransfer
0x18003a07c  lea     rcx, [rbp+57h+var_C8]
0x18003a080  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a085  mov     ebx, 8007139Fh
0x18003a08a  jmp     loc_18003A2D9
0x18003a08f  cmp     esi, r13d
0x18003a092  jnz     short loc_18003A0A6
0x18003a094  mov     ebx, 8007139Fh
0x18003a099  mov     r9d, ebx
0x18003a09c  mov     edx, 7B5h
0x18003a0a1  jmp     loc_180039FF5
0x18003a0a6  mov     rdx, rbx; lpFileName
0x18003a0a9  mov     rcx, [rdi+18h]; hToken
0x18003a0ad  call    ?CheckFullAccessOnFile@@YAHPEAXPEBG@Z; CheckFullAccessOnFile(void *,ushort const *)
0x18003a0b2  test    eax, eax
0x18003a0b4  jnz     short loc_18003A0E4
0x18003a0b6  mov     rcx, [rbp+5Fh]; this
0x18003a0ba  lea     rax, aUserDoesNotHav; "User does not have privileges on regist"...
0x18003a0c1  mov     [rsp+100h+var_E0], rax; int
0x18003a0c6  mov     ebx, 80004005h
0x18003a0cb  mov     r9d, ebx; char *
0x18003a0ce  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a0d5  mov     edx, 7BEh; void *
0x18003a0da  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a0df  jmp     loc_18003A005
0x18003a0e4  lea     rax, [rdi+0E0h]
0x18003a0eb  mov     [rsp+100h+var_D8], rax; void **
0x18003a0f0  mov     rax, [rdi+18h]
0x18003a0f4  mov     [rsp+100h+var_E0], rax; void *
0x18003a0f9  xor     r9d, r9d; HKEY
0x18003a0fc  mov     r8, rbx; unsigned __int16 *
0x18003a0ff  mov     rdx, [rdi+30h]; unsigned __int16 *
0x18003a103  call    ?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z; MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)
0x18003a108  mov     esi, eax
0x18003a10a  mov     dword ptr [rbp+57h+hMem], eax
0x18003a10d  test    eax, eax
0x18003a10f  jns     loc_18003A1A2
0x18003a115  cmp     eax, 800703F1h
0x18003a11a  jnz     short loc_18003A173
0x18003a11c  mov     [rbp+57h+var_78], r12d
0x18003a120  mov     [rbp+57h+var_70], r12
0x18003a124  mov     [rbp+57h+var_68], r12
0x18003a128  mov     [rbp+57h+var_60], r12d
0x18003a12c  xorps   xmm0, xmm0
0x18003a12f  movdqu  [rbp+57h+var_58], xmm0
0x18003a134  mov     rdx, [rdi+18h]; void *
0x18003a138  lea     rcx, [rbp+57h+var_78]; this
0x18003a13c  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18003a141  test    eax, eax
0x18003a143  js      short loc_18003A16A
0x18003a145  mov     ebx, 1
0x18003a14a  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, bl
0x18003a150  jz      short loc_18003A16A
0x18003a152  lea     rax, [rbp+57h+var_48]
0x18003a156  mov     [rsp+100h+var_E0], rax; int
0x18003a15b  mov     r9d, ebx
0x18003a15e  lea     rdx, EVENT_FAILED_LOAD_1009
0x18003a165  call    McGenEventWrite_EtwEventWriteTransfer
0x18003a16a  lea     rcx, [rbp+57h+var_78]; this
0x18003a16e  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18003a173  lea     rcx, [rbp+57h+hMem]
0x18003a177  call    ??$DefaultHiveLoadFailure@AEBJ@ProfileTelemetry@@SAXAEBJ@Z; ProfileTelemetry::DefaultHiveLoadFailure<long const &>(long const &)
0x18003a17c  mov     rcx, [rbp+5Fh]; this
0x18003a180  mov     r9d, esi; char *
0x18003a183  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a18a  mov     edx, 7CEh; void *
0x18003a18f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a194  lea     rcx, [rbp+57h+var_C8]
0x18003a198  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003a19d  jmp     loc_180039EFE
0x18003a1a2  mov     rcx, r14
0x18003a1a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a1aa  mov     ebx, 1
0x18003a1af  test    al, al
0x18003a1b1  jz      short loc_18003A1D4
0x18003a1b3  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18003a1ba  jge     short loc_18003A1D4
0x18003a1bc  lea     rax, [rbp+57h+var_48]
0x18003a1c0  mov     [rsp+100h+var_E0], rax; int
0x18003a1c5  mov     r9d, ebx
0x18003a1c8  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_HIVE_LOADED
0x18003a1cf  call    McGenEventWrite_EtwEventWriteTransfer
0x18003a1d4  mov     rcx, [rdi+30h]; lpSubKey
0x18003a1d8  call    ?VerifyCriticalKeysInUserHive@@YAXPEBG@Z; VerifyCriticalKeysInUserHive(ushort const *)
0x18003a1dd  mov     rcx, r14
0x18003a1e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003a1e5  mov     rcx, [rdi+30h]; unsigned __int16 *
0x18003a1e9  test    al, al
0x18003a1eb  jz      short loc_18003A240
0x18003a1ed  call    ?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z; SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)
0x18003a1f2  mov     esi, eax
0x18003a1f4  test    eax, eax
0x18003a1f6  jns     short loc_18003A252
0x18003a1f8  test    cs:byte_18007F7C1, 2
0x18003a1ff  jz      short loc_18003A210
0x18003a201  mov     r8d, eax
0x18003a204  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_SET_DEFAULT_SECURITY_FAILED
0x18003a20b  call    McTemplateU0q_EtwEventWriteTransfer
0x18003a210  mov     edx, 7E6h; void *
0x18003a215  mov     rcx, [rbp+5Fh]; this
0x18003a219  mov     r9d, esi; char *
0x18003a21c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003a223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a228  lea     r9, [rdi+0E0h]
0x18003a22f  xor     r8d, r8d
0x18003a232  mov     rdx, [rdi+30h]
0x18003a236  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x18003a23b  jmp     loc_18003A194
  ... truncated ...
```
