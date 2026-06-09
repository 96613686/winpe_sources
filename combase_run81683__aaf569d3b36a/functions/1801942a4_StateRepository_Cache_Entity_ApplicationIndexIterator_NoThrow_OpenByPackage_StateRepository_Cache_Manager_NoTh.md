# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1801942a4`
- end: `0x1801945e0`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `828`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this, StateRepository::Cache::Manager_NoThrow *manager, __int64 package)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1802007bc`

## callees

- `0x18003a8bc`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x1801942a4`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180194451`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180194451`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180194354`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180194354`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801944f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801944f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801944c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180194583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18019459d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801944c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180194583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18019459d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180194313`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801943b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801943fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801945b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180194313`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801943b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801943fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801945b2`

## string_xrefs

- `0x180194462`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180194373`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180194517`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801942e8`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-application.hpp`
- `0x18019438e`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-application.hpp`
- `0x1801943d1`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-application.hpp`
- `0x1801944a0`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-application.hpp`
- `0x18019455c`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 package)
{
  unsigned int v6; // ebx
  SRCacheContext *value; // rcx
  SRCacheManager *v9; // rcx
  HRESULT v10; // edi
  __int64 v11; // rdx
  SRCacheContext *v12; // rcx
  __int64 v13; // rdx
  SRCacheContext *v14; // rcx
  unsigned int v15; // edx
  wchar_t *v16; // rcx
  HRESULT v17; // eax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  wchar_t *v20; // rcx
  SRCacheContext *v21; // rcx
  StateRepository::Cache::Context_NoThrow indexContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> > v24; // [rsp+250h] [rbp+150h] BYREF
  void *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !package )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x3DFu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-application.hpp",
      -2147024809);
    return v6;
  }
  value = this->m_context.m_cacheContext.__ptr_.__value_;
  this->m_context.m_cacheContext.__ptr_.__value_ = 0;
  if ( value )
    SRCacheContext_Close(value, manager);
  this->m_index = 0;
  this->m_manager = 0;
  v9 = manager->m_cacheManager.__ptr_.__value_;
  v24.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&indexContext;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  v24.pRaw = 0;
  v24.replace = 1;
  v10 = SRCacheContext_Open(v9, L"Application\\Index\\Package", 0, &v24.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x3E5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-application.hpp",
      v10);
LABEL_8:
    v12 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v10;
  }
  if ( !indexContext.m_cacheContext.__ptr_.__value_ )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x3E6u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-application.hpp",
      -2140733422);
LABEL_13:
    v14 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return v6;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(package, &v24, 17) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_18:
    v15 = 1001;
    goto LABEL_19;
  }
  v10 = StateRepository::Cache::Key_NoThrow::Append(&key, (const wchar_t *)&v24);
  if ( v10 < 0 )
    goto LABEL_18;
  v24.wrapper = &this->m_context.m_cacheContext;
  v24.pRaw = 0;
  v24.replace = 1;
  v10 = SRCacheContext_OpenSubContext(indexContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v24.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v10);
    v15 = 1004;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v15,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-application.hpp",
      v10);
    v16 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( this->m_context.m_cacheContext.__ptr_.__value_ )
    this->m_manager = manager;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(&indexContext, L"Application\\Index\\Package");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x3F2u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-application.hpp",
      v17);
    v19 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_13;
  }
  v20 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v20 )
    SRCache_Free();
  v21 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18);
  return 0;
}

