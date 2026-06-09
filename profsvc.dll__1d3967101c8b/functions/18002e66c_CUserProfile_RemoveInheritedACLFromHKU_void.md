# CUserProfile::RemoveInheritedACLFromHKU(void)

- ea: `0x18002e66c`
- end: `0x18002e9ab`
- name: `?RemoveInheritedACLFromHKU@CUserProfile@@IEAAJXZ`
- size: `831`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
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
- `0x18002e648`
- `0x18002e66c`
- `0x18002e9b4`
- `0x180030558`
- `0x180030578`
- `0x18003a730`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e787`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e787`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e908`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002e835`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002e835`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e851`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e867`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e851`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e867`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002e6ec`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002e71f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002e6ec`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002e71f`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002e878`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002e878`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e6cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e6ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e6cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e6ff`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002e8d7`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002e8d7`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002e7dc`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002e7dc`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002e752`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002e752`

## string_xrefs

- `0x18002e763`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e7f2`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e889`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e936`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e95c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002e69d`: `RemoveInheritedACLFromHKU`

## pseudocode

```c
__int64 __fastcall CUserProfile::RemoveInheritedACLFromHKU(LPCWSTR *this)
{
  void *v2; // rdi
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
  HLOCAL v23; // [rsp+68h] [rbp-98h] BYREF
  void *v24[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v25[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v25);
  v25[0] = &ProfileTelemetry::RemoveInheritedACLFromHKU::`vftable';
  ProfileTelemetry::RemoveInheritedACLFromHKU::StartActivity((ProfileTelemetry::RemoveInheritedACLFromHKU *)v25);
  cbSid = 68;
  v23 = LocalAlloc(0, 0x44u);
  v2 = v23;
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v23, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xBD9,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  v3);
    goto LABEL_27;
  }
  v4 = LocalAlloc(0, 0x44u);
  v21 = 68;
  v24[0] = v4;
  v5 = v4;
  if ( !CreateWellKnownSid(WinRestrictedCodeSid, 0, v4, &v21) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xBDD,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  v6);
LABEL_25:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
LABEL_27:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v23);
    ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU((ProfileTelemetry::RemoveInheritedACLFromHKU *)v25);
    return LastError;
  }
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
    goto LABEL_5;
  }
  pAcl = 0;
  ppSecurityDescriptor = 0;
  SecurityInfo = GetSecurityInfo(phkResult, SE_REGISTRY_KEY, 4u, 0, 0, &pAcl, 0, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    v10 = 3044;
LABEL_9:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  (const char *)SecurityInfo,
                  ppsidGroupa);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
LABEL_5:
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_25;
  }
  v11 = pAcl;
  for ( i = 0; i < pAcl->AceCount; v11 = pAcl )
  {
    pAce = 0;
    if ( GetAce(v11, i, &pAce) )
    {
      if ( (*((_BYTE *)pAce + 1) & 0x10) == 0 || EqualSid((char *)pAce + 8, v2) || EqualSid((char *)pAce + 8, v5) )
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
  if ( SecurityInfo )
  {
    v10 = 3067;
    goto LABEL_9;
  }
  wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
  if ( phkResult )
    RegCloseKey(phkResult);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v23);
  ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU((ProfileTelemetry::RemoveInheritedACLFromHKU *)v25);
  return 0;
}

```

## disassembly

```asm
0x18002e66c  mov     [rsp-8+arg_8], rbx
0x18002e671  mov     [rsp-8+arg_10], rsi
0x18002e676  push    rbp
0x18002e677  push    rdi
0x18002e678  push    r15
0x18002e67a  lea     rbp, [rsp-0E0h]
0x18002e682  sub     rsp, 1E0h
0x18002e689  mov     rax, cs:__security_cookie
0x18002e690  xor     rax, rsp
0x18002e693  mov     [rbp+0F0h+var_20], rax
0x18002e69a  mov     rsi, rcx
0x18002e69d  lea     rdx, aRemoveinherite; "RemoveInheritedACLFromHKU"
0x18002e6a4  lea     rcx, [rbp+0F0h+var_170]; struct wil::details::IFailureCallback *
0x18002e6a8  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002e6ad  lea     rax, ??_7RemoveInheritedACLFromHKU@ProfileTelemetry@@6B@; const ProfileTelemetry::RemoveInheritedACLFromHKU::`vftable'
0x18002e6b4  lea     rcx, [rbp+0F0h+var_170]; this
0x18002e6b8  mov     [rbp+0F0h+var_170], rax
0x18002e6bc  call    ?StartActivity@RemoveInheritedACLFromHKU@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::RemoveInheritedACLFromHKU::StartActivity(void)
0x18002e6c1  mov     r15d, 44h ; 'D'
0x18002e6c7  xor     ecx, ecx; uFlags
0x18002e6c9  mov     edx, r15d; uBytes
0x18002e6cc  call    cs:__imp_LocalAlloc
0x18002e6d2  xor     edx, edx; DomainSid
0x18002e6d4  mov     [rsp+1F0h+cbSid], r15d
0x18002e6d9  lea     r9, [rsp+1F0h+cbSid]; cbSid
0x18002e6de  mov     [rsp+1F0h+var_188], rax
0x18002e6e3  mov     r8, rax; pSid
0x18002e6e6  mov     rdi, rax
0x18002e6e9  lea     ecx, [rdx+54h]; WellKnownSidType
0x18002e6ec  call    cs:__imp_CreateWellKnownSid
0x18002e6f2  test    eax, eax
0x18002e6f4  jz      loc_18002E955
0x18002e6fa  mov     edx, r15d; uBytes
0x18002e6fd  xor     ecx, ecx; uFlags
0x18002e6ff  call    cs:__imp_LocalAlloc
0x18002e705  xor     edx, edx; DomainSid
0x18002e707  mov     [rsp+1F0h+var_194], r15d
0x18002e70c  lea     r9, [rsp+1F0h+var_194]; cbSid
0x18002e711  mov     [rsp+1F0h+var_180], rax
0x18002e716  mov     r8, rax; pSid
0x18002e719  mov     rbx, rax
0x18002e71c  lea     ecx, [rdx+12h]; WellKnownSidType
0x18002e71f  call    cs:__imp_CreateWellKnownSid
0x18002e725  test    eax, eax
0x18002e727  jz      loc_18002E92F
0x18002e72d  xor     edx, edx
0x18002e72f  mov     [rsp+1F0h+phkResult], 0
0x18002e738  lea     rcx, [rsp+1F0h+phkResult]
0x18002e73d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002e742  mov     rdx, [rsi+30h]; lpSubKey
0x18002e746  lea     r8, [rsp+1F0h+phkResult]; phkResult
0x18002e74b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002e752  call    cs:__imp_RegOpenKeyW
0x18002e758  test    eax, eax
0x18002e75a  jz      short loc_18002E792
0x18002e75c  mov     rcx, [rbp+0F8h]; this
0x18002e763  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e76a  mov     r9d, eax; char *
0x18002e76d  mov     edx, 0BE0h; void *
0x18002e772  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e777  mov     ebx, eax
0x18002e779  mov     rcx, [rsp+1F0h+phkResult]; hKey
0x18002e77e  test    rcx, rcx
0x18002e781  jz      loc_18002E949
0x18002e787  call    cs:__imp_RegCloseKey
0x18002e78d  jmp     loc_18002E949
0x18002e792  mov     rcx, [rsp+1F0h+phkResult]; handle
0x18002e797  lea     rax, [rsp+1F0h+var_1A0]
0x18002e79c  mov     [rsp+1F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002e7a1  xor     r9d, r9d; ppsidOwner
0x18002e7a4  lea     rax, [rsp+1F0h+pAcl]
0x18002e7a9  mov     [rsp+1F0h+ppSacl], 0; ppSacl
0x18002e7b2  mov     [rsp+1F0h+ppDacl], rax; ppDacl
0x18002e7b7  mov     [rsp+1F0h+pAcl], 0
0x18002e7c0  lea     r15d, [r9+4]
0x18002e7c4  mov     [rsp+1F0h+var_1A0], 0
0x18002e7cd  mov     r8d, r15d; SecurityInfo
0x18002e7d0  mov     [rsp+1F0h+ppsidGroup], 0; unsigned int
0x18002e7d9  mov     edx, r15d; ObjectType
0x18002e7dc  call    cs:__imp_GetSecurityInfo
0x18002e7e2  test    eax, eax
0x18002e7e4  jz      short loc_18002E812
0x18002e7e6  mov     edx, 0BE4h; void *
0x18002e7eb  mov     rcx, [rbp+0F8h]; this
0x18002e7f2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e7f9  mov     r9d, eax; char *
0x18002e7fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e801  lea     rcx, [rsp+1F0h+var_1A0]
0x18002e806  mov     ebx, eax
0x18002e808  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002e80d  jmp     loc_18002E779
0x18002e812  mov     rcx, [rsp+1F0h+pAcl]; pAcl
0x18002e817  xor     esi, esi
0x18002e819  xor     eax, eax
0x18002e81b  cmp     ax, [rcx+4]
0x18002e81f  jnb     loc_18002E8AF
0x18002e825  lea     r8, [rsp+1F0h+pAce]; pAce
0x18002e82a  mov     [rsp+1F0h+pAce], 0
0x18002e833  mov     edx, esi; dwAceIndex
0x18002e835  call    cs:__imp_GetAce
0x18002e83b  test    eax, eax
0x18002e83d  jz      short loc_18002E89E
0x18002e83f  mov     rcx, [rsp+1F0h+pAce]
0x18002e844  test    byte ptr [rcx+1], 10h
0x18002e848  jz      short loc_18002E89C
0x18002e84a  add     rcx, 8; pSid1
0x18002e84e  mov     rdx, rdi; pSid2
0x18002e851  call    cs:__imp_EqualSid
0x18002e857  test    eax, eax
0x18002e859  jnz     short loc_18002E89C
0x18002e85b  mov     rcx, [rsp+1F0h+pAce]
0x18002e860  mov     rdx, rbx; pSid2
0x18002e863  add     rcx, 8; pSid1
0x18002e867  call    cs:__imp_EqualSid
0x18002e86d  test    eax, eax
0x18002e86f  jnz     short loc_18002E89C
0x18002e871  mov     rcx, [rsp+1F0h+pAcl]; pAcl
0x18002e876  mov     edx, esi; dwAceIndex
0x18002e878  call    cs:__imp_DeleteAce
0x18002e87e  test    eax, eax
0x18002e880  jnz     short loc_18002E89E
0x18002e882  mov     rcx, [rbp+0F8h]; this
0x18002e889  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e890  mov     edx, 0BF2h; void *
0x18002e895  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002e89a  jmp     short loc_18002E89E
0x18002e89c  inc     esi
0x18002e89e  mov     rcx, [rsp+1F0h+pAcl]
0x18002e8a3  movzx   eax, word ptr [rcx+4]
0x18002e8a7  cmp     esi, eax
0x18002e8a9  jb      loc_18002E825
0x18002e8af  mov     [rsp+1F0h+ppSacl], 0; pSacl
0x18002e8b8  xor     r9d, r9d; psidOwner
0x18002e8bb  mov     [rsp+1F0h+ppDacl], rcx; pDacl
0x18002e8c0  mov     r8d, 80000004h; SecurityInfo
0x18002e8c6  mov     rcx, [rsp+1F0h+phkResult]; handle
0x18002e8cb  mov     edx, r15d; ObjectType
0x18002e8ce  mov     [rsp+1F0h+ppsidGroup], 0; psidGroup
0x18002e8d7  call    cs:__imp_SetSecurityInfo
0x18002e8dd  test    eax, eax
0x18002e8df  jz      short loc_18002E8EB
0x18002e8e1  mov     edx, 0BFBh
0x18002e8e6  jmp     loc_18002E7EB
0x18002e8eb  lea     rcx, [rbp+0F0h+var_170]
0x18002e8ef  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002e8f4  lea     rcx, [rsp+1F0h+var_1A0]
0x18002e8f9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002e8fe  mov     rcx, [rsp+1F0h+phkResult]; hKey
0x18002e903  test    rcx, rcx
0x18002e906  jz      short loc_18002E90E
0x18002e908  call    cs:__imp_RegCloseKey
0x18002e90e  lea     rcx, [rsp+1F0h+var_180]
0x18002e913  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002e918  lea     rcx, [rsp+1F0h+var_188]
0x18002e91d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002e922  lea     rcx, [rbp+0F0h+var_170]; this
0x18002e926  call    ??1RemoveInheritedACLFromHKU@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU(void)
0x18002e92b  xor     eax, eax
0x18002e92d  jmp     short loc_18002E984
0x18002e92f  mov     rcx, [rbp+0F8h]; this
0x18002e936  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e93d  mov     edx, 0BDDh; void *
0x18002e942  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002e947  mov     ebx, eax
0x18002e949  lea     rcx, [rsp+1F0h+var_180]
0x18002e94e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002e953  jmp     short loc_18002E96F
0x18002e955  mov     rcx, [rbp+0F8h]; this
0x18002e95c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e963  mov     edx, 0BD9h; void *
0x18002e968  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002e96d  mov     ebx, eax
0x18002e96f  lea     rcx, [rsp+1F0h+var_188]
0x18002e974  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002e979  lea     rcx, [rbp+0F0h+var_170]; this
0x18002e97d  call    ??1RemoveInheritedACLFromHKU@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::RemoveInheritedACLFromHKU::~RemoveInheritedACLFromHKU(void)
0x18002e982  mov     eax, ebx
0x18002e984  mov     rcx, [rbp+0F0h+var_20]
0x18002e98b  xor     rcx, rsp; StackCookie
0x18002e98e  call    __security_check_cookie
0x18002e993  lea     r11, [rsp+1F0h+var_10]
0x18002e99b  mov     rbx, [r11+28h]
0x18002e99f  mov     rsi, [r11+30h]
0x18002e9a3  mov     rsp, r11
0x18002e9a6  pop     r15
0x18002e9a8  pop     rdi
0x18002e9a9  pop     rbp
0x18002e9aa  retn
```
