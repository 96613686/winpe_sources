# TryGetInstalledPackageFullNameFromPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,IUserTokenInternal *,ushort const *,uint,HSTRING__ * *,PackageFamilyErrorDetails *)

- ea: `0x1801ddde4`
- end: `0x1801de2dc`
- name: `?TryGetInstalledPackageFullNameFromPackageFamilyName@@YAJAEAVManager_NoThrow@Cache@StateRepository@@PEAUIUserTokenInternal@@PEBGIPEAPEAUHSTRING__@@PEAW4PackageFamilyErrorDetails@@@Z`
- size: `1272`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, IUserTokenInternal *userTokenInternal, const wchar_t *packageFamilyName, unsigned int packageFullName, HSTRING__ **manager, PackageFamilyErrorDetails *userTokenInternal)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ddda0`

## callees

- `0x18000712c`
- `0x18000833c`
- `0x18001d0e8`
- `0x18003a8bc`
- `0x180041e50`
- `0x180053ac0`
- `0x18012f4e0`
- `0x1801714b8`
- `0x180171578`
- `0x180171818`
- `0x1801999b0`
- `0x18019a654`
- `0x1801ddde4`
- `0x180255010`

## import_xrefs

- `KERNELBASE!FindPackagesByPackageFamily` at `0x1801ddef5`
- `KERNELBASE!FindPackagesByPackageFamily` at `0x1801ddef5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1801ddf5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1801ddf5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801de02f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801de146`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801de02f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801de146`

## string_xrefs

- `0x1801dde55`: `onecore\com\combase\catalog\services.cxx`
- `0x1801dde87`: `onecore\com\combase\catalog\services.cxx`
- `0x1801ddf32`: `onecore\com\combase\catalog\services.cxx`
- `0x1801ddf99`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de008`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de09c`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de17b`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de1b7`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de1e0`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de273`: `onecore\com\combase\catalog\services.cxx`
- `0x1801de2a4`: `onecore\com\combase\catalog\services.cxx`
- `0x1801ddf79`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1801de1f8`: `Family %ls has %d installed packages`

## pseudocode

```c
__int64 __fastcall TryGetInstalledPackageFullNameFromPackageFamilyName(
        StateRepository::Cache::Manager_NoThrow *manager,
        IUserTokenInternal *userTokenInternal,
        const wchar_t *packageFamilyName,
        __int64 packageFullName,
        HSTRING__ **manager_0)
{
  HRESULT v8; // eax
  unsigned int v9; // r15d
  HRESULT v10; // eax
  LONG PackagesByPackageFamily; // eax
  __int64 v13; // rcx
  HRESULT v14; // eax
  HRESULT String; // edi
  unsigned int v16; // edx
  HRESULT v17; // eax
  __int64 v18; // rdx
  SRCacheContext *value; // rcx
  unsigned int v20; // edx
  __int64 v21; // rdx
  __int64 v22; // rdx
  SRCacheContext *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // esi
  HRESULT v27; // eax
  unsigned int v28; // edx
  HRESULT v29; // eax
  unsigned int v30; // r9d
  unsigned int v31; // edx
  HRESULT v32; // eax
  bool found[4]; // [rsp+40h] [rbp-C0h] BYREF
  int impersonating; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int packageNameCount; // [rsp+48h] [rbp-B8h] BYREF
  StateRepository::Cache::Entity::PackageIndexIterator_NoThrow packageIndexIterator; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int bufferLength; // [rsp+68h] [rbp-98h] BYREF
  __int64 packageFamilyId; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *localPackageFullName; // [rsp+78h] [rbp-88h] BYREF
  StateRepository::Cache::Entity::Package_NoThrow package; // [rsp+80h] [rbp-80h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter> > v41; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t buffer[128]; // [rsp+110h] [rbp+10h] BYREF
  void *retaddr; // [rsp+258h] [rbp+158h]

  impersonating = 0;
  *manager_0 = 0;
  if ( userTokenInternal )
  {
    v8 = ((__int64 (__fastcall *)(IUserTokenInternal *, _QWORD, int *, __int64))userTokenInternal->Impersonate)(
           userTokenInternal,
           0,
           &impersonating,
           packageFullName);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x8B3u, "onecore\\com\\combase\\catalog\\services.cxx", v8);
      v10 = userTokenInternal->Revert(userTokenInternal, impersonating);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, 0x8A8u, "onecore\\com\\combase\\catalog\\services.cxx", v10);
      return v9;
    }
  }
  localPackageFullName = 0;
  packageNameCount = 1;
  memset_0(buffer, 0, sizeof(buffer));
  bufferLength = 128;
  PackagesByPackageFamily = FindPackagesByPackageFamily(
                              packageFamilyName,
                              0x10u,
                              &packageNameCount,
                              &localPackageFullName,
                              &bufferLength,
                              buffer,
                              0);
  if ( PackagesByPackageFamily )
  {
    if ( PackagesByPackageFamily != 122 )
    {
      if ( PackagesByPackageFamily == 15701 )
      {
        v29 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                0x8ECu,
                "onecore\\com\\combase\\catalog\\services.cxx",
                0x490u,
                "State for package family %ls is corrupt",
                packageFamilyName);
      }
      else
      {
        if ( PackagesByPackageFamily == 87 )
        {
          v30 = 1168;
          v31 = 2295;
        }
        else
        {
          v30 = PackagesByPackageFamily;
          v31 = 2299;
        }
        v29 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                v31,
                "onecore\\com\\combase\\catalog\\services.cxx",
                v30,
                "Family=%ls",
                packageFamilyName);
      }
      goto LABEL_57;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
    v28 = 2279;
