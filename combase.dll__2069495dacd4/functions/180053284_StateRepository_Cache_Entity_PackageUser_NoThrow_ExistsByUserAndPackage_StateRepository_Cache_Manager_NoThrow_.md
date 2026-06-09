# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x180053284`
- end: `0x180053714`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `1168`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, __int64 user, __int64 package, bool *found)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180052bb8`
- `0x1802007bc`

## callees

- `0x18003a8bc`
- `0x180052310`
- `0x180053284`
- `0x180053efc`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180053392`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18005340b`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180053392`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18005340b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180053301`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180053301`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180053469`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180053469`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053549`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005358c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053549`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005358c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005332b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053493`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053534`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005355e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053577`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800535a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005332b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053493`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053534`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005355e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053577`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800535a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800534e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800534e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x1800534ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x1800534ba`

## string_xrefs

- `0x180053620`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800536a2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800536cc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180053516`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x1800535d4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180053640`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180053687`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x1800534f6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800535f4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18005365b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800536f6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 user,
        __int64 package,
        bool *found)
{
  SRCacheManager *v7; // rcx
  HRESULT v8; // ebx
  __int64 v9; // rcx
  bool v10; // r8
  HRESULT v11; // eax
  __int64 v12; // rcx
  HRESULT IsEmpty; // eax
  HRESULT v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // edx
  __int64 v17; // rdx
  SRCacheContext *v18; // rcx
  wchar_t *v19; // rcx
  SRCacheContext *v20; // rcx
  SRCacheContext *v22; // rcx
  wchar_t *v23; // rcx
  SRCacheContext *v24; // rcx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  StateRepository::Cache::Context_NoThrow indexContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Context_NoThrow context; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD v30[4]; // [rsp+30h] [rbp-D0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t value[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v33; // [rsp+268h] [rbp+168h] BYREF
  char v34; // [rsp+270h] [rbp+170h]
  void *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *found = 0;
  if ( !user )
  {
    v25 = 153;
LABEL_37:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v25,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      -2147024809);
    return (unsigned int)v8;
  }
  if ( !package )
  {
    v25 = 154;
    goto LABEL_37;
  }
  v7 = manager->m_cacheManager.__ptr_.__value_;
  *(_QWORD *)value = &indexContext;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  v33 = 0;
  v34 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageUser\\Index\\UserAndPackage", 0, &v33);
  if ( v34 )
  {
    v9 = **(_QWORD **)value;
    **(_QWORD **)value = v33;
    if ( v9 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v27 = 158;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v27,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      v8);
LABEL_26:
    v20 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v20 )
      SRCacheContext_Close(v20, v17);
    return (unsigned int)v8;
  }
  if ( !indexContext.m_cacheContext.__ptr_.__value_ )
  {
    v8 = -2140733422;
    v27 = 159;
    goto LABEL_44;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(user, value, 17, 16) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
    goto LABEL_46;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append(&key, value);
  if ( v8 < 0 )
  {
LABEL_46:
    v26 = 162;
    goto LABEL_41;
  }
  v11 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(&key, key.m_length + 2, v10);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x16Du,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      v11);
    v26 = 163;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v26,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      v8);
LABEL_24:
    v19 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_26;
  }
  *(_DWORD *)&key.m_key[key.m_length++] = 94;
  if ( (unsigned int)_o__ui64tow_s(package, value, 17, 16) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
    goto LABEL_48;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append(&key, value);
  if ( v8 < 0 )
  {
LABEL_48:
    v26 = 164;
    goto LABEL_41;
  }
  *(_QWORD *)value = &context;
  context.m_cacheContext.__ptr_.__value_ = 0;
  v33 = 0;
  v34 = 1;
  v8 = SRCacheContext_OpenSubContext(indexContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v33);
  if ( v34 )
  {
    v12 = **(_QWORD **)value;
    **(_QWORD **)value = v33;
    if ( v12 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v16 = 168;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v16,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      v8);
    v18 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v17);
    goto LABEL_24;
  }
  if ( !context.m_cacheContext.__ptr_.__value_ )
    goto LABEL_20;
  v30[0] = 0;
  IsEmpty = SRCacheContext_IsEmpty(context.m_cacheContext.__ptr_.__value_, v30);
  v8 = IsEmpty;
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2B8u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      IsEmpty);
    v16 = 172;
    goto LABEL_22;
  }
  *found = v30[0] == 0;
