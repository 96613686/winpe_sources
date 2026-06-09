# CreateHomeDirectory(void *,ushort const *,ushort * *)

- ea: `0x18004debc`
- end: `0x18004e1c1`
- name: `?CreateHomeDirectory@@YAJPEAXPEBGPEAPEAG@Z`
- size: `773`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, LPCWSTR *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007aa8`

## callees

- `0x1800036e0`
- `0x1800049e0`
- `0x180008200`
- `0x18000a320`
- `0x180010f30`
- `0x1800111a0`
- `0x180025254`
- `0x18002541c`
- `0x18002d2d8`
- `0x18002e648`
- `0x180030558`
- `0x180047258`
- `0x18004debc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e190`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004e053`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004e053`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004e00a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004e00a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004e0c6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004e0c6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004e11a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004e11a`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18004e0a4`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18004e0a4`

## string_xrefs

- `0x18004df01`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18004df72`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18004dfdb`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18004e032`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18004e061`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18004e0d9`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

## pseudocode

```c
__int64 __fastcall CreateHomeDirectory(void *a1, const unsigned __int16 *a2, LPCWSTR *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int UserNameAndDomain; // eax
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int UserSid; // eax
  const char *v13; // r9
  DWORD v14; // eax
  __int64 v15; // rdx
  signed int LastError; // eax
  int psidGroup; // [rsp+20h] [rbp-89h]
  unsigned int psidGroupa; // [rsp+20h] [rbp-89h]
  LPCWSTR lpPathName; // [rsp+40h] [rbp-69h] BYREF
  __int64 v21; // [rsp+48h] [rbp-61h]
  __int64 v22; // [rsp+50h] [rbp-59h]
  unsigned __int16 *v23; // [rsp+58h] [rbp-51h] BYREF
  __int64 v24; // [rsp+60h] [rbp-49h]
  __int64 v25; // [rsp+68h] [rbp-41h]
  unsigned __int16 *v26; // [rsp+70h] [rbp-39h] BYREF
  __int64 v27; // [rsp+78h] [rbp-31h]
  __int64 v28; // [rsp+80h] [rbp-29h]
  __int64 v29; // [rsp+88h] [rbp-21h] BYREF
  char v30; // [rsp+90h] [rbp-19h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-11h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  PACL NewAcl; // [rsp+120h] [rbp+77h] BYREF
  PSID pSid; // [rsp+128h] [rbp+7Fh] BYREF

  *a3 = 0;
  v29 = 0;
  v30 = 0;
  v6 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v29, a1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v23);
    v24 = -1;
    v25 = -1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v26);
    v27 = -1;
    v28 = -1;
    UserNameAndDomain = GetUserNameAndDomain(NameSamCompatible, &v26, &v23);
    v7 = UserNameAndDomain;
    if ( UserNameAndDomain < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x435,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)UserNameAndDomain,
        psidGroup);
LABEL_5:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v23);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v26);
      goto LABEL_22;
    }
    psidGroupa = (unsigned int)v23;
    lpPathName = 0;
    v21 = 0;
    v22 = 0;
    v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
           &lpPathName,
           L"%s\\%s.%s",
           a2,
           v26);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v11 = 1080;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)v10,
        psidGroupa);
LABEL_9:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpPathName);
      goto LABEL_5;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = 0;
    if ( CreateDirectoryW(lpPathName, &SecurityAttributes) )
    {
      pSid = 0;
      UserSid = GetUserSid(a1, &pSid);
      v7 = UserSid;
      if ( UserSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44E,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)UserSid,
          psidGroupa);
        goto LABEL_13;
      }
      memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
      pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
      pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
      pListOfExplicitEntries.grfInheritance = 3;
      BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, pSid);
      NewAcl = 0;
      wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
        &NewAcl,
        0);
      v14 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
      if ( v14 )
      {
        v15 = 1114;
LABEL_17:
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
               (const char *)v14,
               psidGroupa);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
LABEL_13:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
        if ( !RemoveDirectoryW(lpPathName) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x447,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
            v13);
        goto LABEL_9;
      }
      v14 = SetNamedSecurityInfoW((LPWSTR)lpPathName, SE_FILE_OBJECT, 0x20000004u, 0, 0, NewAcl, 0);
      if ( v14 )
      {
        v15 = 1124;
        goto LABEL_17;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( (v7 & 0x80000000) == 0 )
          goto LABEL_9;
        v10 = v7;
        v11 = 1132;
        goto LABEL_8;
      }
    }
    *a3 = lpPathName;
    lpPathName = 0;
    v22 = 0;
    v21 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpPathName);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v23);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v26);
    v7 = 0;
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x430,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
    (const char *)(unsigned int)v6,
    psidGroup);
LABEL_22:
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v29);
  return v7;
}

