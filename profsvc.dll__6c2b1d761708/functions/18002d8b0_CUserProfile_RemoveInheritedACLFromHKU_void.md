# CUserProfile::RemoveInheritedACLFromHKU(void)

- ea: `0x18002d8b0`
- end: `0x18002dc22`
- name: `?RemoveInheritedACLFromHKU@CUserProfile@@IEAAJXZ`
- size: `882`
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
- `0x18002d8b0`
- `0x18002dc28`
- `0x18002df48`
- `0x18002df68`
- `0x18002df88`
- `0x180031060`
- `0x18003bc70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002da93`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002da93`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002dab5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002dad1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002dab5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002dad1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d936`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d975`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d936`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d975`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002dae8`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002dae8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d910`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d94f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d910`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d94f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002db4d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002db4d`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002da34`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002da34`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d9ae`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d9ae`

## string_xrefs

- `0x18002d9c5`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002da50`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002daff`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002dbac`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002dbd2`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002d8e1`: `RemoveInheritedACLFromHKU`

## pseudocode

```c
__int64 __fastcall CUserProfile::RemoveInheritedACLFromHKU(LPCWSTR *this)
{
  PSID v2; // rdi
  const char *v3; // r9
  HLOCAL v4; // rax
  void *v5; // rbx
  const char *v6; // r9
  unsigned int v7; // eax
  unsigned int LastError; // ebx
  DWORD SecurityInfo; // eax
  __int64 v10; // rdx
  struct _ACL *v11; // rcx
  DWORD i; // esi
  const char *v13; // r9
  unsigned int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID pAce; // [rsp+60h] [rbp-A0h] BYREF
  PSID v23; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v24[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v25[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v25);
  v25[0] = &ProfileTelemetry::RemoveInheritedACLFromHKU::`vftable';
  ProfileTelemetry::RemoveInheritedACLFromHKU::StartActivity((ProfileTelemetry::RemoveInheritedACLFromHKU *)v25);
  cbSid = 68;
  v23 = LocalAlloc(0, 0x44u);
  v2 = v23;
  if ( CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v23, &cbSid) )
  {
    v4 = LocalAlloc(0, 0x44u);
    v21 = 68;
    v24[0] = v4;
    v5 = v4;
    if ( CreateWellKnownSid(WinRestrictedCodeSid, 0, v4, &v21) )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v7 = RegOpenKeyW(HKEY_USERS, this[6], &phkResult);
      if ( v7 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xBE0,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                      (const char *)v7,
                      ppsidGroup);
      }
      else
      {
        pAcl = 0;
        ppSecurityDescriptor = 0;
        SecurityInfo = GetSecurityInfo(phkResult, SE_REGISTRY_KEY, 4u, 0, 0, &pAcl, 0, &ppSecurityDescriptor);
        if ( SecurityInfo )
        {
          v10 = 3044;
        }
        else
        {
          v11 = pAcl;
          for ( i = 0; i < pAcl->AceCount; v11 = pAcl )
          {
            pAce = 0;
            if ( GetAce(v11, i, &pAce) )
            {
              if ( (*((_BYTE *)pAce + 1) & 0x10) == 0
                || EqualSid((char *)pAce + 8, v2)
                || EqualSid((char *)pAce + 8, v5) )
              {
                ++i;
              }
              else if ( !DeleteAce(pAcl, i) )
              {
                wil::details::in1diag3::_Log_GetLastError(
                  retaddr,
                  (void *)0xBF2,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  v13);
              }
            }
          }
          SecurityInfo = SetSecurityInfo(phkResult, SE_REGISTRY_KEY, 0x80000004, 0, 0, v11, 0);
          if ( !SecurityInfo )
          {
            wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v23);
            ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU((ProfileTelemetry::RemoveInheritedACLFromHKU *)v25);
            return 0;
          }
          v10 = 3067;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v10,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                      (const char *)SecurityInfo,
                      ppsidGroupa);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBDD,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                    v6);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xBD9,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  v3);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v23);
  ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU((ProfileTelemetry::RemoveInheritedACLFromHKU *)v25);
  return LastError;
}

