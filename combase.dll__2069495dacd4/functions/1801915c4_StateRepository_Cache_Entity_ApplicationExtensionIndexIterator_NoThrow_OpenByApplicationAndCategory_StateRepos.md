# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x1801915c4`
- end: `0x180191974`
- name: `?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `944`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this, StateRepository::Cache::Manager_NoThrow *manager, __int64 application, const wchar_t *category)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180200c78`

## callees

- `0x18003a8bc`
- `0x180052310`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x1801915c4`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180191773`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180191773`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180191676`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180191676`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180191891`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180191891`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801917e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18019191c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180191936`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801917e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18019191c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180191936`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180191635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801916d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18019171f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18019194b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180191635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801916d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18019171f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18019194b`

## string_xrefs

- `0x180191784`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180191811`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180191695`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801918b0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18019160a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801916b0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801916f3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801917c2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801918f5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180191652`: `ApplicationExtension\Index\ApplicationAndCategory`
- `0x1801918d7`: `ApplicationExtension\Index\ApplicationAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 application,
        const wchar_t *category)
{
  unsigned int v8; // ebx
  SRCacheContext *value; // rcx
  SRCacheManager *v11; // rcx
  HRESULT v12; // edi
  __int64 v13; // rdx
  SRCacheContext *v14; // rcx
  __int64 v15; // rdx
  SRCacheContext *v16; // rcx
  bool v17; // r8
  unsigned int v18; // edx
  wchar_t *v19; // rcx
  HRESULT v20; // eax
  HRESULT v21; // eax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  wchar_t *v24; // rcx
  SRCacheContext *v25; // rcx
  StateRepository::Cache::Context_NoThrow indexContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> > v28; // [rsp+250h] [rbp+150h] BYREF
  void *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !application )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2EDu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      -2147024809);
    return v8;
  }
  value = this->m_context.m_cacheContext.__ptr_.__value_;
  this->m_context.m_cacheContext.__ptr_.__value_ = 0;
  if ( value )
    SRCacheContext_Close(value, manager);
  this->m_index = 0;
  this->m_manager = 0;
  v11 = manager->m_cacheManager.__ptr_.__value_;
  v28.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&indexContext;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  v28.pRaw = 0;
  v28.replace = 1;
  v12 = SRCacheContext_Open(v11, L"ApplicationExtension\\Index\\ApplicationAndCategory", 0, &v28.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2F3u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      v12);
LABEL_8:
    v14 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return (unsigned int)v12;
  }
  if ( !indexContext.m_cacheContext.__ptr_.__value_ )
  {
    v8 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2F4u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      -2140733422);
LABEL_13:
    v16 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v16 )
      SRCacheContext_Close(v16, v15);
    return v8;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(application, &v28, 17, 16) )
  {
    v12 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_18:
    v18 = 759;
    goto LABEL_19;
  }
  v12 = StateRepository::Cache::Key_NoThrow::Append(&key, (const wchar_t *)&v28);
  if ( v12 < 0 )
    goto LABEL_18;
  v20 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(&key, key.m_length + 2, v17);
  v12 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x16Du,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      v20);
    v18 = 760;
    goto LABEL_19;
  }
  *(_DWORD *)&key.m_key[key.m_length++] = 94;
  v12 = StateRepository::Cache::Key_NoThrow::Append(&key, category);
  if ( v12 < 0 )
  {
    v18 = 761;
    goto LABEL_19;
  }
  v28.wrapper = &this->m_context.m_cacheContext;
  v28.pRaw = 0;
  v28.replace = 1;
  v12 = SRCacheContext_OpenSubContext(indexContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v28.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v12);
    v18 = 764;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v18,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      v12);
    v19 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( this->m_context.m_cacheContext.__ptr_.__value_ )
    this->m_manager = manager;
  v21 = StateRepository::Cache::Context_NoThrow::AddToCache(
          &indexContext,
          L"ApplicationExtension\\Index\\ApplicationAndCategory");
  v8 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x302u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      v21);
    v23 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v23 )
      SRCache_Free();
    goto LABEL_13;
  }
  v24 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v24 )
    SRCache_Free();
  v25 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v25 )
    SRCacheContext_Close(v25, v22);
  return 0;
}

