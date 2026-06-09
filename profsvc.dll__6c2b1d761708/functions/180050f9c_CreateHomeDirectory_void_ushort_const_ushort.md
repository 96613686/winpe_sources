# CreateHomeDirectory(void *,ushort const *,ushort * *)

- ea: `0x180050f9c`
- end: `0x1800512ca`
- name: `?CreateHomeDirectory@@YAJPEAXPEBGPEAPEAG@Z`
- size: `814`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800054cc`

## callees

- `0x180004330`
- `0x180005dd0`
- `0x180007b58`
- `0x18000d030`
- `0x18000e1a0`
- `0x1800127a0`
- `0x180012ac8`
- `0x18002793c`
- `0x18002df68`
- `0x180030ad0`
- `0x180031060`
- `0x1800493b4`
- `0x180050f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051293`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180051139`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180051139`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800510ea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800510ea`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800511bc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800511bc`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180051216`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180051216`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x180051194`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x180051194`

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
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
               (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
               (const char *)v14,
               psidGroupa);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
LABEL_13:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
        if ( !RemoveDirectoryW(lpPathName) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x447,
            (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
    (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
    (const char *)(unsigned int)v6,
    psidGroup);
LABEL_22:
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v29);
  return v7;
}

```

## disassembly

```asm
0x180050f9c  mov     [rsp-8+arg_0], rbx
0x180050fa1  push    rbp
0x180050fa2  push    rsi
0x180050fa3  push    rdi
0x180050fa4  push    r14
0x180050fa6  push    r15
0x180050fa8  lea     rbp, [rsp-37h]
0x180050fad  sub     rsp, 0E0h
0x180050fb4  xor     r15d, r15d
0x180050fb7  mov     r14, rdx
0x180050fba  mov     rdx, rcx; void *
0x180050fbd  mov     [r8], r15
0x180050fc0  mov     rdi, rcx
0x180050fc3  mov     [rbp+57h+var_78], r15
0x180050fc7  lea     rcx, [rbp+57h+var_78]; this
0x180050fcb  mov     [rbp+57h+var_70], r15b
0x180050fcf  mov     rsi, r8
0x180050fd2  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180050fd7  mov     ebx, eax
0x180050fd9  test    eax, eax
0x180050fdb  jns     short loc_180050FFA
0x180050fdd  mov     rcx, [rbp+5Fh]; this
0x180050fe1  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180050fe8  mov     r9d, eax; char *
0x180050feb  mov     edx, 430h; void *
0x180050ff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050ff5  jmp     loc_180051270
0x180050ffa  lea     rcx, [rbp+57h+var_A8]
0x180050ffe  mov     [rbp+57h+var_90], r15
0x180051002  mov     [rbp+57h+var_88], r15
0x180051006  mov     [rbp+57h+var_80], r15
0x18005100a  mov     [rbp+57h+var_A8], r15
0x18005100e  mov     [rbp+57h+var_A0], r15
0x180051012  mov     [rbp+57h+var_98], r15
0x180051016  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18005101b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005101f  lea     rcx, [rbp+57h+var_90]
0x180051023  mov     [rbp+57h+var_A0], rbx
0x180051027  mov     [rbp+57h+var_98], rbx
0x18005102b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180051030  lea     r8, [rbp+57h+var_A8]; unsigned __int16 **
0x180051034  mov     [rbp+57h+var_88], rbx
0x180051038  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18005103c  mov     [rbp+57h+var_80], rbx
0x180051040  lea     ecx, [rbx+3]; NameFormat
0x180051043  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180051048  mov     ebx, eax
0x18005104a  test    eax, eax
0x18005104c  jns     short loc_18005107D
0x18005104e  mov     rcx, [rbp+5Fh]; this
0x180051052  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180051059  mov     r9d, eax; char *
0x18005105c  mov     edx, 435h; void *
0x180051061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051066  lea     rcx, [rbp+57h+var_A8]
0x18005106a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18005106f  lea     rcx, [rbp+57h+var_90]
0x180051073  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180051078  jmp     loc_180051270
0x18005107d  mov     rax, [rbp+57h+var_A8]
0x180051081  lea     rdx, aSSS; "%s\\%s.%s"
0x180051088  mov     r9, [rbp+57h+var_90]
0x18005108c  lea     rcx, [rbp+57h+lpPathName]
0x180051090  mov     r8, r14
0x180051093  mov     [rsp+100h+psidGroup], rax; unsigned int
0x180051098  mov     [rbp+57h+lpPathName], r15
0x18005109c  mov     [rbp+57h+var_B8], r15
0x1800510a0  mov     [rbp+57h+var_B0], r15
0x1800510a4  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800510a9  mov     ebx, eax
0x1800510ab  test    eax, eax
0x1800510ad  jns     short loc_1800510D2
0x1800510af  mov     r9d, eax; char *
0x1800510b2  mov     edx, 438h; void *
0x1800510b7  mov     rcx, [rbp+5Fh]; this
0x1800510bb  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x1800510c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800510c7  lea     rcx, [rbp+57h+lpPathName]
0x1800510cb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800510d0  jmp     short loc_180051066
0x1800510d2  mov     rcx, [rbp+57h+lpPathName]; lpPathName
0x1800510d6  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1800510da  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1800510e2  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r15
0x1800510e6  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r15
0x1800510ea  call    cs:__imp_CreateDirectoryW
0x1800510f1  nop     dword ptr [rax+rax+00h]
0x1800510f6  test    eax, eax
0x1800510f8  jz      loc_180051293
0x1800510fe  lea     rdx, [rbp+57h+pSid]; void **
0x180051102  mov     [rbp+57h+pSid], r15
0x180051106  mov     rcx, rdi; TokenHandle
0x180051109  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18005110e  mov     ebx, eax
0x180051110  test    eax, eax
0x180051112  jns     short loc_180051167
0x180051114  mov     rcx, [rbp+5Fh]; this
0x180051118  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18005111f  mov     r9d, eax; char *
0x180051122  mov     edx, 44Eh; void *
0x180051127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005112c  lea     rcx, [rbp+57h+pSid]
0x180051130  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051135  mov     rcx, [rbp+57h+lpPathName]; lpPathName
0x180051139  call    cs:__imp_RemoveDirectoryW
0x180051140  nop     dword ptr [rax+rax+00h]
0x180051145  test    eax, eax
0x180051147  jnz     loc_1800510C7
0x18005114d  mov     rcx, [rbp+5Fh]; this
0x180051151  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180051158  mov     edx, 447h; void *
0x18005115d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180051162  jmp     loc_1800510C7
0x180051167  mov     rdx, [rbp+57h+pSid]; pSid
0x18005116b  lea     rcx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x18005116f  xorps   xmm0, xmm0
0x180051172  mov     ebx, 1
0x180051177  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18005117b  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x180051182  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], ebx
0x180051185  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18005118c  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180051190  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180051194  call    cs:__imp_BuildTrusteeWithSidW
0x18005119b  nop     dword ptr [rax+rax+00h]
0x1800511a0  xor     edx, edx
0x1800511a2  mov     [rbp+57h+NewAcl], r15
0x1800511a6  lea     rcx, [rbp+57h+NewAcl]
0x1800511aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x1800511af  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800511b3  xor     r8d, r8d; OldAcl
0x1800511b6  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800511ba  mov     ecx, ebx; cCountOfExplicitEntries
0x1800511bc  call    cs:__imp_SetEntriesInAclW
0x1800511c3  nop     dword ptr [rax+rax+00h]
0x1800511c8  test    eax, eax
0x1800511ca  jz      short loc_1800511F4
0x1800511cc  mov     edx, 45Ah; void *
0x1800511d1  mov     rcx, [rbp+5Fh]; this
0x1800511d5  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x1800511dc  mov     r9d, eax; char *
0x1800511df  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800511e4  lea     rcx, [rbp+57h+NewAcl]
0x1800511e8  mov     ebx, eax
0x1800511ea  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800511ef  jmp     loc_18005112C
0x1800511f4  mov     rax, [rbp+57h+NewAcl]
0x1800511f8  xor     r9d, r9d; psidOwner
0x1800511fb  mov     rcx, [rbp+57h+lpPathName]; pObjectName
0x1800511ff  mov     r8d, 20000004h; SecurityInfo
0x180051205  mov     [rsp+100h+pSacl], r15; pSacl
0x18005120a  mov     edx, ebx; ObjectType
0x18005120c  mov     [rsp+100h+pDacl], rax; pDacl
0x180051211  mov     [rsp+100h+psidGroup], r15; psidGroup
0x180051216  call    cs:__imp_SetNamedSecurityInfoW
0x18005121d  nop     dword ptr [rax+rax+00h]
0x180051222  test    eax, eax
0x180051224  jz      short loc_18005122D
0x180051226  mov     edx, 464h
0x18005122b  jmp     short loc_1800511D1
0x18005122d  lea     rcx, [rbp+57h+NewAcl]
0x180051231  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180051236  lea     rcx, [rbp+57h+pSid]
0x18005123a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005123f  mov     rax, [rbp+57h+lpPathName]
0x180051243  lea     rcx, [rbp+57h+lpPathName]
0x180051247  mov     [rsi], rax
0x18005124a  mov     [rbp+57h+lpPathName], r15
0x18005124e  mov     [rbp+57h+var_B0], r15
0x180051252  mov     [rbp+57h+var_B8], r15
0x180051256  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18005125b  lea     rcx, [rbp+57h+var_A8]
0x18005125f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180051264  lea     rcx, [rbp+57h+var_90]
0x180051268  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18005126d  mov     ebx, r15d
0x180051270  lea     rcx, [rbp+57h+var_78]; this
0x180051274  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180051279  mov     eax, ebx
0x18005127b  mov     rbx, [rsp+100h+arg_0]
0x180051283  add     rsp, 0E0h
0x18005128a  pop     r15
0x18005128c  pop     r14
0x18005128e  pop     rdi
0x18005128f  pop     rsi
0x180051290  pop     rbp
0x180051291  retn
0x180051293  call    cs:__imp_GetLastError
0x18005129a  nop     dword ptr [rax+rax+00h]
0x18005129f  mov     ebx, eax
0x1800512a1  cmp     eax, 0B7h
0x1800512a6  jz      short loc_18005123F
0x1800512a8  test    eax, eax
0x1800512aa  jle     short loc_1800512B5
0x1800512ac  movzx   ebx, ax
0x1800512af  or      ebx, 80070000h
0x1800512b5  test    ebx, ebx
0x1800512b7  jns     loc_1800510C7
0x1800512bd  mov     r9d, ebx
0x1800512c0  mov     edx, 46Ch
0x1800512c5  jmp     loc_1800510B7
```
