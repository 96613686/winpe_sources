# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18018d890`
- end: `0x18018db25`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `661`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, __int64 cacheId, StateRepository::Cache::Context_NoThrow *context, bool *found)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1801dc44c`

## callees

- `0x18003a8bc`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x18018d890`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018d9c6`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018d9c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018d8fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018d8fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018da6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018da6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018da37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018dae2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018da37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018dae2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d958`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018daf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d958`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018daf7`

## string_xrefs

- `0x18018d9d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18018d91a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018da8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018d93a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18018da15`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 cacheId,
        StateRepository::Cache::Context_NoThrow *context,
        bool *found)
{
  SRCacheManager *value; // rcx
  HRESULT v8; // ebx
  unsigned int v9; // edx
  __int64 v10; // rdx
  SRCacheContext *v11; // rcx
  unsigned int v13; // edx
  wchar_t *v14; // rcx
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  SRCacheContext *v17; // rcx
  StateRepository::Cache::Context_NoThrow dataContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> > v20; // [rsp+250h] [rbp+150h] BYREF
  void *retaddr; // [rsp+2A8h] [rbp+1A8h]

  value = manager->m_cacheManager.__ptr_.__value_;
  v20.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&dataContext;
  v20.replace = 1;
  dataContext.m_cacheContext.__ptr_.__value_ = 0;
  v20.pRaw = 0;
  v8 = SRCacheContext_Open(value, L"Activation\\Data", 0, &v20.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v9 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v9,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      v8);
LABEL_4:
    v11 = dataContext.m_cacheContext.__ptr_.__value_;
    dataContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v11 )
      SRCacheContext_Close(v11, v10);
    return (unsigned int)v8;
  }
  if ( !dataContext.m_cacheContext.__ptr_.__value_ )
  {
    v8 = -2140733422;
    v9 = 392;
    goto LABEL_3;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(cacheId, &v20, 17, 16) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_12:
    v13 = 395;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append(&key, (const wchar_t *)&v20);
  if ( v8 < 0 )
    goto LABEL_12;
  v20.wrapper = &context->m_cacheContext;
  v20.pRaw = 0;
  v20.replace = 1;
  v8 = SRCacheContext_OpenSubContext(dataContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v20.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v13 = 396;
    goto LABEL_13;
  }
  *found = context->m_cacheContext.__ptr_.__value_ != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(&dataContext, L"Activation\\Data");
  if ( v8 < 0 )
  {
    v13 = 398;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v13,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      v8);
    v14 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_4;
  }
  v16 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v16 )
    SRCache_Free();
  v17 = dataContext.m_cacheContext.__ptr_.__value_;
  dataContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v17 )
    SRCacheContext_Close(v17, v15);
  return 0;
}

