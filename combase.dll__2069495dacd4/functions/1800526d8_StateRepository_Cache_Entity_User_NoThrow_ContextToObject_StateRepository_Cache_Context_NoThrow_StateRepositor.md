# StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)

- ea: `0x1800526d8`
- end: `0x180052870`
- name: `?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `408`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Context_NoThrow *context, StateRepository::Cache::Entity::User_NoThrow *entity, StateRepository::Cache::Entity::User_NoThrow::CacheFlags cacheId, __int64 context)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180052bb8`

## callees

- `0x18003a8bc`
- `0x18003cf8c`
- `0x1800526d8`
- `0x180052878`
- `0x1800a4730`
- `0x1801de3fc`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800527cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800527cd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800527ac`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800527ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180052772`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180052772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800527ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005282f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052839`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800527ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005282f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052839`

## string_xrefs

- `0x180052703`: `UserSid`
- `0x18005280a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052852`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *context,
        StateRepository::Cache::Entity::User_NoThrow *entity,
        StateRepository::Cache::Entity::User_NoThrow::CacheFlags cacheId,
        __int64 a4)
{
  HRESULT Field; // ebx
  void *v7; // rcx
  wchar_t *v8; // rcx
  BOOL v9; // r14d
  _QWORD *v10; // rbx
  wchar_t *v11; // rdi
  void *m_ptr; // rbx
  DWORD LengthSid; // eax
  void *v14; // rcx
  wchar_t *v16; // rcx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > userSidAsSid; // [rsp+20h] [rbp-28h] BYREF
  void **p_userSidAsString; // [rsp+28h] [rbp-20h]
  wchar_t *value; // [rsp+30h] [rbp-18h] BYREF
  char v20; // [rsp+38h] [rbp-10h]
  void *retaddr; // [rsp+78h] [rbp+30h]
  wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (__cdecl*)(void *),&SRCache_Free> > userSidAsString; // [rsp+90h] [rbp+48h] BYREF

  userSidAsString.__ptr_.__value_ = 0;
  value = 0;
  p_userSidAsString = (void **)&userSidAsString;
  v20 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(context, L"UserSid", &value);
  if ( v20 )
  {
    v7 = *p_userSidAsString;
    *p_userSidAsString = value;
    if ( v7 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x347u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      Field);
  }
  else
  {
    v8 = userSidAsString.__ptr_.__value_;
    if ( !userSidAsString.__ptr_.__value_ )
    {
      entity->m_userSid = 0;
LABEL_15:
      userSidAsString.__ptr_.__value_ = 0;
      if ( v8 )
        SRCache_Free();
      entity->m__cacheId = a4;
      return 0;
    }
    userSidAsSid.m_ptr = 0;
    p_userSidAsString = (void **)&userSidAsSid;
    value = 0;
    v20 = 1;
    v9 = ConvertStringSidToSidW(userSidAsString.__ptr_.__value_, (PSID *)&value);
    if ( v20 )
    {
      v10 = p_userSidAsString;
      v11 = value;
      if ( *p_userSidAsString )
        wil::details::close_invoke_helper<1,void * (*)(void *),&void * LocalFree(void *),void *>::close_reset(*p_userSidAsString);
      *v10 = v11;
    }
    if ( v9 )
    {
      m_ptr = userSidAsSid.m_ptr;
      LengthSid = GetLengthSid(userSidAsSid.m_ptr);
      memcpy_0(entity->m_userSidBuffer, m_ptr, LengthSid);
      v14 = userSidAsSid.m_ptr;
      entity->m_userSid = entity->m_userSidBuffer;
      if ( v14 )
        LocalFree(v14);
      v8 = userSidAsString.__ptr_.__value_;
      goto LABEL_15;
    }
    Field = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              0x34Fu,
              "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp");
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&userSidAsSid);
  }
  v16 = userSidAsString.__ptr_.__value_;
  userSidAsString.__ptr_.__value_ = 0;
  if ( v16 )
    SRCache_Free();
  return (unsigned int)Field;
}

