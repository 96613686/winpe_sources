# StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x180195228`
- end: `0x1801955d8`
- name: `?OpenByPackageAndCategory@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `944`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *this, StateRepository::Cache::Manager_NoThrow *manager, __int64 package, const wchar_t *category)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1801dc400`

## callees

- `0x18003a8bc`
- `0x180052310`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x180195228`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801953d7`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801953d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801952da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801952da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801954f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801954f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180195448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180195580`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18019559a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180195448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180195580`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18019559a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180195299`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180195337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180195383`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801955af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180195299`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180195337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180195383`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801955af`

## string_xrefs

- `0x1801953e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180195475`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1801952f9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180195514`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18019526e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180195314`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180195357`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180195426`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180195559`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1801952b6`: `PackageExtension\Index\PackageAndCategory`
- `0x18019553b`: `PackageExtension\Index\PackageAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(
        StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *this,
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 package,
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

  if ( !package )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2D5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
  v12 = SRCacheContext_Open(v11, L"PackageExtension\\Index\\PackageAndCategory", 0, &v28.pRaw);
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
      0x2DBu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
      0x2DCu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
  if ( (unsigned int)_o__ui64tow_s(package, &v28, 17, 16) )
  {
    v12 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_18:
    v18 = 735;
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
    v18 = 736;
    goto LABEL_19;
  }
  *(_DWORD *)&key.m_key[key.m_length++] = 94;
  v12 = StateRepository::Cache::Key_NoThrow::Append(&key, category);
  if ( v12 < 0 )
  {
    v18 = 737;
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
    v18 = 740;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v18,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
          L"PackageExtension\\Index\\PackageAndCategory");
  v8 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2EAu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
0x180195228  push    rbp
0x18019522a  push    rbx
0x18019522b  push    rsi
0x18019522c  push    rdi
0x18019522d  push    r12
0x18019522f  push    r14
0x180195231  push    r15
0x180195233  lea     rbp, [rsp-180h]
0x18019523b  sub     rsp, 280h
0x180195242  mov     rax, cs:__security_cookie
0x180195249  xor     rax, rsp
0x18019524c  mov     [rbp+1B0h+var_38], rax
0x180195253  xor     r12d, r12d
0x180195256  mov     r15, category
0x180195259  mov     r14, package
0x18019525c  mov     rsi, manager
0x18019525f  mov     rbx, this
0x180195262  test    package, package
0x180195265  jnz     short loc_18019528E
0x180195267  mov     this, [rbp+1B8h]; callerReturnAddress
0x18019526e  lea     package, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180195275  mov     ebx, 80070057h
0x18019527a  mov     edx, 2D5h; lineNumber
0x18019527f  mov     r9d, ebx; hr
0x180195282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195287  mov     eax, ebx
0x180195289  jmp     loc_1801955B7
0x18019528e  mov     this, [this]
0x180195291  mov     [rbx], r12
0x180195294  test    this, this
0x180195297  jz      short loc_18019529F
0x180195299  call    cs:__imp_SRCacheContext_Close
0x18019529f  mov     [rbx+8], r12d
0x1801952a3  lea     rax, [rsp+2B0h+indexContext]
0x1801952a8  mov     [rbx+10h], r12
0x1801952ac  lea     category, [rbp+1B0h+var_60.pRaw]
0x1801952b3  mov     this, [rsi]
0x1801952b6  lea     manager, aPackageextensi_0; "PackageExtension\\Index\\PackageAndCate"...
0x1801952bd  xor     r8d, r8d
0x1801952c0  mov     [rbp+1B0h+var_60.wrapper], rax
0x1801952c7  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x1801952cc  mov     [rbp+1B0h+var_60.pRaw], r12
0x1801952d3  mov     [rbp+1B0h+var_60.replace], 1
0x1801952da  call    cs:__imp_SRCacheContext_Open
0x1801952e0  lea     this, [rbp+1B0h+var_60]; this
0x1801952e7  mov     edi, eax
0x1801952e9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801952ee  test    edi, edi
0x1801952f0  jns     short loc_180195344
0x1801952f2  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801952f9  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180195300  mov     r9d, edi; hr
0x180195303  mov     edx, 18Ch; lineNumber
0x180195308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019530d  mov     this, [rbp+1B8h]; callerReturnAddress
0x180195314  lea     package, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019531b  mov     r9d, edi; hr
0x18019531e  mov     edx, 2DBh; lineNumber
0x180195323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195328  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18019532d  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x180195332  test    this, this
0x180195335  jz      short loc_18019533D
0x180195337  call    cs:__imp_SRCacheContext_Close
0x18019533d  mov     eax, edi
0x18019533f  jmp     loc_1801955B7
0x180195344  cmp     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x180195349  setnz   al
0x18019534c  test    al, al
0x18019534e  jnz     short loc_18019538E
0x180195350  mov     this, [rbp+1B8h]; callerReturnAddress
0x180195357  lea     package, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019535e  mov     ebx, 80670012h
0x180195363  mov     edx, 2DCh; lineNumber
0x180195368  mov     r9d, ebx; hr
0x18019536b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195370  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180195375  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x18019537a  test    this, this
0x18019537d  jz      loc_180195287
0x180195383  call    cs:__imp_SRCacheContext_Close
0x180195389  jmp     loc_180195287
0x18019538e  xor     edx, edx; Val
0x180195390  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x180195395  mov     r8d, 200h; Size
0x18019539b  lea     this, [rsp+2B0h+key.m_smallKey]; void *
0x1801953a0  call    memset_0
0x1801953a5  mov     r9d, 10h
0x1801953ab  mov     [rbp+1B0h+key.m_length], r12
0x1801953b2  lea     rax, [rsp+2B0h+key.m_smallKey]
0x1801953b7  mov     [rbp+1B0h+key.m_capacity], 100h
0x1801953c2  lea     manager, [rbp+1B0h+var_60]
0x1801953c9  mov     [rbp+1B0h+key.m_key], rax
0x1801953d0  mov     this, r14
0x1801953d3  lea     r8d, [category+1]
0x1801953d7  call    cs:__imp__o__ui64tow_s
0x1801953dd  test    eax, eax
0x1801953df  jz      short loc_180195403
0x1801953e1  mov     this, [rbp+1B8h]; callerReturnAddress
0x1801953e8  lea     package, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801953ef  mov     edi, 8000FFFFh
0x1801953f4  mov     edx, 166h; lineNumber
0x1801953f9  mov     r9d, edi; hr
0x1801953fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195401  jmp     short loc_18019541A
0x180195403  lea     manager, [rbp+1B0h+var_60]; value
0x18019540a  lea     this, [rsp+2B0h+key]; this
0x18019540f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180195414  mov     edi, eax
0x180195416  test    eax, eax
0x180195418  jns     short loc_180195453
0x18019541a  mov     edx, 2DFh; lineNumber
0x18019541f  mov     this, [rbp+1B8h]; callerReturnAddress
0x180195426  lea     package, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019542d  mov     r9d, edi; hr
0x180195430  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195435  mov     this, [rsp+2B0h+key.m_largeKey.__ptr_.__value_]
0x18019543a  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x18019543f  test    this, this
0x180195442  jz      loc_180195328
0x180195448  call    cs:__imp_SRCache_Free
0x18019544e  jmp     loc_180195328
0x180195453  mov     manager, [rbp+1B0h+key.m_length]
0x18019545a  lea     this, [rsp+2B0h+key]; this
0x18019545f  add     manager, 2; capacity
0x180195463  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180195468  mov     edi, eax
0x18019546a  test    eax, eax
0x18019546c  jns     short loc_180195490
0x18019546e  mov     this, [rbp+1B8h]; callerReturnAddress
0x180195475  lea     package, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019547c  mov     r9d, eax; hr
0x18019547f  mov     edx, 16Dh; lineNumber
0x180195484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195489  mov     edx, 2E0h
0x18019548e  jmp     short loc_18019541F
0x180195490  mov     package, [rbp+1B0h+key.m_length]
0x180195497  mov     manager, r15; value
0x18019549a  mov     this, [rbp+1B0h+key.m_key]
0x1801954a1  mov     dword ptr [this+package*2], 5Eh ; '^'
0x1801954a9  lea     this, [rsp+2B0h+key]; this
0x1801954ae  inc     [rbp+1B0h+key.m_length]
0x1801954b5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1801954ba  mov     edi, eax
0x1801954bc  test    eax, eax
0x1801954be  jns     short loc_1801954CA
0x1801954c0  mov     edx, 2E1h
0x1801954c5  jmp     loc_18019541F
0x1801954ca  mov     manager, [rbp+1B0h+key.m_key]
0x1801954d1  lea     category, [rbp+1B0h+var_60.pRaw]
0x1801954d8  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801954dd  xor     r8d, r8d
0x1801954e0  mov     [rbp+1B0h+var_60.wrapper], rbx
0x1801954e7  mov     [rbp+1B0h+var_60.pRaw], r12
0x1801954ee  mov     [rbp+1B0h+var_60.replace], 1
0x1801954f5  call    cs:__imp_SRCacheContext_OpenSubContext
0x1801954fb  lea     this, [rbp+1B0h+var_60]; this
0x180195502  mov     edi, eax
0x180195504  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180195509  test    edi, edi
0x18019550b  jns     short loc_180195532
0x18019550d  mov     this, [rbp+1B8h]; callerReturnAddress
0x180195514  lea     package, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18019551b  mov     r9d, edi; hr
0x18019551e  mov     edx, 1B0h; lineNumber
0x180195523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195528  mov     edx, 2E4h
0x18019552d  jmp     loc_18019541F
0x180195532  cmp     [rbx], r12
0x180195535  jz      short loc_18019553B
0x180195537  mov     [rbx+10h], rsi
0x18019553b  lea     manager, aPackageextensi_0; "PackageExtension\\Index\\PackageAndCate"...
0x180195542  lea     this, [rsp+2B0h+indexContext]; this
0x180195547  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18019554c  mov     ebx, eax
0x18019554e  test    eax, eax
0x180195550  jns     short loc_18019558B
0x180195552  mov     this, [rbp+1B8h]; callerReturnAddress
0x180195559  lea     package, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180195560  mov     r9d, eax; hr
0x180195563  mov     edx, 2EAh; lineNumber
0x180195568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019556d  mov     this, [rsp+2B0h+key.m_largeKey.__ptr_.__value_]
0x180195572  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x180195577  test    this, this
0x18019557a  jz      loc_180195370
0x180195580  call    cs:__imp_SRCache_Free
0x180195586  jmp     loc_180195370
0x18019558b  mov     this, [rsp+2B0h+key.m_largeKey.__ptr_.__value_]
0x180195590  mov     [rsp+2B0h+key.m_largeKey.__ptr_.__value_], r12
0x180195595  test    this, this
0x180195598  jz      short loc_1801955A0
0x18019559a  call    cs:__imp_SRCache_Free
0x1801955a0  mov     this, [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_]
0x1801955a5  mov     [rsp+2B0h+indexContext.m_cacheContext.__ptr_.__value_], r12
0x1801955aa  test    this, this
0x1801955ad  jz      short loc_1801955B5
0x1801955af  call    cs:__imp_SRCacheContext_Close
0x1801955b5  xor     eax, eax
0x1801955b7  mov     this, [rbp+1B0h+var_38]
0x1801955be  xor     this, rsp; StackCookie
0x1801955c1  call    __security_check_cookie
0x1801955c6  add     rsp, 280h
0x1801955cd  pop     r15
0x1801955cf  pop     r14
0x1801955d1  pop     r12
0x1801955d3  pop     rdi
0x1801955d4  pop     rsi
0x1801955d5  pop     rbx
0x1801955d6  pop     rbp
0x1801955d7  retn
```