LABEL_20:
  v14 = SRCacheContext_AddToCache(indexContext.m_cacheContext.__ptr_.__value_, L"PackageUser\\Index\\UserAndPackage");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1A6u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v14);
    v16 = 176;
    goto LABEL_22;
  }
  v22 = context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v22 )
    ((void (*)(void))SRCacheContext_Close)();
  v23 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v23 )
    SRCache_Free();
  v24 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v24 )
    SRCacheContext_Close(v24, v15);
  return 0;
}

```

## disassembly

```asm
0x180053284  push    rbp
0x180053286  push    rbx
0x180053287  push    rsi
0x180053288  push    rdi
0x180053289  push    r14
0x18005328b  push    r15
0x18005328d  lea     rbp, [rsp-198h]
0x180053295  sub     rsp, 298h
0x18005329c  mov     rax, cs:__security_cookie
0x1800532a3  xor     rax, rsp
0x1800532a6  mov     [rbp+1C0h+var_38], rax
0x1800532ad  xor     r15d, r15d
0x1800532b0  mov     r14, found
0x1800532b3  mov     [found], r15b
0x1800532b6  mov     rdi, package
0x1800532b9  mov     rsi, user
0x1800532bc  test    user, user
0x1800532bf  jz      loc_1800535C8
0x1800532c5  test    package, package
0x1800532c8  jz      loc_180053612
0x1800532ce  mov     manager, [manager]
0x1800532d1  lea     rax, [rsp+2C0h+indexContext]
0x1800532d6  lea     found, [rbp+1C0h+var_58]
0x1800532dd  mov     qword ptr [rbp+1C0h+value], rax
0x1800532e4  xor     r8d, r8d
0x1800532e7  mov     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x1800532ec  lea     user, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x1800532f3  mov     [rbp+1C0h+var_58], r15
0x1800532fa  mov     [rbp+1C0h+var_50], 1
0x180053301  call    cs:__imp_SRCacheContext_Open
0x180053307  mov     ebx, eax
0x180053309  cmp     [rbp+1C0h+var_50], r15b
0x180053310  jz      short loc_180053331
0x180053312  mov     package, qword ptr [rbp+1C0h+value]
0x180053319  mov     user, [rbp+1C0h+var_58]
0x180053320  mov     manager, [package]
0x180053323  mov     [package], user
0x180053326  test    manager, manager
0x180053329  jz      short loc_180053331
0x18005332b  call    cs:__imp_SRCacheContext_Close
0x180053331  test    ebx, ebx
0x180053333  js      loc_180053654
0x180053339  cmp     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18005333e  setnz   al
0x180053341  test    al, al
0x180053343  jz      loc_180053676
0x180053349  xor     edx, edx; Val
0x18005334b  mov     [rsp+2C0h+key.m_largeKey.__ptr_.__value_], r15
0x180053350  mov     r8d, 200h; Size
0x180053356  lea     manager, [rsp+2C0h+key.m_smallKey]; void *
0x18005335b  call    memset_0
0x180053360  mov     r9d, 10h
0x180053366  mov     [rbp+1C0h+key.m_length], r15
0x18005336d  lea     rax, [rsp+2C0h+key.m_smallKey]
0x180053372  mov     [rbp+1C0h+key.m_capacity], 100h
0x18005337d  lea     user, [rbp+1C0h+value]
0x180053384  mov     [rbp+1C0h+key.m_key], rax
0x18005338b  mov     manager, rsi
0x18005338e  lea     r8d, [found+1]
0x180053392  call    cs:__imp__o__ui64tow_s
0x180053398  test    eax, eax
0x18005339a  jnz     loc_18005369B
0x1800533a0  lea     user, [rbp+1C0h+value]; value
0x1800533a7  lea     manager, [rsp+2C0h+key]; this
0x1800533ac  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800533b1  mov     ebx, eax
0x1800533b3  test    eax, eax
0x1800533b5  js      loc_1800536BB
0x1800533bb  mov     user, [rbp+1C0h+key.m_length]
0x1800533c2  lea     manager, [rsp+2C0h+key]; this
0x1800533c7  add     user, 2; capacity
0x1800533cb  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x1800533d0  mov     ebx, eax
0x1800533d2  test    eax, eax
0x1800533d4  js      loc_180053619
0x1800533da  mov     r10, [rbp+1C0h+key.m_length]
0x1800533e1  mov     r9d, 10h
0x1800533e7  mov     user, [rbp+1C0h+key.m_key]
0x1800533ee  mov     manager, rdi
0x1800533f1  lea     r8d, [found+1]
0x1800533f5  mov     dword ptr [user+r10*2], 5Eh ; '^'
0x1800533fd  lea     user, [rbp+1C0h+value]
0x180053404  inc     [rbp+1C0h+key.m_length]
0x18005340b  call    cs:__imp__o__ui64tow_s
0x180053411  test    eax, eax
0x180053413  jnz     loc_1800536C5
0x180053419  lea     user, [rbp+1C0h+value]; value
0x180053420  lea     manager, [rsp+2C0h+key]; this
0x180053425  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18005342a  mov     ebx, eax
0x18005342c  test    eax, eax
0x18005342e  js      loc_1800536E5
0x180053434  mov     user, [rbp+1C0h+key.m_key]
0x18005343b  lea     rax, [rsp+2C0h+context]
0x180053440  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053445  lea     found, [rbp+1C0h+var_58]
0x18005344c  xor     r8d, r8d
0x18005344f  mov     qword ptr [rbp+1C0h+value], rax
0x180053456  mov     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x18005345b  mov     [rbp+1C0h+var_58], r15
0x180053462  mov     [rbp+1C0h+var_50], 1
0x180053469  call    cs:__imp_SRCacheContext_OpenSubContext
0x18005346f  mov     ebx, eax
0x180053471  cmp     [rbp+1C0h+var_50], r15b
0x180053478  jz      short loc_180053499
0x18005347a  mov     package, qword ptr [rbp+1C0h+value]
0x180053481  mov     user, [rbp+1C0h+var_58]
0x180053488  mov     manager, [package]
0x18005348b  mov     [package], user
0x18005348e  test    manager, manager
0x180053491  jz      short loc_180053499
0x180053493  call    cs:__imp_SRCacheContext_Close
0x180053499  test    ebx, ebx
0x18005349b  js      loc_1800536EF
0x1800534a1  mov     manager, [rsp+2C0h+context.m_cacheContext.__ptr_.__value_]
0x1800534a6  test    manager, manager
0x1800534a9  setnz   al
0x1800534ac  test    al, al
0x1800534ae  jz      short loc_1800534D7
0x1800534b0  lea     user, [rsp+2C0h+var_290]
0x1800534b5  mov     [rsp+2C0h+var_290], r15d
0x1800534ba  call    cs:__imp_SRCacheContext_IsEmpty
0x1800534c0  mov     ebx, eax
0x1800534c2  test    eax, eax
0x1800534c4  js      loc_1800535ED
0x1800534ca  cmp     [rsp+2C0h+var_290], r15d
0x1800534cf  setnz   al
0x1800534d2  xor     al, 1
0x1800534d4  mov     [r14], al
0x1800534d7  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1800534dc  lea     user, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x1800534e3  call    cs:__imp_SRCacheContext_AddToCache
0x1800534e9  mov     ebx, eax
0x1800534eb  test    eax, eax
0x1800534ed  jns     short loc_180053568
0x1800534ef  mov     manager, [rbp+1C8h]; callerReturnAddress
0x1800534f6  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800534fd  mov     r9d, eax; hr
0x180053500  mov     edx, 1A6h; lineNumber
0x180053505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005350a  mov     edx, 0B0h; lineNumber
0x18005350f  mov     manager, [rbp+1C8h]; callerReturnAddress
0x180053516  lea     package, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005351d  mov     r9d, ebx; hr
0x180053520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053525  mov     manager, [rsp+2C0h+context.m_cacheContext.__ptr_.__value_]
0x18005352a  mov     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x18005352f  test    manager, manager
0x180053532  jz      short loc_18005353A
0x180053534  call    cs:__imp_SRCacheContext_Close
0x18005353a  mov     manager, [rsp+2C0h+key.m_largeKey.__ptr_.__value_]
0x18005353f  mov     [rsp+2C0h+key.m_largeKey.__ptr_.__value_], r15
0x180053544  test    manager, manager
0x180053547  jz      short loc_18005354F
0x180053549  call    cs:__imp_SRCache_Free
0x18005354f  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053554  mov     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x180053559  test    manager, manager
0x18005355c  jz      short loc_180053564
0x18005355e  call    cs:__imp_SRCacheContext_Close
0x180053564  mov     eax, ebx
0x180053566  jmp     short loc_1800535A9
0x180053568  mov     manager, [rsp+2C0h+context.m_cacheContext.__ptr_.__value_]
0x18005356d  mov     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x180053572  test    manager, manager
0x180053575  jz      short loc_18005357D
0x180053577  call    cs:__imp_SRCacheContext_Close
0x18005357d  mov     manager, [rsp+2C0h+key.m_largeKey.__ptr_.__value_]
0x180053582  mov     [rsp+2C0h+key.m_largeKey.__ptr_.__value_], r15
0x180053587  test    manager, manager
0x18005358a  jz      short loc_180053592
0x18005358c  call    cs:__imp_SRCache_Free
0x180053592  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053597  mov     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18005359c  test    manager, manager
0x18005359f  jz      short loc_1800535A7
0x1800535a1  call    cs:__imp_SRCacheContext_Close
0x1800535a7  xor     eax, eax
0x1800535a9  mov     manager, [rbp+1C0h+var_38]
0x1800535b0  xor     manager, rsp; StackCookie
0x1800535b3  call    __security_check_cookie
0x1800535b8  add     rsp, 298h
0x1800535bf  pop     r15
0x1800535c1  pop     r14
0x1800535c3  pop     rdi
0x1800535c4  pop     rsi
0x1800535c5  pop     rbx
0x1800535c6  pop     rbp
0x1800535c7  retn
0x1800535c8  mov     edx, 99h; lineNumber
0x1800535cd  mov     manager, [rbp+1C8h]; callerReturnAddress
0x1800535d4  lea     package, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800535db  mov     ebx, 80070057h
0x1800535e0  mov     r9d, ebx; hr
0x1800535e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800535e8  jmp     loc_180053564
0x1800535ed  mov     manager, [rbp+1C8h]; callerReturnAddress
0x1800535f4  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800535fb  mov     r9d, ebx; hr
0x1800535fe  mov     edx, 2B8h; lineNumber
0x180053603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053608  mov     edx, 0ACh
0x18005360d  jmp     loc_18005350F
0x180053612  mov     edx, 9Ah
0x180053617  jmp     short loc_1800535CD
0x180053619  mov     manager, [rbp+1C8h]; callerReturnAddress
0x180053620  lea     package, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053627  mov     r9d, ebx; hr
0x18005362a  mov     edx, 16Dh; lineNumber
0x18005362f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053634  mov     edx, 0A3h; lineNumber
0x180053639  mov     manager, [rbp+1C8h]; callerReturnAddress
0x180053640  lea     package, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053647  mov     r9d, ebx; hr
0x18005364a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005364f  jmp     loc_18005353A
0x180053654  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18005365b  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053662  mov     r9d, ebx; hr
0x180053665  mov     edx, 18Ch; lineNumber
0x18005366a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005366f  mov     edx, 9Eh
0x180053674  jmp     short loc_180053680
0x180053676  mov     ebx, 80670012h
0x18005367b  mov     edx, 9Fh; lineNumber
0x180053680  mov     manager, [rbp+1C8h]; callerReturnAddress
0x180053687  lea     package, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005368e  mov     r9d, ebx; hr
0x180053691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053696  jmp     loc_18005354F
0x18005369b  mov     manager, [rbp+1C8h]; callerReturnAddress
0x1800536a2  lea     package, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800536a9  mov     ebx, 8000FFFFh
0x1800536ae  mov     edx, 166h; lineNumber
0x1800536b3  mov     r9d, ebx; hr
0x1800536b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800536bb  mov     edx, 0A2h
0x1800536c0  jmp     loc_180053639
0x1800536c5  mov     manager, [rbp+1C8h]; callerReturnAddress
0x1800536cc  lea     package, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800536d3  mov     ebx, 8000FFFFh
0x1800536d8  mov     edx, 166h; lineNumber
0x1800536dd  mov     r9d, ebx; hr
0x1800536e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800536e5  mov     edx, 0A4h
0x1800536ea  jmp     loc_180053639
0x1800536ef  mov     manager, [rbp+1C8h]; callerReturnAddress
0x1800536f6  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800536fd  mov     r9d, ebx; hr
0x180053700  mov     edx, 1B0h; lineNumber
0x180053705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005370a  mov     edx, 0A8h
0x18005370f  jmp     loc_18005350F
```