LABEL_48:
    v29 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            v28,
            "onecore\\com\\combase\\catalog\\services.cxx",
            0x490u,
            "Family %ls has %d installed packages",
            packageFamilyName,
            packageNameCount);
LABEL_57:
    v26 = v29;
    goto LABEL_58;
  }
  if ( !packageNameCount )
  {
    if ( userTokenInternal )
    {
      v14 = userTokenInternal->Revert(userTokenInternal, impersonating);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, 0x8A8u, "onecore\\com\\combase\\catalog\\services.cxx", v14);
    }
    if ( !manager->m_cacheManager.__ptr_.__value_ )
    {
      v41.wrapper = &manager->m_cacheManager;
      v41.pRaw = 0;
      v41.replace = 1;
      String = SRCacheManager_Open(0, &v41.pRaw);
      wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v41);
      if ( String < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0xA5u,
          "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
          String);
        v16 = 2305;
LABEL_14:
        wil::details::in1diag3::Return_Hr(retaddr, v16, "onecore\\com\\combase\\catalog\\services.cxx", String);
        return (unsigned int)String;
      }
    }
    packageFamilyId = 0;
    String = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
               manager,
               packageFamilyName,
               &packageFamilyId);
    if ( String < 0 )
    {
      v16 = 2309;
      goto LABEL_14;
    }
    if ( packageFamilyId )
    {
      packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
      packageIndexIterator.m_index = 0;
      packageIndexIterator.m_manager = 0;
      v17 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
              manager,
              packageFamilyId,
              &packageIndexIterator);
      String = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x90Du, "onecore\\com\\combase\\catalog\\services.cxx", v17);
LABEL_21:
        value = packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_;
        packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
        if ( value )
          SRCacheContext_Close(value, v18);
        return (unsigned int)String;
      }
      memset(&package, 0, 84);
      package.m_displayName.__ptr_.__value_ = 0;
      package.m_sourceBundle = 0;
      found[0] = 0;
      String = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(
                 &packageIndexIterator,
                 (StateRepository::Cache::Entity::Package_NoThrow::CacheFlags)29,
                 &package,
                 found);
      if ( String < 0 )
      {
        v20 = 2327;
LABEL_25:
        wil::details::in1diag3::Return_Hr(retaddr, v20, "onecore\\com\\combase\\catalog\\services.cxx", String);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
        goto LABEL_21;
      }
      while ( found[0] )
      {
        if ( ((*(_WORD *)package.m_flags & 0x1000) != 0 || (*(_WORD *)package.m_flags2 & 0x100) != 0)
          && package.m_packageType == Server )
        {
          v21 = -1;
          do
            ++v21;
          while ( package.m_packageFullName.__ptr_.__value_[v21] );
          String = WindowsCreateString(package.m_packageFullName.__ptr_.__value_, v21, manager_0);
          if ( String < 0 )
          {
            v20 = 2339;
            goto LABEL_25;
          }
          break;
        }
        ++packageIndexIterator.m_index;
        String = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(
                   &packageIndexIterator,
                   (StateRepository::Cache::Entity::Package_NoThrow::CacheFlags)29,
                   &package,
                   found);
        if ( String < 0 )
        {
          v20 = 2344;
          goto LABEL_25;
        }
      }
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
      v23 = packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_;
      packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_ = 0;
      if ( v23 )
        SRCacheContext_Close(v23, v22);
    }
    return 0;
  }
  if ( packageNameCount != 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
    v28 = 2269;
    goto LABEL_48;
  }
  v24 = -1;
  do
    ++v24;
  while ( localPackageFullName[v24] );
  v25 = WindowsCreateString(localPackageFullName, v24, manager_0);
  v26 = v25;
  if ( v25 >= 0 )
  {
    if ( userTokenInternal )
    {
      v27 = userTokenInternal->Revert(userTokenInternal, impersonating);
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, 0x8A8u, "onecore\\com\\combase\\catalog\\services.cxx", v27);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x8CFu, "onecore\\com\\combase\\catalog\\services.cxx", v25);
LABEL_58:
  if ( userTokenInternal )
  {
    v32 = userTokenInternal->Revert(userTokenInternal, impersonating);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, 0x8A8u, "onecore\\com\\combase\\catalog\\services.cxx", v32);
  }
  return v26;
}

