# CUserProfile::CopyDefaultProfileAndLoadHive(ushort const *)

- ea: `0x18003b26c`
- end: `0x18003b842`
- name: `?CopyDefaultProfileAndLoadHive@CUserProfile@@IEAAJPEBG@Z`
- size: `1494`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003b0c4`

## callees

- `0x180005dd0`
- `0x180006498`
- `0x18000721c`
- `0x180007b58`
- `0x18000d030`
- `0x18000e1a0`
- `0x18001378c`
- `0x180016150`
- `0x1800178bc`
- `0x18001c358`
- `0x180024b84`
- `0x180024cb0`
- `0x18002df48`
- `0x180030ad0`
- `0x180030af8`
- `0x180035860`
- `0x18003a7d8`
- `0x18003b26c`
- `0x18003bc70`
- `0x18003d678`
- `0x180041560`
- `0x180042880`
- `0x180044434`
- `0x180049e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b588`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b30b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b380`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b569`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b30b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b380`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003b569`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x18003b471`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x18003b471`
- `ext-ms-win-profile-profsvc-l1-1-0!ConnectToRoamingVhdProfile` at `0x18003b4c2`
- `ext-ms-win-profile-profsvc-l1-1-0!ConnectToRoamingVhdProfile` at `0x18003b4c2`

## string_xrefs

- `0x18003b35d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b395`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b3f6`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b446`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b485`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b519`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b5fe`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b6b3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b74c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003b5ea`: `User does not have privileges on registry hive`

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
  int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  char IsEnabled; // al
  __int64 v23; // rcx
  const WCHAR *v24; // rbx
  DWORD FileAttributesW; // esi
  DWORD v26; // eax
  __int64 v27; // rcx
  HKEY v28; // rcx
  int v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // ecx
  int v33; // r8d
  char v34; // al
  HKEY v35; // rdx
  const unsigned __int16 *v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  signed int v41; // eax
  const wchar_t **v42; // rax
  __int64 v43; // rcx
  const wchar_t *v44; // r8
  int v46; // [rsp+20h] [rbp-89h]
  int v47; // [rsp+20h] [rbp-89h]
  HLOCAL hMem; // [rsp+30h] [rbp-79h] BYREF
  LPCWSTR v49[3]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v50; // [rsp+50h] [rbp-59h] BYREF
  char v51; // [rsp+58h] [rbp-51h]
  __int64 v52; // [rsp+60h] [rbp-49h] BYREF
  char v53; // [rsp+68h] [rbp-41h]
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-39h] BYREF
  int v55; // [rsp+88h] [rbp-21h] BYREF
  __int64 v56; // [rsp+90h] [rbp-19h]
  __int64 v57; // [rsp+98h] [rbp-11h]
  int v58; // [rsp+A0h] [rbp-9h]
  __int128 v59; // [rsp+A8h] [rbp-1h]
  int v60[4]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = 0;
  LODWORD(hMem) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
      v46);
    goto LABEL_75;
  }
  if ( GetFileAttributesW(lpFileName[0]) != -1 )
    goto LABEL_15;
  if ( GetLastError() == 1326 )
  {
    v50 = 0;
    v51 = 0;
    v10 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v50, *((void **)this + 3));
    LastError = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v10,
        v46);
LABEL_10:
      v11 = (CAutoImpersonate *)&v50;
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
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v50);
LABEL_15:
    v13 = (*((_DWORD *)this + 2) & 0xC) != 0 ? 692482 : 819458;
    if ( (*((_DWORD *)this + 3) & 0x2000) == 0 )
      v13 |= 0x31u;
    v52 = 0;
    v53 = 0;
    v14 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v52, *((void **)this + 3));
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x792,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v14,
        v46);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v52);
LABEL_19:
      LastError = v15;
      goto LABEL_75;
    }
    v46 = 0;
    if ( !(unsigned int)CopyProfileDirectoryEx2(a2, *((_QWORD *)this + 19), v13, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x794,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                    v17);
      v11 = (CAutoImpersonate *)&v52;
      goto LABEL_11;
    }
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v52);
    if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent() )
    {
      v18 = ConnectToRoamingVhdProfile(*((_QWORD *)this + 19), *((_QWORD *)this + 3), *((unsigned int *)this + 3));
      LastError = v18;
      if ( v18 < 0 )
      {
        v8 = (unsigned int)v18;
        v9 = 1946;
        goto LABEL_24;
      }
    }
    memset(v49, 0, sizeof(v49));
    v19 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            v49,
            L"%s\\%s",
            *((_QWORD *)this + 19),
            L"ntuser.dat");
    LastError = v19;
    if ( v19 < 0 )
    {
      v20 = (unsigned int)v19;
      v21 = 1951;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)v20,
        0);
LABEL_33:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v49);
      goto LABEL_75;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl);
    v24 = v49[0];
    if ( IsEnabled && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
      McTemplateU0z_EtwEventWriteTransfer(v23, EVENT_COPY_DEFAULT_PROFILE_NEWHIVE, v49[0]);
    FileAttributesW = GetFileAttributesW(v24);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl) )
    {
      if ( FileAttributesW == -1 )
      {
        v26 = GetLastError();
        if ( (byte_1800828C1 & 2) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v27, EVENT_COPY_DEFAULT_PROFILE_HIVE_NOT_FOUND, v26);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v49);
        LastError = -2147019873;
        goto LABEL_75;
      }
    }
    else if ( FileAttributesW == -1 )
    {
      LastError = -2147019873;
      v20 = 2147947423LL;
      v21 = 1973;
      goto LABEL_32;
    }
    if ( !(unsigned int)CheckFullAccessOnFile(*((HANDLE *)this + 3), v24) )
    {
      LastError = -2147467259;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x7BE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)0x80004005LL,
        (int)"User does not have privileges on registry hive",
        0);
      goto LABEL_33;
    }
    v29 = MountRegHive(v28, *((const unsigned __int16 **)this + 6), v24, 0, *((HANDLE *)this + 3), (void **)this + 28);
    v15 = v29;
    LODWORD(hMem) = v29;
    if ( v29 < 0 )
    {
      if ( v29 == -2147023887 )
      {
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        if ( CThreadContext::ImpersonateUser((CThreadContext *)&v55, *((void **)this + 3)) >= 0
          && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
        {
          McGenEventWrite_EtwEventWriteTransfer(v30, (unsigned int)EVENT_FAILED_LOAD_1009, v31, 1, (__int64)v60);
        }
        CThreadContext::~CThreadContext((CThreadContext *)&v55);
      }
      ProfileTelemetry::DefaultHiveLoadFailure<long const &>(&hMem);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7CE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v15,
        v47);
      goto LABEL_53;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(
        v32,
        (unsigned int)EVENT_COPY_DEFAULT_PROFILE_HIVE_LOADED,
        v33,
        1,
        (__int64)v60);
    }
    VerifyCriticalKeysInUserHive(*((LPCWSTR *)this + 6));
    v34 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl);
    v36 = (const unsigned __int16 *)*((_QWORD *)this + 6);
    if ( v34 )
    {
      v37 = SetDefaultUserHiveSecurity(v36, v35);
      v15 = v37;
      if ( v37 < 0 )
      {
        if ( (byte_1800828C1 & 2) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(
            v38,
            EVENT_COPY_DEFAULT_PROFILE_SET_DEFAULT_SECURITY_FAILED,
            (unsigned int)v37);
        v39 = 2022;
        goto LABEL_62;
      }
    }
    else
    {
      v15 = SetDefaultUserHiveSecurity(v36, v35);
      if ( v15 < 0 )
      {
        v39 = 2027;
LABEL_62:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v15,
          v47);
        UnmountRegHive(v40, *((_QWORD *)this + 6), 0, (char *)this + 224);
LABEL_53:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v49);
        goto LABEL_19;
      }
    }
    if ( (*((_BYTE *)this + 8) & 4) != 0
      || (v41 = LoadChangeUserClasses(
                  *((const unsigned __int16 **)this + 6),
                  0,
                  1,
                  0,
                  (void **)this + 29,
                  *((HANDLE *)this + 3)),
          v15 = v41,
          v41 >= 0) )
    {
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v49);
      LastError = 0;
      goto LABEL_75;
    }
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
    {
      v42 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v41);
      v44 = L"???";
      if ( *v42 )
        v44 = *v42;
      McTemplateU0z_EtwEventWriteTransfer(v43, EVENT_FAIL_LOAD_CLASSES_HIVE, v44);
      v4 = 1;
    }
    if ( (v4 & 1) != 0 )
      LocalFree(hMem);
    v39 = 2037;
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x18003b26c  mov     [rsp-8+arg_10], rbx
0x18003b271  push    rbp
0x18003b272  push    rsi
0x18003b273  push    rdi
0x18003b274  push    r12
0x18003b276  push    r13
0x18003b278  push    r14
0x18003b27a  push    r15
0x18003b27c  lea     rbp, [rsp-27h]
0x18003b281  sub     rsp, 0D0h
0x18003b288  mov     rax, cs:__security_cookie
0x18003b28f  xor     rax, rsp
0x18003b292  mov     [rbp+57h+var_38], rax
0x18003b296  mov     r14, rdx
0x18003b299  mov     rdi, rcx
0x18003b29c  xor     r12d, r12d
0x18003b29f  mov     r15d, r12d
0x18003b2a2  mov     dword ptr [rbp+57h+hMem], r12d
0x18003b2a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003b2ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003b2b2  test    al, al
0x18003b2b4  jz      short loc_18003B2CE
0x18003b2b6  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18003b2bd  jge     short loc_18003B2CE
0x18003b2bf  mov     r8, r14
0x18003b2c2  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_START
0x18003b2c9  call    McTemplateU0z_EtwEventWriteTransfer
0x18003b2ce  mov     [rbp+57h+lpFileName], r12
0x18003b2d2  mov     [rbp+57h+var_88], r12
0x18003b2d6  mov     [rbp+57h+var_80], r12
0x18003b2da  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18003b2e1  mov     r8, r14
0x18003b2e4  lea     rdx, aSS_0; "%s\\%s"
0x18003b2eb  lea     rcx, [rbp+57h+lpFileName]
0x18003b2ef  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003b2f4  mov     ebx, eax
0x18003b2f6  test    eax, eax
0x18003b2f8  jns     short loc_18003B307
0x18003b2fa  mov     r9d, eax
0x18003b2fd  mov     edx, 771h
0x18003b302  jmp     loc_18003B442
0x18003b307  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18003b30b  call    cs:__imp_GetFileAttributesW
0x18003b312  nop     dword ptr [rax+rax+00h]
0x18003b317  or      r13d, 0FFFFFFFFh
0x18003b31b  cmp     eax, r13d
0x18003b31e  jnz     loc_18003B3B3
0x18003b324  call    cs:__imp_GetLastError
0x18003b32b  nop     dword ptr [rax+rax+00h]
0x18003b330  cmp     eax, 52Eh
0x18003b335  jnz     loc_18003B417
0x18003b33b  mov     [rbp+57h+var_B0], r12
0x18003b33f  mov     [rbp+57h+var_A8], r12b
0x18003b343  mov     rdx, [rdi+18h]; void *
0x18003b347  lea     rcx, [rbp+57h+var_B0]; this
0x18003b34b  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18003b350  mov     ebx, eax
0x18003b352  test    eax, eax
0x18003b354  jns     short loc_18003B37C
0x18003b356  mov     rcx, [rbp+5Fh]; this
0x18003b35a  mov     r9d, eax; char *
0x18003b35d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b364  mov     edx, 77Ah; void *
0x18003b369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b36e  lea     rcx, [rbp+57h+var_B0]; this
0x18003b372  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003b377  jmp     loc_18003B80F
0x18003b37c  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18003b380  call    cs:__imp_GetFileAttributesW
0x18003b387  nop     dword ptr [rax+rax+00h]
0x18003b38c  cmp     eax, r13d
0x18003b38f  jnz     short loc_18003B3AA
0x18003b391  mov     rcx, [rbp+5Fh]; this
0x18003b395  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b39c  mov     edx, 77Bh; void *
0x18003b3a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b3a6  mov     ebx, eax
0x18003b3a8  jmp     short loc_18003B36E
0x18003b3aa  lea     rcx, [rbp+57h+var_B0]; this
0x18003b3ae  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003b3b3  mov     eax, [rdi+8]
0x18003b3b6  and     al, 0Ch
0x18003b3b8  neg     al
0x18003b3ba  sbb     ebx, ebx
0x18003b3bc  and     ebx, 0FFFE1000h
0x18003b3c2  add     ebx, 0C8102h
0x18003b3c8  test    dword ptr [rdi+0Ch], 2000h
0x18003b3cf  jnz     short loc_18003B3D4
0x18003b3d1  or      ebx, 31h
0x18003b3d4  mov     [rbp+57h+var_A0], r12
0x18003b3d8  mov     [rbp+57h+var_98], r12b
0x18003b3dc  mov     rdx, [rdi+18h]; void *
0x18003b3e0  lea     rcx, [rbp+57h+var_A0]; this
0x18003b3e4  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18003b3e9  mov     esi, eax
0x18003b3eb  test    eax, eax
0x18003b3ed  jns     short loc_18003B457
0x18003b3ef  mov     rcx, [rbp+5Fh]; this
0x18003b3f3  mov     r9d, eax; char *
0x18003b3f6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b3fd  mov     edx, 792h; void *
0x18003b402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b407  lea     rcx, [rbp+57h+var_A0]; this
0x18003b40b  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003b410  mov     ebx, esi
0x18003b412  jmp     loc_18003B80F
0x18003b417  call    cs:__imp_GetLastError
0x18003b41e  nop     dword ptr [rax+rax+00h]
0x18003b423  mov     ebx, eax
0x18003b425  test    eax, eax
0x18003b427  jle     short loc_18003B432
0x18003b429  movzx   ebx, ax
0x18003b42c  or      ebx, 80070000h
0x18003b432  test    ebx, ebx
0x18003b434  jns     loc_18003B80F
0x18003b43a  mov     r9d, ebx; char *
0x18003b43d  mov     edx, 780h; void *
0x18003b442  mov     rcx, [rbp+5Fh]; this
0x18003b446  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b44d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b452  jmp     loc_18003B80F
0x18003b457  mov     [rsp+100h+var_D8], r12; char *
0x18003b45c  mov     [rsp+100h+var_E0], r12; int
0x18003b461  xor     r9d, r9d
0x18003b464  mov     r8d, ebx
0x18003b467  mov     rdx, [rdi+98h]
0x18003b46e  mov     rcx, r14
0x18003b471  call    cs:__imp_CopyProfileDirectoryEx2
0x18003b478  nop     dword ptr [rax+rax+00h]
0x18003b47d  test    eax, eax
0x18003b47f  jnz     short loc_18003B4A1
0x18003b481  mov     rcx, [rbp+5Fh]; this
0x18003b485  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b48c  mov     edx, 794h; void *
0x18003b491  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b496  mov     ebx, eax
0x18003b498  lea     rcx, [rbp+57h+var_A0]
0x18003b49c  jmp     loc_18003B372
0x18003b4a1  lea     rcx, [rbp+57h+var_A0]; this
0x18003b4a5  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18003b4aa  call    IsWaitForNetworkForRoamingProfilePresent
0x18003b4af  test    al, al
0x18003b4b1  jz      short loc_18003B4E1
0x18003b4b3  mov     r8d, [rdi+0Ch]
0x18003b4b7  mov     rdx, [rdi+18h]
0x18003b4bb  mov     rcx, [rdi+98h]
0x18003b4c2  call    cs:__imp_ConnectToRoamingVhdProfile
0x18003b4c9  nop     dword ptr [rax+rax+00h]
0x18003b4ce  mov     ebx, eax
0x18003b4d0  test    eax, eax
0x18003b4d2  jns     short loc_18003B4E1
0x18003b4d4  mov     r9d, eax
0x18003b4d7  mov     edx, 79Ah
0x18003b4dc  jmp     loc_18003B442
0x18003b4e1  mov     [rbp+57h+var_C8], r12
0x18003b4e5  mov     [rbp+57h+var_C0], r12
0x18003b4e9  mov     [rbp+57h+var_B8], r12
0x18003b4ed  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18003b4f4  mov     r8, [rdi+98h]
0x18003b4fb  lea     rdx, aSS_0; "%s\\%s"
0x18003b502  lea     rcx, [rbp+57h+var_C8]
0x18003b506  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003b50b  mov     ebx, eax
0x18003b50d  test    eax, eax
0x18003b50f  jns     short loc_18003B537
0x18003b511  mov     r9d, eax; char *
0x18003b514  mov     edx, 79Fh; void *
0x18003b519  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b520  mov     rcx, [rbp+5Fh]; this
0x18003b524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b529  lea     rcx, [rbp+57h+var_C8]
0x18003b52d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003b532  jmp     loc_18003B80F
0x18003b537  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18003b53e  mov     rcx, r14
0x18003b541  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003b546  mov     rbx, [rbp+57h+var_C8]
0x18003b54a  test    al, al
0x18003b54c  jz      short loc_18003B566
0x18003b54e  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18003b555  jge     short loc_18003B566
0x18003b557  mov     r8, rbx
0x18003b55a  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_NEWHIVE
0x18003b561  call    McTemplateU0z_EtwEventWriteTransfer
0x18003b566  mov     rcx, rbx; lpFileName
0x18003b569  call    cs:__imp_GetFileAttributesW
0x18003b570  nop     dword ptr [rax+rax+00h]
0x18003b575  mov     esi, eax
0x18003b577  mov     rcx, r14
0x18003b57a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003b57f  test    al, al
0x18003b581  jz      short loc_18003B5BF
0x18003b583  cmp     esi, r13d
0x18003b586  jnz     short loc_18003B5D6
0x18003b588  call    cs:__imp_GetLastError
0x18003b58f  nop     dword ptr [rax+rax+00h]
0x18003b594  test    cs:byte_1800828C1, 2
0x18003b59b  jz      short loc_18003B5AC
0x18003b59d  mov     r8d, eax
0x18003b5a0  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_HIVE_NOT_FOUND
0x18003b5a7  call    McTemplateU0q_EtwEventWriteTransfer
0x18003b5ac  lea     rcx, [rbp+57h+var_C8]
0x18003b5b0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003b5b5  mov     ebx, 8007139Fh
0x18003b5ba  jmp     loc_18003B80F
0x18003b5bf  cmp     esi, r13d
0x18003b5c2  jnz     short loc_18003B5D6
0x18003b5c4  mov     ebx, 8007139Fh
0x18003b5c9  mov     r9d, ebx
0x18003b5cc  mov     edx, 7B5h
0x18003b5d1  jmp     loc_18003B519
0x18003b5d6  mov     rdx, rbx; lpFileName
0x18003b5d9  mov     rcx, [rdi+18h]; hToken
0x18003b5dd  call    ?CheckFullAccessOnFile@@YAHPEAXPEBG@Z; CheckFullAccessOnFile(void *,ushort const *)
0x18003b5e2  test    eax, eax
0x18003b5e4  jnz     short loc_18003B614
0x18003b5e6  mov     rcx, [rbp+5Fh]; this
0x18003b5ea  lea     rax, aUserDoesNotHav; "User does not have privileges on regist"...
0x18003b5f1  mov     [rsp+100h+var_E0], rax; int
0x18003b5f6  mov     ebx, 80004005h
0x18003b5fb  mov     r9d, ebx; char *
0x18003b5fe  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b605  mov     edx, 7BEh; void *
0x18003b60a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b60f  jmp     loc_18003B529
0x18003b614  lea     rax, [rdi+0E0h]
0x18003b61b  mov     [rsp+100h+var_D8], rax; void **
0x18003b620  mov     rax, [rdi+18h]
0x18003b624  mov     [rsp+100h+var_E0], rax; void *
0x18003b629  xor     r9d, r9d; HKEY
0x18003b62c  mov     r8, rbx; unsigned __int16 *
0x18003b62f  mov     rdx, [rdi+30h]; unsigned __int16 *
0x18003b633  call    ?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z; MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)
0x18003b638  mov     esi, eax
0x18003b63a  mov     dword ptr [rbp+57h+hMem], eax
0x18003b63d  test    eax, eax
0x18003b63f  jns     loc_18003B6D2
0x18003b645  cmp     eax, 800703F1h
0x18003b64a  jnz     short loc_18003B6A3
0x18003b64c  mov     [rbp+57h+var_78], r12d
0x18003b650  mov     [rbp+57h+var_70], r12
0x18003b654  mov     [rbp+57h+var_68], r12
0x18003b658  mov     [rbp+57h+var_60], r12d
0x18003b65c  xorps   xmm0, xmm0
0x18003b65f  movdqu  [rbp+57h+var_58], xmm0
0x18003b664  mov     rdx, [rdi+18h]; void *
0x18003b668  lea     rcx, [rbp+57h+var_78]; this
0x18003b66c  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18003b671  test    eax, eax
0x18003b673  js      short loc_18003B69A
0x18003b675  mov     ebx, 1
0x18003b67a  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, bl
0x18003b680  jz      short loc_18003B69A
0x18003b682  lea     rax, [rbp+57h+var_48]
0x18003b686  mov     [rsp+100h+var_E0], rax; int
0x18003b68b  mov     r9d, ebx
0x18003b68e  lea     rdx, EVENT_FAILED_LOAD_1009
0x18003b695  call    McGenEventWrite_EtwEventWriteTransfer
0x18003b69a  lea     rcx, [rbp+57h+var_78]; this
0x18003b69e  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18003b6a3  lea     rcx, [rbp+57h+hMem]
0x18003b6a7  call    ??$DefaultHiveLoadFailure@AEBJ@ProfileTelemetry@@SAXAEBJ@Z; ProfileTelemetry::DefaultHiveLoadFailure<long const &>(long const &)
0x18003b6ac  mov     rcx, [rbp+5Fh]; this
0x18003b6b0  mov     r9d, esi; char *
0x18003b6b3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003b6ba  mov     edx, 7CEh; void *
0x18003b6bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b6c4  lea     rcx, [rbp+57h+var_C8]
0x18003b6c8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003b6cd  jmp     loc_18003B410
0x18003b6d2  mov     rcx, r14
0x18003b6d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003b6da  mov     ebx, 1
0x18003b6df  test    al, al
0x18003b6e1  jz      short loc_18003B704
0x18003b6e3  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18003b6ea  jge     short loc_18003B704
0x18003b6ec  lea     rax, [rbp+57h+var_48]
0x18003b6f0  mov     [rsp+100h+var_E0], rax; int
0x18003b6f5  mov     r9d, ebx
0x18003b6f8  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_HIVE_LOADED
0x18003b6ff  call    McGenEventWrite_EtwEventWriteTransfer
0x18003b704  mov     rcx, [rdi+30h]; lpSubKey
0x18003b708  call    ?VerifyCriticalKeysInUserHive@@YAXPEBG@Z; VerifyCriticalKeysInUserHive(ushort const *)
0x18003b70d  mov     rcx, r14
0x18003b710  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18003b715  mov     rcx, [rdi+30h]; unsigned __int16 *
0x18003b719  test    al, al
0x18003b71b  jz      short loc_18003B770
0x18003b71d  call    ?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z; SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)
0x18003b722  mov     esi, eax
0x18003b724  test    eax, eax
0x18003b726  jns     short loc_18003B782
0x18003b728  test    cs:byte_1800828C1, 2
0x18003b72f  jz      short loc_18003B740
0x18003b731  mov     r8d, eax
0x18003b734  lea     rdx, EVENT_COPY_DEFAULT_PROFILE_SET_DEFAULT_SECURITY_FAILED
0x18003b73b  call    McTemplateU0q_EtwEventWriteTransfer
0x18003b740  mov     edx, 7E6h; void *
0x18003b745  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
