# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x1800523b8`
- end: `0x1800526cf`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `791`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, const wchar_t *userSidAsString, __int64 *cacheId)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180052bb8`
- `0x180201484`

## callees

- `0x18003a8bc`
- `0x1800523b8`
- `0x180053efc`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180052416`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180052416`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800524d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800524d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800525e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800525e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800525a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052641`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800525a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052641`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005243a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800524f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052577`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800525be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005262c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052656`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005243a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800524f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052577`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800525be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005262c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052656`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180052522`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180052522`

## string_xrefs

- `0x18005240f`: `User\Index\UserSid`
- `0x18005251b`: `User\Index\UserSid`
- `0x180052559`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052586`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052696`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052539`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800525ff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18005266a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800526b1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        StateRepository::Cache::Manager_NoThrow *manager,
        const wchar_t *userSidAsString,
        __int64 *cacheId)
{
  SRCacheManager *value; // rcx
  HRESULT v6; // ebx
  SRCacheContext *v7; // rdx
  SRCacheContext *v8; // rcx
  HRESULT v9; // eax
  SRCacheContext *v10; // rdx
  SRCacheContext *v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // edx
  __int64 v15; // rdx
  SRCacheContext *v16; // rcx
  wchar_t *v17; // rcx
  SRCacheContext *v18; // rcx
  HRESULT v20; // eax
  SRCacheContext *v21; // rcx
  wchar_t *v22; // rcx
  SRCacheContext *v23; // rcx
  unsigned int v24; // edx
  StateRepository::Cache::Context_NoThrow indexContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Context_NoThrow context; // [rsp+28h] [rbp-D8h] BYREF
  StateRepository::Cache::Context_NoThrow *p_indexContext; // [rsp+30h] [rbp-D0h]
  SRCacheContext *v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  StateRepository::Cache::Key_NoThrow key; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v29 = 1;
  *cacheId = 0;
  value = manager->m_cacheManager.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  p_indexContext = &indexContext;
  v28 = 0;
  v6 = SRCacheContext_Open(value, L"User\\Index\\UserSid", 0, &v28);
  if ( v29 )
  {
    v7 = v28;
    v8 = p_indexContext->m_cacheContext.__ptr_.__value_;
    p_indexContext->m_cacheContext.__ptr_.__value_ = v28;
    if ( v8 )
      SRCacheContext_Close(v8, v7);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v6);
    v24 = 185;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v24,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      v6);
LABEL_19:
    v18 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v15);
    return (unsigned int)v6;
  }
  if ( !indexContext.m_cacheContext.__ptr_.__value_ )
  {
    v6 = -2140733422;
    v24 = 186;
    goto LABEL_33;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_key = key.m_smallKey;
  key.m_capacity = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append(&key, userSidAsString);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xBDu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      v9);
LABEL_17:
    v17 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v17 )
      SRCache_Free();
    goto LABEL_19;
  }
  p_indexContext = &context;
  context.m_cacheContext.__ptr_.__value_ = 0;
  v28 = 0;
  v29 = 1;
  v6 = SRCacheContext_OpenSubContext(indexContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v28);
  if ( v29 )
  {
    v10 = v28;
    v11 = p_indexContext->m_cacheContext.__ptr_.__value_;
    p_indexContext->m_cacheContext.__ptr_.__value_ = v28;
    if ( v11 )
      SRCacheContext_Close(v11, v10);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v6);
    v14 = 193;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v14,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      v6);
    v16 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v16 )
      SRCacheContext_Close(v16, v15);
    goto LABEL_17;
  }
  if ( context.m_cacheContext.__ptr_.__value_ )
  {
    v20 = SRCacheContext_EnumerateData(context.m_cacheContext.__ptr_.__value_, 0, cacheId);
    v6 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x2A6u,
        "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        v20);
      v14 = 196;
      goto LABEL_14;
    }
  }
  v12 = SRCacheContext_AddToCache(indexContext.m_cacheContext.__ptr_.__value_, L"User\\Index\\UserSid");
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1A6u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v12);
    v14 = 199;
    goto LABEL_14;
  }
  v21 = context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v13);
  v22 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v22 )
    SRCache_Free();
  v23 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v23 )
    SRCacheContext_Close(v23, v13);
  return 0;
}

