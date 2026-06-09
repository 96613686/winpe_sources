# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800528b8`
- end: `0x180052bb1`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `761`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, __int64 cacheId, StateRepository::Cache::Context_NoThrow *context, bool *found)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180052bb8`

## callees

- `0x18003a8bc`
- `0x1800528b8`
- `0x180053efc`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800529b4`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800529b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180052923`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180052923`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180052a08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180052a08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052aaa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052afc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052aaa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052afc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005294d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052a32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052abf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052b11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005294d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052a32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052abf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052b11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180052a55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180052a55`

## string_xrefs

- `0x180052b69`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180052a8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052b4e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052a6c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180052b22`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180052b93`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"User\\Data", 0, &v27);
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
    v23 = 267;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v23,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      v8);
LABEL_16:
    v19 = dataContext.m_cacheContext.__ptr_.__value_;
    dataContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v19 )
      SRCacheContext_Close(v19, v17);
    return (unsigned int)v8;
  }
  if ( !dataContext.m_cacheContext.__ptr_.__value_ )
  {
    v8 = -2140733422;
    v23 = 268;
    goto LABEL_26;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_capacity = 256;
  key.m_key = key.m_smallKey;
  if ( (unsigned int)_o__ui64tow_s(cacheId, value, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
    goto LABEL_28;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append(&key, value);
  if ( v8 < 0 )
  {
LABEL_28:
    v16 = 271;
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
    v16 = 272;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v16,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      v8);
    v18 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_16;
  }
  v13 = dataContext.m_cacheContext.__ptr_.__value_;
  *found = context->m_cacheContext.__ptr_.__value_ != 0;
  v14 = SRCacheContext_AddToCache(v13, L"User\\Data");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1A6u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v14);
    v16 = 274;
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
0x1800528b8  mov     [rsp-8+arg_10], rbx
0x1800528bd  push    rbp
0x1800528be  push    rsi
0x1800528bf  push    rdi
0x1800528c0  push    r14
0x1800528c2  push    r15
0x1800528c4  lea     rbp, [rsp-180h]
0x1800528cc  sub     rsp, 280h
0x1800528d3  mov     rax, cs:__security_cookie
0x1800528da  xor     rax, rsp
0x1800528dd  mov     [rbp+1A0h+var_28], rax
0x1800528e4  mov     manager, [manager]
0x1800528e7  lea     rax, [rsp+2A0h+dataContext]
0x1800528ec  mov     r14, found
0x1800528ef  mov     qword ptr [rbp+1A0h+value], rax
0x1800528f6  mov     rdi, context
0x1800528f9  mov     [rbp+1A0h+var_40], 1
0x180052900  mov     rsi, cacheId
0x180052903  lea     found, [rbp+1A0h+var_48]
0x18005290a  xor     r15d, r15d
0x18005290d  lea     cacheId, aUserData; "User\\Data"
0x180052914  xor     r8d, r8d
0x180052917  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x18005291c  mov     [rbp+1A0h+var_48], r15
0x180052923  call    cs:__imp_SRCacheContext_Open
0x180052929  mov     ebx, eax
0x18005292b  cmp     [rbp+1A0h+var_40], r15b
0x180052932  jz      short loc_180052953
0x180052934  mov     context, qword ptr [rbp+1A0h+value]
0x18005293b  mov     cacheId, [rbp+1A0h+var_48]
0x180052942  mov     manager, [context]
0x180052945  mov     [context], cacheId
0x180052948  test    manager, manager
0x18005294b  jz      short loc_180052953
0x18005294d  call    cs:__imp_SRCacheContext_Close
0x180052953  test    ebx, ebx
0x180052955  js      loc_180052B1B
0x18005295b  cmp     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x180052960  setnz   al
0x180052963  test    al, al
0x180052965  jz      loc_180052B3D
0x18005296b  xor     edx, edx; Val
0x18005296d  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x180052972  mov     r8d, 200h; Size
0x180052978  lea     manager, [rsp+2A0h+key.m_smallKey]; void *
0x18005297d  call    memset_0
0x180052982  mov     r9d, 10h
0x180052988  mov     [rbp+1A0h+key.m_length], r15
0x18005298f  lea     rax, [rsp+2A0h+key.m_smallKey]
0x180052994  mov     [rbp+1A0h+key.m_capacity], 100h
0x18005299f  lea     cacheId, [rbp+1A0h+value]
0x1800529a6  mov     [rbp+1A0h+key.m_key], rax
0x1800529ad  mov     manager, rsi
0x1800529b0  lea     r8d, [found+1]
0x1800529b4  call    cs:__imp__o__ui64tow_s
0x1800529ba  test    eax, eax
0x1800529bc  jnz     loc_180052B62
0x1800529c2  lea     cacheId, [rbp+1A0h+value]; value
0x1800529c9  lea     manager, [rsp+2A0h+key]; this
0x1800529ce  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800529d3  mov     ebx, eax
0x1800529d5  test    eax, eax
0x1800529d7  js      loc_180052B82
0x1800529dd  mov     cacheId, [rbp+1A0h+key.m_key]
0x1800529e4  lea     found, [rbp+1A0h+var_48]
0x1800529eb  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x1800529f0  xor     r8d, r8d
0x1800529f3  mov     qword ptr [rbp+1A0h+value], rdi
0x1800529fa  mov     [rbp+1A0h+var_48], r15
0x180052a01  mov     [rbp+1A0h+var_40], 1
0x180052a08  call    cs:__imp_SRCacheContext_OpenSubContext
0x180052a0e  mov     ebx, eax
0x180052a10  cmp     [rbp+1A0h+var_40], r15b
0x180052a17  jz      short loc_180052A38
0x180052a19  mov     context, qword ptr [rbp+1A0h+value]
0x180052a20  mov     cacheId, [rbp+1A0h+var_48]
0x180052a27  mov     manager, [context]
0x180052a2a  mov     [context], cacheId
0x180052a2d  test    manager, manager
0x180052a30  jz      short loc_180052A38
0x180052a32  call    cs:__imp_SRCacheContext_Close
0x180052a38  test    ebx, ebx
0x180052a3a  js      loc_180052B8C
0x180052a40  cmp     [rdi], r15
0x180052a43  lea     cacheId, aUserData; "User\\Data"
0x180052a4a  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x180052a4f  setnz   al
0x180052a52  mov     [r14], al
0x180052a55  call    cs:__imp_SRCacheContext_AddToCache
0x180052a5b  mov     ebx, eax
0x180052a5d  test    eax, eax
0x180052a5f  jns     loc_180052AED
0x180052a65  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052a6c  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052a73  mov     r9d, eax; hr
0x180052a76  mov     edx, 1A6h; lineNumber
0x180052a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a80  mov     edx, 112h; lineNumber
0x180052a85  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052a8c  lea     context, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052a93  mov     r9d, ebx; hr
0x180052a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a9b  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180052aa0  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x180052aa5  test    manager, manager
0x180052aa8  jz      short loc_180052AB0
0x180052aaa  call    cs:__imp_SRCache_Free
0x180052ab0  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x180052ab5  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x180052aba  test    manager, manager
0x180052abd  jz      short loc_180052AC5
0x180052abf  call    cs:__imp_SRCacheContext_Close
0x180052ac5  mov     eax, ebx
0x180052ac7  mov     manager, [rbp+1A0h+var_28]
0x180052ace  xor     manager, rsp; StackCookie
0x180052ad1  call    __security_check_cookie
0x180052ad6  mov     rbx, [rsp+2A0h+arg_10]
0x180052ade  add     rsp, 280h
0x180052ae5  pop     r15
0x180052ae7  pop     r14
0x180052ae9  pop     rdi
0x180052aea  pop     rsi
0x180052aeb  pop     rbp
0x180052aec  retn
0x180052aed  mov     manager, [rsp+2A0h+key.m_largeKey.__ptr_.__value_]
0x180052af2  mov     [rsp+2A0h+key.m_largeKey.__ptr_.__value_], r15
0x180052af7  test    manager, manager
0x180052afa  jz      short loc_180052B02
0x180052afc  call    cs:__imp_SRCache_Free
0x180052b02  mov     manager, [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_]
0x180052b07  mov     [rsp+2A0h+dataContext.m_cacheContext.__ptr_.__value_], r15
0x180052b0c  test    manager, manager
0x180052b0f  jz      short loc_180052B17
0x180052b11  call    cs:__imp_SRCacheContext_Close
0x180052b17  xor     eax, eax
0x180052b19  jmp     short loc_180052AC7
0x180052b1b  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052b22  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052b29  mov     r9d, ebx; hr
0x180052b2c  mov     edx, 18Ch; lineNumber
0x180052b31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b36  mov     edx, 10Bh
0x180052b3b  jmp     short loc_180052B47
0x180052b3d  mov     ebx, 80670012h
0x180052b42  mov     edx, 10Ch; lineNumber
0x180052b47  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052b4e  lea     context, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052b55  mov     r9d, ebx; hr
0x180052b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b5d  jmp     loc_180052AB0
0x180052b62  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052b69  lea     context, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052b70  mov     ebx, 8000FFFFh
0x180052b75  mov     edx, 166h; lineNumber
0x180052b7a  mov     r9d, ebx; hr
0x180052b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b82  mov     edx, 10Fh
0x180052b87  jmp     loc_180052A85
0x180052b8c  mov     manager, [rbp+1A8h]; callerReturnAddress
0x180052b93  lea     context, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052b9a  mov     r9d, ebx; hr
0x180052b9d  mov     edx, 1B0h; lineNumber
0x180052ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ba7  mov     edx, 110h
0x180052bac  jmp     loc_180052A85
```
