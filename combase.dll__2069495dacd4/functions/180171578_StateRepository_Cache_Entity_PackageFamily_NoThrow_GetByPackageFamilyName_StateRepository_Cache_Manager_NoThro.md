# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180171578`
- end: `0x180171812`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, const wchar_t *packageFamilyName, __int64 *cacheId)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180171068`
- `0x1801712a4`
- `0x1801ddde4`

## callees

- `0x18003a8bc`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x18012faa8`
- `0x180171578`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801715d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801715d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180171704`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180171704`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801716cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801717d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801716cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801717d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171763`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801717c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801717ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171763`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801717c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801717ed`

## string_xrefs

- `0x180171613`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1801716a5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180171741`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1801715f3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180171721`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        StateRepository::Cache::Manager_NoThrow *manager,
        const wchar_t *packageFamilyName,
        __int64 *cacheId)
{
  SRCacheManager *value; // rcx
  HRESULT v6; // ebx
  unsigned int v7; // edx
  __int64 v8; // rdx
  SRCacheContext *v9; // rcx
  HRESULT v11; // eax
  wchar_t *v12; // rcx
  unsigned int v13; // edx
  SRCacheContext *v14; // rcx
  __int64 v15; // rdx
  SRCacheContext *v16; // rcx
  wchar_t *v17; // rcx
  SRCacheContext *v18; // rcx
  StateRepository::Cache::Context_NoThrow indexContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Context_NoThrow context; // [rsp+28h] [rbp-D8h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> > v21; // [rsp+30h] [rbp-D0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v21.replace = 1;
  *cacheId = 0;
  value = manager->m_cacheManager.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  v21.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&indexContext;
  v21.pRaw = 0;
  v6 = SRCacheContext_Open(value, L"PackageFamily\\Index\\PackageFamilyName", 0, &v21.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v6);
    v7 = 193;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v7,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      v6);
LABEL_4:
    v9 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v9 )
      SRCacheContext_Close(v9, v8);
    return (unsigned int)v6;
  }
  if ( !indexContext.m_cacheContext.__ptr_.__value_ )
  {
    v6 = -2140733422;
    v7 = 194;
    goto LABEL_3;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_key = key.m_smallKey;
  key.m_capacity = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append(&key, packageFamilyName);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xC5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      v11);
LABEL_11:
    v12 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v21.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&context;
  context.m_cacheContext.__ptr_.__value_ = 0;
  v21.pRaw = 0;
  v21.replace = 1;
  v6 = SRCacheContext_OpenSubContext(indexContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v21.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v6);
    v13 = 201;
    goto LABEL_15;
  }
  if ( context.m_cacheContext.__ptr_.__value_ )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData(&context, 0, cacheId);
    if ( v6 < 0 )
    {
      v13 = 204;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(&indexContext, L"PackageFamily\\Index\\PackageFamilyName");
  if ( v6 < 0 )
  {
    v13 = 207;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v13,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      v6);
    v14 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v8);
    goto LABEL_11;
  }
  v16 = context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v16 )
    SRCacheContext_Close(v16, v15);
  v17 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v17 )
    SRCache_Free();
  v18 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v18 )
    SRCacheContext_Close(v18, v15);
  return 0;
}

```

## disassembly

