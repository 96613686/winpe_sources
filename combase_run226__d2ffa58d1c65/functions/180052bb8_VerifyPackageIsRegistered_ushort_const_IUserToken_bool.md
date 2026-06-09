# VerifyPackageIsRegistered(ushort const *,IUserToken *,bool)

- ea: `0x180052bb8`
- end: `0x180053144`
- name: `?VerifyPackageIsRegistered@@YAJPEBGPEAUIUserToken@@_N@Z`
- size: `1420`
- prototype: `HRESULT __fastcall(const wchar_t *packageFullName, IUserToken *userToken, bool verifyForMachineScope)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180050fdc`

## callees

- `0x18003a8bc`
- `0x18003cf8c`
- `0x1800521b8`
- `0x1800523b8`
- `0x1800526d8`
- `0x1800528b8`
- `0x180052bb8`
- `0x180053284`
- `0x180053ac0`
- `0x180053be0`
- `0x18005422c`
- `0x1800545bc`
- `0x180058e20`
- `0x1801999b0`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052d20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053051`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052d20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053051`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180052ed5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180052ed5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180052c1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180052c1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052e56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052f66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052fda`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800530b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052e56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052f66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052fda`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800530b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052c3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052c92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052d13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052d85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052c3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052c92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052d13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052d85`

## string_xrefs

- `0x180053061`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180053092`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180052fbc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052fec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180053002`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180053030`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052c6f`: `onecore\com\combase\catalog\services.cxx`
- `0x180052d51`: `onecore\com\combase\catalog\services.cxx`
- `0x1800530da`: `onecore\com\combase\catalog\services.cxx`
- `0x180052c54`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall VerifyPackageIsRegistered(
        const wchar_t *packageFullName,
        IUserToken *userToken,
        bool verifyForMachineScope)
{
  HRESULT SelfSid; // ebx
  SRCacheManager *value; // rcx
  SRCacheManager *v8; // rcx
  SRCacheManager *v10; // rcx
  unsigned int v11; // edx
  SRCacheManager *v12; // rcx
  char v13; // si
  ProcessToken *v14; // rcx
  void *v15; // rdi
  HRESULT v16; // eax
  __int64 v17; // rdx
  char v18; // si
  __int64 v19; // rdi
  HRESULT v20; // eax
  __int64 v21; // rdx
  StateRepository::Cache::Entity::User_NoThrow::CacheFlags v22; // r8d
  SRCacheContext *v23; // rcx
  unsigned int v24; // edx
  __int64 v25; // rdx
  SRCacheContext *v26; // rcx
  unsigned int v27; // edx
  unsigned int v28; // edx
  __int64 v29; // rdx
  SRCacheContext *v30; // rcx
  unsigned int v31; // edx
  IUserToken_vtbl *v32; // rax
  unsigned __int16 cbSidIgnored; // [rsp+30h] [rbp-D0h] BYREF
  StateRepository::Cache::Manager_NoThrow srcacheManager; // [rsp+38h] [rbp-C8h] BYREF
  StateRepository::Cache::Context_NoThrow context; // [rsp+40h] [rbp-C0h] BYREF
  void *userSid; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  __int64 cacheId; // [rsp+58h] [rbp-A8h] BYREF
  StateRepository::Cache::Manager_NoThrow *p_srcacheManager; // [rsp+60h] [rbp-A0h]
  SRCacheManager *v40; // [rsp+68h] [rbp-98h] BYREF
  char v41; // [rsp+70h] [rbp-90h]
  StateRepository::Cache::Entity::Package_NoThrow package; // [rsp+80h] [rbp-80h] BYREF
  StateRepository::Cache::Entity::User_NoThrow user; // [rsp+F0h] [rbp-10h] BYREF
  void *retaddr; // [rsp+198h] [rbp+98h]

  if ( g_disableCatalogPackageRegistrationChecks )
    return 0;
  srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
  p_srcacheManager = &srcacheManager;
  v40 = 0;
  v41 = 1;
  SelfSid = SRCacheManager_Open(0, &v40);
  if ( v41 )
  {
    value = p_srcacheManager->m_cacheManager.__ptr_.__value_;
    p_srcacheManager->m_cacheManager.__ptr_.__value_ = v40;
    if ( value )
      SRCacheManager_Close();
  }
  if ( SelfSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xA5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      SelfSid);
    wil::details::in1diag3::Return_Hr(retaddr, 0xD6Fu, "onecore\\com\\combase\\catalog\\services.cxx", SelfSid);
LABEL_7:
    v8 = srcacheManager.m_cacheManager.__ptr_.__value_;
    srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
    if ( v8 )
      SRCacheManager_Close();
    return (unsigned int)SelfSid;
  }
  memset(&package, 0, 84);
  v13 = 0;
  package.m_displayName.__ptr_.__value_ = 0;
  package.m_sourceBundle = 0;
  LOBYTE(cbSidIgnored) = 0;
  userSid = 0;
  SelfSid = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
              &srcacheManager,
              packageFullName,
              (__int64 *)&userSid);
  if ( SelfSid < 0 )
  {
    v28 = 1165;
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v28,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      SelfSid);
    v11 = 3444;
    goto LABEL_67;
  }
  v15 = userSid;
  if ( !userSid )
    goto LABEL_31;
  context.m_cacheContext.__ptr_.__value_ = 0;
  v16 = StateRepository::Cache::Entity::Package_NoThrow::Open(
          &srcacheManager,
          (__int64)userSid,
          &context,
          (bool *)&cbSidIgnored);
  SelfSid = v16;
  if ( v16 < 0 )
  {
    v31 = 1110;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v31,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v16);
    v30 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v30 )
      SRCacheContext_Close(v30, v29);
    v28 = 1168;
    goto LABEL_59;
  }
  v13 = cbSidIgnored;
  if ( (_BYTE)cbSidIgnored )
  {
    v16 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&context, &package, Default, (__int64)v15);
    SelfSid = v16;
    if ( v16 < 0 )
    {
      v31 = 1115;
      goto LABEL_61;
    }
  }
  v14 = (ProcessToken *)context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v14 )
    SRCacheContext_Close(v14, v17);
LABEL_31:
  if ( !v13 || (package.m_flags[0] & 8) == 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xD79u,
      "onecore\\com\\combase\\catalog\\services.cxx",
      -2147023728,
      "Package %ls is not machine registered",
      packageFullName);
    goto LABEL_21;
  }
  if ( verifyForMachineScope )
  {
    if ( (*(_WORD *)package.m_flags & 0x1000) == 0 && (*(_WORD *)package.m_flags2 & 0x100) == 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0xD81u,
        "onecore\\com\\combase\\catalog\\services.cxx",
        -2147023728,
        "Package %ls is not singleton or system registered",
        packageFullName);
      goto LABEL_21;
    }
LABEL_14:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
    v10 = srcacheManager.m_cacheManager.__ptr_.__value_;
    srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
    if ( v10 )
      SRCacheManager_Close();
    return 0;
  }
  if ( (*(_WORD *)package.m_flags2 & 0x1000) != 0 )
    goto LABEL_14;
  userSid = 0;
  if ( userToken )
  {
    v32 = userToken->__vftable;
    cbSidIgnored = 0;
    SelfSid = v32->GetUserSid(userToken, (unsigned __int8 **)&userSid, &cbSidIgnored);
    if ( SelfSid < 0 )
    {
      v11 = 3472;
      goto LABEL_67;
    }
  }
  else
  {
    SelfSid = ProcessToken::GetSelfSid(v14, &userSid);
    if ( SelfSid < 0 )
    {
      v11 = 3476;
      goto LABEL_67;
    }
  }
  user.m__cacheId = 0;
  memset_0(user.m_userSidBuffer, 0, sizeof(user.m_userSidBuffer));
  user.m_userSid = 0;
  v18 = 0;
  LOBYTE(cbSidIgnored) = 0;
  hMem = 0;
  if ( ConvertSidToStringSidW(userSid, (LPWSTR *)&hMem) )
  {
    cacheId = 0;
    SelfSid = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
                &srcacheManager,
                (const wchar_t *)hMem,
                &cacheId);
    if ( SelfSid < 0 )
    {
      v27 = 245;
    }
    else
    {
      v19 = cacheId;
      if ( !cacheId )
      {
LABEL_45:
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_11;
      }
      context.m_cacheContext.__ptr_.__value_ = 0;
      v20 = StateRepository::Cache::Entity::User_NoThrow::Open(
              &srcacheManager,
              cacheId,
              &context,
              (bool *)&cbSidIgnored);
      SelfSid = v20;
      if ( v20 < 0 )
      {
        v24 = 155;
      }
      else
      {
        v18 = cbSidIgnored;
        if ( !(_BYTE)cbSidIgnored
          || (v20 = StateRepository::Cache::Entity::User_NoThrow::ContextToObject(&context, &user, v22, v19),
              SelfSid = v20,
              v20 >= 0) )
        {
          v23 = context.m_cacheContext.__ptr_.__value_;
          context.m_cacheContext.__ptr_.__value_ = 0;
          if ( v23 )
            SRCacheContext_Close(v23, v21);
          goto LABEL_45;
        }
        v24 = 160;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v24,
        "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        v20);
      v26 = context.m_cacheContext.__ptr_.__value_;
      context.m_cacheContext.__ptr_.__value_ = 0;
      if ( v26 )
        SRCacheContext_Close(v26, v25);
      v27 = 248;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v27,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      SelfSid);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xDEu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      SelfSid);
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_18;
  }
  SelfSid = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              0xDCu,
              "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp");
  if ( hMem )
    LocalFree(hMem);
  if ( SelfSid < 0 )
  {
LABEL_18:
    v11 = 3482;
LABEL_67:
    wil::details::in1diag3::Return_Hr(retaddr, v11, "onecore\\com\\combase\\catalog\\services.cxx", SelfSid);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
    goto LABEL_7;
  }
LABEL_11:
  if ( !v18 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xD9Fu,
      "onecore\\com\\combase\\catalog\\services.cxx",
      -2147023728,
      "Package %ls is not user registered",
      packageFullName);
    goto LABEL_21;
  }
  LOBYTE(cbSidIgnored) = 0;
  SelfSid = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
              &srcacheManager,
              user.m__cacheId,
              package.m__cacheId,
              (bool *)&cbSidIgnored);
  if ( SelfSid < 0 )
  {
    v11 = 3491;
    goto LABEL_67;
  }
  if ( (_BYTE)cbSidIgnored )
    goto LABEL_14;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0xDA6u,
    "onecore\\com\\combase\\catalog\\services.cxx",
    -2147023728,
    "Package %ls is not user registered",
    packageFullName);
LABEL_21:
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
  v12 = srcacheManager.m_cacheManager.__ptr_.__value_;
  srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
  if ( v12 )
    SRCacheManager_Close();
  return 2147943568LL;
}

```