```

## disassembly

```asm
0x18004debc  mov     [rsp-8+arg_0], rbx
0x18004dec1  push    rbp
0x18004dec2  push    rsi
0x18004dec3  push    rdi
0x18004dec4  push    r14
0x18004dec6  push    r15
0x18004dec8  lea     rbp, [rsp-37h]
0x18004decd  sub     rsp, 0E0h
0x18004ded4  xor     r15d, r15d
0x18004ded7  mov     r14, rdx
0x18004deda  mov     rdx, rcx; void *
0x18004dedd  mov     [r8], r15
0x18004dee0  mov     rdi, rcx
0x18004dee3  mov     [rbp+57h+var_78], r15
0x18004dee7  lea     rcx, [rbp+57h+var_78]; this
0x18004deeb  mov     [rbp+57h+var_70], r15b
0x18004deef  mov     rsi, r8
0x18004def2  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18004def7  mov     ebx, eax
0x18004def9  test    eax, eax
0x18004defb  jns     short loc_18004DF1A
0x18004defd  mov     rcx, [rbp+5Fh]; this
0x18004df01  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004df08  mov     r9d, eax; char *
0x18004df0b  mov     edx, 430h; void *
0x18004df10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004df15  jmp     loc_18004E16E
0x18004df1a  lea     rcx, [rbp+57h+var_A8]
0x18004df1e  mov     [rbp+57h+var_90], r15
0x18004df22  mov     [rbp+57h+var_88], r15
0x18004df26  mov     [rbp+57h+var_80], r15
0x18004df2a  mov     [rbp+57h+var_A8], r15
0x18004df2e  mov     [rbp+57h+var_A0], r15
0x18004df32  mov     [rbp+57h+var_98], r15
0x18004df36  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004df3b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004df3f  lea     rcx, [rbp+57h+var_90]
0x18004df43  mov     [rbp+57h+var_A0], rbx
0x18004df47  mov     [rbp+57h+var_98], rbx
0x18004df4b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004df50  lea     r8, [rbp+57h+var_A8]; unsigned __int16 **
0x18004df54  mov     [rbp+57h+var_88], rbx
0x18004df58  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18004df5c  mov     [rbp+57h+var_80], rbx
0x18004df60  lea     ecx, [rbx+3]; NameFormat
0x18004df63  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x18004df68  mov     ebx, eax
0x18004df6a  test    eax, eax
0x18004df6c  jns     short loc_18004DF9D
0x18004df6e  mov     rcx, [rbp+5Fh]; this
0x18004df72  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004df79  mov     r9d, eax; char *
0x18004df7c  mov     edx, 435h; void *
0x18004df81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004df86  lea     rcx, [rbp+57h+var_A8]
0x18004df8a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004df8f  lea     rcx, [rbp+57h+var_90]
0x18004df93  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004df98  jmp     loc_18004E16E
0x18004df9d  mov     rax, [rbp+57h+var_A8]
0x18004dfa1  lea     rdx, aSSS; "%s\\%s.%s"
0x18004dfa8  mov     r9, [rbp+57h+var_90]
0x18004dfac  lea     rcx, [rbp+57h+lpPathName]
0x18004dfb0  mov     r8, r14
0x18004dfb3  mov     [rsp+100h+psidGroup], rax; unsigned int
0x18004dfb8  mov     [rbp+57h+lpPathName], r15
0x18004dfbc  mov     [rbp+57h+var_B8], r15
0x18004dfc0  mov     [rbp+57h+var_B0], r15
0x18004dfc4  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004dfc9  mov     ebx, eax
0x18004dfcb  test    eax, eax
0x18004dfcd  jns     short loc_18004DFF2
0x18004dfcf  mov     r9d, eax; char *
0x18004dfd2  mov     edx, 438h; void *
0x18004dfd7  mov     rcx, [rbp+5Fh]; this
0x18004dfdb  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004dfe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dfe7  lea     rcx, [rbp+57h+lpPathName]
0x18004dfeb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004dff0  jmp     short loc_18004DF86
0x18004dff2  mov     rcx, [rbp+57h+lpPathName]; lpPathName
0x18004dff6  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18004dffa  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18004e002  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r15
0x18004e006  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r15
0x18004e00a  call    cs:__imp_CreateDirectoryW
0x18004e010  test    eax, eax
0x18004e012  jz      loc_18004E190
0x18004e018  lea     rdx, [rbp+57h+pSid]; void **
0x18004e01c  mov     [rbp+57h+pSid], r15
0x18004e020  mov     rcx, rdi; TokenHandle
0x18004e023  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18004e028  mov     ebx, eax
0x18004e02a  test    eax, eax
0x18004e02c  jns     short loc_18004E077
0x18004e02e  mov     rcx, [rbp+5Fh]; this
0x18004e032  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e039  mov     r9d, eax; char *
0x18004e03c  mov     edx, 44Eh; void *
0x18004e041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e046  lea     rcx, [rbp+57h+pSid]
0x18004e04a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004e04f  mov     rcx, [rbp+57h+lpPathName]; lpPathName
0x18004e053  call    cs:__imp_RemoveDirectoryW
0x18004e059  test    eax, eax
0x18004e05b  jnz     short loc_18004DFE7
0x18004e05d  mov     rcx, [rbp+5Fh]; this
0x18004e061  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e068  mov     edx, 447h; void *
0x18004e06d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004e072  jmp     loc_18004DFE7
0x18004e077  mov     rdx, [rbp+57h+pSid]; pSid
0x18004e07b  lea     rcx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x18004e07f  xorps   xmm0, xmm0
0x18004e082  mov     ebx, 1
0x18004e087  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18004e08b  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18004e092  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], ebx
0x18004e095  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18004e09c  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18004e0a0  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18004e0a4  call    cs:__imp_BuildTrusteeWithSidW
0x18004e0aa  xor     edx, edx
0x18004e0ac  mov     [rbp+57h+NewAcl], r15
0x18004e0b0  lea     rcx, [rbp+57h+NewAcl]
0x18004e0b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x18004e0b9  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18004e0bd  xor     r8d, r8d; OldAcl
0x18004e0c0  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004e0c4  mov     ecx, ebx; cCountOfExplicitEntries
0x18004e0c6  call    cs:__imp_SetEntriesInAclW
0x18004e0cc  test    eax, eax
0x18004e0ce  jz      short loc_18004E0F8
0x18004e0d0  mov     edx, 45Ah; void *
0x18004e0d5  mov     rcx, [rbp+5Fh]; this
0x18004e0d9  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e0e0  mov     r9d, eax; char *
0x18004e0e3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e0e8  lea     rcx, [rbp+57h+NewAcl]
0x18004e0ec  mov     ebx, eax
0x18004e0ee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e0f3  jmp     loc_18004E046
0x18004e0f8  mov     rax, [rbp+57h+NewAcl]
0x18004e0fc  xor     r9d, r9d; psidOwner
0x18004e0ff  mov     rcx, [rbp+57h+lpPathName]; pObjectName
0x18004e103  mov     r8d, 20000004h; SecurityInfo
0x18004e109  mov     [rsp+100h+pSacl], r15; pSacl
0x18004e10e  mov     edx, ebx; ObjectType
0x18004e110  mov     [rsp+100h+pDacl], rax; pDacl
0x18004e115  mov     [rsp+100h+psidGroup], r15; psidGroup
0x18004e11a  call    cs:__imp_SetNamedSecurityInfoW
0x18004e120  test    eax, eax
0x18004e122  jz      short loc_18004E12B
0x18004e124  mov     edx, 464h
0x18004e129  jmp     short loc_18004E0D5
0x18004e12b  lea     rcx, [rbp+57h+NewAcl]
0x18004e12f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e134  lea     rcx, [rbp+57h+pSid]
0x18004e138  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004e13d  mov     rax, [rbp+57h+lpPathName]
0x18004e141  lea     rcx, [rbp+57h+lpPathName]
0x18004e145  mov     [rsi], rax
0x18004e148  mov     [rbp+57h+lpPathName], r15
0x18004e14c  mov     [rbp+57h+var_B0], r15
0x18004e150  mov     [rbp+57h+var_B8], r15
0x18004e154  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004e159  lea     rcx, [rbp+57h+var_A8]
0x18004e15d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004e162  lea     rcx, [rbp+57h+var_90]
0x18004e166  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004e16b  mov     ebx, r15d
0x18004e16e  lea     rcx, [rbp+57h+var_78]; this
0x18004e172  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18004e177  mov     eax, ebx
0x18004e179  mov     rbx, [rsp+100h+arg_0]
0x18004e181  add     rsp, 0E0h
0x18004e188  pop     r15
0x18004e18a  pop     r14
0x18004e18c  pop     rdi
0x18004e18d  pop     rsi
0x18004e18e  pop     rbp
0x18004e18f  retn
0x18004e190  call    cs:__imp_GetLastError
0x18004e196  mov     ebx, eax
0x18004e198  cmp     eax, 0B7h
0x18004e19d  jz      short loc_18004E13D
0x18004e19f  test    eax, eax
0x18004e1a1  jle     short loc_18004E1AC
0x18004e1a3  movzx   ebx, ax
0x18004e1a6  or      ebx, 80070000h
0x18004e1ac  test    ebx, ebx
0x18004e1ae  jns     loc_18004DFE7
0x18004e1b4  mov     r9d, ebx
0x18004e1b7  mov     edx, 46Ch
0x18004e1bc  jmp     loc_18004DFD7
```
