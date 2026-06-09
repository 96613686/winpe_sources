# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800545bc`
- end: `0x1800548b3`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `759`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, __int64 cacheId, StateRepository::Cache::Context_NoThrow *context, bool *found)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180052bb8`
- `0x18005412c`
- `0x180054a20`

## callees

- `0x18003a8bc`
- `0x180053efc`
- `0x1800545bc`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800546b8`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800546b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180054627`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180054627`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18005470c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18005470c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800547aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800547d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800547aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800547d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054651`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054736`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800547bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800547ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054651`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054736`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800547bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800547ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180054759`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180054759`

## string_xrefs

- `0x180054873`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18005478c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180054836`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18005476c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180054851`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180054895`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        StateRepository::Cache::Manager_NoThrow *manager,
        __int64 cacheId,
        StateRepository::Cache::Context_NoThrow *context,
        bool *found)
{
  SRCacheManager *v4; // rcx
  HRESULT v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  SRCacheContext *v13; // rcx
  HRESULT v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // edx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  SRCacheContext *v19; // rcx
  wchar_t *v21; // rcx
  SRCacheContext *v22; // rcx
  unsigned int v23; // edx
  StateRepository::Cache::Context_NoThrow dataContext; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t value[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h] BYREF
  char v28; // [rsp+260h] [rbp+160h]
  void *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = manager->m_cacheManager.__ptr_.__value_;
  *(_QWORD *)value = &dataContext;
  v28 = 1;
  dataContext.m_cacheContext.__ptr_.__value_ = 0;
  v27 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v27);
  if ( v28 )
  {
    v9 = v27;
    v10 = **(_QWORD **)value;
    **(_QWORD **)value = v27;
    if ( v10 )
      SRCacheContext_Close(v10, v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v23 = 1192;
    goto LABEL_26;
  }
  if ( !dataContext.m_cacheContext.__ptr_.__value_ )
  {
    v8 = -2140733422;
    v23 = 1193;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v23,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v8);
LABEL_16:
    v19 = dataContext.m_cacheContext.__ptr_.__value_;
    dataContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v19 )
      SRCacheContext_Close(v19, v17);
    return (unsigned int)v8;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(cacheId, value, 17, 16) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
    goto LABEL_24;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append(&key, value);
  if ( v8 < 0 )
  {
LABEL_24:
    v16 = 1196;
    goto LABEL_14;
  }
  *(_QWORD *)value = context;
  v27 = 0;
  v28 = 1;
  v8 = SRCacheContext_OpenSubContext(dataContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v27);
  if ( v28 )
  {
    v11 = v27;
    v12 = **(_QWORD **)value;
    **(_QWORD **)value = v27;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v8);
    v16 = 1197;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v16,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v8);
    v18 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_16;
  }
  v13 = dataContext.m_cacheContext.__ptr_.__value_;
  *found = context->m_cacheContext.__ptr_.__value_ != 0;
  v14 = SRCacheContext_AddToCache(v13, L"Package\\Data");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1A6u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v14);
    v16 = 1199;
    goto LABEL_14;
  }
  v21 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v21 )
    SRCache_Free();
  v22 = dataContext.m_cacheContext.__ptr_.__value_;
  dataContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v15);
  return 0;
}

```

## disassembly