```

## disassembly

```asm
0x18018d890  mov     [rsp-8+arg_10], rbx
0x18018d895  push    rbp
0x18018d896  push    rsi
0x18018d897  push    rdi
0x18018d898  push    r14
0x18018d89a  push    r15
0x18018d89c  lea     rbp, [rsp-180h]
0x18018d8a4  sub     rsp, 280h
0x18018d8ab  mov     rax, cs:__security_cookie
0x18018d8b2  xor     rax, rsp
0x18018d8b5  mov     [rbp+1A0h+var_28], rax
0x18018d8bc  mov     manager, [manager]
0x18018d8bf  lea     rax, [rsp+2A0h+dataContext]
0x18018d8c4  mov     rsi, found
0x18018d8c7  mov     [rbp+1A0h+var_50.wrapper], rax
0x18018d8ce  mov     rdi, context
0x18018d8d1  mov     [rbp+1A0h+var_50.replace], 1
0x18018d8d8  mov     r14, cacheId
0x18018d8db  lea     found, [rbp+1A0h+var_50.pRaw]
0x18018d8e2  xor     r15d, r15d
0x18018d8e5  lea     cacheId, aActivationData; "Activation\\Data"
0x18018d8ec  xor     r8d, r8d
0x18018d8ef  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018d8f4  mov     [rbp+1A0h+var_50.pRaw], r15
0x18018d8fb  call    cs:__imp_SRCacheContext_Open
0x18018d901  lea     manager, [rbp+1A0h+var_50]; this
0x18018d908  mov     ebx, eax
0x18018d90a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018d90f  test    ebx, ebx
0x18018d911  jns     short loc_18018D965
0x18018d913  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018d91a  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d921  mov     r9d, ebx; hr
0x18018d924  mov     edx, 18Ch; lineNumber
0x18018d929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d92e  mov     edx, 187h; lineNumber
0x18018d933  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018d93a  lea     context, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d941  mov     r9d, ebx; hr
0x18018d944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d949  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x18018d94e  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018d953  test    manager, manager
0x18018d956  jz      short loc_18018D95E
0x18018d958  call    cs:__imp_SRCacheContext_Close
0x18018d95e  mov     eax, ebx
0x18018d960  jmp     loc_18018DAFF
0x18018d965  cmp     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018d96a  setnz   al
0x18018d96d  test    al, al
0x18018d96f  jnz     short loc_18018D97D
0x18018d971  mov     ebx, 80670012h
0x18018d976  mov     edx, 188h
0x18018d97b  jmp     short loc_18018D933
0x18018d97d  xor     edx, edx; Val
0x18018d97f  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018d984  mov     r8d, 200h; Size
0x18018d98a  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x18018d98f  call    memset_0
0x18018d994  mov     r9d, 10h
0x18018d99a  mov     [rbp+1A0h+key.m_length], r15
0x18018d9a1  lea     rax, [rsp+2A0h+key.m_smallKey]
0x18018d9a6  mov     [rbp+1A0h+key.m_capacity], 100h
0x18018d9b1  lea     cacheId, [rbp+1A0h+var_50]
0x18018d9b8  mov     [rbp+1A0h+key.m_key], rax
0x18018d9bf  mov     manager, r14
0x18018d9c2  lea     r8d, [found+1]
0x18018d9c6  call    cs:__imp__o__ui64tow_s
0x18018d9cc  test    eax, eax
0x18018d9ce  jz      short loc_18018D9F2
0x18018d9d0  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018d9d7  lea     context, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d9de  mov     ebx, 8000FFFFh
0x18018d9e3  mov     edx, 166h; lineNumber
0x18018d9e8  mov     r9d, ebx; hr
0x18018d9eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d9f0  jmp     short loc_18018DA09
0x18018d9f2  lea     cacheId, [rbp+1A0h+var_50]; value
0x18018d9f9  lea     manager, [rsp+2A0h+key]; this
0x18018d9fe  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18018da03  mov     ebx, eax
0x18018da05  test    eax, eax
0x18018da07  jns     short loc_18018DA42
0x18018da09  mov     edx, 18Bh; lineNumber
0x18018da0e  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018da15  lea     context, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018da1c  mov     r9d, ebx; hr
0x18018da1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018da24  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018da29  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018da2e  test    manager, manager
0x18018da31  jz      loc_18018D949
0x18018da37  call    cs:__imp_SRCache_Free
0x18018da3d  jmp     loc_18018D949
0x18018da42  mov     cacheId, [rbp+1A0h+key.m_key]
0x18018da49  lea     found, [rbp+1A0h+var_50.pRaw]
0x18018da50  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x18018da55  xor     r8d, r8d
0x18018da58  mov     [rbp+1A0h+var_50.wrapper], rdi
0x18018da5f  mov     [rbp+1A0h+var_50.pRaw], r15
0x18018da66  mov     [rbp+1A0h+var_50.replace], 1
0x18018da6d  call    cs:__imp_SRCacheContext_OpenSubContext
0x18018da73  lea     manager, [rbp+1A0h+var_50]; this
0x18018da7a  mov     ebx, eax
0x18018da7c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018da81  test    ebx, ebx
0x18018da83  jns     short loc_18018DAAA
0x18018da85  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018da8c  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018da93  mov     r9d, ebx; hr
0x18018da96  mov     edx, 1B0h; lineNumber
0x18018da9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018daa0  mov     edx, 18Ch
0x18018daa5  jmp     loc_18018DA0E
0x18018daaa  cmp     [rdi], r15
0x18018daad  lea     cacheId, aActivationData; "Activation\\Data"
0x18018dab4  lea     manager, [rsp+2A0h+dataContext]; this
0x18018dab9  setnz   al
0x18018dabc  mov     [rsi], al
0x18018dabe  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18018dac3  mov     ebx, eax
0x18018dac5  test    eax, eax
0x18018dac7  jns     short loc_18018DAD3
0x18018dac9  mov     edx, 18Eh
0x18018dace  jmp     loc_18018DA0E
0x18018dad3  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018dad8  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018dadd  test    manager, manager
0x18018dae0  jz      short loc_18018DAE8
0x18018dae2  call    cs:__imp_SRCache_Free
0x18018dae8  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x18018daed  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018daf2  test    manager, manager
0x18018daf5  jz      short loc_18018DAFD
0x18018daf7  call    cs:__imp_SRCacheContext_Close
0x18018dafd  xor     eax, eax
0x18018daff  mov     manager, [rbp+1A0h+var_28]
0x18018db06  xor     manager, rsp; StackCookie
0x18018db09  call    __security_check_cookie
0x18018db0e  mov     rbx, [rsp+2A0h+arg_10]
0x18018db16  add     rsp, 280h
0x18018db1d  pop     r15
0x18018db1f  pop     r14
0x18018db21  pop     rdi
0x18018db22  pop     rsi
0x18018db23  pop     rbp
0x18018db24  retn
```