## disassembly

```asm
0x180052bb8  mov     [rsp-8+arg_10], rbx
0x180052bbd  push    rbp
0x180052bbe  push    rsi
0x180052bbf  push    rdi
0x180052bc0  push    r12
0x180052bc2  push    r13
0x180052bc4  push    r14
0x180052bc6  push    r15
0x180052bc8  lea     rbp, [rsp-60h]
0x180052bcd  sub     rsp, 160h
0x180052bd4  mov     rax, cs:__security_cookie
0x180052bdb  xor     rax, rsp
0x180052bde  mov     [rbp+90h+var_40], rax
0x180052be2  xor     r13d, r13d
0x180052be5  mov     r12b, verifyForMachineScope
0x180052be8  cmp     cs:?g_disableCatalogPackageRegistrationChecks@@3_NA, r13b; bool g_disableCatalogPackageRegistrationChecks
0x180052bef  mov     r14, userToken
0x180052bf2  mov     r15, packageFullName
0x180052bf5  jnz     loc_180052D19
0x180052bfb  lea     rax, [rsp+190h+srcacheManager]
0x180052c00  mov     [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_], r13
0x180052c05  lea     userToken, [rsp+190h+var_128]
0x180052c0a  mov     [rsp+190h+var_130], rax
0x180052c0f  xor     ecx, ecx
0x180052c11  mov     [rsp+190h+var_128], r13
0x180052c16  mov     [rsp+190h+var_120], 1
0x180052c1b  call    cs:__imp_SRCacheManager_Open
0x180052c21  mov     ebx, eax
0x180052c23  cmp     [rsp+190h+var_120], r13b
0x180052c28  jz      short loc_180052C45
0x180052c2a  mov     r8, [rsp+190h+var_130]
0x180052c2f  mov     userToken, [rsp+190h+var_128]
0x180052c34  mov     packageFullName, [r8]
0x180052c37  mov     [r8], userToken
0x180052c3a  test    packageFullName, packageFullName
0x180052c3d  jz      short loc_180052C45
0x180052c3f  call    cs:__imp_SRCacheManager_Close
0x180052c45  test    ebx, ebx
0x180052c47  jns     loc_180052D95
0x180052c4d  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180052c54  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052c5b  mov     r9d, ebx; hr
0x180052c5e  mov     edx, 0A5h; lineNumber
0x180052c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052c68  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180052c6f  lea     r8, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x180052c76  mov     r9d, ebx; hr
0x180052c79  mov     edx, 0D6Fh; lineNumber
0x180052c7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052c83  mov     packageFullName, [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_]
0x180052c88  mov     [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_], r13
0x180052c8d  test    packageFullName, packageFullName
0x180052c90  jz      short loc_180052C98
0x180052c92  call    cs:__imp_SRCacheManager_Close
0x180052c98  mov     eax, ebx
0x180052c9a  mov     packageFullName, [rbp+90h+var_40]
0x180052c9e  xor     packageFullName, rsp; StackCookie
0x180052ca1  call    __security_check_cookie
0x180052ca6  mov     rbx, [rsp+190h+arg_10]
0x180052cae  add     rsp, 160h
0x180052cb5  pop     r15
0x180052cb7  pop     r14
0x180052cb9  pop     r13
0x180052cbb  pop     r12
0x180052cbd  pop     rdi
0x180052cbe  pop     rsi
0x180052cbf  pop     rbp
0x180052cc0  retn
0x180052cc1  test    ebx, ebx
0x180052cc3  js      short loc_180052D26
0x180052cc5  test    sil, sil
0x180052cc8  jz      loc_180053133
0x180052cce  mov     r8, [rbp+90h+package.m__cacheId]; package
0x180052cd2  lea     r9, [rsp+190h+cbSidIgnored]; found
0x180052cd7  mov     userToken, [rbp+90h+user.m__cacheId]; user
0x180052cdb  lea     packageFullName, [rsp+190h+srcacheManager]; manager
0x180052ce0  mov     byte ptr [rsp+190h+cbSidIgnored], r13b
0x180052ce5  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x180052cea  mov     ebx, eax
0x180052cec  test    eax, eax
0x180052cee  js      loc_1800530CE
0x180052cf4  cmp     byte ptr [rsp+190h+cbSidIgnored], r13b
0x180052cf9  jz      short loc_180052D30
0x180052cfb  lea     packageFullName, [rbp+90h+package]; this
0x180052cff  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180052d04  mov     packageFullName, [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_]
0x180052d09  mov     [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_], r13
0x180052d0e  test    packageFullName, packageFullName
0x180052d11  jz      short loc_180052D19
0x180052d13  call    cs:__imp_SRCacheManager_Close
0x180052d19  xor     eax, eax
0x180052d1b  jmp     loc_180052C9A
0x180052d20  call    cs:__imp_LocalFree
0x180052d26  mov     edx, 0D9Ah
0x180052d2b  jmp     loc_1800530D3
0x180052d30  lea     rax, aPackageLsIsNot; "Package %ls is not user registered"
0x180052d37  mov     edx, 0DA6h
0x180052d3c  jmp     short loc_180052D4A
0x180052d3e  lea     rax, aPackageLsIsNot_1; "Package %ls is not machine registered"
0x180052d45  mov     edx, 0D79h; lineNumber
0x180052d4a  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180052d51  lea     r8, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x180052d58  mov     [rsp+190h+var_168], r15
0x180052d5d  mov     r9d, 80070490h; hr
0x180052d63  mov     [rsp+190h+formatString], rax; formatString
0x180052d68  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052d6d  lea     packageFullName, [rbp+90h+package]; this
0x180052d71  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180052d76  mov     packageFullName, [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_]
0x180052d7b  mov     [rsp+190h+srcacheManager.m_cacheManager.__ptr_.__value_], r13
0x180052d80  test    packageFullName, packageFullName
0x180052d83  jz      short loc_180052D8B
0x180052d85  call    cs:__imp_SRCacheManager_Close
0x180052d8b  mov     eax, 80070490h
0x180052d90  jmp     loc_180052C9A
0x180052d95  xorps   xmm0, xmm0
0x180052d98  mov     [rbp+90h+package.m_packageFamily], r13
0x180052d9c  lea     r8, [rsp+190h+userSid]; cacheId
0x180052da1  movdqa  xmmword ptr [rbp+90h+package.m__cacheId], xmm0
0x180052da6  mov     userToken, r15; packageFullName
0x180052da9  movdqa  xmmword ptr [rbp+90h+package.m_mutableLink.__ptr_.__value_], xmm0
0x180052dae  lea     packageFullName, [rsp+190h+srcacheManager]; manager
0x180052db3  mov     qword ptr [rbp+90h+package.m_packageType], r13
0x180052db7  mov     qword ptr [rbp+90h+package.m_flags2], r13
0x180052dbb  mov     sil, r13b
0x180052dbe  mov     [rbp+90h+package.m_volume], r13
0x180052dc2  mov     [rbp+90h+package.m_oSMaxVersionTested], r13
0x180052dc6  mov     [rbp+90h+package.m_installedLocation.__ptr_.__value_], r13
0x180052dca  mov     [rbp+90h+package.m_targetDeviceFamilyName], r13d
0x180052dce  mov     [rbp+90h+package.m_displayName.__ptr_.__value_], r13
0x180052dd2  mov     [rbp+90h+package.m_sourceBundle], r13
0x180052dd6  mov     byte ptr [rsp+190h+cbSidIgnored], r13b
0x180052ddb  mov     [rsp+190h+userSid], r13
0x180052de0  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180052de5  mov     ebx, eax
0x180052de7  test    eax, eax
0x180052de9  js      loc_18005305C
0x180052def  mov     rdi, [rsp+190h+userSid]
0x180052df4  test    rdi, rdi
0x180052df7  jz      short loc_180052E5C
0x180052df9  lea     r9, [rsp+190h+cbSidIgnored]; found
0x180052dfe  mov     [rsp+190h+context.m_cacheContext.__ptr_.__value_], r13
0x180052e03  lea     r8, [rsp+190h+context]; context
0x180052e08  mov     userToken, rdi; cacheId
0x180052e0b  lea     packageFullName, [rsp+190h+srcacheManager]; manager
0x180052e10  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180052e15  mov     ebx, eax
0x180052e17  test    eax, eax
0x180052e19  js      loc_1800530C0
0x180052e1f  mov     sil, byte ptr [rsp+190h+cbSidIgnored]
0x180052e24  test    sil, sil
0x180052e27  jz      short loc_180052E47
0x180052e29  mov     r9, rdi; cacheId
0x180052e2c  lea     userToken, [rbp+90h+package]; entity
0x180052e30  xor     r8d, r8d; cacheFlags
0x180052e33  lea     packageFullName, [rsp+190h+context]; context
0x180052e38  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180052e3d  mov     ebx, eax
0x180052e3f  test    eax, eax
0x180052e41  js      loc_1800530C7
0x180052e47  mov     packageFullName, [rsp+190h+context.m_cacheContext.__ptr_.__value_]
0x180052e4c  mov     [rsp+190h+context.m_cacheContext.__ptr_.__value_], r13
0x180052e51  test    packageFullName, packageFullName
0x180052e54  jz      short loc_180052E5C
0x180052e56  call    cs:__imp_SRCacheContext_Close
0x180052e5c  test    sil, sil
0x180052e5f  jz      loc_180052D3E
0x180052e65  test    [rbp+90h+package.m_flags], 8
0x180052e69  jz      loc_180052D3E
0x180052e6f  test    r12b, r12b
0x180052e72  jnz     loc_180052F85
0x180052e78  test    dword ptr [rbp+90h+package.m_flags2], 1000h
0x180052e7f  jnz     loc_180052CFB
0x180052e85  mov     [rsp+190h+userSid], r13
0x180052e8a  lea     userToken, [rsp+190h+userSid]; ppSelfSid
0x180052e8f  test    r14, r14
0x180052e92  jnz     loc_1800530F7
0x180052e98  call    ?GetSelfSid@ProcessToken@@QEAAJPEAPEAX@Z; ProcessToken::GetSelfSid(void * *)
0x180052e9d  mov     ebx, eax
0x180052e9f  test    eax, eax
0x180052ea1  js      loc_180053122
0x180052ea7  xor     edx, edx; Val
0x180052ea9  mov     [rbp+90h+user.m__cacheId], r13
0x180052ead  lea     packageFullName, [rbp+90h+user.m_userSidBuffer]; void *
0x180052eb1  lea     r8d, [userToken+44h]; Size
0x180052eb5  call    memset_0
0x180052eba  mov     packageFullName, [rsp+190h+userSid]; Sid
0x180052ebf  lea     userToken, [rsp+190h+hMem]; StringSid
0x180052ec4  mov     [rbp+90h+user.m_userSid], r13
0x180052ec8  mov     sil, r13b
0x180052ecb  mov     byte ptr [rsp+190h+cbSidIgnored], r13b
0x180052ed0  mov     [rsp+190h+hMem], r13
0x180052ed5  call    cs:__imp_ConvertSidToStringSidW
0x180052edb  test    eax, eax
0x180052edd  jz      loc_180053029
0x180052ee3  mov     userToken, [rsp+190h+hMem]; userSidAsString
0x180052ee8  lea     r8, [rsp+190h+cacheId]; cacheId
0x180052eed  lea     packageFullName, [rsp+190h+srcacheManager]; manager
0x180052ef2  mov     [rsp+190h+cacheId], r13
0x180052ef7  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180052efc  mov     ebx, eax
0x180052efe  test    eax, eax
0x180052f00  js      loc_180053081
0x180052f06  mov     rdi, [rsp+190h+cacheId]
0x180052f0b  test    rdi, rdi
0x180052f0e  jz      short loc_180052F6C
0x180052f10  lea     r9, [rsp+190h+cbSidIgnored]; found
0x180052f15  mov     [rsp+190h+context.m_cacheContext.__ptr_.__value_], r13
0x180052f1a  lea     r8, [rsp+190h+context]; context
0x180052f1f  mov     userToken, rdi; cacheId
0x180052f22  lea     packageFullName, [rsp+190h+srcacheManager]; manager
0x180052f27  call    ?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180052f2c  mov     ebx, eax
0x180052f2e  test    eax, eax
0x180052f30  js      short loc_180052FB0
0x180052f32  mov     sil, byte ptr [rsp+190h+cbSidIgnored]
0x180052f37  test    sil, sil
0x180052f3a  jz      short loc_180052F57
0x180052f3c  mov     r9, rdi; context
0x180052f3f  lea     userToken, [rbp+90h+user]; entity
0x180052f43  lea     packageFullName, [rsp+190h+context]; context
0x180052f48  call    ?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)
0x180052f4d  mov     ebx, eax
0x180052f4f  test    eax, eax
0x180052f51  js      loc_180053129
0x180052f57  mov     packageFullName, [rsp+190h+context.m_cacheContext.__ptr_.__value_]
0x180052f5c  mov     [rsp+190h+context.m_cacheContext.__ptr_.__value_], r13
0x180052f61  test    packageFullName, packageFullName
0x180052f64  jz      short loc_180052F6C
0x180052f66  call    cs:__imp_SRCacheContext_Close
0x180052f6c  mov     packageFullName, [rsp+190h+hMem]; hMem
0x180052f71  test    packageFullName, packageFullName
0x180052f74  jz      loc_180052CC5
0x180052f7a  call    cs:__imp_LocalFree
0x180052f80  jmp     loc_180052CC5
0x180052f85  test    dword ptr [rbp+90h+package.m_flags], 1000h
0x180052f8c  jnz     loc_180052CFB
0x180052f92  test    dword ptr [rbp+90h+package.m_flags2], 100h
0x180052f99  jnz     loc_180052CFB
0x180052f9f  lea     rax, aPackageLsIsNot_0; "Package %ls is not singleton or system "...
0x180052fa6  mov     edx, 0D81h
0x180052fab  jmp     loc_180052D4A
0x180052fb0  mov     edx, 9Bh; lineNumber
0x180052fb5  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180052fbc  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052fc3  mov     r9d, eax; hr
0x180052fc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052fcb  mov     packageFullName, [rsp+190h+context.m_cacheContext.__ptr_.__value_]
0x180052fd0  mov     [rsp+190h+context.m_cacheContext.__ptr_.__value_], r13
0x180052fd5  test    packageFullName, packageFullName
0x180052fd8  jz      short loc_180052FE0
0x180052fda  call    cs:__imp_SRCacheContext_Close
0x180052fe0  mov     edx, 0F8h; lineNumber
0x180052fe5  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180052fec  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052ff3  mov     r9d, ebx; hr
0x180052ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ffb  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180053002  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053009  mov     r9d, ebx; hr
0x18005300c  mov     edx, 0DEh; lineNumber
0x180053011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053016  mov     packageFullName, [rsp+190h+hMem]; hMem
0x18005301b  test    packageFullName, packageFullName
0x18005301e  jnz     loc_180052D20
0x180053024  jmp     loc_180052D26
0x180053029  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180053030  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053037  mov     edx, 0DCh; lineNumber
0x18005303c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180053041  mov     packageFullName, [rsp+190h+hMem]; hMem
0x180053046  mov     ebx, eax
0x180053048  test    packageFullName, packageFullName
0x18005304b  jz      loc_180052CC1
0x180053051  call    cs:__imp_LocalFree
0x180053057  jmp     loc_180052CC1
0x18005305c  mov     edx, 48Dh; lineNumber
0x180053061  lea     rdi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053068  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x18005306f  mov     r9d, ebx; hr
0x180053072  mov     r8, rdi; fileName
0x180053075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005307a  mov     edx, 0D74h
0x18005307f  jmp     short loc_1800530D3
0x180053081  mov     edx, 0F5h
0x180053086  jmp     loc_180052FE5
0x18005308b  mov     packageFullName, [rbp+98h]; callerReturnAddress
0x180053092  lea     rdi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053099  mov     r8, rdi; fileName
0x18005309c  mov     r9d, eax; hr
0x18005309f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800530a4  mov     packageFullName, [rsp+190h+context.m_cacheContext.__ptr_.__value_]
0x1800530a9  mov     [rsp+190h+context.m_cacheContext.__ptr_.__value_], r13
0x1800530ae  test    packageFullName, packageFullName
0x1800530b1  jz      short loc_1800530B9
0x1800530b3  call    cs:__imp_SRCacheContext_Close
0x1800530b9  mov     edx, 490h
0x1800530be  jmp     short loc_180053068
0x1800530c0  mov     edx, 456h; lineNumber
0x1800530c5  jmp     short loc_18005308B
  ... truncated ...
```