```

## disassembly

```asm
0x1800523b8  push    rbp
0x1800523ba  push    rbx
0x1800523bb  push    rsi
0x1800523bc  push    rdi
0x1800523bd  push    r14
0x1800523bf  lea     rbp, [rsp-180h]
0x1800523c7  sub     rsp, 280h
0x1800523ce  mov     rax, cs:__security_cookie
0x1800523d5  xor     rax, rsp
0x1800523d8  mov     [rbp+1A0h+var_30], rax
0x1800523df  xor     r14d, r14d
0x1800523e2  mov     [rsp+2A0h+var_260], 1
0x1800523e7  mov     [cacheId], r14
0x1800523ea  lea     rax, [rsp+2A0h+indexContext]
0x1800523ef  mov     manager, [manager]
0x1800523f2  lea     r9, [rsp+2A0h+var_268]
0x1800523f7  mov     rdi, cacheId
0x1800523fa  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x1800523ff  mov     rsi, userSidAsString
0x180052402  mov     [rsp+2A0h+var_270], rax
0x180052407  xor     r8d, r8d
0x18005240a  mov     [rsp+2A0h+var_268], r14
0x18005240f  lea     userSidAsString, aUserIndexUsers; "User\\Index\\UserSid"
0x180052416  call    cs:__imp_SRCacheContext_Open
0x18005241c  mov     ebx, eax
0x18005241e  cmp     [rsp+2A0h+var_260], r14b
0x180052423  jz      short loc_180052440
0x180052425  mov     cacheId, [rsp+2A0h+var_270]
0x18005242a  mov     userSidAsString, [rsp+2A0h+var_268]
0x18005242f  mov     manager, [cacheId]
0x180052432  mov     [cacheId], userSidAsString
0x180052435  test    manager, manager
0x180052438  jz      short loc_180052440
0x18005243a  call    cs:__imp_SRCacheContext_Close
0x180052440  test    ebx, ebx
0x180052442  js      loc_180052663
0x180052448  cmp     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x18005244d  setnz   al
0x180052450  test    al, al
0x180052452  jz      loc_180052685
0x180052458  xor     edx, edx; Val
0x18005245a  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x18005245f  mov     r8d, 200h; Size
0x180052465  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x18005246a  call    memset_0
0x18005246f  lea     rax, [rsp+2A0h+key.m_smallKey]
0x180052474  mov     [rbp+1A0h+key.m_length], r14
0x18005247b  mov     userSidAsString, rsi; value
0x18005247e  mov     [rbp+1A0h+key.m_key], rax
0x180052485  lea     manager, [rsp+2A0h+key]; this
0x18005248a  mov     [rbp+1A0h+key.m_capacity], 100h
0x180052495  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18005249a  mov     ebx, eax
0x18005249c  test    eax, eax
0x18005249e  js      loc_18005257F
0x1800524a4  mov     userSidAsString, [rbp+1A0h+key.m_key]
0x1800524ab  lea     rax, [rsp+2A0h+context]
0x1800524b0  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1800524b5  lea     r9, [rsp+2A0h+var_268]
0x1800524ba  xor     r8d, r8d
0x1800524bd  mov     [rsp+2A0h+var_270], rax
0x1800524c2  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x1800524c7  mov     [rsp+2A0h+var_268], r14
0x1800524cc  mov     [rsp+2A0h+var_260], 1
0x1800524d1  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800524d7  mov     ebx, eax
0x1800524d9  cmp     [rsp+2A0h+var_260], r14b
0x1800524de  jz      short loc_1800524FB
0x1800524e0  mov     cacheId, [rsp+2A0h+var_270]
0x1800524e5  mov     userSidAsString, [rsp+2A0h+var_268]
0x1800524ea  mov     manager, [cacheId]
0x1800524ed  mov     [cacheId], userSidAsString
0x1800524f0  test    manager, manager
0x1800524f3  jz      short loc_1800524FB
0x1800524f5  call    cs:__imp_SRCacheContext_Close
0x1800524fb  test    ebx, ebx
0x1800524fd  js      loc_1800526AA
0x180052503  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x180052508  test    manager, manager
0x18005250b  setnz   al
0x18005250e  test    al, al
0x180052510  jnz     loc_1800525E3
0x180052516  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18005251b  lea     userSidAsString, aUserIndexUsers; "User\\Index\\UserSid"
0x180052522  call    cs:__imp_SRCacheContext_AddToCache
0x180052528  mov     ebx, eax
0x18005252a  test    eax, eax
0x18005252c  jns     loc_18005261D
0x180052532  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052539  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052540  mov     r9d, eax; hr
0x180052543  mov     edx, 1A6h; lineNumber
0x180052548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005254d  mov     edx, 0C7h; lineNumber
0x180052552  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052559  lea     cacheId, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052560  mov     r9d, ebx; hr
0x180052563  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052568  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x18005256d  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x180052572  test    manager, manager
0x180052575  jz      short loc_18005259A
0x180052577  call    cs:__imp_SRCacheContext_Close
0x18005257d  jmp     short loc_18005259A
0x18005257f  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052586  lea     cacheId, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005258d  mov     r9d, ebx; hr
0x180052590  mov     edx, 0BDh; lineNumber
0x180052595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005259a  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18005259f  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x1800525a4  test    manager, manager
0x1800525a7  jz      short loc_1800525AF
0x1800525a9  call    cs:__imp_SRCache_Free
0x1800525af  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1800525b4  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x1800525b9  test    manager, manager
0x1800525bc  jz      short loc_1800525C4
0x1800525be  call    cs:__imp_SRCacheContext_Close
0x1800525c4  mov     eax, ebx
0x1800525c6  mov     manager, [rbp+1A0h+var_30]
0x1800525cd  xor     manager, rsp; StackCookie
0x1800525d0  call    __security_check_cookie
0x1800525d5  add     rsp, 280h
0x1800525dc  pop     r14
0x1800525de  pop     rdi
0x1800525df  pop     rsi
0x1800525e0  pop     rbx
0x1800525e1  pop     rbp
0x1800525e2  retn
0x1800525e3  mov     cacheId, rdi
0x1800525e6  xor     edx, edx
0x1800525e8  call    cs:__imp_SRCacheContext_EnumerateData
0x1800525ee  mov     ebx, eax
0x1800525f0  test    eax, eax
0x1800525f2  jns     loc_180052516
0x1800525f8  mov     manager, [rbp+1A8h]; callerReturnAddress
0x1800525ff  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052606  mov     r9d, eax; hr
0x180052609  mov     edx, 2A6h; lineNumber
0x18005260e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052613  mov     edx, 0C4h
0x180052618  jmp     loc_180052552
0x18005261d  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x180052622  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x180052627  test    manager, manager
0x18005262a  jz      short loc_180052632
0x18005262c  call    cs:__imp_SRCacheContext_Close
0x180052632  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180052637  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x18005263c  test    manager, manager
0x18005263f  jz      short loc_180052647
0x180052641  call    cs:__imp_SRCache_Free
0x180052647  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18005264c  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x180052651  test    manager, manager
0x180052654  jz      short loc_18005265C
0x180052656  call    cs:__imp_SRCacheContext_Close
0x18005265c  xor     eax, eax
0x18005265e  jmp     loc_1800525C6
0x180052663  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18005266a  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052671  mov     r9d, ebx; hr
0x180052674  mov     edx, 18Ch; lineNumber
0x180052679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005267e  mov     edx, 0B9h
0x180052683  jmp     short loc_18005268F
0x180052685  mov     ebx, 80670012h
0x18005268a  mov     edx, 0BAh; lineNumber
0x18005268f  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052696  lea     cacheId, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005269d  mov     r9d, ebx; hr
0x1800526a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800526a5  jmp     loc_1800525AF
0x1800526aa  mov     manager, [rbp+1A8h]; callerReturnAddress
0x1800526b1  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800526b8  mov     r9d, ebx; hr
0x1800526bb  mov     edx, 1B0h; lineNumber
0x1800526c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800526c5  mov     edx, 0C1h
0x1800526ca  jmp     loc_180052552
```