```asm
0x180171578  push    rbp
0x18017157a  push    rbx
0x18017157b  push    rsi
0x18017157c  push    rdi
0x18017157d  push    r14
0x18017157f  lea     rbp, [rsp-180h]
0x180171587  sub     rsp, 280h
0x18017158e  mov     rax, cs:__security_cookie
0x180171595  xor     rax, rsp
0x180171598  mov     [rbp+1A0h+var_30], rax
0x18017159f  xor     r14d, r14d
0x1801715a2  mov     [rsp+2A0h+var_270.replace], 1
0x1801715a7  mov     [cacheId], r14
0x1801715aa  lea     rax, [rsp+2A0h+indexContext]
0x1801715af  mov     manager, [manager]
0x1801715b2  lea     r9, [rsp+2A0h+var_270.pRaw]
0x1801715b7  mov     rdi, cacheId
0x1801715ba  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x1801715bf  mov     rsi, packageFamilyName
0x1801715c2  mov     [rsp+2A0h+var_270.wrapper], rax
0x1801715c7  xor     r8d, r8d
0x1801715ca  mov     [rsp+2A0h+var_270.pRaw], r14
0x1801715cf  lea     packageFamilyName, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x1801715d6  call    cs:__imp_SRCacheContext_Open
0x1801715dc  lea     manager, [rsp+2A0h+var_270]; this
0x1801715e1  mov     ebx, eax
0x1801715e3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801715e8  test    ebx, ebx
0x1801715ea  jns     short loc_18017163E
0x1801715ec  mov     manager, [rbp+1A8h]; callerReturnAddress
0x1801715f3  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801715fa  mov     r9d, ebx; hr
0x1801715fd  mov     edx, 18Ch; lineNumber
0x180171602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171607  mov     edx, 0C1h; lineNumber
0x18017160c  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180171613  lea     cacheId, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18017161a  mov     r9d, ebx; hr
0x18017161d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171622  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180171627  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x18017162c  test    manager, manager
0x18017162f  jz      short loc_180171637
0x180171631  call    cs:__imp_SRCacheContext_Close
0x180171637  mov     eax, ebx
0x180171639  jmp     loc_1801717F5
0x18017163e  cmp     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x180171643  setnz   al
0x180171646  test    al, al
0x180171648  jnz     short loc_180171656
0x18017164a  mov     ebx, 80670012h
0x18017164f  mov     edx, 0C2h
0x180171654  jmp     short loc_18017160C
0x180171656  xor     edx, edx; Val
0x180171658  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x18017165d  mov     r8d, 200h; Size
0x180171663  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x180171668  call    memset_0
0x18017166d  lea     rax, [rsp+2A0h+key.m_smallKey]
0x180171672  mov     [rbp+1A0h+key.m_length], r14
0x180171679  mov     packageFamilyName, rsi; value
0x18017167c  mov     [rbp+1A0h+key.m_key], rax
0x180171683  lea     manager, [rsp+2A0h+key]; this
0x180171688  mov     [rbp+1A0h+key.m_capacity], 100h
0x180171693  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180171698  mov     ebx, eax
0x18017169a  test    eax, eax
0x18017169c  jns     short loc_1801716D7
0x18017169e  mov     manager, [rbp+1A8h]; callerReturnAddress
0x1801716a5  lea     cacheId, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801716ac  mov     r9d, eax; hr
0x1801716af  mov     edx, 0C5h; lineNumber
0x1801716b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801716b9  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x1801716be  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x1801716c3  test    manager, manager
0x1801716c6  jz      loc_180171622
0x1801716cc  call    cs:__imp_SRCache_Free
0x1801716d2  jmp     loc_180171622
0x1801716d7  mov     packageFamilyName, [rbp+1A0h+key.m_key]
0x1801716de  lea     rax, [rsp+2A0h+context]
0x1801716e3  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801716e8  lea     r9, [rsp+2A0h+var_270.pRaw]
0x1801716ed  xor     r8d, r8d
0x1801716f0  mov     [rsp+2A0h+var_270.wrapper], rax
0x1801716f5  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x1801716fa  mov     [rsp+2A0h+var_270.pRaw], r14
0x1801716ff  mov     [rsp+2A0h+var_270.replace], 1
0x180171704  call    cs:__imp_SRCacheContext_OpenSubContext
0x18017170a  lea     manager, [rsp+2A0h+var_270]; this
0x18017170f  mov     ebx, eax
0x180171711  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180171716  test    ebx, ebx
0x180171718  jns     short loc_18017176E
0x18017171a  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180171721  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180171728  mov     r9d, ebx; hr
0x18017172b  mov     edx, 1B0h; lineNumber
0x180171730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171735  mov     edx, 0C9h; lineNumber
0x18017173a  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180171741  lea     cacheId, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180171748  mov     r9d, ebx; hr
0x18017174b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171750  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x180171755  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x18017175a  test    manager, manager
0x18017175d  jz      loc_1801716B9
0x180171763  call    cs:__imp_SRCacheContext_Close
0x180171769  jmp     loc_1801716B9
0x18017176e  cmp     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x180171773  setnz   al
0x180171776  test    al, al
0x180171778  jz      short loc_180171796
0x18017177a  mov     cacheId, rdi; cacheId
0x18017177d  lea     manager, [rsp+2A0h+context]; this
0x180171782  xor     edx, edx; index
0x180171784  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180171789  mov     ebx, eax
0x18017178b  test    eax, eax
0x18017178d  jns     short loc_180171796
0x18017178f  mov     edx, 0CCh
0x180171794  jmp     short loc_18017173A
0x180171796  lea     packageFamilyName, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18017179d  lea     manager, [rsp+2A0h+indexContext]; this
0x1801717a2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801717a7  mov     ebx, eax
0x1801717a9  test    eax, eax
0x1801717ab  jns     short loc_1801717B4
0x1801717ad  mov     edx, 0CFh
0x1801717b2  jmp     short loc_18017173A
0x1801717b4  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x1801717b9  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x1801717be  test    manager, manager
0x1801717c1  jz      short loc_1801717C9
0x1801717c3  call    cs:__imp_SRCacheContext_Close
0x1801717c9  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x1801717ce  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x1801717d3  test    manager, manager
0x1801717d6  jz      short loc_1801717DE
0x1801717d8  call    cs:__imp_SRCache_Free
0x1801717de  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801717e3  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x1801717e8  test    manager, manager
0x1801717eb  jz      short loc_1801717F3
0x1801717ed  call    cs:__imp_SRCacheContext_Close
0x1801717f3  xor     eax, eax
0x1801717f5  mov     manager, [rbp+1A0h+var_30]
0x1801717fc  xor     manager, rsp; StackCookie
0x1801717ff  call    __security_check_cookie
0x180171804  add     rsp, 280h
0x18017180b  pop     r14
0x18017180d  pop     rdi
0x18017180e  pop     rsi
0x18017180f  pop     rbx
0x180171810  pop     rbp
0x180171811  retn
```