```

## disassembly

```asm
0x1801915c4  push    rbp
0x1801915c6  push    rbx
0x1801915c7  push    rsi
0x1801915c8  push    rdi
0x1801915c9  push    r12
0x1801915cb  push    r14
0x1801915cd  push    r15
0x1801915cf  lea     rbp, [rsp-180h]
0x1801915d7  sub     rsp, 280h
0x1801915de  mov     rax, cs:__security_cookie
0x1801915e5  xor     rax, rsp
0x1801915e8  mov     [rbp+1B0h+var_38], rax
0x1801915ef  xor     r12d, r12d
0x1801915f2  mov     r15, category
0x1801915f5  mov     r14, application
0x1801915f8  mov     rsi, manager
0x1801915fb  mov     rbx, this
0x1801915fe  test    application, application
0x180191601  jnz     short loc_18019162A
0x180191603  mov     this, [rbp+1B8h]; callerReturnAddress
0x18019160a  lea     application, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180191611  mov     ebx, 80070057h
0x180191616  mov     edx, 2EDh; lineNumber
0x18019161b  mov     r9d, ebx; hr
0x18019161e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191623  mov     eax, ebx
0x180191625  jmp     loc_180191953
0x18019162a  mov     this, [this]
0x18019162d  mov     [rbx], r12
0x180191630  test    this, this
0x180191633  jz      short loc_18019163B
0x180191635  call    cs:__imp_SRCacheContext_Close
0x18019163b  mov     [rbx+8], r12d
0x18019163f  lea     rax, [rsp+2B0h+indexContext]
0x180191644  mov     [rbx+10h], r12
0x180191648  lea     category, [rbp+1B0h+var_60.pRaw]
0x18019164f  mov     this, [rsi]
0x180191652  lea     manager, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x180191659  xor     r8d, r8d
0x18019165c  mov     [rbp+1B0h+var_60.wrapper], rax
0x180191663  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x180191668  mov     [rbp+1B0h+var_60.pRaw], r12
0x18019166f  mov     [rbp+1B0h+var_60.replace], 1
0x180191676  call    cs:__imp_SRCacheContext_Open
0x18019167c  lea     this, [rbp+1B0h+var_60]; this
0x180191683  mov     edi, eax
0x180191685  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18019168a  test    edi, edi
0x18019168c  jns     short loc_1801916E0
0x18019168e  mov     this, [rbp+1B8h]; callerReturnAddress
0x180191695  lea     application, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019169c  mov     r9d, edi; hr
0x18019169f  mov     edx, 18Ch; lineNumber
0x1801916a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801916a9  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801916b0  lea     application, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801916b7  mov     r9d, edi; hr
0x1801916ba  mov     edx, 2F3h; lineNumber
0x1801916bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801916c4  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801916c9  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x1801916ce  test    this, this
0x1801916d1  jz      short loc_1801916D9
0x1801916d3  call    cs:__imp_SRCacheContext_Close
0x1801916d9  mov     eax, edi
0x1801916db  jmp     loc_180191953
0x1801916e0  cmp     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x1801916e5  setnz   al
0x1801916e8  test    al, al
0x1801916ea  jnz     short loc_18019172A
0x1801916ec  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801916f3  lea     application, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801916fa  mov     ebx, 80670012h
0x1801916ff  mov     edx, 2F4h; lineNumber
0x180191704  mov     r9d, ebx; hr
0x180191707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019170c  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180191711  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x180191716  test    this, this
0x180191719  jz      loc_180191623
0x18019171f  call    cs:__imp_SRCacheContext_Close
0x180191725  jmp     loc_180191623
0x18019172a  xor     edx, edx; Val
0x18019172c  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x180191731  mov     r8d, 200h; Size
0x180191737  lea     this, [rsp+2B0h+key.m_smallKey]; void *
0x18019173c  call    memset_0
0x180191741  mov     r9d, 10h
0x180191747  mov     [rbp+1B0h+key.m_length], r12
0x18019174e  lea     rax, [rsp+2B0h+key.m_smallKey]
0x180191753  mov     [rbp+1B0h+key.m_capacity], 100h
0x18019175e  lea     manager, [rbp+1B0h+var_60]
0x180191765  mov     [rbp+1B0h+key.m_key], rax
0x18019176c  mov     this, r14
0x18019176f  lea     r8d, [category+1]
0x180191773  call    cs:__imp__o__ui64tow_s
0x180191779  test    eax, eax
0x18019177b  jz      short loc_18019179F
0x18019177d  mov     this, [rbp+1B8h]; callerReturnAddress
0x180191784  lea     application, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019178b  mov     edi, 8000FFFFh
0x180191790  mov     edx, 166h; lineNumber
0x180191795  mov     r9d, edi; hr
0x180191798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019179d  jmp     short loc_1801917B6
0x18019179f  lea     manager, [rbp+1B0h+var_60]; value
0x1801917a6  lea     this, [rsp+2B0h+key]; this
0x1801917ab  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1801917b0  mov     edi, eax
0x1801917b2  test    eax, eax
0x1801917b4  jns     short loc_1801917EF
0x1801917b6  mov     edx, 2F7h; lineNumber
0x1801917bb  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801917c2  lea     application, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801917c9  mov     r9d, edi; hr
0x1801917cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801917d1  mov     this, [rsp+2B0h+key.m_largeKey.__ptr_.__value_]
0x1801917d6  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x1801917db  test    this, this
0x1801917de  jz      loc_1801916C4
0x1801917e4  call    cs:__imp_SRCache_Free
0x1801917ea  jmp     loc_1801916C4
0x1801917ef  mov     manager, [rbp+1B0h+key.m_length]
0x1801917f6  lea     this, [rsp+2B0h+key]; this
0x1801917fb  add     manager, 2; capacity
0x1801917ff  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180191804  mov     edi, eax
0x180191806  test    eax, eax
0x180191808  jns     short loc_18019182C
0x18019180a  mov     this, [rbp+1B8h]; callerReturnAddress
0x180191811  lea     application, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180191818  mov     r9d, eax; hr
0x18019181b  mov     edx, 16Dh; lineNumber
0x180191820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191825  mov     edx, 2F8h
0x18019182a  jmp     short loc_1801917BB
0x18019182c  mov     application, [rbp+1B0h+key.m_length]
0x180191833  mov     manager, r15; value
0x180191836  mov     this, [rbp+1B0h+key.m_key]
0x18019183d  mov     dword ptr [this+application*2], 5Eh ; '^'
0x180191845  lea     this, [rsp+2B0h+key]; this
0x18019184a  inc     [rbp+1B0h+key.m_length]
0x180191851  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180191856  mov     edi, eax
0x180191858  test    eax, eax
0x18019185a  jns     short loc_180191866
0x18019185c  mov     edx, 2F9h
0x180191861  jmp     loc_1801917BB
0x180191866  mov     manager, [rbp+1B0h+key.m_key]
0x18019186d  lea     category, [rbp+1B0h+var_60.pRaw]
0x180191874  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180191879  xor     r8d, r8d
0x18019187c  mov     [rbp+1B0h+var_60.wrapper], rbx
0x180191883  mov     [rbp+1B0h+var_60.pRaw], r12
0x18019188a  mov     [rbp+1B0h+var_60.replace], 1
0x180191891  call    cs:__imp_SRCacheContext_OpenSubContext
0x180191897  lea     this, [rbp+1B0h+var_60]; this
0x18019189e  mov     edi, eax
0x1801918a0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801918a5  test    edi, edi
0x1801918a7  jns     short loc_1801918CE
0x1801918a9  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801918b0  lea     application, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801918b7  mov     r9d, edi; hr
0x1801918ba  mov     edx, 1B0h; lineNumber
0x1801918bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801918c4  mov     edx, 2FCh
0x1801918c9  jmp     loc_1801917BB
0x1801918ce  cmp     [rbx], r12
0x1801918d1  jz      short loc_1801918D7
0x1801918d3  mov     [rbx+10h], rsi
0x1801918d7  lea     manager, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1801918de  lea     this, [rsp+2B0h+indexContext]; this
0x1801918e3  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801918e8  mov     ebx, eax
0x1801918ea  test    eax, eax
0x1801918ec  jns     short loc_180191927
0x1801918ee  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801918f5  lea     application, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801918fc  mov     r9d, eax; hr
0x1801918ff  mov     edx, 302h; lineNumber
0x180191904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191909  mov     this, [rsp+2B0h+key.m_largeKey.__ptr_.__value_]
0x18019190e  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x180191913  test    this, this
0x180191916  jz      loc_18019170C
0x18019191c  call    cs:__imp_SRCache_Free
0x180191922  jmp     loc_18019170C
0x180191927  mov     this, [rsp+2B0h+key.m_largeKey.__ptr_.__value_]
0x18019192c  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x180191931  test    this, this
0x180191934  jz      short loc_18019193C
0x180191936  call    cs:__imp_SRCache_Free
0x18019193c  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180191941  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x180191946  test    this, this
0x180191949  jz      short loc_180191951
0x18019194b  call    cs:__imp_SRCacheContext_Close
0x180191951  xor     eax, eax
0x180191953  mov     this, [rbp+1B0h+var_38]
0x18019195a  xor     this, rsp; StackCookie
0x18019195d  call    __security_check_cookie
0x180191962  add     rsp, 280h
0x180191969  pop     r15
0x18019196b  pop     r14
0x18019196d  pop     r12
0x18019196f  pop     rdi
0x180191970  pop     rsi
0x180191971  pop     rbx
0x180191972  pop     rbp
0x180191973  retn
```
