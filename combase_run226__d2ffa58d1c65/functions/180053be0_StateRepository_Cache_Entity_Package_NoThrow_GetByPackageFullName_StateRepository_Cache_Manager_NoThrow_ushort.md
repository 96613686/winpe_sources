# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180053be0`
- end: `0x180053ef4`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `788`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, const wchar_t *packageFullName, __int64 *cacheId)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180052bb8`
- `0x180053b48`
- `0x180054a20`
- `0x18012eebc`
- `0x1802007bc`

## callees

- `0x18003a8bc`
- `0x180053be0`
- `0x180053efc`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180053c3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180053c3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180053cf9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180053cf9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180053e53`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180053e53`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053dd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053e14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053dd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180053e14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053c62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053d1d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053d9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053de6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053dff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053e29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053c62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053d1d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053d9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053de6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053dff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180053e29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180053d4a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180053d4a`

## string_xrefs

- `0x180053d81`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180053dae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180053ebb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180053d61`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180053e6a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180053e8f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180053ed6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        StateRepository::Cache::Manager_NoThrow *manager,
        const wchar_t *packageFullName,
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
  SRCacheContext *v20; // rcx
  wchar_t *v21; // rcx
  SRCacheContext *v22; // rcx
  HRESULT v23; // eax
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
  v6 = SRCacheContext_Open(value, L"Package\\Index\\PackageFullName", 0, &v28);
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
    v24 = 1128;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v24,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v24 = 1129;
    goto LABEL_33;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_key = key.m_smallKey;
  key.m_capacity = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append(&key, packageFullName);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x46Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v14 = 1136;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v14,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v6);
    v16 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v16 )
      SRCacheContext_Close(v16, v15);
    goto LABEL_17;
  }
  if ( context.m_cacheContext.__ptr_.__value_ )
  {
    v23 = SRCacheContext_EnumerateData(context.m_cacheContext.__ptr_.__value_, 0, cacheId);
    v6 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x2A6u,
        "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        v23);
      v14 = 1139;
      goto LABEL_14;
    }
  }
  v12 = SRCacheContext_AddToCache(indexContext.m_cacheContext.__ptr_.__value_, L"Package\\Index\\PackageFullName");
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1A6u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v12);
    v14 = 1142;
    goto LABEL_14;
  }
  v20 = context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v20 )
    SRCacheContext_Close(v20, v13);
  v21 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v21 )
    SRCache_Free();
  v22 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v13);
  return 0;
}

```

## disassembly

