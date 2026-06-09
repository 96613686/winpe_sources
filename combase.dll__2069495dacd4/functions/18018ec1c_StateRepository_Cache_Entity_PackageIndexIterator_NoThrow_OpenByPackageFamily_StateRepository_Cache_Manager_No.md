# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18018ec1c`
- end: `0x18018ef58`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `828`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this, StateRepository::Cache::Manager_NoThrow *manager, __int64 packageFamily)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180171818`

## callees

- `0x18003a8bc`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x18018ec1c`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018edc9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018edc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018eccc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018eccc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018ee70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018ee70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018ee3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018eefb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018ef15`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018ee3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018eefb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018ef15`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ec8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ed29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ed75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ef2a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ec8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ed29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ed75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018ef2a`

## string_xrefs

- `0x18018edda`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18018ec60`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18018ed06`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18018ed49`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18018ee18`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18018eed4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18018eceb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018ee8f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 packageFamily)
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

  if ( !packageFamily )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x792u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
  v10 = SRCacheContext_Open(v9, L"Package\\Index\\PackageFamily", 0, &v24.pRaw);
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
      0x798u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
      0x799u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
  if ( (unsigned int)_o__ui64tow_s(packageFamily, &v24, 17, 16) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_18:
    v15 = 1948;
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
    v15 = 1951;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v15,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v10);
    v16 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( this->m_context.m_cacheContext.__ptr_.__value_ )
    this->m_manager = manager;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(&indexContext, L"Package\\Index\\PackageFamily");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x7A5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
0x18018ec1c  mov     [rsp-8+arg_18], rbx
0x18018ec21  push    rbp
0x18018ec22  push    rsi
0x18018ec23  push    rdi
0x18018ec24  push    r14
0x18018ec26  push    r15
0x18018ec28  lea     rbp, [rsp-180h]
0x18018ec30  sub     rsp, 280h
0x18018ec37  mov     rax, cs:__security_cookie
0x18018ec3e  xor     rax, rsp
0x18018ec41  mov     [rbp+1A0h+var_28], rax
0x18018ec48  xor     r15d, r15d
0x18018ec4b  mov     r14, packageFamily
0x18018ec4e  mov     rsi, manager
0x18018ec51  mov     rbx, this
0x18018ec54  test    packageFamily, packageFamily
0x18018ec57  jnz     short loc_18018EC80
0x18018ec59  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018ec60  lea     packageFamily, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ec67  mov     ebx, 80070057h
0x18018ec6c  mov     edx, 792h; lineNumber
0x18018ec71  mov     r9d, ebx; hr
0x18018ec74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018ec79  mov     eax, ebx
0x18018ec7b  jmp     loc_18018EF32
0x18018ec80  mov     this, [this]
0x18018ec83  mov     [rbx], r15
0x18018ec86  test    this, this
0x18018ec89  jz      short loc_18018EC91
0x18018ec8b  call    cs:__imp_SRCacheContext_Close
0x18018ec91  mov     [rbx+8], r15d
0x18018ec95  lea     rax, [rsp+2A0h+indexContext]
0x18018ec9a  mov     [rbx+10h], r15
0x18018ec9e  lea     r9, [rbp+1A0h+var_50.pRaw]
0x18018eca5  mov     this, [rsi]
0x18018eca8  lea     manager, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18018ecaf  xor     r8d, r8d
0x18018ecb2  mov     [rbp+1A0h+var_50.wrapper], rax
0x18018ecb9  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018ecbe  mov     [rbp+1A0h+var_50.pRaw], r15
0x18018ecc5  mov     [rbp+1A0h+var_50.replace], 1
0x18018eccc  call    cs:__imp_SRCacheContext_Open
0x18018ecd2  lea     this, [rbp+1A0h+var_50]; this
0x18018ecd9  mov     edi, eax
0x18018ecdb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018ece0  test    edi, edi
0x18018ece2  jns     short loc_18018ED36
0x18018ece4  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018eceb  lea     packageFamily, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ecf2  mov     r9d, edi; hr
0x18018ecf5  mov     edx, 18Ch; lineNumber
0x18018ecfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018ecff  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018ed06  lea     packageFamily, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ed0d  mov     r9d, edi; hr
0x18018ed10  mov     edx, 798h; lineNumber
0x18018ed15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018ed1a  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018ed1f  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018ed24  test    this, this
0x18018ed27  jz      short loc_18018ED2F
0x18018ed29  call    cs:__imp_SRCacheContext_Close
0x18018ed2f  mov     eax, edi
0x18018ed31  jmp     loc_18018EF32
0x18018ed36  cmp     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018ed3b  setnz   al
0x18018ed3e  test    al, al
0x18018ed40  jnz     short loc_18018ED80
0x18018ed42  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018ed49  lea     packageFamily, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ed50  mov     ebx, 80670012h
0x18018ed55  mov     edx, 799h; lineNumber
0x18018ed5a  mov     r9d, ebx; hr
0x18018ed5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018ed62  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018ed67  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018ed6c  test    this, this
0x18018ed6f  jz      loc_18018EC79
0x18018ed75  call    cs:__imp_SRCacheContext_Close
0x18018ed7b  jmp     loc_18018EC79
0x18018ed80  xor     edx, edx; Val
0x18018ed82  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018ed87  mov     r8d, 200h; Size
0x18018ed8d  lea     this, [rsp+2A0h+key.m_smallKey]; void *
0x18018ed92  call    memset_0
0x18018ed97  mov     r9d, 10h
0x18018ed9d  mov     [rbp+1A0h+key.m_length], r15
0x18018eda4  lea     rax, [rsp+2A0h+key.m_smallKey]
0x18018eda9  mov     [rbp+1A0h+key.m_capacity], 100h
0x18018edb4  lea     manager, [rbp+1A0h+var_50]
0x18018edbb  mov     [rbp+1A0h+key.m_key], rax
0x18018edc2  mov     this, r14
0x18018edc5  lea     r8d, [r9+1]
0x18018edc9  call    cs:__imp__o__ui64tow_s
0x18018edcf  test    eax, eax
0x18018edd1  jz      short loc_18018EDF5
0x18018edd3  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018edda  lea     packageFamily, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ede1  mov     edi, 8000FFFFh
0x18018ede6  mov     edx, 166h; lineNumber
0x18018edeb  mov     r9d, edi; hr
0x18018edee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018edf3  jmp     short loc_18018EE0C
0x18018edf5  lea     manager, [rbp+1A0h+var_50]; value
0x18018edfc  lea     this, [rsp+2A0h+key]; this
0x18018ee01  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18018ee06  mov     edi, eax
0x18018ee08  test    eax, eax
0x18018ee0a  jns     short loc_18018EE45
0x18018ee0c  mov     edx, 79Ch; lineNumber
0x18018ee11  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018ee18  lea     packageFamily, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ee1f  mov     r9d, edi; hr
0x18018ee22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018ee27  mov     this, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018ee2c  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018ee31  test    this, this
0x18018ee34  jz      loc_18018ED1A
0x18018ee3a  call    cs:__imp_SRCache_Free
0x18018ee40  jmp     loc_18018ED1A
0x18018ee45  mov     manager, [rbp+1A0h+key.m_key]
0x18018ee4c  lea     r9, [rbp+1A0h+var_50.pRaw]
0x18018ee53  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018ee58  xor     r8d, r8d
0x18018ee5b  mov     [rbp+1A0h+var_50.wrapper], rbx
0x18018ee62  mov     [rbp+1A0h+var_50.pRaw], r15
0x18018ee69  mov     [rbp+1A0h+var_50.replace], 1
0x18018ee70  call    cs:__imp_SRCacheContext_OpenSubContext
0x18018ee76  lea     this, [rbp+1A0h+var_50]; this
0x18018ee7d  mov     edi, eax
0x18018ee7f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018ee84  test    edi, edi
0x18018ee86  jns     short loc_18018EEAD
0x18018ee88  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018ee8f  lea     packageFamily, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018ee96  mov     r9d, edi; hr
0x18018ee99  mov     edx, 1B0h; lineNumber
0x18018ee9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018eea3  mov     edx, 79Fh
0x18018eea8  jmp     loc_18018EE11
0x18018eead  cmp     [rbx], r15
0x18018eeb0  jz      short loc_18018EEB6
0x18018eeb2  mov     [rbx+10h], rsi
0x18018eeb6  lea     manager, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18018eebd  lea     this, [rsp+2A0h+indexContext]; this
0x18018eec2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18018eec7  mov     ebx, eax
0x18018eec9  test    eax, eax
0x18018eecb  jns     short loc_18018EF06
0x18018eecd  mov     this, [rbp+1A8h]; callerReturnAddress
0x18018eed4  lea     packageFamily, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018eedb  mov     r9d, eax; hr
0x18018eede  mov     edx, 7A5h; lineNumber
0x18018eee3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018eee8  mov     this, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018eeed  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018eef2  test    this, this
0x18018eef5  jz      loc_18018ED62
0x18018eefb  call    cs:__imp_SRCache_Free
0x18018ef01  jmp     loc_18018ED62
0x18018ef06  mov     this, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018ef0b  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018ef10  test    this, this
0x18018ef13  jz      short loc_18018EF1B
0x18018ef15  call    cs:__imp_SRCache_Free
0x18018ef1b  mov     this, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018ef20  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018ef25  test    this, this
0x18018ef28  jz      short loc_18018EF30
0x18018ef2a  call    cs:__imp_SRCacheContext_Close
0x18018ef30  xor     eax, eax
0x18018ef32  mov     this, [rbp+1A0h+var_28]
0x18018ef39  xor     this, rsp; StackCookie
0x18018ef3c  call    __security_check_cookie
0x18018ef41  mov     rbx, [rsp+2A0h+arg_18]
0x18018ef49  add     rsp, 280h
0x18018ef50  pop     r15
0x18018ef52  pop     r14
0x18018ef54  pop     rdi
0x18018ef55  pop     rsi
0x18018ef56  pop     rbp
0x18018ef57  retn
```
