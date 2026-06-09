# CUserProfile::AddCurrentUserToACL(void)

- ea: `0x18002db58`
- end: `0x18002ddfc`
- name: `?AddCurrentUserToACL@CUserProfile@@IEAAJXZ`
- size: `676`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003840c`

## callees

- `0x18001e308`
- `0x18001f060`
- `0x180025254`
- `0x180028de4`
- `0x18002db38`
- `0x18002db58`
- `0x18002de04`
- `0x18002e648`
- `0x18003a730`
- `0x1800455c8`
- `0x180047258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ddc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ddc9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002dc96`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002dc96`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002dd87`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002dd87`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002dd26`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002dd26`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002dc3a`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002dc3a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002dbca`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002dbca`

## string_xrefs

- `0x18002dbdb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002dc4b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002dca7`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002dd3c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002db81`: `AddCurrentUserToACL`

## pseudocode

```c
__int64 __fastcall CUserProfile::AddCurrentUserToACL(LPCWSTR *this)
{
  unsigned int v2; // eax
  unsigned int LastError; // ebx
  DWORD SecurityInfo; // eax
  const WCHAR *v5; // rcx
  const char *v6; // r9
  DWORD v7; // eax
  __int64 v8; // rdx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  PACL OldAcl; // [rsp+60h] [rbp-A0h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v18[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v18);
  v18[0] = &ProfileTelemetry::AddCurrentUserToACL::`vftable';
  ProfileTelemetry::AddCurrentUserToACL::StartActivity((ProfileTelemetry::AddCurrentUserToACL *)v18);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v2 = RegOpenKeyW(HKEY_USERS, this[6], &phkResult);
  if ( v2 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xC07,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  (const char *)v2,
                  ppsidGroup);
    goto LABEL_6;
  }
  OldAcl = 0;
  ppSecurityDescriptor = 0;
  SecurityInfo = GetSecurityInfo(phkResult, SE_REGISTRY_KEY, 4u, 0, 0, &OldAcl, 0, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xC0B,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  (const char *)SecurityInfo,
                  ppsidGroupa);
LABEL_5:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
LABEL_6:
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_19;
  }
  v5 = this[6];
  Sid = 0;
  if ( !ConvertStringSidToSidW(v5, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC0E,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  v6);
LABEL_10:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    goto LABEL_5;
  }
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  pListOfExplicitEntries.grfInheritance = 2;
  pListOfExplicitEntries.grfAccessPermissions = 983103;
  NewAcl = 0;
  wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
    &NewAcl,
    0);
  v7 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
  if ( v7 )
  {
    v8 = 3097;
LABEL_13:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  (const char *)v7,
                  ppsidGroupa);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&NewAcl);
    goto LABEL_10;
  }
  v7 = SetSecurityInfo(phkResult, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
  if ( v7 )
  {
    v8 = 3098;
    goto LABEL_13;
  }
  wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&NewAcl);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
  if ( phkResult )
    RegCloseKey(phkResult);
  LastError = 0;
LABEL_19:
  ProfileTelemetry::AddCurrentUserToACL::~AddCurrentUserToACL((ProfileTelemetry::AddCurrentUserToACL *)v18);
  return LastError;
}