```asm
0x180053be0  push    rbp
0x180053be2  push    rbx
0x180053be3  push    rsi
0x180053be4  push    rdi
0x180053be5  push    r14
0x180053be7  lea     rbp, [rsp-180h]
0x180053bef  sub     rsp, 280h
0x180053bf6  mov     rax, cs:__security_cookie
0x180053bfd  xor     rax, rsp
0x180053c00  mov     [rbp+1A0h+var_30], rax
0x180053c07  xor     r14d, r14d
0x180053c0a  mov     [rsp+2A0h+var_260], 1
0x180053c0f  mov     [cacheId], r14
0x180053c12  lea     rax, [rsp+2A0h+indexContext]
0x180053c17  mov     manager, [manager]
0x180053c1a  lea     r9, [rsp+2A0h+var_268]
0x180053c1f  mov     rdi, cacheId
0x180053c22  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x180053c27  mov     rsi, packageFullName
0x180053c2a  mov     [rsp+2A0h+var_270], rax
0x180053c2f  xor     r8d, r8d
0x180053c32  mov     [rsp+2A0h+var_268], r14
0x180053c37  lea     packageFullName, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180053c3e  call    cs:__imp_SRCacheContext_Open
0x180053c44  mov     ebx, eax
0x180053c46  cmp     [rsp+2A0h+var_260], r14b
0x180053c4b  jz      short loc_180053C68
0x180053c4d  mov     cacheId, [rsp+2A0h+var_270]
0x180053c52  mov     packageFullName, [rsp+2A0h+var_268]
0x180053c57  mov     manager, [cacheId]
0x180053c5a  mov     [cacheId], packageFullName
0x180053c5d  test    manager, manager
0x180053c60  jz      short loc_180053C68
0x180053c62  call    cs:__imp_SRCacheContext_Close
0x180053c68  test    ebx, ebx
0x180053c6a  js      loc_180053E88
0x180053c70  cmp     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x180053c75  setnz   al
0x180053c78  test    al, al
0x180053c7a  jz      loc_180053EAA
0x180053c80  xor     edx, edx; Val
0x180053c82  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x180053c87  mov     r8d, 200h; Size
0x180053c8d  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x180053c92  call    memset_0
0x180053c97  lea     rax, [rsp+2A0h+key.m_smallKey]
0x180053c9c  mov     [rbp+1A0h+key.m_length], r14
0x180053ca3  mov     packageFullName, rsi; value
0x180053ca6  mov     [rbp+1A0h+key.m_key], rax
0x180053cad  lea     manager, [rsp+2A0h+key]; this
0x180053cb2  mov     [rbp+1A0h+key.m_capacity], 100h
0x180053cbd  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180053cc2  mov     ebx, eax
0x180053cc4  test    eax, eax
0x180053cc6  js      loc_180053DA7
0x180053ccc  mov     packageFullName, [rbp+1A0h+key.m_key]
0x180053cd3  lea     rax, [rsp+2A0h+context]
0x180053cd8  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053cdd  lea     r9, [rsp+2A0h+var_268]
0x180053ce2  xor     r8d, r8d
0x180053ce5  mov     [rsp+2A0h+var_270], rax
0x180053cea  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x180053cef  mov     [rsp+2A0h+var_268], r14
0x180053cf4  mov     [rsp+2A0h+var_260], 1
0x180053cf9  call    cs:__imp_SRCacheContext_OpenSubContext
0x180053cff  mov     ebx, eax
0x180053d01  cmp     [rsp+2A0h+var_260], r14b
0x180053d06  jz      short loc_180053D23
0x180053d08  mov     cacheId, [rsp+2A0h+var_270]
0x180053d0d  mov     packageFullName, [rsp+2A0h+var_268]
0x180053d12  mov     manager, [cacheId]
0x180053d15  mov     [cacheId], packageFullName
0x180053d18  test    manager, manager
0x180053d1b  jz      short loc_180053D23
0x180053d1d  call    cs:__imp_SRCacheContext_Close
0x180053d23  test    ebx, ebx
0x180053d25  js      loc_180053ECF
0x180053d2b  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x180053d30  test    manager, manager
0x180053d33  setnz   al
0x180053d36  test    al, al
0x180053d38  jnz     loc_180053E4E
0x180053d3e  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053d43  lea     packageFullName, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180053d4a  call    cs:__imp_SRCacheContext_AddToCache
0x180053d50  mov     ebx, eax
0x180053d52  test    eax, eax
0x180053d54  jns     loc_180053DF0
0x180053d5a  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053d61  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053d68  mov     r9d, eax; hr
0x180053d6b  mov     edx, 1A6h; lineNumber
0x180053d70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053d75  mov     edx, 476h; lineNumber
0x180053d7a  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053d81  lea     cacheId, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053d88  mov     r9d, ebx; hr
0x180053d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053d90  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x180053d95  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x180053d9a  test    manager, manager
0x180053d9d  jz      short loc_180053DC2
0x180053d9f  call    cs:__imp_SRCacheContext_Close
0x180053da5  jmp     short loc_180053DC2
0x180053da7  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053dae  lea     cacheId, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053db5  mov     r9d, ebx; hr
0x180053db8  mov     edx, 46Ch; lineNumber
0x180053dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053dc2  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180053dc7  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x180053dcc  test    manager, manager
0x180053dcf  jz      short loc_180053DD7
0x180053dd1  call    cs:__imp_SRCache_Free
0x180053dd7  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053ddc  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x180053de1  test    manager, manager
0x180053de4  jz      short loc_180053DEC
0x180053de6  call    cs:__imp_SRCacheContext_Close
0x180053dec  mov     eax, ebx
0x180053dee  jmp     short loc_180053E31
0x180053df0  mov     manager, [rsp+2A0h+context.m_cacheContext.__ptr_.__value_]
0x180053df5  mov     [rsp+2A0h+context.m_cacheContext.__ptr_.__value_], r14
0x180053dfa  test    manager, manager
0x180053dfd  jz      short loc_180053E05
0x180053dff  call    cs:__imp_SRCacheContext_Close
0x180053e05  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180053e0a  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r14
0x180053e0f  test    manager, manager
0x180053e12  jz      short loc_180053E1A
0x180053e14  call    cs:__imp_SRCache_Free
0x180053e1a  mov     manager, [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_]
0x180053e1f  mov     [rsp+2A0h+indexContext.m_cacheContext.__ptr_.__value_], r14
0x180053e24  test    manager, manager
0x180053e27  jz      short loc_180053E2F
0x180053e29  call    cs:__imp_SRCacheContext_Close
0x180053e2f  xor     eax, eax
0x180053e31  mov     manager, [rbp+1A0h+var_30]
0x180053e38  xor     manager, rsp; StackCookie
0x180053e3b  call    __security_check_cookie
0x180053e40  add     rsp, 280h
0x180053e47  pop     r14
0x180053e49  pop     rdi
0x180053e4a  pop     rsi
0x180053e4b  pop     rbx
0x180053e4c  pop     rbp
0x180053e4d  retn
0x180053e4e  mov     cacheId, rdi
0x180053e51  xor     edx, edx
0x180053e53  call    cs:__imp_SRCacheContext_EnumerateData
0x180053e59  mov     ebx, eax
0x180053e5b  test    eax, eax
0x180053e5d  jns     loc_180053D3E
0x180053e63  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053e6a  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053e71  mov     r9d, eax; hr
0x180053e74  mov     edx, 2A6h; lineNumber
0x180053e79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053e7e  mov     edx, 473h
0x180053e83  jmp     loc_180053D7A
0x180053e88  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053e8f  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053e96  mov     r9d, ebx; hr
0x180053e99  mov     edx, 18Ch; lineNumber
0x180053e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053ea3  mov     edx, 468h
0x180053ea8  jmp     short loc_180053EB4
0x180053eaa  mov     ebx, 80670012h
0x180053eaf  mov     edx, 469h; lineNumber
0x180053eb4  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053ebb  lea     cacheId, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053ec2  mov     r9d, ebx; hr
0x180053ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053eca  jmp     loc_180053DD7
0x180053ecf  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180053ed6  lea     cacheId, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180053edd  mov     r9d, ebx; hr
0x180053ee0  mov     edx, 1B0h; lineNumber
0x180053ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053eea  mov     edx, 470h
0x180053eef  jmp     loc_180053D7A
```
