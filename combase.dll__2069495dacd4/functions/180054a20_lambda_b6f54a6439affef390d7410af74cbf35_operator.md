# _lambda_b6f54a6439affef390d7410af74cbf35_::operator()

- ea: `0x180054a20`
- end: `0x180054c93`
- name: `_lambda_b6f54a6439affef390d7410af74cbf35_::operator()`
- size: `627`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180054dfc`

## callees

- `0x18003a8bc`
- `0x18003c7ec`
- `0x180053ac0`
- `0x180053be0`
- `0x18005422c`
- `0x1800545bc`
- `0x180054a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180054a58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180054a58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054b94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054c4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054b94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180054c4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180054a79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180054ac0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180054bc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180054a79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180054ac0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180054bc8`

## string_xrefs

- `0x180054bec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180054c2e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180054a9f`: `onecore\com\combase\extensioncatalog\extensionregistration.cpp`
- `0x180054c08`: `onecore\com\combase\extensioncatalog\extensionregistration.cpp`
- `0x180054c6c`: `onecore\com\combase\extensioncatalog\extensionregistration.cpp`
- `0x180054a87`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall lambda_b6f54a6439affef390d7410af74cbf35_::operator()(__int64 *a1)
{
  HRESULT v2; // ebx
  SRCacheManager *value; // rcx
  SRCacheManager *v4; // rcx
  __int64 v6; // rax
  const wchar_t *v7; // rdx
  bool v8; // si
  __int64 v9; // rdi
  HRESULT v10; // eax
  __int64 v11; // rdx
  SRCacheContext *v12; // rcx
  SRCacheManager *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  SRCacheContext *v16; // rcx
  unsigned int v17; // edx
  __int64 cacheId; // [rsp+20h] [rbp-59h] BYREF
  StateRepository::Cache::Manager_NoThrow *p_manager; // [rsp+28h] [rbp-51h]
  SRCacheManager *v20; // [rsp+30h] [rbp-49h] BYREF
  char v21; // [rsp+38h] [rbp-41h]
  StateRepository::Cache::Entity::Package_NoThrow package; // [rsp+40h] [rbp-39h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+5Fh]
  bool found; // [rsp+E8h] [rbp+6Fh] BYREF
  StateRepository::Cache::Manager_NoThrow manager; // [rsp+F0h] [rbp+77h] BYREF
  StateRepository::Cache::Context_NoThrow context; // [rsp+F8h] [rbp+7Fh] BYREF

  v21 = 1;
  manager.m_cacheManager.__ptr_.__value_ = 0;
  p_manager = &manager;
  v20 = 0;
  v2 = SRCacheManager_Open(0, &v20);
  if ( v21 )
  {
    value = p_manager->m_cacheManager.__ptr_.__value_;
    p_manager->m_cacheManager.__ptr_.__value_ = v20;
    if ( value )
      SRCacheManager_Close();
  }
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xA5u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      v2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1DEu,
      "onecore\\com\\combase\\extensioncatalog\\extensionregistration.cpp",
      v2);
LABEL_6:
    v4 = manager.m_cacheManager.__ptr_.__value_;
    manager.m_cacheManager.__ptr_.__value_ = 0;
    if ( v4 )
      SRCacheManager_Close();
    return (unsigned int)v2;
  }
  v6 = *a1;
  memset(&package, 0, 84);
  package.m_displayName.__ptr_.__value_ = 0;
  package.m_sourceBundle = 0;
  if ( *(_QWORD *)v6 )
    v7 = *(const wchar_t **)(*(_QWORD *)v6 + 16LL);
  else
    v7 = g_WindowsEmptyStringInternal;
  found = 0;
  cacheId = 0;
  v8 = 0;
  v2 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&manager, v7, &cacheId);
  if ( v2 < 0 )
  {
    v14 = 1165;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v14,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1E4u,
      "onecore\\com\\combase\\extensioncatalog\\extensionregistration.cpp",
      v2);
LABEL_31:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
    goto LABEL_6;
  }
  v9 = cacheId;
  if ( !cacheId )
    goto LABEL_18;
  context.m_cacheContext.__ptr_.__value_ = 0;
  v10 = StateRepository::Cache::Entity::Package_NoThrow::Open(&manager, cacheId, &context, &found);
  v2 = v10;
  if ( v10 < 0 )
  {
    v17 = 1110;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v17,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v10);
    v16 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v16 )
      SRCacheContext_Close(v16, v15);
    v14 = 1168;
    goto LABEL_23;
  }
  v8 = found;
  if ( found )
  {
    v10 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(
            &context,
            &package,
            (StateRepository::Cache::Entity::Package_NoThrow::CacheFlags)16,
            v9);
    v2 = v10;
    if ( v10 < 0 )
    {
      v17 = 1115;
      goto LABEL_25;
    }
  }
  v12 = context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v12 )
    SRCacheContext_Close(v12, v11);
LABEL_18:
  if ( !v8 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           0x1E8u,
           "onecore\\com\\combase\\extensioncatalog\\extensionregistration.cpp",
           0x490u);
    goto LABEL_31;
  }
  *(_BYTE *)a1[1] = (*(_WORD *)package.m_flags2 & 0x1000) != 0;
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(&package);
  v13 = manager.m_cacheManager.__ptr_.__value_;
  manager.m_cacheManager.__ptr_.__value_ = 0;
  if ( v13 )
    SRCacheManager_Close();
  return 0;
}

```