```asm
0x1800545bc  mov     [rsp-8+arg_10], rbx
0x1800545c1  push    rbp
0x1800545c2  push    rsi
0x1800545c3  push    rdi
0x1800545c4  push    r14
0x1800545c6  push    r15
0x1800545c8  lea     rbp, [rsp-180h]
0x1800545d0  sub     rsp, 280h
0x1800545d7  mov     rax, cs:__security_cookie
0x1800545de  xor     rax, rsp
0x1800545e1  mov     [rbp+1A0h+var_28], rax
0x1800545e8  mov     manager, [manager]
0x1800545eb  lea     rax, [rsp+2A0h+dataContext]
0x1800545f0  mov     r14, found
0x1800545f3  mov     qword ptr [rbp+1A0h+value], rax
0x1800545fa  mov     rdi, context
0x1800545fd  mov     [rbp+1A0h+var_40], 1
0x180054604  mov     rsi, cacheId
0x180054607  lea     found, [rbp+1A0h+var_48]
0x18005460e  xor     r15d, r15d
0x180054611  lea     cacheId, aPackageData; "Package\\Data"
0x180054618  xor     r8d, r8d
0x18005461b  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x180054620  mov     [rbp+1A0h+var_48], r15
0x180054627  call    cs:__imp_SRCacheContext_Open
0x18005462d  mov     ebx, eax
0x18005462f  cmp     [rbp+1A0h+var_40], r15b
0x180054636  jz      short loc_180054657
0x180054638  mov     context, qword ptr [rbp+1A0h+value]
0x18005463f  mov     cacheId, [rbp+1A0h+var_48]
0x180054646  mov     manager, [context]
0x180054649  mov     [context], cacheId
0x18005464c  test    manager, manager
0x18005464f  jz      short loc_180054657
0x180054651  call    cs:__imp_SRCacheContext_Close
0x180054657  test    ebx, ebx
0x180054659  js      loc_18005484A
0x18005465f  cmp     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x180054664  setnz   al
0x180054667  test    al, al
0x180054669  jz      loc_180054825
0x18005466f  xor     edx, edx; Val
0x180054671  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x180054676  mov     r8d, 200h; Size
0x18005467c  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x180054681  call    memset_0
0x180054686  mov     r9d, 10h
0x18005468c  mov     [rbp+1A0h+key.m_length], r15
0x180054693  lea     rax, [rsp+2A0h+key.m_smallKey]
0x180054698  mov     [rbp+1A0h+key.m_capacity], 100h
0x1800546a3  lea     cacheId, [rbp+1A0h+value]
0x1800546aa  mov     [rbp+1A0h+key.m_key], rax
0x1800546b1  mov     manager, rsi
0x1800546b4  lea     r8d, [found+1]
0x1800546b8  call    cs:__imp__o__ui64tow_s
0x1800546be  test    eax, eax
0x1800546c0  jnz     loc_18005486C
0x1800546c6  lea     cacheId, [rbp+1A0h+value]; value
0x1800546cd  lea     manager, [rsp+2A0h+key]; this
0x1800546d2  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800546d7  mov     ebx, eax
0x1800546d9  test    eax, eax
0x1800546db  js      loc_18005481B
0x1800546e1  mov     cacheId, [rbp+1A0h+key.m_key]
0x1800546e8  lea     found, [rbp+1A0h+var_48]
0x1800546ef  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x1800546f4  xor     r8d, r8d
0x1800546f7  mov     qword ptr [rbp+1A0h+value], rdi
0x1800546fe  mov     [rbp+1A0h+var_48], r15
0x180054705  mov     [rbp+1A0h+var_40], 1
0x18005470c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180054712  mov     ebx, eax
0x180054714  cmp     [rbp+1A0h+var_40], r15b
0x18005471b  jz      short loc_18005473C
0x18005471d  mov     context, qword ptr [rbp+1A0h+value]
0x180054724  mov     cacheId, [rbp+1A0h+var_48]
0x18005472b  mov     manager, [context]
0x18005472e  mov     [context], cacheId
0x180054731  test    manager, manager
0x180054734  jz      short loc_18005473C
0x180054736  call    cs:__imp_SRCacheContext_Close
0x18005473c  test    ebx, ebx
0x18005473e  js      loc_18005488E
0x180054744  cmp     [rdi], r15
0x180054747  lea     cacheId, aPackageData; "Package\\Data"
0x18005474e  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x180054753  setnz   al
0x180054756  mov     [r14], al
0x180054759  call    cs:__imp_SRCacheContext_AddToCache
0x18005475f  mov     ebx, eax
0x180054761  test    eax, eax
0x180054763  jns     short loc_1800547C9
0x180054765  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18005476c  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054773  mov     r9d, eax; hr
0x180054776  mov     edx, 1A6h; lineNumber
0x18005477b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054780  mov     edx, 4AFh; lineNumber
0x180054785  mov     manager, [rbp+1A8h]; callerReturnAddress
0x18005478c  lea     context, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054793  mov     r9d, ebx; hr
0x180054796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005479b  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x1800547a0  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x1800547a5  test    manager, manager
0x1800547a8  jz      short loc_1800547B0
0x1800547aa  call    cs:__imp_SRCache_Free
0x1800547b0  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x1800547b5  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x1800547ba  test    manager, manager
0x1800547bd  jz      short loc_1800547C5
0x1800547bf  call    cs:__imp_SRCacheContext_Close
0x1800547c5  mov     eax, ebx
0x1800547c7  jmp     short loc_1800547F5
0x1800547c9  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x1800547ce  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x1800547d3  test    manager, manager
0x1800547d6  jz      short loc_1800547DE
0x1800547d8  call    cs:__imp_SRCache_Free
0x1800547de  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x1800547e3  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x1800547e8  test    manager, manager
0x1800547eb  jz      short loc_1800547F3
0x1800547ed  call    cs:__imp_SRCacheContext_Close
0x1800547f3  xor     eax, eax
0x1800547f5  mov     manager, [rbp+1A0h+var_28]
0x1800547fc  xor     manager, rsp; StackCookie
0x1800547ff  call    __security_check_cookie
0x180054804  mov     rbx, [rsp+2A0h+arg_10]
0x18005480c  add     rsp, 280h
0x180054813  pop     r15
0x180054815  pop     r14
0x180054817  pop     rdi
0x180054818  pop     rsi
0x180054819  pop     rbp
0x18005481a  retn
0x18005481b  mov     edx, 4ACh
0x180054820  jmp     loc_180054785
0x180054825  mov     ebx, 80670012h
0x18005482a  mov     edx, 4A9h; lineNumber
0x18005482f  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180054836  lea     context, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005483d  mov     r9d, ebx; hr
0x180054840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054845  jmp     loc_1800547B0
0x18005484a  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180054851  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054858  mov     r9d, ebx; hr
0x18005485b  mov     edx, 18Ch; lineNumber
0x180054860  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054865  mov     edx, 4A8h
0x18005486a  jmp     short loc_18005482F
0x18005486c  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180054873  lea     context, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005487a  mov     ebx, 8000FFFFh
0x18005487f  mov     edx, 166h; lineNumber
0x180054884  mov     r9d, ebx; hr
0x180054887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005488c  jmp     short loc_18005481B
0x18005488e  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180054895  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005489c  mov     r9d, ebx; hr
0x18005489f  mov     edx, 1B0h; lineNumber
0x1800548a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800548a9  mov     edx, 4ADh
0x1800548ae  jmp     loc_180054785
```
