# StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18018e5c8`
- end: `0x18018e85d`
- name: `?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `661`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, __int64 cacheId, StateRepository::Cache::Context_NoThrow *context, bool *found)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1801dc5f4`

## callees

- `0x18003a8bc`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x18018e5c8`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018e6fe`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018e6fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018e633`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018e633`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018e7a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018e7a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018e76f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018e81a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018e76f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018e81a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018e690`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018e82f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018e690`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018e82f`

## string_xrefs

- `0x18018e70f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18018e652`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018e7c4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018e61d`: `PackageExtension\Data`
- `0x18018e7e5`: `PackageExtension\Data`
- `0x18018e672`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x18018e74d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(value, L"PackageExtension\\Data", 0, &v20.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v9 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v9,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
    v9 = 318;
    goto LABEL_3;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(cacheId, &v20, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_12:
    v13 = 321;
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
    v13 = 322;
    goto LABEL_13;
  }
  *found = context->m_cacheContext.__ptr_.__value_ != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(&dataContext, L"PackageExtension\\Data");
  if ( v8 < 0 )
  {
    v13 = 324;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v13,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
0x18018e5c8  mov     [rsp-8+arg_10], rbx
0x18018e5cd  push    rbp
0x18018e5ce  push    rsi
0x18018e5cf  push    rdi
0x18018e5d0  push    r14
0x18018e5d2  push    r15
0x18018e5d4  lea     rbp, [rsp-180h]
0x18018e5dc  sub     rsp, 280h
0x18018e5e3  mov     rax, cs:__security_cookie
0x18018e5ea  xor     rax, rsp
0x18018e5ed  mov     [rbp+1A0h+var_28], rax
0x18018e5f4  mov     manager, [manager]
0x18018e5f7  lea     rax, [rsp+2A0h+dataContext]
0x18018e5fc  mov     rsi, found
0x18018e5ff  mov     [rbp+1A0h+var_50.wrapper], rax
0x18018e606  mov     rdi, context
0x18018e609  mov     [rbp+1A0h+var_50.replace], 1
0x18018e610  mov     r14, cacheId
0x18018e613  lea     found, [rbp+1A0h+var_50.pRaw]
0x18018e61a  xor     r15d, r15d
0x18018e61d  lea     cacheId, aPackageextensi; "PackageExtension\\Data"
0x18018e624  xor     r8d, r8d
0x18018e627  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018e62c  mov     [rbp+1A0h+var_50.pRaw], r15
0x18018e633  call    cs:__imp_SRCacheContext_Open
0x18018e639  lea     manager, [rbp+1A0h+var_50]; this
0x18018e640  mov     ebx, eax
0x18018e642  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018e647  test    ebx, ebx
0x18018e649  jns     short loc_18018E69D
0x18018e64b  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018e652  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018e659  mov     r9d, ebx; hr
0x18018e65c  mov     edx, 18Ch; lineNumber
0x18018e661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018e666  mov     edx, 13Dh; lineNumber
0x18018e66b  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018e672  lea     context, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018e679  mov     r9d, ebx; hr
0x18018e67c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018e681  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x18018e686  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018e68b  test    manager, manager
0x18018e68e  jz      short loc_18018E696
0x18018e690  call    cs:__imp_SRCacheContext_Close
0x18018e696  mov     eax, ebx
0x18018e698  jmp     loc_18018E837
0x18018e69d  cmp     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018e6a2  setnz   al
0x18018e6a5  test    al, al
0x18018e6a7  jnz     short loc_18018E6B5
0x18018e6a9  mov     ebx, 80670012h
0x18018e6ae  mov     edx, 13Eh
0x18018e6b3  jmp     short loc_18018E66B
0x18018e6b5  xor     edx, edx; Val
0x18018e6b7  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018e6bc  mov     r8d, 200h; Size
0x18018e6c2  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x18018e6c7  call    memset_0
0x18018e6cc  mov     r9d, 10h
0x18018e6d2  mov     [rbp+1A0h+key.m_length], r15
0x18018e6d9  lea     rax, [rsp+2A0h+key.m_smallKey]
0x18018e6de  mov     [rbp+1A0h+key.m_capacity], 100h
0x18018e6e9  lea     cacheId, [rbp+1A0h+var_50]
0x18018e6f0  mov     [rbp+1A0h+key.m_key], rax
0x18018e6f7  mov     manager, r14
0x18018e6fa  lea     r8d, [found+1]
0x18018e6fe  call    cs:__imp__o__ui64tow_s
0x18018e704  test    eax, eax
0x18018e706  jz      short loc_18018E72A
0x18018e708  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018e70f  lea     context, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018e716  mov     ebx, 8000FFFFh
0x18018e71b  mov     edx, 166h; lineNumber
0x18018e720  mov     r9d, ebx; hr
0x18018e723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018e728  jmp     short loc_18018E741
0x18018e72a  lea     cacheId, [rbp+1A0h+var_50]; value
0x18018e731  lea     manager, [rsp+2A0h+key]; this
0x18018e736  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18018e73b  mov     ebx, eax
0x18018e73d  test    eax, eax
0x18018e73f  jns     short loc_18018E77A
0x18018e741  mov     edx, 141h; lineNumber
0x18018e746  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018e74d  lea     context, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018e754  mov     r9d, ebx; hr
0x18018e757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018e75c  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018e761  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018e766  test    manager, manager
0x18018e769  jz      loc_18018E681
0x18018e76f  call    cs:__imp_SRCache_Free
0x18018e775  jmp     loc_18018E681
0x18018e77a  mov     cacheId, [rbp+1A0h+key.m_key]
0x18018e781  lea     found, [rbp+1A0h+var_50.pRaw]
0x18018e788  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x18018e78d  xor     r8d, r8d
0x18018e790  mov     [rbp+1A0h+var_50.wrapper], rdi
0x18018e797  mov     [rbp+1A0h+var_50.pRaw], r15
0x18018e79e  mov     [rbp+1A0h+var_50.replace], 1
0x18018e7a5  call    cs:__imp_SRCacheContext_OpenSubContext
0x18018e7ab  lea     manager, [rbp+1A0h+var_50]; this
0x18018e7b2  mov     ebx, eax
0x18018e7b4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018e7b9  test    ebx, ebx
0x18018e7bb  jns     short loc_18018E7E2
0x18018e7bd  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18018e7c4  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018e7cb  mov     r9d, ebx; hr
0x18018e7ce  mov     edx, 1B0h; lineNumber
0x18018e7d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018e7d8  mov     edx, 142h
0x18018e7dd  jmp     loc_18018E746
0x18018e7e2  cmp     [rdi], r15
0x18018e7e5  lea     cacheId, aPackageextensi; "PackageExtension\\Data"
0x18018e7ec  lea     manager, [rsp+2A0h+dataContext]; this
0x18018e7f1  setnz   al
0x18018e7f4  mov     [rsi], al
0x18018e7f6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18018e7fb  mov     ebx, eax
0x18018e7fd  test    eax, eax
0x18018e7ff  jns     short loc_18018E80B
0x18018e801  mov     edx, 144h
0x18018e806  jmp     loc_18018E746
0x18018e80b  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x18018e810  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x18018e815  test    manager, manager
0x18018e818  jz      short loc_18018E820
0x18018e81a  call    cs:__imp_SRCache_Free
0x18018e820  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x18018e825  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18018e82a  test    manager, manager
0x18018e82d  jz      short loc_18018E835
0x18018e82f  call    cs:__imp_SRCacheContext_Close
0x18018e835  xor     eax, eax
0x18018e837  mov     manager, [rbp+1A0h+var_28]
0x18018e83e  xor     manager, rsp; StackCookie
0x18018e841  call    __security_check_cookie
0x18018e846  mov     rbx, [rsp+2A0h+arg_10]
0x18018e84e  add     rsp, 280h
0x18018e855  pop     r15
0x18018e857  pop     r14
0x18018e859  pop     rdi
0x18018e85a  pop     rsi
0x18018e85b  pop     rbp
0x18018e85c  retn
```
