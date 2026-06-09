# CExtensionMainAndOptionalPackagesIterator::CheckIfShouldHaveFoundCurrentIndex(bool *)

- ea: `0x1802007bc`
- end: `0x180200ae3`
- name: `?CheckIfShouldHaveFoundCurrentIndex@CExtensionMainAndOptionalPackagesIterator@@AEAAJPEA_N@Z`
- size: `807`
- prototype: `HRESULT __fastcall(CExtensionMainAndOptionalPackagesIterator *this, bool *shouldHaveFound)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d4fb8`

## callees

- `0x18003a8bc`
- `0x18003c7ec`
- `0x180053284`
- `0x180053be0`
- `0x18008ce08`
- `0x1800c4250`
- `0x18012f4e0`
- `0x1801942a4`
- `0x1802000cc`
- `0x1802007bc`
- `0x180200c78`
- `0x180200dac`
- `0x180201434`
- `0x180201484`

## import_xrefs

- `KERNELBASE!GetEffectivePackageStatusForUser` at `0x18020094a`
- `KERNELBASE!GetEffectivePackageStatusForUser` at `0x18020094a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802007f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802007f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180200a25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180200ab3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180200a25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180200ab3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180200842`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180200ac6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180200842`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180200ac6`

## string_xrefs

- `0x18020086f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180200826`: `onecore\com\combase\extensioncatalog\extensioncatalog.cpp`
- `0x180200958`: `onecore\com\combase\extensioncatalog\extensioncatalog.cpp`
- `0x180200a05`: `onecore\com\combase\extensioncatalog\extensioncatalog.cpp`
- `0x180200809`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1802009e8`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-application.hpp`

## pseudocode