```

## disassembly

```asm
0x18002db58  mov     [rsp-8+arg_8], rbx
0x18002db5d  push    rbp
0x18002db5e  lea     rbp, [rsp-100h]
0x18002db66  sub     rsp, 200h
0x18002db6d  mov     rax, cs:__security_cookie
0x18002db74  xor     rax, rsp
0x18002db77  mov     [rbp+100h+var_10], rax
0x18002db7e  mov     rbx, rcx
0x18002db81  lea     rdx, aAddcurrentuser; "AddCurrentUserToACL"
0x18002db88  lea     rcx, [rbp+100h+var_160]; struct wil::details::IFailureCallback *
0x18002db8c  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002db91  lea     rax, ??_7AddCurrentUserToACL@ProfileTelemetry@@6B@; const ProfileTelemetry::AddCurrentUserToACL::`vftable'
0x18002db98  lea     rcx, [rbp+100h+var_160]; this
0x18002db9c  mov     [rbp+100h+var_160], rax
0x18002dba0  call    ?StartActivity@AddCurrentUserToACL@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::AddCurrentUserToACL::StartActivity(void)
0x18002dba5  xor     edx, edx
0x18002dba7  mov     [rsp+200h+phkResult], 0
0x18002dbb0  lea     rcx, [rsp+200h+phkResult]
0x18002dbb5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002dbba  mov     rdx, [rbx+30h]; lpSubKey
0x18002dbbe  lea     r8, [rsp+200h+phkResult]; phkResult
0x18002dbc3  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002dbca  call    cs:__imp_RegOpenKeyW
0x18002dbd0  test    eax, eax
0x18002dbd2  jz      short loc_18002DBF3
0x18002dbd4  mov     rcx, [rbp+108h]; this
0x18002dbdb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dbe2  mov     r9d, eax; char *
0x18002dbe5  mov     edx, 0C07h; void *
0x18002dbea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002dbef  mov     ebx, eax
0x18002dbf1  jmp     short loc_18002DC6B
0x18002dbf3  mov     rcx, [rsp+200h+phkResult]; handle
0x18002dbf8  lea     rax, [rsp+200h+var_1A8]
0x18002dbfd  mov     [rsp+200h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002dc02  xor     r9d, r9d; ppsidOwner
0x18002dc05  lea     rax, [rsp+200h+OldAcl]
0x18002dc0a  mov     [rsp+200h+ppSacl], 0; ppSacl
0x18002dc13  mov     [rsp+200h+ppDacl], rax; ppDacl
0x18002dc18  mov     [rsp+200h+OldAcl], 0
0x18002dc21  lea     edx, [r9+4]; ObjectType
0x18002dc25  mov     [rsp+200h+var_1A8], 0
0x18002dc2e  mov     r8d, edx; SecurityInfo
0x18002dc31  mov     [rsp+200h+ppsidGroup], 0; unsigned int
0x18002dc3a  call    cs:__imp_GetSecurityInfo
0x18002dc40  test    eax, eax
0x18002dc42  jz      short loc_18002DC84
0x18002dc44  mov     rcx, [rbp+108h]; this
0x18002dc4b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dc52  mov     r9d, eax; char *
0x18002dc55  mov     edx, 0C0Bh; void *
0x18002dc5a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002dc5f  mov     ebx, eax
0x18002dc61  lea     rcx, [rsp+200h+var_1A8]
0x18002dc66  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002dc6b  mov     rcx, [rsp+200h+phkResult]; hKey
0x18002dc70  test    rcx, rcx
0x18002dc73  jz      loc_18002DDD1
0x18002dc79  call    cs:__imp_RegCloseKey
0x18002dc7f  jmp     loc_18002DDD1
0x18002dc84  mov     rcx, [rbx+30h]; StringSid
0x18002dc88  lea     rdx, [rsp+200h+Sid]; Sid
0x18002dc8d  mov     [rsp+200h+Sid], 0
0x18002dc96  call    cs:__imp_ConvertStringSidToSidW
0x18002dc9c  test    eax, eax
0x18002dc9e  jnz     short loc_18002DCC6
0x18002dca0  mov     rcx, [rbp+108h]; this
0x18002dca7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dcae  mov     edx, 0C0Eh; void *
0x18002dcb3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dcb8  mov     ebx, eax
0x18002dcba  lea     rcx, [rsp+200h+Sid]
0x18002dcbf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002dcc4  jmp     short loc_18002DC61
0x18002dcc6  mov     rax, [rsp+200h+Sid]
0x18002dccb  lea     rcx, [rsp+200h+NewAcl]
0x18002dcd0  xorps   xmm0, xmm0
0x18002dcd3  mov     [rbp+100h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18002dcd7  mov     ebx, 1
0x18002dcdc  mov     qword ptr [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18002dce4  xor     edx, edx
0x18002dce6  mov     [rsp+200h+pListOfExplicitEntries.grfAccessMode], ebx
0x18002dcea  movdqu  xmmword ptr [rsp+200h+pListOfExplicitEntries+0Ch], xmm0
0x18002dcf0  mov     [rsp+200h+pListOfExplicitEntries.grfInheritance], 2
0x18002dcf8  mov     [rsp+200h+pListOfExplicitEntries.grfAccessPermissions], 0F003Fh
0x18002dd00  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x18002dd07  mov     [rsp+200h+NewAcl], 0
0x18002dd10  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x18002dd15  mov     r8, [rsp+200h+OldAcl]; OldAcl
0x18002dd1a  lea     r9, [rsp+200h+NewAcl]; NewAcl
0x18002dd1f  lea     rdx, [rsp+200h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002dd24  mov     ecx, ebx; cCountOfExplicitEntries
0x18002dd26  call    cs:__imp_SetEntriesInAclW
0x18002dd2c  test    eax, eax
0x18002dd2e  jz      short loc_18002DD5C
0x18002dd30  mov     edx, 0C19h; void *
0x18002dd35  mov     rcx, [rbp+108h]; this
0x18002dd3c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dd43  mov     r9d, eax; char *
0x18002dd46  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002dd4b  lea     rcx, [rsp+200h+NewAcl]
0x18002dd50  mov     ebx, eax
0x18002dd52  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002dd57  jmp     loc_18002DCBA
0x18002dd5c  mov     rax, [rsp+200h+NewAcl]
0x18002dd61  xor     r9d, r9d; psidOwner
0x18002dd64  mov     rcx, [rsp+200h+phkResult]; handle
0x18002dd69  mov     [rsp+200h+ppSacl], 0; pSacl
0x18002dd72  mov     [rsp+200h+ppDacl], rax; pDacl
0x18002dd77  lea     edx, [r9+4]; ObjectType
0x18002dd7b  mov     [rsp+200h+ppsidGroup], 0; psidGroup
0x18002dd84  mov     r8d, edx; SecurityInfo
0x18002dd87  call    cs:__imp_SetSecurityInfo
0x18002dd8d  test    eax, eax
0x18002dd8f  jz      short loc_18002DD98
0x18002dd91  mov     edx, 0C1Ah
0x18002dd96  jmp     short loc_18002DD35
0x18002dd98  lea     rcx, [rbp+100h+var_160]
0x18002dd9c  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002dda1  lea     rcx, [rsp+200h+NewAcl]
0x18002dda6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002ddab  lea     rcx, [rsp+200h+Sid]
0x18002ddb0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002ddb5  lea     rcx, [rsp+200h+var_1A8]
0x18002ddba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002ddbf  mov     rcx, [rsp+200h+phkResult]; hKey
0x18002ddc4  test    rcx, rcx
0x18002ddc7  jz      short loc_18002DDCF
0x18002ddc9  call    cs:__imp_RegCloseKey
0x18002ddcf  xor     ebx, ebx
0x18002ddd1  lea     rcx, [rbp+100h+var_160]; this
0x18002ddd5  call    ??1AddCurrentUserToACL@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::AddCurrentUserToACL::~AddCurrentUserToACL(void)
0x18002ddda  mov     eax, ebx
0x18002dddc  mov     rcx, [rbp+100h+var_10]
0x18002dde3  xor     rcx, rsp; StackCookie
0x18002dde6  call    __security_check_cookie
0x18002ddeb  mov     rbx, [rsp+200h+arg_8]
0x18002ddf3  add     rsp, 200h
0x18002ddfa  pop     rbp
0x18002ddfb  retn
```