```

## disassembly

```asm
0x1800526d8  mov     [rsp-30h+userSidAsString.__ptr_.__value_], r8
0x1800526dd  push    rbp
0x1800526de  push    rbx
0x1800526df  push    rsi
0x1800526e0  push    rdi
0x1800526e1  push    r14
0x1800526e3  push    r15
0x1800526e5  mov     rbp, rsp
0x1800526e8  sub     rsp, 48h
0x1800526ec  mov     rsi, entity
0x1800526ef  mov     [rbp+userSidAsString.__ptr_.__value_], 0
0x1800526f7  lea     rax, [rbp+userSidAsString]
0x1800526fb  mov     [rbp+value], 0
0x180052703  lea     entity, aUsersid; "UserSid"
0x18005270a  mov     [rbp+var_20], rax
0x18005270e  lea     r8, [rbp+value]; value
0x180052712  mov     [rbp+var_10], 1
0x180052716  mov     r15, cacheId
0x180052719  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18005271e  cmp     [rbp+var_10], 0
0x180052722  mov     ebx, eax
0x180052724  jz      short loc_18005273D
0x180052726  mov     r8, [rbp+var_20]
0x18005272a  mov     entity, [rbp+value]
0x18005272e  mov     context, [r8]
0x180052731  mov     [r8], entity
0x180052734  test    context, context
0x180052737  jnz     loc_180052839
0x18005273d  test    ebx, ebx
0x18005273f  js      loc_180052806
0x180052745  mov     context, [rbp+userSidAsString.__ptr_.__value_]; StringSid
0x180052749  test    context, context
0x18005274c  jz      loc_1800527D9
0x180052752  lea     rax, [rbp+userSidAsSid]
0x180052756  mov     [rbp+userSidAsSid.m_ptr], 0
0x18005275e  lea     entity, [rbp+value]; Sid
0x180052762  mov     [rbp+var_20], rax
0x180052766  mov     [rbp+value], 0
0x18005276e  mov     [rbp+var_10], 1
0x180052772  call    cs:__imp_ConvertStringSidToSidW
0x180052778  cmp     [rbp+var_10], 0
0x18005277c  mov     r14d, eax
0x18005277f  jz      short loc_180052798
0x180052781  mov     rbx, [rbp+var_20]
0x180052785  mov     rdi, [rbp+value]
0x180052789  mov     context, [rbx]; value
0x18005278c  test    context, context
0x18005278f  jnz     loc_180052844
0x180052795  mov     [rbx], rdi
0x180052798  test    r14d, r14d
0x18005279b  jz      loc_18005284E
0x1800527a1  mov     rbx, [rbp+userSidAsSid.m_ptr]
0x1800527a5  lea     rdi, [rsi+8]
0x1800527a9  mov     context, rbx; pSid
0x1800527ac  call    cs:__imp_GetLengthSid
0x1800527b2  mov     r8d, eax; Size
0x1800527b5  mov     entity, rbx; Src
0x1800527b8  mov     context, rdi; void *
0x1800527bb  call    memcpy_0
0x1800527c0  mov     context, [rbp+userSidAsSid.m_ptr]; hMem
0x1800527c4  mov     [rsi+50h], rdi
0x1800527c8  test    context, context
0x1800527cb  jz      short loc_1800527D3
0x1800527cd  call    cs:__imp_LocalFree
0x1800527d3  mov     context, [rbp+userSidAsString.__ptr_.__value_]
0x1800527d7  jmp     short loc_1800527E1
0x1800527d9  mov     qword ptr [rsi+50h], 0
0x1800527e1  mov     [rbp+userSidAsString.__ptr_.__value_], 0
0x1800527e9  test    context, context
0x1800527ec  jz      short loc_1800527F4
0x1800527ee  call    cs:__imp_SRCache_Free
0x1800527f4  mov     [rsi], r15
0x1800527f7  xor     eax, eax
0x1800527f9  add     rsp, 48h
0x1800527fd  pop     r15
0x1800527ff  pop     r14
0x180052801  pop     rdi
0x180052802  pop     rsi
0x180052803  pop     rbx
0x180052804  pop     rbp
0x180052805  retn
0x180052806  mov     context, [rbp+30h]; callerReturnAddress
0x18005280a  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052811  mov     r9d, ebx; hr
0x180052814  mov     edx, 347h; lineNumber
0x180052819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005281e  mov     context, [rbp+userSidAsString.__ptr_.__value_]
0x180052822  mov     [rbp+userSidAsString.__ptr_.__value_], 0
0x18005282a  test    context, context
0x18005282d  jz      short loc_180052835
0x18005282f  call    cs:__imp_SRCache_Free
0x180052835  mov     eax, ebx
0x180052837  jmp     short loc_1800527F9
0x180052839  call    cs:__imp_SRCache_Free
0x18005283f  jmp     loc_18005273D
0x180052844  call    ?close_reset@?$close_invoke_helper@$00P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,void * (*)(void *),&LocalFree(void *),void *>::close_reset(void *)
0x180052849  jmp     loc_180052795
0x18005284e  mov     context, [rbp+30h]; callerReturnAddress
0x180052852  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052859  mov     edx, 34Fh; lineNumber
0x18005285e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052863  lea     context, [rbp+userSidAsSid]; this
0x180052867  mov     ebx, eax
0x180052869  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005286e  jmp     short loc_18005281E
```