```c
__int64 __fastcall CExtensionMainAndOptionalPackagesIterator::CheckIfShouldHaveFoundCurrentIndex(
        CExtensionMainAndOptionalPackagesIterator *this,
        bool *shouldHaveFound)
{
  HRESULT v4; // ebx
  void *v5; // rdx
  unsigned int v6; // edx
  SRCacheManager *value; // rcx
  HRESULT token_information; // eax
  unsigned int v10; // edx
  HSTRING__ *hstr; // rcx
  const wchar_t *StringRawBuffer; // rax
  HSTRING__ *v13; // rcx
  PCWSTR v14; // rax
  unsigned int EffectivePackageStatusForUser; // eax
  HSTRING__ *v16; // rcx
  const wchar_t *v17; // rax
  HRESULT v18; // eax
  unsigned int v19; // edx
  __int64 v20; // rdx
  SRCacheContext *v21; // rcx
  __int64 v22; // rdx
  HSTRING__ *v23; // rcx
  const wchar_t *v24; // rax
  SRCacheContext *v25; // rcx
  SRCacheManager *v26; // rcx
  __int64 srcachePackageId; // [rsp+20h] [rbp-50h] BYREF
  __int64 srcacheApplicationId; // [rsp+28h] [rbp-48h] BYREF
  __int64 srCacheUserId; // [rsp+30h] [rbp-40h] BYREF
  StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow applicationIterator; // [rsp+38h] [rbp-38h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter> > v31; // [rsp+50h] [rbp-20h] BYREF
  void *retaddr; // [rsp+98h] [rbp+28h]
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> foundApplicationExtension; // [rsp+A8h] [rbp+38h] BYREF
  unsigned int packageStatus; // [rsp+B0h] [rbp+40h] BYREF
  StateRepository::Cache::Manager_NoThrow srcacheManager; // [rsp+B8h] [rbp+48h] BYREF

  v31.replace = 1;
  *shouldHaveFound = 0;
  srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
  v31.wrapper = (wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter> *)&srcacheManager;
  v31.pRaw = 0;
  v4 = SRCacheManager_Open(0, &v31.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v31);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xA5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      v4);
    v6 = 784;
LABEL_3:
    wil::details::in1diag3::Return_Hr(retaddr, v6, "onecore\\com\\combase\\extensioncatalog\\extensioncatalog.cpp", v4);
LABEL_4:
    value = srcacheManager.m_cacheManager.__ptr_.__value_;
    srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
    if ( value )
      SRCacheManager_Close();
    return (unsigned int)v4;
  }
  srCacheUserId = 0;
  foundApplicationExtension.__ptr_.__value_ = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&foundApplicationExtension, v5);
  v4 = token_information;
  if ( token_information < 0 )
  {
    v10 = 326;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v10,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      token_information);
    goto LABEL_13;
  }
  token_information = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
                        &srcacheManager,
                        foundApplicationExtension.__ptr_.__value_->User.Sid,
                        &srCacheUserId);
  v4 = token_information;
  if ( token_information < 0 )
  {
    v10 = 327;
    goto LABEL_9;
  }
  v4 = 0;
LABEL_13:
  std::unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo>::reset<unsigned char *,0>(&foundApplicationExtension, 0);
  if ( v4 < 0 )
  {
    v6 = 787;
    goto LABEL_3;
  }
  if ( srCacheUserId )
  {
    hstr = this->_mainPackageId.hstr_;
    srcachePackageId = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(hstr, 0);
    v4 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
           &srcacheManager,
           StringRawBuffer,
           &srcachePackageId);
    if ( v4 < 0 )
    {
      v6 = 796;
      goto LABEL_3;
    }
    if ( srcachePackageId )
    {
      LOBYTE(foundApplicationExtension.__ptr_.__value_) = 0;
      v4 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
             &srcacheManager,
             srCacheUserId,
             srcachePackageId,
             (bool *)&foundApplicationExtension);
      if ( v4 < 0 )
      {
        v6 = 805;
        goto LABEL_3;
      }
      if ( LOBYTE(foundApplicationExtension.__ptr_.__value_) )
      {
        v13 = this->_mainPackageId.hstr_;
        packageStatus = 0;
        v14 = WindowsGetStringRawBuffer(v13, 0);
        EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v14, &packageStatus);
        if ( EffectivePackageStatusForUser )
        {
          v4 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 0x32Eu,
                 "onecore\\com\\combase\\extensioncatalog\\extensioncatalog.cpp",
                 EffectivePackageStatusForUser);
          goto LABEL_4;
        }
        if ( (packageStatus & 0x4400B07) == 0 )
        {
          v16 = this->_contractId.hstr_;
          LOBYTE(foundApplicationExtension.__ptr_.__value_) = 0;
          v17 = WindowsGetStringRawBuffer(v16, 0);
          v4 = StateRepository::Cache::Entity::PackageExtension_NoThrow::ExistsByPackageAndCategory(
                 &srcacheManager,
                 srcachePackageId,
                 v17,
                 (bool *)&foundApplicationExtension);
          if ( v4 < 0 )
          {
            v6 = 824;
            goto LABEL_3;
          }
          if ( !LOBYTE(foundApplicationExtension.__ptr_.__value_) )
          {
            applicationIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
            applicationIterator.m_index = 0;
            applicationIterator.m_manager = 0;
            v18 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
                    &applicationIterator,
                    &srcacheManager,
                    srcachePackageId);
            v4 = v18;
            if ( v18 >= 0 )
            {
              srcacheApplicationId = 0;
              v4 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(
                     &applicationIterator,
                     &srcacheApplicationId);
              if ( v4 >= 0 )
              {
                while ( srcacheApplicationId )
                {
                  v23 = this->_contractId.hstr_;
                  LOBYTE(foundApplicationExtension.__ptr_.__value_) = 0;
                  v24 = WindowsGetStringRawBuffer(v23, 0);
                  v4 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ExistsByApplicationAndCategory(
                         &srcacheManager,
                         srcacheApplicationId,
                         v24,
                         (bool *)&foundApplicationExtension);
                  if ( v4 < 0 )
                  {
                    v19 = 839;
                    goto LABEL_31;
                  }
                  if ( LOBYTE(foundApplicationExtension.__ptr_.__value_) )
                  {
                    *shouldHaveFound = 1;
                    break;
                  }
                  ++applicationIterator.m_index;
                  v4 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(
                         &applicationIterator,
                         &srcacheApplicationId);
                  if ( v4 < 0 )
                  {
                    v19 = 847;
                    goto LABEL_31;
                  }
                }
                v25 = applicationIterator.m_context.m_cacheContext.__ptr_.__value_;
                applicationIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
                if ( v25 )
                  SRCacheContext_Close(v25, v22);
                goto LABEL_43;
              }
              v19 = 835;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                0x47Bu,
                "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-application.hpp",
                v18);
              v19 = 833;
            }
LABEL_31:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              v19,
              "onecore\\com\\combase\\extensioncatalog\\extensioncatalog.cpp",
              v4);
            v21 = applicationIterator.m_context.m_cacheContext.__ptr_.__value_;
            applicationIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
            if ( v21 )
              SRCacheContext_Close(v21, v20);
            goto LABEL_4;
          }
          *shouldHaveFound = 1;
        }
      }
    }
  }
LABEL_43:
  v26 = srcacheManager.m_cacheManager.__ptr_.__value_;
  srcacheManager.m_cacheManager.__ptr_.__value_ = 0;
  if ( v26 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x1802007bc  push    rbp
0x1802007be  push    rbx
0x1802007bf  push    rsi
0x1802007c0  push    rdi
0x1802007c1  push    r14
0x1802007c3  mov     rbp, rsp
0x1802007c6  sub     rsp, 70h
0x1802007ca  xor     r14d, r14d
0x1802007cd  mov     [rbp+var_20.replace], 1
0x1802007d1  mov     [shouldHaveFound], r14b
0x1802007d4  lea     rax, [rbp+srcacheManager]
0x1802007d8  mov     rdi, shouldHaveFound
0x1802007db  mov     [rbp+srcacheManager.m_cacheManager.__ptr_.__value_], r14
0x1802007df  mov     rsi, this
0x1802007e2  mov     [rbp+var_20.wrapper], rax
0x1802007e6  lea     shouldHaveFound, [rbp+var_20.pRaw]
0x1802007ea  mov     [rbp+var_20.pRaw], r14
0x1802007ee  xor     ecx, ecx
0x1802007f0  call    cs:__imp_SRCacheManager_Open
0x1802007f6  lea     this, [rbp+var_20]; this
0x1802007fa  mov     ebx, eax
0x1802007fc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180200801  test    ebx, ebx
0x180200803  jns     short loc_18020084F
0x180200805  mov     this, [rbp+28h]; callerReturnAddress
0x180200809  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180200810  mov     r9d, ebx; hr
0x180200813  mov     edx, 0A5h; lineNumber
0x180200818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020081d  mov     edx, 310h; lineNumber
0x180200822  mov     this, [rbp+28h]; callerReturnAddress
0x180200826  lea     r8, aOnecoreComComb_178; "onecore\\com\\combase\\extensioncatalog"...
0x18020082d  mov     r9d, ebx; hr
0x180200830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180200835  mov     this, [rbp+srcacheManager.m_cacheManager.__ptr_.__value_]
0x180200839  mov     [rbp+srcacheManager.m_cacheManager.__ptr_.__value_], r14
0x18020083d  test    this, this
0x180200840  jz      short loc_180200848
0x180200842  call    cs:__imp_SRCacheManager_Close
0x180200848  mov     eax, ebx
0x18020084a  jmp     loc_180200ACE
0x18020084f  lea     this, [rbp+foundApplicationExtension]; tokenInfo
0x180200853  mov     [rbp+srCacheUserId], r14
0x180200857  mov     [rbp+foundApplicationExtension], r14
0x18020085b  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180200860  mov     ebx, eax
0x180200862  test    eax, eax
0x180200864  jns     short loc_180200880
0x180200866  mov     edx, 146h; lineNumber
0x18020086b  mov     this, [rbp+28h]; callerReturnAddress
0x18020086f  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180200876  mov     r9d, eax; hr
0x180200879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020087e  jmp     short loc_1802008A4
0x180200880  mov     shouldHaveFound, [rbp+foundApplicationExtension]
0x180200884  lea     r8, [rbp+srCacheUserId]; cacheId
0x180200888  lea     this, [rbp+srcacheManager]; manager
0x18020088c  mov     shouldHaveFound, [shouldHaveFound]; userSid
0x18020088f  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180200894  mov     ebx, eax
0x180200896  test    eax, eax
0x180200898  jns     short loc_1802008A1
0x18020089a  mov     edx, 147h
0x18020089f  jmp     short loc_18020086B
0x1802008a1  mov     ebx, r14d
0x1802008a4  xor     edx, edx; __p
0x1802008a6  lea     this, [rbp+foundApplicationExtension]; this
0x1802008aa  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EUDeleteMarshaledTargetInfo@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0],DeleteMarshaledTargetInfo>::reset<uchar *,0>(uchar *)
0x1802008af  test    ebx, ebx
0x1802008b1  jns     short loc_1802008BD
0x1802008b3  mov     edx, 313h
0x1802008b8  jmp     loc_180200822
0x1802008bd  cmp     [rbp+srCacheUserId], r14
0x1802008c1  jz      loc_180200AB9
0x1802008c7  mov     this, [rsi+50h]; string
0x1802008cb  xor     edx, edx; length
0x1802008cd  mov     [rbp+srcachePackageId], r14
0x1802008d1  call    WindowsGetStringRawBuffer
0x1802008d6  lea     r8, [rbp+srcachePackageId]; cacheId
0x1802008da  mov     shouldHaveFound, rax; packageFullName
0x1802008dd  lea     this, [rbp+srcacheManager]; manager
0x1802008e1  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1802008e6  mov     ebx, eax
0x1802008e8  test    eax, eax
0x1802008ea  jns     short loc_1802008F6
0x1802008ec  mov     edx, 31Ch
0x1802008f1  jmp     loc_180200822
0x1802008f6  mov     r8, [rbp+srcachePackageId]; package
0x1802008fa  test    r8, r8
0x1802008fd  jz      loc_180200AB9
0x180200903  mov     shouldHaveFound, [rbp+srCacheUserId]; user
0x180200907  lea     r9, [rbp+foundApplicationExtension]; found
0x18020090b  lea     this, [rbp+srcacheManager]; manager
0x18020090f  mov     byte ptr [rbp+foundApplicationExtension], r14b
0x180200913  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x180200918  mov     ebx, eax
0x18020091a  test    eax, eax
0x18020091c  jns     short loc_180200928
0x18020091e  mov     edx, 325h
0x180200923  jmp     loc_180200822
0x180200928  cmp     byte ptr [rbp+foundApplicationExtension], r14b
0x18020092c  jz      loc_180200AB9
0x180200932  mov     this, [rsi+50h]; string
0x180200936  xor     edx, edx; length
0x180200938  mov     [rbp+packageStatus], r14d
0x18020093c  call    WindowsGetStringRawBuffer
0x180200941  lea     r8, [rbp+packageStatus]
0x180200945  mov     shouldHaveFound, rax
0x180200948  xor     ecx, ecx
0x18020094a  call    cs:__imp_GetEffectivePackageStatusForUser
0x180200950  test    eax, eax
0x180200952  jz      short loc_180200973
0x180200954  mov     this, [rbp+28h]; callerReturnAddress
0x180200958  lea     r8, aOnecoreComComb_178; "onecore\\com\\combase\\extensioncatalog"...
0x18020095f  mov     r9d, eax; err
0x180200962  mov     edx, 32Eh; lineNumber
0x180200967  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18020096c  mov     ebx, eax
0x18020096e  jmp     loc_180200835
0x180200973  test    [rbp+packageStatus], 4400B07h
0x18020097a  jnz     loc_180200AB9
0x180200980  mov     this, [rsi+10h]; string
0x180200984  xor     edx, edx; length
0x180200986  mov     byte ptr [rbp+foundApplicationExtension], r14b
0x18020098a  call    WindowsGetStringRawBuffer
0x18020098f  mov     shouldHaveFound, [rbp+srcachePackageId]; package
0x180200993  lea     r9, [rbp+foundApplicationExtension]; found
0x180200997  mov     r8, rax; category
0x18020099a  lea     this, [rbp+srcacheManager]; manager
0x18020099e  call    ?ExistsByPackageAndCategory@PackageExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::ExistsByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)
0x1802009a3  mov     ebx, eax
0x1802009a5  test    eax, eax
0x1802009a7  jns     short loc_1802009B3
0x1802009a9  mov     edx, 338h
0x1802009ae  jmp     loc_180200822
0x1802009b3  cmp     byte ptr [rbp+foundApplicationExtension], r14b
0x1802009b7  jz      short loc_1802009C1
0x1802009b9  mov     byte ptr [rdi], 1
0x1802009bc  jmp     loc_180200AB9
0x1802009c1  mov     r8, [rbp+srcachePackageId]; package
0x1802009c5  lea     shouldHaveFound, [rbp+srcacheManager]; manager
0x1802009c9  lea     this, [rbp+applicationIterator]; this
0x1802009cd  mov     [rbp+applicationIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x1802009d1  mov     [rbp+applicationIterator.m_index], r14d
0x1802009d5  mov     [rbp+applicationIterator.m_manager], r14
0x1802009d9  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x1802009de  mov     ebx, eax
0x1802009e0  test    eax, eax
0x1802009e2  jns     short loc_180200A30
0x1802009e4  mov     this, [rbp+28h]; callerReturnAddress
0x1802009e8  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1802009ef  mov     r9d, eax; hr
0x1802009f2  mov     edx, 47Bh; lineNumber
0x1802009f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802009fc  mov     edx, 341h; lineNumber
0x180200a01  mov     this, [rbp+28h]; callerReturnAddress
0x180200a05  lea     r8, aOnecoreComComb_178; "onecore\\com\\combase\\extensioncatalog"...
0x180200a0c  mov     r9d, ebx; hr
0x180200a0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180200a14  mov     this, [rbp+applicationIterator.m_context.m_cacheContext.__ptr_.__value_]
0x180200a18  mov     [rbp+applicationIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x180200a1c  test    this, this
0x180200a1f  jz      loc_180200835
0x180200a25  call    cs:__imp_SRCacheContext_Close
0x180200a2b  jmp     loc_180200835
0x180200a30  lea     shouldHaveFound, [rbp+srcacheApplicationId]; cacheId
0x180200a34  mov     [rbp+srcacheApplicationId], r14
0x180200a38  lea     this, [rbp+applicationIterator]; this
0x180200a3c  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEA_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(__int64 &)
0x180200a41  mov     ebx, eax
0x180200a43  test    eax, eax
0x180200a45  jns     short loc_180200A4E
0x180200a47  mov     edx, 343h
0x180200a4c  jmp     short loc_180200A01
0x180200a4e  cmp     [rbp+srcacheApplicationId], r14
0x180200a52  jz      short loc_180200AA6
0x180200a54  mov     this, [rsi+10h]; string
0x180200a58  xor     edx, edx; length
0x180200a5a  mov     byte ptr [rbp+foundApplicationExtension], r14b
0x180200a5e  call    WindowsGetStringRawBuffer
0x180200a63  mov     shouldHaveFound, [rbp+srcacheApplicationId]; application
0x180200a67  lea     r9, [rbp+foundApplicationExtension]; found
0x180200a6b  mov     r8, rax; category
0x180200a6e  lea     this, [rbp+srcacheManager]; manager
0x180200a72  call    ?ExistsByApplicationAndCategory@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ExistsByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)
0x180200a77  mov     ebx, eax
0x180200a79  test    eax, eax
0x180200a7b  js      short loc_180200AD9
0x180200a7d  cmp     byte ptr [rbp+foundApplicationExtension], r14b
0x180200a81  jnz     short loc_180200AA3
0x180200a83  inc     [rbp+applicationIterator.m_index]
0x180200a86  lea     shouldHaveFound, [rbp+srcacheApplicationId]; cacheId
0x180200a8a  lea     this, [rbp+applicationIterator]; this
0x180200a8e  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEA_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(__int64 &)
0x180200a93  mov     ebx, eax
0x180200a95  test    eax, eax
0x180200a97  jns     short loc_180200A4E
0x180200a99  mov     edx, 34Fh
0x180200a9e  jmp     loc_180200A01
0x180200aa3  mov     byte ptr [rdi], 1
0x180200aa6  mov     this, [rbp+applicationIterator.m_context.m_cacheContext.__ptr_.__value_]
0x180200aaa  mov     [rbp+applicationIterator.m_context.m_cacheContext.__ptr_.__value_], r14
0x180200aae  test    this, this
0x180200ab1  jz      short loc_180200AB9
0x180200ab3  call    cs:__imp_SRCacheContext_Close
0x180200ab9  mov     this, [rbp+srcacheManager.m_cacheManager.__ptr_.__value_]
0x180200abd  mov     [rbp+srcacheManager.m_cacheManager.__ptr_.__value_], r14
0x180200ac1  test    this, this
0x180200ac4  jz      short loc_180200ACC
0x180200ac6  call    cs:__imp_SRCacheManager_Close
0x180200acc  xor     eax, eax
0x180200ace  add     rsp, 70h
0x180200ad2  pop     r14
0x180200ad4  pop     rdi
0x180200ad5  pop     rsi
0x180200ad6  pop     rbx
0x180200ad7  pop     rbp
0x180200ad8  retn
0x180200ad9  mov     edx, 347h
0x180200ade  jmp     loc_180200A01
```