```

## disassembly

```asm
0x1801942a4  mov     [rsp-8+arg_18], rbx
0x1801942a9  push    rbp
0x1801942aa  push    rsi
0x1801942ab  push    rdi
0x1801942ac  push    r14
0x1801942ae  push    r15
0x1801942b0  lea     rbp, [rsp-180h]
0x1801942b8  sub     rsp, 280h
0x1801942bf  mov     rax, cs:__security_cookie
0x1801942c6  xor     rax, rsp
0x1801942c9  mov     [rbp+1A0h+var_28], rax
0x1801942d0  xor     r15d, r15d
0x1801942d3  mov     r14, package
0x1801942d6  mov     rsi, manager
0x1801942d9  mov     rbx, this
0x1801942dc  test    package, package
0x1801942df  jnz     short loc_180194308
0x1801942e1  mov     this, [rbp+1A8h]; callerReturnAddress
0x1801942e8  lea     package, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801942ef  mov     ebx, 80070057h
0x1801942f4  mov     edx, 3DFh; lineNumber
0x1801942f9  mov     r9d, ebx; hr
0x1801942fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180194301  mov     eax, ebx
0x180194303  jmp     loc_1801945BA
0x180194308  mov     this, [this]
0x18019430b  mov     [rbx], r15
0x18019430e  test    this, this
0x180194311  jz      short loc_180194319
0x180194313  call    cs:__imp_SRCacheContext_Close
0x180194319  mov     [rbx+8], r15d
0x18019431d  lea     rax, [rsp+2A0h+indexContext]
0x180194322  mov     [rbx+10h], r15
0x180194326  lea     r9, [rbp+1A0h+var_50.pRaw]
0x18019432d  mov     this, [rsi]
0x180194330  lea     manager, aApplicationInd; "Application\\Index\\Package"
0x180194337  xor     r8d, r8d
0x18019433a  mov     [rbp+1A0h+var_50.wrapper], rax
0x180194341  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x180194346  mov     [rbp+1A0h+var_50.pRaw], r15
0x18019434d  mov     [rbp+1A0h+var_50.replace], 1
0x180194354  call    cs:__imp_SRCacheContext_Open
0x18019435a  lea     this, [rbp+1A0h+var_50]; this
0x180194361  mov     edi, eax
0x180194363  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180194368  test    edi, edi
0x18019436a  jns     short loc_1801943BE
0x18019436c  mov     this, [rbp+1A8h]; callerReturnAddress
0x180194373  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019437a  mov     r9d, edi; hr
0x18019437d  mov     edx, 18Ch; lineNumber
0x180194382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180194387  mov     this, [rbp+1A8h]; callerReturnAddress
0x18019438e  lea     package, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180194395  mov     r9d, edi; hr
0x180194398  mov     edx, 3E5h; lineNumber
0x18019439d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801943a2  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801943a7  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x1801943ac  test    this, this
0x1801943af  jz      short loc_1801943B7
0x1801943b1  call    cs:__imp_SRCacheContext_Close
0x1801943b7  mov     eax, edi
0x1801943b9  jmp     loc_1801945BA
0x1801943be  cmp     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x1801943c3  setnz   al
0x1801943c6  test    al, al
0x1801943c8  jnz     short loc_180194408
0x1801943ca  mov     this, [rbp+1A8h]; callerReturnAddress
0x1801943d1  lea     package, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801943d8  mov     ebx, 80670012h
0x1801943dd  mov     edx, 3E6h; lineNumber
0x1801943e2  mov     r9d, ebx; hr
0x1801943e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801943ea  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801943ef  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x1801943f4  test    this, this
0x1801943f7  jz      loc_180194301
0x1801943fd  call    cs:__imp_SRCacheContext_Close
0x180194403  jmp     loc_180194301
0x180194408  xor     edx, edx; Val
0x18019440a  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18019440f  mov     r8d, 200h; Size
0x180194415  lea     this, [rsp+2A0h+key.m_smallKey]; void *
0x18019441a  call    memset_0
0x18019441f  mov     r9d, 10h
0x180194425  mov     [rbp+1A0h+key.m_length], r15
0x18019442c  lea     rax, [rsp+2A0h+key.m_smallKey]
0x180194431  mov     [rbp+1A0h+key.m_capacity], 100h
0x18019443c  lea     manager, [rbp+1A0h+var_50]
0x180194443  mov     [rbp+1A0h+key.m_key], rax
0x18019444a  mov     this, r14
0x18019444d  lea     r8d, [r9+1]
0x180194451  call    cs:__imp__o__ui64tow_s
0x180194457  test    eax, eax
0x180194459  jz      short loc_18019447D
0x18019445b  mov     this, [rbp+1A8h]; callerReturnAddress
0x180194462  lea     package, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180194469  mov     edi, 8000FFFFh
0x18019446e  mov     edx, 166h; lineNumber
0x180194473  mov     r9d, edi; hr
0x180194476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019447b  jmp     short loc_180194494
0x18019447d  lea     manager, [rbp+1A0h+var_50]; value
0x180194484  lea     this, [rsp+2A0h+key]; this
0x180194489  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18019448e  mov     edi, eax
0x180194490  test    eax, eax
0x180194492  jns     short loc_1801944CD
0x180194494  mov     edx, 3E9h; lineNumber
0x180194499  mov     this, [rbp+1A8h]; callerReturnAddress
0x1801944a0  lea     package, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801944a7  mov     r9d, edi; hr
0x1801944aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801944af  mov     this, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x1801944b4  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x1801944b9  test    this, this
0x1801944bc  jz      loc_1801943A2
0x1801944c2  call    cs:__imp_SRCache_Free
0x1801944c8  jmp     loc_1801943A2
0x1801944cd  mov     manager, [rbp+1A0h+key.m_key]
0x1801944d4  lea     r9, [rbp+1A0h+var_50.pRaw]
0x1801944db  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801944e0  xor     r8d, r8d
0x1801944e3  mov     [rbp+1A0h+var_50.wrapper], rbx
0x1801944ea  mov     [rbp+1A0h+var_50.pRaw], r15
0x1801944f1  mov     [rbp+1A0h+var_50.replace], 1
0x1801944f8  call    cs:__imp_SRCacheContext_OpenSubContext
0x1801944fe  lea     this, [rbp+1A0h+var_50]; this
0x180194505  mov     edi, eax
0x180194507  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18019450c  test    edi, edi
0x18019450e  jns     short loc_180194535
0x180194510  mov     this, [rbp+1A8h]; callerReturnAddress
0x180194517  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019451e  mov     r9d, edi; hr
0x180194521  mov     edx, 1B0h; lineNumber
0x180194526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019452b  mov     edx, 3ECh
0x180194530  jmp     loc_180194499
0x180194535  cmp     [rbx], r15
0x180194538  jz      short loc_18019453E
0x18019453a  mov     [rbx+10h], rsi
0x18019453e  lea     manager, aApplicationInd; "Application\\Index\\Package"
0x180194545  lea     this, [rsp+2A0h+indexContext]; this
0x18019454a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18019454f  mov     ebx, eax
0x180194551  test    eax, eax
0x180194553  jns     short loc_18019458E
0x180194555  mov     this, [rbp+1A8h]; callerReturnAddress
0x18019455c  lea     package, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180194563  mov     r9d, eax; hr
0x180194566  mov     edx, 3F2h; lineNumber
0x18019456b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180194570  mov     this, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180194575  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18019457a  test    this, this
0x18019457d  jz      loc_1801943EA
0x180194583  call    cs:__imp_SRCache_Free
0x180194589  jmp     loc_1801943EA
0x18019458e  mov     this, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180194593  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x180194598  test    this, this
0x18019459b  jz      short loc_1801945A3
0x18019459d  call    cs:__imp_SRCache_Free
0x1801945a3  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801945a8  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x1801945ad  test    this, this
0x1801945b0  jz      short loc_1801945B8
0x1801945b2  call    cs:__imp_SRCacheContext_Close
0x1801945b8  xor     eax, eax
0x1801945ba  mov     this, [rbp+1A0h+var_28]
0x1801945c1  xor     this, rsp; StackCookie
0x1801945c4  call    __security_check_cookie
0x1801945c9  mov     rbx, [rsp+2A0h+arg_18]
0x1801945d1  add     rsp, 280h
0x1801945d8  pop     r15
0x1801945da  pop     r14
0x1801945dc  pop     rdi
0x1801945dd  pop     rsi
0x1801945de  pop     rbp
0x1801945df  retn
```
