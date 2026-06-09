# CUserProfile::AddCurrentUserToACL(void)

- ea: `0x18002d000`
- end: `0x18002d2ac`
- name: `?AddCurrentUserToACL@CUserProfile@@IEAAJXZ`
- size: `684`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003a19c`

## callees

- `0x1800130d0`
- `0x180013770`
- `0x180018430`
- `0x18002793c`
- `0x18002adcc`
- `0x18002d000`
- `0x18002df48`
- `0x18002e098`
- `0x180031060`
- `0x18003bc70`
- `0x180047588`
- `0x1800493b4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d139`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d139`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002d236`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002d236`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002d1cf`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002d1cf`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002d0eb`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002d0eb`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d072`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d072`

## string_xrefs

- `0x18002d089`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002d102`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002d150`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002d1eb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002d029`: `AddCurrentUserToACL`

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
  PACL NewAcl; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
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
  }
  else
  {
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
    }
    else
    {
      v5 = this[6];
      Sid = 0;
      if ( ConvertStringSidToSidW(v5, &Sid) )
      {
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
        }
        else
        {
          v7 = SetSecurityInfo(phkResult, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
          if ( !v7 )
          {
            wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
            LastError = 0;
            goto LABEL_15;
          }
          v8 = 3098;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v8,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                      (const char *)v7,
                      ppsidGroupa);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xC0E,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                      v6);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  ProfileTelemetry::AddCurrentUserToACL::~AddCurrentUserToACL((ProfileTelemetry::AddCurrentUserToACL *)v18);
  return LastError;
}

```

## disassembly