```

## disassembly

```asm
0x18002d8b0  mov     [rsp-8+arg_8], rbx
0x18002d8b5  mov     [rsp-8+arg_10], rsi
0x18002d8ba  push    rbp
0x18002d8bb  push    rdi
0x18002d8bc  push    r15
0x18002d8be  lea     rbp, [rsp-0E0h]
0x18002d8c6  sub     rsp, 1E0h
0x18002d8cd  mov     rax, cs:__security_cookie
0x18002d8d4  xor     rax, rsp
0x18002d8d7  mov     [rbp+0F0h+var_20], rax
0x18002d8de  mov     rsi, rcx
0x18002d8e1  lea     rdx, aRemoveinherite; "RemoveInheritedACLFromHKU"
0x18002d8e8  lea     rcx, [rbp+0F0h+var_170]; struct wil::details::IFailureCallback *
0x18002d8ec  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002d8f1  lea     rax, ??_7RemoveInheritedACLFromHKU@ProfileTelemetry@@6B@; const ProfileTelemetry::RemoveInheritedACLFromHKU::`vftable'
0x18002d8f8  lea     rcx, [rbp+0F0h+var_170]; this
0x18002d8fc  mov     [rbp+0F0h+var_170], rax
0x18002d900  call    ?StartActivity@RemoveInheritedACLFromHKU@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::RemoveInheritedACLFromHKU::StartActivity(void)
0x18002d905  mov     r15d, 44h ; 'D'
0x18002d90b  xor     ecx, ecx; uFlags
0x18002d90d  mov     edx, r15d; uBytes
0x18002d910  call    cs:__imp_LocalAlloc
0x18002d917  nop     dword ptr [rax+rax+00h]
0x18002d91c  xor     edx, edx; DomainSid
0x18002d91e  mov     [rsp+1F0h+cbSid], r15d
0x18002d923  lea     r9, [rsp+1F0h+cbSid]; cbSid
0x18002d928  mov     [rsp+1F0h+var_188], rax
0x18002d92d  mov     r8, rax; pSid
0x18002d930  mov     rdi, rax
0x18002d933  lea     ecx, [rdx+54h]; WellKnownSidType
0x18002d936  call    cs:__imp_CreateWellKnownSid
0x18002d93d  nop     dword ptr [rax+rax+00h]
0x18002d942  test    eax, eax
0x18002d944  jz      loc_18002DBCB
0x18002d94a  mov     edx, r15d; uBytes
0x18002d94d  xor     ecx, ecx; uFlags
0x18002d94f  call    cs:__imp_LocalAlloc
0x18002d956  nop     dword ptr [rax+rax+00h]
0x18002d95b  xor     edx, edx; DomainSid
0x18002d95d  mov     [rsp+1F0h+var_194], r15d
0x18002d962  lea     r9, [rsp+1F0h+var_194]; cbSid
0x18002d967  mov     [rsp+1F0h+var_180], rax
0x18002d96c  mov     r8, rax; pSid
0x18002d96f  mov     rbx, rax
0x18002d972  lea     ecx, [rdx+12h]; WellKnownSidType
0x18002d975  call    cs:__imp_CreateWellKnownSid
0x18002d97c  nop     dword ptr [rax+rax+00h]
0x18002d981  test    eax, eax
0x18002d983  jz      loc_18002DBA5
0x18002d989  xor     edx, edx
0x18002d98b  mov     [rsp+1F0h+phkResult], 0
0x18002d994  lea     rcx, [rsp+1F0h+phkResult]
0x18002d999  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d99e  mov     rdx, [rsi+30h]; lpSubKey
0x18002d9a2  lea     r8, [rsp+1F0h+phkResult]; phkResult
0x18002d9a7  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002d9ae  call    cs:__imp_RegOpenKeyW
0x18002d9b5  nop     dword ptr [rax+rax+00h]
0x18002d9ba  test    eax, eax
0x18002d9bc  jz      short loc_18002D9EA
0x18002d9be  mov     rcx, [rbp+0F8h]; this
0x18002d9c5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d9cc  mov     r9d, eax; char *
0x18002d9cf  mov     edx, 0BE0h; void *
0x18002d9d4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d9d9  mov     ebx, eax
0x18002d9db  lea     rcx, [rsp+1F0h+phkResult]
0x18002d9e0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d9e5  jmp     loc_18002DBBF
0x18002d9ea  mov     rcx, [rsp+1F0h+phkResult]; handle
0x18002d9ef  lea     rax, [rsp+1F0h+var_1A0]
0x18002d9f4  mov     [rsp+1F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002d9f9  xor     r9d, r9d; ppsidOwner
0x18002d9fc  lea     rax, [rsp+1F0h+pAcl]
0x18002da01  mov     [rsp+1F0h+ppSacl], 0; ppSacl
0x18002da0a  mov     [rsp+1F0h+ppDacl], rax; ppDacl
0x18002da0f  mov     [rsp+1F0h+pAcl], 0
0x18002da18  lea     r15d, [r9+4]
0x18002da1c  mov     [rsp+1F0h+var_1A0], 0
0x18002da25  mov     r8d, r15d; SecurityInfo
0x18002da28  mov     [rsp+1F0h+ppsidGroup], 0; unsigned int
0x18002da31  mov     edx, r15d; ObjectType
0x18002da34  call    cs:__imp_GetSecurityInfo
0x18002da3b  nop     dword ptr [rax+rax+00h]
0x18002da40  test    eax, eax
0x18002da42  jz      short loc_18002DA70
0x18002da44  mov     edx, 0BE4h; void *
0x18002da49  mov     rcx, [rbp+0F8h]; this
0x18002da50  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002da57  mov     r9d, eax; char *
0x18002da5a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002da5f  lea     rcx, [rsp+1F0h+var_1A0]
0x18002da64  mov     ebx, eax
0x18002da66  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002da6b  jmp     loc_18002D9DB
0x18002da70  mov     rcx, [rsp+1F0h+pAcl]; pAcl
0x18002da75  xor     esi, esi
0x18002da77  xor     eax, eax
0x18002da79  cmp     ax, [rcx+4]
0x18002da7d  jnb     loc_18002DB25
0x18002da83  lea     r8, [rsp+1F0h+pAce]; pAce
0x18002da88  mov     [rsp+1F0h+pAce], 0
0x18002da91  mov     edx, esi; dwAceIndex
0x18002da93  call    cs:__imp_GetAce
0x18002da9a  nop     dword ptr [rax+rax+00h]
0x18002da9f  test    eax, eax
0x18002daa1  jz      short loc_18002DB14
0x18002daa3  mov     rcx, [rsp+1F0h+pAce]
0x18002daa8  test    byte ptr [rcx+1], 10h
0x18002daac  jz      short loc_18002DB12
0x18002daae  add     rcx, 8; pSid1
0x18002dab2  mov     rdx, rdi; pSid2
0x18002dab5  call    cs:__imp_EqualSid
0x18002dabc  nop     dword ptr [rax+rax+00h]
0x18002dac1  test    eax, eax
0x18002dac3  jnz     short loc_18002DB12
0x18002dac5  mov     rcx, [rsp+1F0h+pAce]
0x18002daca  mov     rdx, rbx; pSid2
0x18002dacd  add     rcx, 8; pSid1
0x18002dad1  call    cs:__imp_EqualSid
0x18002dad8  nop     dword ptr [rax+rax+00h]
0x18002dadd  test    eax, eax
0x18002dadf  jnz     short loc_18002DB12
0x18002dae1  mov     rcx, [rsp+1F0h+pAcl]; pAcl
0x18002dae6  mov     edx, esi; dwAceIndex
0x18002dae8  call    cs:__imp_DeleteAce
0x18002daef  nop     dword ptr [rax+rax+00h]
0x18002daf4  test    eax, eax
0x18002daf6  jnz     short loc_18002DB14
0x18002daf8  mov     rcx, [rbp+0F8h]; this
0x18002daff  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002db06  mov     edx, 0BF2h; void *
0x18002db0b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002db10  jmp     short loc_18002DB14
0x18002db12  inc     esi
0x18002db14  mov     rcx, [rsp+1F0h+pAcl]
0x18002db19  movzx   eax, word ptr [rcx+4]
0x18002db1d  cmp     esi, eax
0x18002db1f  jb      loc_18002DA83
0x18002db25  mov     [rsp+1F0h+ppSacl], 0; pSacl
0x18002db2e  xor     r9d, r9d; psidOwner
0x18002db31  mov     [rsp+1F0h+ppDacl], rcx; pDacl
0x18002db36  mov     r8d, 80000004h; SecurityInfo
0x18002db3c  mov     rcx, [rsp+1F0h+phkResult]; handle
0x18002db41  mov     edx, r15d; ObjectType
0x18002db44  mov     [rsp+1F0h+ppsidGroup], 0; psidGroup
0x18002db4d  call    cs:__imp_SetSecurityInfo
0x18002db54  nop     dword ptr [rax+rax+00h]
0x18002db59  test    eax, eax
0x18002db5b  jz      short loc_18002DB67
0x18002db5d  mov     edx, 0BFBh
0x18002db62  jmp     loc_18002DA49
0x18002db67  lea     rcx, [rbp+0F0h+var_170]
0x18002db6b  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002db70  lea     rcx, [rsp+1F0h+var_1A0]
0x18002db75  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002db7a  lea     rcx, [rsp+1F0h+phkResult]
0x18002db7f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002db84  lea     rcx, [rsp+1F0h+var_180]
0x18002db89  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002db8e  lea     rcx, [rsp+1F0h+var_188]
0x18002db93  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002db98  lea     rcx, [rbp+0F0h+var_170]; this
0x18002db9c  call    ??1RemoveInheritedACLFromHKU@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU(void)
0x18002dba1  xor     eax, eax
0x18002dba3  jmp     short loc_18002DBFA
0x18002dba5  mov     rcx, [rbp+0F8h]; this
0x18002dbac  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dbb3  mov     edx, 0BDDh; void *
0x18002dbb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dbbd  mov     ebx, eax
0x18002dbbf  lea     rcx, [rsp+1F0h+var_180]
0x18002dbc4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002dbc9  jmp     short loc_18002DBE5
0x18002dbcb  mov     rcx, [rbp+0F8h]; this
0x18002dbd2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dbd9  mov     edx, 0BD9h; void *
0x18002dbde  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dbe3  mov     ebx, eax
0x18002dbe5  lea     rcx, [rsp+1F0h+var_188]
0x18002dbea  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002dbef  lea     rcx, [rbp+0F0h+var_170]; this
0x18002dbf3  call    ??1RemoveInheritedACLFromHKU@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU(void)
0x18002dbf8  mov     eax, ebx
0x18002dbfa  mov     rcx, [rbp+0F0h+var_20]
0x18002dc01  xor     rcx, rsp; StackCookie
0x18002dc04  call    __security_check_cookie
0x18002dc09  lea     r11, [rsp+1F0h+var_10]
0x18002dc11  mov     rbx, [r11+28h]
0x18002dc15  mov     rsi, [r11+30h]
0x18002dc19  mov     rsp, r11
0x18002dc1c  pop     r15
0x18002dc1e  pop     rdi
0x18002dc1f  pop     rbp
0x18002dc20  retn
```