## disassembly

```asm
0x180054a20  mov     [rsp-8+arg_0], rbx
0x180054a25  push    rbp
0x180054a26  push    rsi
0x180054a27  push    rdi
0x180054a28  push    r14
0x180054a2a  push    r15
0x180054a2c  lea     rbp, [rsp-37h]
0x180054a31  sub     rsp, 0B0h
0x180054a38  mov     r14, this
0x180054a3b  mov     [rbp+57h+var_98], 1
0x180054a3f  xor     r15d, r15d
0x180054a42  lea     rax, [rbp+57h+manager]
0x180054a46  xor     ecx, ecx
0x180054a48  mov     [rbp+57h+manager.m_cacheManager.__ptr_.__value_], r15
0x180054a4c  lea     rdx, [rbp+57h+var_A0]
0x180054a50  mov     [rbp+57h+var_A8], rax
0x180054a54  mov     [rbp+57h+var_A0], r15
0x180054a58  call    cs:__imp_SRCacheManager_Open
0x180054a5e  mov     ebx, eax
0x180054a60  cmp     [rbp+57h+var_98], r15b
0x180054a64  jz      short loc_180054A7F
0x180054a66  mov     r8, [rbp+57h+var_A8]
0x180054a6a  mov     rdx, [rbp+57h+var_A0]
0x180054a6e  mov     this, [r8]
0x180054a71  mov     [r8], rdx
0x180054a74  test    this, this
0x180054a77  jz      short loc_180054A7F
0x180054a79  call    cs:__imp_SRCacheManager_Close
0x180054a7f  test    ebx, ebx
0x180054a81  jns     short loc_180054ACD
0x180054a83  mov     this, [rbp+5Fh]; callerReturnAddress
0x180054a87  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054a8e  mov     r9d, ebx; hr
0x180054a91  mov     edx, 0A5h; lineNumber
0x180054a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054a9b  mov     this, [rbp+5Fh]; callerReturnAddress
0x180054a9f  lea     r8, aOnecoreComComb_173; "onecore\\com\\combase\\extensioncatalog"...
0x180054aa6  mov     r9d, ebx; hr
0x180054aa9  mov     edx, 1DEh; lineNumber
0x180054aae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054ab3  mov     this, [rbp+57h+manager.m_cacheManager.__ptr_.__value_]
0x180054ab7  mov     [rbp+57h+manager.m_cacheManager.__ptr_.__value_], r15
0x180054abb  test    this, this
0x180054abe  jz      short loc_180054AC6
0x180054ac0  call    cs:__imp_SRCacheManager_Close
0x180054ac6  mov     eax, ebx
0x180054ac8  jmp     loc_180054BD0
0x180054acd  mov     rax, [r14]
0x180054ad0  xorps   xmm0, xmm0
0x180054ad3  movdqa  xmmword ptr [rbp+57h+package.m__cacheId], xmm0
0x180054ad8  mov     [rbp+57h+package.m_packageFamily], r15
0x180054adc  mov     qword ptr [rbp+57h+package.m_packageType], r15
0x180054ae0  mov     qword ptr [rbp+57h+package.m_flags2], r15
0x180054ae4  mov     [rbp+57h+package.m_volume], r15
0x180054ae8  mov     [rbp+57h+package.m_oSMaxVersionTested], r15
0x180054aec  mov     [rbp+57h+package.m_installedLocation.__ptr_.__value_], r15
0x180054af0  movdqa  xmmword ptr [rbp+57h+package.m_mutableLink.__ptr_.__value_], xmm0
0x180054af5  mov     [rbp+57h+package.m_targetDeviceFamilyName], r15d
0x180054af9  mov     [rbp+57h+package.m_displayName.__ptr_.__value_], r15
0x180054afd  mov     [rbp+57h+package.m_sourceBundle], r15
0x180054b01  mov     this, [rax]
0x180054b04  test    this, this
0x180054b07  jz      loc_180054C1E
0x180054b0d  mov     rdx, [this+10h]; packageFullName
0x180054b11  lea     r8, [rbp+57h+cacheId]; cacheId
0x180054b15  mov     [rbp+57h+found], r15b
0x180054b19  lea     this, [rbp+57h+manager]; manager
0x180054b1d  mov     [rbp+57h+cacheId], r15
0x180054b21  mov     sil, r15b
0x180054b24  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180054b29  mov     ebx, eax
0x180054b2b  test    eax, eax
0x180054b2d  js      loc_180054BE7
0x180054b33  mov     rdi, [rbp+57h+cacheId]
0x180054b37  test    rdi, rdi
0x180054b3a  jz      short loc_180054B9A
0x180054b3c  lea     r9, [rbp+57h+found]; found
0x180054b40  mov     [rbp+57h+context.m_cacheContext.__ptr_.__value_], r15
0x180054b44  lea     r8, [rbp+57h+context]; context
0x180054b48  mov     rdx, rdi; cacheId
0x180054b4b  lea     this, [rbp+57h+manager]; manager
0x180054b4f  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180054b54  mov     ebx, eax
0x180054b56  test    eax, eax
0x180054b58  js      loc_180054C5A
0x180054b5e  mov     sil, [rbp+57h+found]
0x180054b62  test    sil, sil
0x180054b65  jz      short loc_180054B87
0x180054b67  mov     r9, rdi; cacheId
0x180054b6a  lea     rdx, [rbp+57h+package]; entity
0x180054b6e  mov     r8d, 10h; cacheFlags
0x180054b74  lea     this, [rbp+57h+context]; context
0x180054b78  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180054b7d  mov     ebx, eax
0x180054b7f  test    eax, eax
0x180054b81  js      loc_180054C61
0x180054b87  mov     this, [rbp+57h+context.m_cacheContext.__ptr_.__value_]
0x180054b8b  mov     [rbp+57h+context.m_cacheContext.__ptr_.__value_], r15
0x180054b8f  test    this, this
0x180054b92  jz      short loc_180054B9A
0x180054b94  call    cs:__imp_SRCacheContext_Close
0x180054b9a  test    sil, sil
0x180054b9d  jz      loc_180054C68
0x180054ba3  mov     ecx, dword ptr [rbp+57h+package.m_flags2]
0x180054ba6  mov     rax, [r14+8]
0x180054baa  shr     ecx, 0Ch
0x180054bad  and     cl, 1
0x180054bb0  mov     [rax], cl
0x180054bb2  lea     this, [rbp+57h+package]; this
0x180054bb6  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180054bbb  mov     this, [rbp+57h+manager.m_cacheManager.__ptr_.__value_]
0x180054bbf  mov     [rbp+57h+manager.m_cacheManager.__ptr_.__value_], r15
0x180054bc3  test    this, this
0x180054bc6  jz      short loc_180054BCE
0x180054bc8  call    cs:__imp_SRCacheManager_Close
0x180054bce  xor     eax, eax
0x180054bd0  mov     rbx, [rsp+0D0h+arg_0]
0x180054bd8  add     rsp, 0B0h
0x180054bdf  pop     r15
0x180054be1  pop     r14
0x180054be3  pop     rdi
0x180054be4  pop     rsi
0x180054be5  pop     rbp
0x180054be6  retn
0x180054be7  mov     eax, 48Dh
0x180054bec  lea     rdi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054bf3  mov     this, [rbp+5Fh]; callerReturnAddress
0x180054bf7  mov     r9d, ebx; hr
0x180054bfa  mov     r8, rdi; fileName
0x180054bfd  mov     edx, eax; lineNumber
0x180054bff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054c04  mov     this, [rbp+5Fh]; callerReturnAddress
0x180054c08  lea     r8, aOnecoreComComb_173; "onecore\\com\\combase\\extensioncatalog"...
0x180054c0f  mov     r9d, ebx; hr
0x180054c12  mov     edx, 1E4h; lineNumber
0x180054c17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054c1c  jmp     short loc_180054C85
0x180054c1e  lea     rdx, ?g_WindowsEmptyStringInternal@@3QBGB; ushort const near * const g_WindowsEmptyStringInternal
0x180054c25  jmp     loc_180054B11
0x180054c2a  mov     this, [rbp+5Fh]; callerReturnAddress
0x180054c2e  lea     rdi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054c35  mov     r8, rdi; fileName
0x180054c38  mov     r9d, eax; hr
0x180054c3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054c40  mov     this, [rbp+57h+context.m_cacheContext.__ptr_.__value_]
0x180054c44  mov     [rbp+57h+context.m_cacheContext.__ptr_.__value_], r15
0x180054c48  test    this, this
0x180054c4b  jz      short loc_180054C53
0x180054c4d  call    cs:__imp_SRCacheContext_Close
0x180054c53  mov     eax, 490h
0x180054c58  jmp     short loc_180054BF3
0x180054c5a  mov     edx, 456h; lineNumber
0x180054c5f  jmp     short loc_180054C2A
0x180054c61  mov     edx, 45Bh
0x180054c66  jmp     short loc_180054C2A
0x180054c68  mov     this, [rbp+5Fh]; callerReturnAddress
0x180054c6c  lea     r8, aOnecoreComComb_173; "onecore\\com\\combase\\extensioncatalog"...
0x180054c73  mov     r9d, 490h; err
0x180054c79  mov     edx, 1E8h; lineNumber
0x180054c7e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054c83  mov     ebx, eax
0x180054c85  lea     this, [rbp+57h+package]; this
0x180054c89  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180054c8e  jmp     loc_180054AB3
```