```asm
0x18002d000  mov     [rsp-8+arg_8], rbx
0x18002d005  push    rbp
0x18002d006  lea     rbp, [rsp-100h]
0x18002d00e  sub     rsp, 200h
0x18002d015  mov     rax, cs:__security_cookie
0x18002d01c  xor     rax, rsp
0x18002d01f  mov     [rbp+100h+var_10], rax
0x18002d026  mov     rbx, rcx
0x18002d029  lea     rdx, aAddcurrentuser; "AddCurrentUserToACL"
0x18002d030  lea     rcx, [rbp+100h+var_160]; struct wil::details::IFailureCallback *
0x18002d034  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002d039  lea     rax, ??_7AddCurrentUserToACL@ProfileTelemetry@@6B@; const ProfileTelemetry::AddCurrentUserToACL::`vftable'
0x18002d040  lea     rcx, [rbp+100h+var_160]; this
0x18002d044  mov     [rbp+100h+var_160], rax
0x18002d048  call    ?StartActivity@AddCurrentUserToACL@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::AddCurrentUserToACL::StartActivity(void)
0x18002d04d  xor     edx, edx
0x18002d04f  mov     [rsp+200h+phkResult], 0
0x18002d058  lea     rcx, [rsp+200h+phkResult]
0x18002d05d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d062  mov     rdx, [rbx+30h]; lpSubKey
0x18002d066  lea     r8, [rsp+200h+phkResult]; phkResult
0x18002d06b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002d072  call    cs:__imp_RegOpenKeyW
0x18002d079  nop     dword ptr [rax+rax+00h]
0x18002d07e  test    eax, eax
0x18002d080  jz      short loc_18002D0A4
0x18002d082  mov     rcx, [rbp+108h]; this
0x18002d089  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d090  mov     r9d, eax; char *
0x18002d093  mov     edx, 0C07h; void *
0x18002d098  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d09d  mov     ebx, eax
0x18002d09f  jmp     loc_18002D276
0x18002d0a4  mov     rcx, [rsp+200h+phkResult]; handle
0x18002d0a9  lea     rax, [rsp+200h+var_1B0]
0x18002d0ae  mov     [rsp+200h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002d0b3  xor     r9d, r9d; ppsidOwner
0x18002d0b6  lea     rax, [rsp+200h+OldAcl]
0x18002d0bb  mov     [rsp+200h+ppSacl], 0; ppSacl
0x18002d0c4  mov     [rsp+200h+ppDacl], rax; ppDacl
0x18002d0c9  mov     [rsp+200h+OldAcl], 0
0x18002d0d2  lea     edx, [r9+4]; ObjectType
0x18002d0d6  mov     [rsp+200h+var_1B0], 0
0x18002d0df  mov     r8d, edx; SecurityInfo
0x18002d0e2  mov     [rsp+200h+ppsidGroup], 0; unsigned int
0x18002d0eb  call    cs:__imp_GetSecurityInfo
0x18002d0f2  nop     dword ptr [rax+rax+00h]
0x18002d0f7  test    eax, eax
0x18002d0f9  jz      short loc_18002D127
0x18002d0fb  mov     rcx, [rbp+108h]; this
0x18002d102  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d109  mov     r9d, eax; char *
0x18002d10c  mov     edx, 0C0Bh; void *
0x18002d111  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d116  mov     ebx, eax
0x18002d118  lea     rcx, [rsp+200h+var_1B0]
0x18002d11d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d122  jmp     loc_18002D276
0x18002d127  mov     rcx, [rbx+30h]; StringSid
0x18002d12b  lea     rdx, [rsp+200h+Sid]; Sid
0x18002d130  mov     [rsp+200h+Sid], 0
0x18002d139  call    cs:__imp_ConvertStringSidToSidW
0x18002d140  nop     dword ptr [rax+rax+00h]
0x18002d145  test    eax, eax
0x18002d147  jnz     short loc_18002D16F
0x18002d149  mov     rcx, [rbp+108h]; this
0x18002d150  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d157  mov     edx, 0C0Eh; void *
0x18002d15c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d161  mov     ebx, eax
0x18002d163  lea     rcx, [rsp+200h+Sid]
0x18002d168  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d16d  jmp     short loc_18002D118
0x18002d16f  mov     rax, [rsp+200h+Sid]
0x18002d174  lea     rcx, [rsp+200h+NewAcl]
0x18002d179  xorps   xmm0, xmm0
0x18002d17c  mov     [rbp+100h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18002d180  mov     ebx, 1
0x18002d185  mov     qword ptr [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18002d18d  xor     edx, edx
0x18002d18f  mov     [rsp+200h+pListOfExplicitEntries.grfAccessMode], ebx
0x18002d193  movdqu  xmmword ptr [rsp+200h+pListOfExplicitEntries+0Ch], xmm0
0x18002d199  mov     [rsp+200h+pListOfExplicitEntries.grfInheritance], 2
0x18002d1a1  mov     [rsp+200h+pListOfExplicitEntries.grfAccessPermissions], 0F003Fh
0x18002d1a9  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x18002d1b0  mov     [rsp+200h+NewAcl], 0
0x18002d1b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x18002d1be  mov     r8, [rsp+200h+OldAcl]; OldAcl
0x18002d1c3  lea     r9, [rsp+200h+NewAcl]; NewAcl
0x18002d1c8  lea     rdx, [rsp+200h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002d1cd  mov     ecx, ebx; cCountOfExplicitEntries
0x18002d1cf  call    cs:__imp_SetEntriesInAclW
0x18002d1d6  nop     dword ptr [rax+rax+00h]
0x18002d1db  test    eax, eax
0x18002d1dd  jz      short loc_18002D20B
0x18002d1df  mov     edx, 0C19h; void *
0x18002d1e4  mov     rcx, [rbp+108h]; this
0x18002d1eb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d1f2  mov     r9d, eax; char *
0x18002d1f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d1fa  lea     rcx, [rsp+200h+NewAcl]
0x18002d1ff  mov     ebx, eax
0x18002d201  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d206  jmp     loc_18002D163
0x18002d20b  mov     rax, [rsp+200h+NewAcl]
0x18002d210  xor     r9d, r9d; psidOwner
0x18002d213  mov     rcx, [rsp+200h+phkResult]; handle
0x18002d218  mov     [rsp+200h+ppSacl], 0; pSacl
0x18002d221  mov     [rsp+200h+ppDacl], rax; pDacl
0x18002d226  lea     edx, [r9+4]; ObjectType
0x18002d22a  mov     [rsp+200h+ppsidGroup], 0; psidGroup
0x18002d233  mov     r8d, edx; SecurityInfo
0x18002d236  call    cs:__imp_SetSecurityInfo
0x18002d23d  nop     dword ptr [rax+rax+00h]
0x18002d242  test    eax, eax
0x18002d244  jz      short loc_18002D24D
0x18002d246  mov     edx, 0C1Ah
0x18002d24b  jmp     short loc_18002D1E4
0x18002d24d  lea     rcx, [rbp+100h+var_160]
0x18002d251  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002d256  lea     rcx, [rsp+200h+NewAcl]
0x18002d25b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d260  lea     rcx, [rsp+200h+Sid]
0x18002d265  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d26a  lea     rcx, [rsp+200h+var_1B0]
0x18002d26f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d274  xor     ebx, ebx
0x18002d276  lea     rcx, [rsp+200h+phkResult]
0x18002d27b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d280  lea     rcx, [rbp+100h+var_160]; this
0x18002d284  call    ??1AddCurrentUserToACL@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::AddCurrentUserToACL::~AddCurrentUserToACL(void)
0x18002d289  mov     eax, ebx
0x18002d28b  mov     rcx, [rbp+100h+var_10]
0x18002d292  xor     rcx, rsp; StackCookie
0x18002d295  call    __security_check_cookie
0x18002d29a  mov     rbx, [rsp+200h+arg_8]
0x18002d2a2  add     rsp, 200h
0x18002d2a9  pop     rbp
0x18002d2aa  retn
```