```

## disassembly

```asm
0x1801ddde4  push    rbp
0x1801ddde6  push    rsi
0x1801ddde7  push    rdi
0x1801ddde8  push    r12
0x1801dddea  push    r13
0x1801dddec  push    r14
0x1801dddee  push    r15
0x1801dddf0  lea     rbp, [rsp-120h]
0x1801dddf8  sub     rsp, 220h
0x1801dddff  mov     rax, cs:__security_cookie
0x1801dde06  xor     rax, rsp
0x1801dde09  mov     [rbp+150h+var_40], rax
0x1801dde10  mov     r12, [rbp+150h+manager_0]
0x1801dde17  xor     r13d, r13d
0x1801dde1a  mov     [rsp+250h+impersonating], r13d
0x1801dde1f  mov     rsi, packageFamilyName
0x1801dde22  mov     rdi, userTokenInternal
0x1801dde25  mov     r14, manager
0x1801dde28  mov     [r12], r13
0x1801dde2c  test    userTokenInternal, userTokenInternal
0x1801dde2f  jz      short loc_1801DDEA3
0x1801dde31  mov     rax, [userTokenInternal]
0x1801dde34  lea     packageFamilyName, [rsp+250h+impersonating]
0x1801dde39  xor     edx, edx
0x1801dde3b  mov     manager, rdi
0x1801dde3e  mov     rax, [rax+60h]
0x1801dde42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dde47  mov     r15d, eax
0x1801dde4a  test    eax, eax
0x1801dde4c  jns     short loc_1801DDEA3
0x1801dde4e  mov     manager, [rbp+158h]; callerReturnAddress
0x1801dde55  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801dde5c  mov     r9d, eax; hr
0x1801dde5f  mov     edx, 8B3h; lineNumber
0x1801dde64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dde69  mov     manager, [rdi]
0x1801dde6c  mov     edx, [rsp+250h+impersonating]
0x1801dde70  mov     rax, [manager+68h]
0x1801dde74  mov     manager, rdi
0x1801dde77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dde7c  test    eax, eax
0x1801dde7e  jns     short loc_1801DDE9B
0x1801dde80  mov     manager, [rbp+158h]; callerReturnAddress
0x1801dde87  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801dde8e  mov     r9d, eax; hr
0x1801dde91  mov     edx, 8A8h; lineNumber
0x1801dde96  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801dde9b  mov     eax, r15d
0x1801dde9e  jmp     loc_1801DE2BA
0x1801ddea3  mov     r15d, 1
0x1801ddea9  mov     [rsp+250h+localPackageFullName], r13
0x1801ddeae  xor     edx, edx; Val
0x1801ddeb0  mov     [rsp+250h+packageNameCount], r15d
0x1801ddeb5  mov     r8d, 100h; Size
0x1801ddebb  lea     manager, [rbp+150h+buffer]; void *
0x1801ddebf  call    memset_0
0x1801ddec4  lea     rax, [rbp+150h+buffer]
0x1801ddec8  mov     [rsp+250h+packageProperties], r13; packageProperties
0x1801ddecd  mov     [rsp+250h+var_228], rax; buffer
0x1801dded2  lea     r9, [rsp+250h+localPackageFullName]; packageFullNames
0x1801dded7  lea     rax, [rsp+250h+bufferLength]
0x1801ddedc  mov     [rsp+250h+bufferLength], 80h
0x1801ddee4  lea     packageFamilyName, [rsp+250h+packageNameCount]; count
0x1801ddee9  mov     [rsp+250h+var_230], rax; bufferLength
0x1801ddeee  lea     edx, [r15+0Fh]; packageFilters
0x1801ddef2  mov     manager, rsi; packageFamilyName
0x1801ddef5  call    cs:__imp_FindPackagesByPackageFamily
0x1801ddefb  test    eax, eax
0x1801ddefd  jnz     loc_1801DE210
0x1801ddf03  mov     eax, [rsp+250h+packageNameCount]
0x1801ddf07  test    eax, eax
0x1801ddf09  jnz     loc_1801DE14E
0x1801ddf0f  test    rdi, rdi
0x1801ddf12  jz      short loc_1801DDF46
0x1801ddf14  mov     rax, [rdi]
0x1801ddf17  mov     manager, rdi
0x1801ddf1a  mov     edx, [rsp+250h+impersonating]
0x1801ddf1e  mov     rax, [rax+68h]
0x1801ddf22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ddf27  test    eax, eax
0x1801ddf29  jns     short loc_1801DDF46
0x1801ddf2b  mov     manager, [rbp+158h]; callerReturnAddress
0x1801ddf32  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801ddf39  mov     r9d, eax; hr
0x1801ddf3c  mov     edx, 8A8h; lineNumber
0x1801ddf41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801ddf46  cmp     [r14], r13
0x1801ddf49  jnz     short loc_1801DDFAF
0x1801ddf4b  lea     userTokenInternal, [rbp+150h+var_160.pRaw]
0x1801ddf4f  mov     [rbp+150h+var_160.wrapper], r14
0x1801ddf53  xor     ecx, ecx
0x1801ddf55  mov     [rbp+150h+var_160.pRaw], r13
0x1801ddf59  mov     [rbp+150h+var_160.replace], r15b
0x1801ddf5d  call    cs:__imp_SRCacheManager_Open
0x1801ddf63  lea     manager, [rbp+150h+var_160]; this
0x1801ddf67  mov     edi, eax
0x1801ddf69  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1801ddf6e  test    edi, edi
0x1801ddf70  jns     short loc_1801DDFAF
0x1801ddf72  mov     manager, [rbp+158h]; callerReturnAddress
0x1801ddf79  lea     packageFamilyName, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801ddf80  mov     r9d, edi; hr
0x1801ddf83  mov     edx, 0A5h; lineNumber
0x1801ddf88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ddf8d  mov     edx, 901h; lineNumber
0x1801ddf92  mov     manager, [rbp+158h]; callerReturnAddress
0x1801ddf99  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801ddfa0  mov     r9d, edi; hr
0x1801ddfa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ddfa8  mov     eax, edi
0x1801ddfaa  jmp     loc_1801DE2BA
0x1801ddfaf  lea     packageFamilyName, [rsp+250h+packageFamilyId]; cacheId
0x1801ddfb4  mov     [rsp+250h+packageFamilyId], r13
0x1801ddfb9  mov     userTokenInternal, rsi; packageFamilyName
0x1801ddfbc  mov     manager, r14; manager
0x1801ddfbf  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1801ddfc4  mov     edi, eax
0x1801ddfc6  test    eax, eax
0x1801ddfc8  jns     short loc_1801DDFD1
0x1801ddfca  mov     edx, 905h
0x1801ddfcf  jmp     short loc_1801DDF92
0x1801ddfd1  mov     userTokenInternal, [rsp+250h+packageFamilyId]; packageFamily
0x1801ddfd6  test    userTokenInternal, userTokenInternal
0x1801ddfd9  jz      loc_1801DE1CB
0x1801ddfdf  lea     packageFamilyName, [rsp+250h+packageIndexIterator]; iterator
0x1801ddfe4  mov     [rsp+250h+packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_], r13
0x1801ddfe9  mov     manager, r14; manager
0x1801ddfec  mov     [rsp+250h+packageIndexIterator.m_index], r13d
0x1801ddff1  mov     [rsp+250h+packageIndexIterator.m_manager], r13
0x1801ddff6  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x1801ddffb  mov     edi, eax
0x1801ddffd  test    eax, eax
0x1801ddfff  jns     short loc_1801DE03A
0x1801de001  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de008  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de00f  mov     r9d, eax; hr
0x1801de012  mov     edx, 90Dh; lineNumber
0x1801de017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801de01c  mov     manager, [rsp+250h+packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_]
0x1801de021  mov     [rsp+250h+packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_], r13
0x1801de026  test    manager, manager
0x1801de029  jz      loc_1801DDFA8
0x1801de02f  call    cs:__imp_SRCacheContext_Close
0x1801de035  jmp     loc_1801DDFA8
0x1801de03a  xorps   xmm0, xmm0
0x1801de03d  mov     [rbp+150h+package.m_packageFamily], r13
0x1801de041  mov     esi, 1Dh
0x1801de046  movdqa  xmmword ptr [rbp+150h+package.m__cacheId], xmm0
0x1801de04b  mov     edx, esi; cacheFlags
0x1801de04d  mov     qword ptr [rbp+150h+package.m_packageType], r13
0x1801de051  lea     r9, [rsp+250h+found]; found
0x1801de056  mov     qword ptr [rbp+150h+package.m_flags2], r13
0x1801de05a  lea     packageFamilyName, [rbp+150h+package]; entity
0x1801de05e  mov     [rbp+150h+package.m_volume], r13
0x1801de062  lea     manager, [rsp+250h+packageIndexIterator]; this
0x1801de067  mov     [rbp+150h+package.m_oSMaxVersionTested], r13
0x1801de06b  mov     [rbp+150h+package.m_installedLocation.__ptr_.__value_], r13
0x1801de06f  movdqa  xmmword ptr [rbp+150h+package.m_mutableLink.__ptr_.__value_], xmm0
0x1801de074  mov     [rbp+150h+package.m_targetDeviceFamilyName], r13d
0x1801de078  mov     [rbp+150h+package.m_displayName.__ptr_.__value_], r13
0x1801de07c  mov     [rbp+150h+package.m_sourceBundle], r13
0x1801de080  mov     [rsp+250h+found], r13b
0x1801de085  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1801de08a  mov     edi, eax
0x1801de08c  test    eax, eax
0x1801de08e  jns     short loc_1801DE0B9
0x1801de090  mov     edx, 917h; lineNumber
0x1801de095  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de09c  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de0a3  mov     r9d, edi; hr
0x1801de0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801de0ab  lea     manager, [rbp+150h+package]; this
0x1801de0af  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1801de0b4  jmp     loc_1801DE01C
0x1801de0b9  cmp     [rsp+250h+found], r13b
0x1801de0be  jz      short loc_1801DE12A
0x1801de0c0  test    dword ptr [rbp+150h+package.m_flags], 1000h
0x1801de0c7  jnz     short loc_1801DE0D2
0x1801de0c9  test    dword ptr [rbp+150h+package.m_flags2], 100h
0x1801de0d0  jz      short loc_1801DE0D8
0x1801de0d2  cmp     [rbp+150h+package.m_packageType], r15d
0x1801de0d6  jz      short loc_1801DE100
0x1801de0d8  add     [rsp+250h+packageIndexIterator.m_index], r15d
0x1801de0dd  lea     r9, [rsp+250h+found]; found
0x1801de0e2  lea     packageFamilyName, [rbp+150h+package]; entity
0x1801de0e6  mov     userTokenInternal, rsi; cacheFlags
0x1801de0e9  lea     manager, [rsp+250h+packageIndexIterator]; this
0x1801de0ee  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1801de0f3  mov     edi, eax
0x1801de0f5  test    eax, eax
0x1801de0f7  jns     short loc_1801DE0B9
0x1801de0f9  mov     edx, 928h
0x1801de0fe  jmp     short loc_1801DE095
0x1801de100  mov     manager, [rbp+150h+package.m_packageFullName.__ptr_.__value_]; sourceString
0x1801de104  or      userTokenInternal, 0FFFFFFFFFFFFFFFFh
0x1801de108  inc     userTokenInternal; length
0x1801de10b  cmp     [manager+userTokenInternal*2], r13w
0x1801de110  jnz     short loc_1801DE108
0x1801de112  mov     packageFamilyName, r12; string
0x1801de115  call    WindowsCreateString
0x1801de11a  mov     edi, eax
0x1801de11c  test    eax, eax
0x1801de11e  jns     short loc_1801DE12A
0x1801de120  mov     edx, 923h
0x1801de125  jmp     loc_1801DE095
0x1801de12a  lea     manager, [rbp+150h+package]; this
0x1801de12e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1801de133  mov     manager, [rsp+250h+packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_]
0x1801de138  mov     [rsp+250h+packageIndexIterator.m_context.m_cacheContext.__ptr_.__value_], r13
0x1801de13d  test    manager, manager
0x1801de140  jz      loc_1801DE1CB
0x1801de146  call    cs:__imp_SRCacheContext_Close
0x1801de14c  jmp     short loc_1801DE1CB
0x1801de14e  cmp     eax, r15d
0x1801de151  jnz     short loc_1801DE1D2
0x1801de153  mov     manager, [rsp+250h+localPackageFullName]; sourceString
0x1801de158  or      userTokenInternal, 0FFFFFFFFFFFFFFFFh
0x1801de15c  inc     userTokenInternal; length
0x1801de15f  cmp     [manager+userTokenInternal*2], r13w
0x1801de164  jnz     short loc_1801DE15C
0x1801de166  mov     packageFamilyName, r12; string
0x1801de169  call    WindowsCreateString
0x1801de16e  mov     esi, eax
0x1801de170  test    eax, eax
0x1801de172  jns     short loc_1801DE194
0x1801de174  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de17b  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de182  mov     r9d, eax; hr
0x1801de185  mov     edx, 8CFh; lineNumber
0x1801de18a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801de18f  jmp     loc_1801DE281
0x1801de194  test    rdi, rdi
0x1801de197  jz      short loc_1801DE1CB
0x1801de199  mov     rax, [rdi]
0x1801de19c  mov     manager, rdi
0x1801de19f  mov     edx, [rsp+250h+impersonating]
0x1801de1a3  mov     rax, [rax+68h]
0x1801de1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de1ac  test    eax, eax
0x1801de1ae  jns     short loc_1801DE1CB
0x1801de1b0  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de1b7  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de1be  mov     r9d, eax; hr
0x1801de1c1  mov     edx, 8A8h; lineNumber
0x1801de1c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801de1cb  xor     eax, eax
0x1801de1cd  jmp     loc_1801DE2BA
0x1801de1d2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "More than one package per family installed")
0x1801de1d7  mov     edx, 8DDh; lineNumber
0x1801de1dc  mov     eax, [rsp+250h+packageNameCount]
0x1801de1e0  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de1e7  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de1ee  mov     r9d, 490h; err
0x1801de1f4  mov     dword ptr [rsp+250h+packageProperties], eax
0x1801de1f8  lea     rax, aFamilyLsHasDIn; "Family %ls has %d installed packages"
0x1801de1ff  mov     [rsp+250h+var_228], rsi
0x1801de204  mov     [rsp+250h+var_230], rax; formatString
0x1801de209  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1801de20e  jmp     short loc_1801DE27F
0x1801de210  cmp     eax, 7Ah ; 'z'
0x1801de213  jnz     short loc_1801DE221
0x1801de215  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "More than one package per family installed")
0x1801de21a  mov     edx, 8E7h
0x1801de21f  jmp     short loc_1801DE1DC
0x1801de221  mov     [rsp+250h+var_228], rsi
0x1801de226  cmp     eax, 3D55h
0x1801de22b  jnz     short loc_1801DE246
0x1801de22d  lea     rax, aStateForPackag; "State for package family %ls is corrupt"
0x1801de234  mov     r9d, 490h
0x1801de23a  mov     [rsp+250h+var_230], rax
0x1801de23f  mov     edx, 8ECh
0x1801de244  jmp     short loc_1801DE26C
0x1801de246  lea     userTokenInternal, aFamilyLs; "Family=%ls"
0x1801de24d  mov     [rsp+250h+var_230], userTokenInternal; formatString
0x1801de252  cmp     eax, 57h ; 'W'
0x1801de255  jnz     short loc_1801DE264
0x1801de257  mov     r9d, 490h
0x1801de25d  mov     edx, 8F7h
0x1801de262  jmp     short loc_1801DE26C
0x1801de264  mov     r9d, eax; err
0x1801de267  mov     edx, 8FBh; lineNumber
0x1801de26c  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de273  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de27a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1801de27f  mov     esi, eax
0x1801de281  test    rdi, rdi
0x1801de284  jz      short loc_1801DE2B8
0x1801de286  mov     manager, [rdi]
0x1801de289  mov     edx, [rsp+250h+impersonating]
0x1801de28d  mov     rax, [manager+68h]
0x1801de291  mov     manager, rdi
0x1801de294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de299  test    eax, eax
0x1801de29b  jns     short loc_1801DE2B8
0x1801de29d  mov     manager, [rbp+158h]; callerReturnAddress
0x1801de2a4  lea     packageFamilyName, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x1801de2ab  mov     r9d, eax; hr
0x1801de2ae  mov     edx, 8A8h; lineNumber
0x1801de2b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801de2b8  mov     eax, esi
  ... truncated ...
```
