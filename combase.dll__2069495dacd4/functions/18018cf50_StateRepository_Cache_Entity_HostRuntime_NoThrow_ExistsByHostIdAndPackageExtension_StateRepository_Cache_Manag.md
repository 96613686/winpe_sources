# StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64,bool &)

- ea: `0x18018cf50`
- end: `0x18018d2fe`
- name: `?ExistsByHostIdAndPackageExtension@HostRuntime_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBG_JAEA_N@Z`
- size: `942`
- prototype: `HRESULT __fastcall(StateRepository::Cache::Manager_NoThrow *manager, const wchar_t *hostId, __int64 packageExtension, bool *found)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18012eebc`

## callees

- `0x18003a8bc`
- `0x180052310`
- `0x180053efc`
- `0x18011f704`
- `0x180126db0`
- `0x18013c938`
- `0x18018cf50`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018d158`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18018d158`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018cfe5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018cfe5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018d1da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018d1da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018d0df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018d2c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018d0df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018d2c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d046`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d23b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d2ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d2d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d046`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d23b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d2ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018d2d7`

## string_xrefs

- `0x18018d10c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18018d169`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18018d004`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018d1f9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18018cf94`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x18018d024`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x18018d0bd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x18018d219`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x18018cfd0`: `HostRuntime\Index\HostIdAndPackageExtension`
- `0x18018d27d`: `HostRuntime\Index\HostIdAndPackageExtension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(
        StateRepository::Cache::Manager_NoThrow *manager,
        const wchar_t *hostId,
        __int64 packageExtension,
        bool *found)
{
  HRESULT v7; // ebx
  SRCacheManager *value; // rcx
  unsigned int v10; // edx
  __int64 v11; // rdx
  SRCacheContext *v12; // rcx
  bool v13; // r8
  unsigned int v14; // edx
  wchar_t *v15; // rcx
  HRESULT v16; // eax
  unsigned int v17; // edx
  SRCacheContext *v18; // rcx
  __int64 v19; // rdx
  SRCacheContext *v20; // rcx
  wchar_t *v21; // rcx
  SRCacheContext *v22; // rcx
  bool isEmpty; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Cache::Context_NoThrow indexContext; // [rsp+28h] [rbp-D8h] BYREF
  StateRepository::Cache::Context_NoThrow context; // [rsp+30h] [rbp-D0h] BYREF
  StateRepository::Cache::Key_NoThrow key; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> > v27; // [rsp+260h] [rbp+160h] BYREF
  void *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *found = 0;
  if ( !packageExtension )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x67u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      -2147024809);
    return (unsigned int)v7;
  }
  value = manager->m_cacheManager.__ptr_.__value_;
  v27.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&indexContext;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  v27.pRaw = 0;
  v27.replace = 1;
  v7 = SRCacheContext_Open(value, L"HostRuntime\\Index\\HostIdAndPackageExtension", 0, &v27.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v27);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x18Cu,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v7);
    v10 = 107;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v10,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      v7);
LABEL_7:
    v12 = indexContext.m_cacheContext.__ptr_.__value_;
    indexContext.m_cacheContext.__ptr_.__value_ = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v7;
  }
  if ( !indexContext.m_cacheContext.__ptr_.__value_ )
  {
    v7 = -2140733422;
    v10 = 108;
    goto LABEL_6;
  }
  key.m_largeKey.__ptr_.__value_ = 0;
  memset_0(key.m_smallKey, 0, sizeof(key.m_smallKey));
  key.m_length = 0;
  key.m_key = key.m_smallKey;
  key.m_capacity = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append(&key, hostId);
  if ( v7 < 0 )
  {
    v14 = 111;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v14,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      v7);
LABEL_14:
    v15 = key.m_largeKey.__ptr_.__value_;
    key.m_largeKey.__ptr_.__value_ = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_7;
  }
  v16 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(&key, key.m_length + 2, v13);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x16Du,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      v16);
    v14 = 112;
    goto LABEL_13;
  }
  *(_DWORD *)&key.m_key[key.m_length++] = 94;
  if ( (unsigned int)_o__ui64tow_s(packageExtension, &v27, 17, 16) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x166u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      -2147418113);
LABEL_21:
    v14 = 113;
    goto LABEL_13;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append(&key, (const wchar_t *)&v27);
  if ( v7 < 0 )
    goto LABEL_21;
  v27.wrapper = (wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter> *)&context;
  context.m_cacheContext.__ptr_.__value_ = 0;
  v27.pRaw = 0;
  v27.replace = 1;
  v7 = SRCacheContext_OpenSubContext(indexContext.m_cacheContext.__ptr_.__value_, key.m_key, 0, &v27.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v27);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x1B0u,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      v7);
    v17 = 117;
    goto LABEL_24;
  }
  if ( context.m_cacheContext.__ptr_.__value_ )
  {
    isEmpty = 0;
    v7 = StateRepository::Cache::Context_NoThrow::IsEmpty(&context, &isEmpty);
    if ( v7 < 0 )
    {
      v17 = 121;
      goto LABEL_24;
    }
    *found = !isEmpty;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         &indexContext,
         L"HostRuntime\\Index\\HostIdAndPackageExtension");
  if ( v7 < 0 )
  {
    v17 = 125;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v17,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      v7);
    v18 = context.m_cacheContext.__ptr_.__value_;
    context.m_cacheContext.__ptr_.__value_ = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v11);
    goto LABEL_14;
  }
  v20 = context.m_cacheContext.__ptr_.__value_;
  context.m_cacheContext.__ptr_.__value_ = 0;
  if ( v20 )
    SRCacheContext_Close(v20, v19);
  v21 = key.m_largeKey.__ptr_.__value_;
  key.m_largeKey.__ptr_.__value_ = 0;
  if ( v21 )
    SRCache_Free();
  v22 = indexContext.m_cacheContext.__ptr_.__value_;
  indexContext.m_cacheContext.__ptr_.__value_ = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v19);
  return 0;
}

```

## disassembly

```asm
0x18018cf50  push    rbp
0x18018cf52  push    rbx
0x18018cf53  push    rsi
0x18018cf54  push    rdi
0x18018cf55  push    r14
0x18018cf57  push    r15
0x18018cf59  lea     rbp, [rsp-198h]
0x18018cf61  sub     rsp, 298h
0x18018cf68  mov     rax, cs:__security_cookie
0x18018cf6f  xor     rax, rsp
0x18018cf72  mov     [rbp+1C0h+var_38], rax
0x18018cf79  xor     r15d, r15d
0x18018cf7c  mov     rdi, found
0x18018cf7f  mov     [found], r15b
0x18018cf82  mov     rsi, packageExtension
0x18018cf85  mov     r14, hostId
0x18018cf88  test    packageExtension, packageExtension
0x18018cf8b  jnz     short loc_18018CFB2
0x18018cf8d  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018cf94  lea     packageExtension, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018cf9b  mov     ebx, 80070057h
0x18018cfa0  lea     edx, [rsi+67h]; lineNumber
0x18018cfa3  mov     r9d, ebx; hr
0x18018cfa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018cfab  mov     eax, ebx
0x18018cfad  jmp     loc_18018D2DF
0x18018cfb2  mov     manager, [manager]
0x18018cfb5  lea     rax, [rsp+2C0h+indexContext]
0x18018cfba  lea     found, [rbp+1C0h+var_60.pRaw]
0x18018cfc1  mov     [rbp+1C0h+var_60.wrapper], rax
0x18018cfc8  xor     r8d, r8d
0x18018cfcb  mov     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018cfd0  lea     hostId, aHostruntimeInd; "HostRuntime\\Index\\HostIdAndPackageExt"...
0x18018cfd7  mov     [rbp+1C0h+var_60.pRaw], r15
0x18018cfde  mov     [rbp+1C0h+var_60.replace], 1
0x18018cfe5  call    cs:__imp_SRCacheContext_Open
0x18018cfeb  lea     manager, [rbp+1C0h+var_60]; this
0x18018cff2  mov     ebx, eax
0x18018cff4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018cff9  test    ebx, ebx
0x18018cffb  jns     short loc_18018D051
0x18018cffd  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d004  lea     packageExtension, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d00b  mov     r9d, ebx; hr
0x18018d00e  mov     edx, 18Ch; lineNumber
0x18018d013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d018  mov     edx, 6Bh ; 'k'; lineNumber
0x18018d01d  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d024  lea     packageExtension, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d02b  mov     r9d, ebx; hr
0x18018d02e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d033  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018d038  mov     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018d03d  test    manager, manager
0x18018d040  jz      loc_18018CFAB
0x18018d046  call    cs:__imp_SRCacheContext_Close
0x18018d04c  jmp     loc_18018CFAB
0x18018d051  cmp     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018d056  setnz   al
0x18018d059  test    al, al
0x18018d05b  jnz     short loc_18018D069
0x18018d05d  mov     ebx, 80670012h
0x18018d062  mov     edx, 6Ch ; 'l'
0x18018d067  jmp     short loc_18018D01D
0x18018d069  xor     edx, edx; Val
0x18018d06b  mov     [rsp+2C0h+key.m_largeKey.__ptr_.__value_], r15
0x18018d070  mov     r8d, 200h; Size
0x18018d076  lea     manager, [rsp+2C0h+key.m_smallKey]; void *
0x18018d07b  call    memset_0
0x18018d080  lea     rax, [rsp+2C0h+key.m_smallKey]
0x18018d085  mov     [rbp+1C0h+key.m_length], r15
0x18018d08c  mov     hostId, r14; value
0x18018d08f  mov     [rbp+1C0h+key.m_key], rax
0x18018d096  lea     manager, [rsp+2C0h+key]; this
0x18018d09b  mov     [rbp+1C0h+key.m_capacity], 100h
0x18018d0a6  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18018d0ab  mov     ebx, eax
0x18018d0ad  test    eax, eax
0x18018d0af  jns     short loc_18018D0EA
0x18018d0b1  mov     edx, 6Fh ; 'o'; lineNumber
0x18018d0b6  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d0bd  lea     packageExtension, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d0c4  mov     r9d, ebx; hr
0x18018d0c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d0cc  mov     manager, [rsp+2C0h+key.m_largeKey.__ptr_.__value_]
0x18018d0d1  mov     [rsp+2C0h+key.m_largeKey.__ptr_.__value_], r15
0x18018d0d6  test    manager, manager
0x18018d0d9  jz      loc_18018D033
0x18018d0df  call    cs:__imp_SRCache_Free
0x18018d0e5  jmp     loc_18018D033
0x18018d0ea  mov     hostId, [rbp+1C0h+key.m_length]
0x18018d0f1  lea     manager, [rsp+2C0h+key]; this
0x18018d0f6  add     hostId, 2; capacity
0x18018d0fa  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18018d0ff  mov     ebx, eax
0x18018d101  test    eax, eax
0x18018d103  jns     short loc_18018D127
0x18018d105  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d10c  lea     packageExtension, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d113  mov     r9d, eax; hr
0x18018d116  mov     edx, 16Dh; lineNumber
0x18018d11b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d120  mov     edx, 70h ; 'p'
0x18018d125  jmp     short loc_18018D0B6
0x18018d127  mov     packageExtension, [rbp+1C0h+key.m_length]
0x18018d12e  mov     r9d, 10h
0x18018d134  mov     hostId, [rbp+1C0h+key.m_key]
0x18018d13b  mov     manager, rsi
0x18018d13e  mov     dword ptr [hostId+packageExtension*2], 5Eh ; '^'
0x18018d146  lea     r8d, [found+1]
0x18018d14a  inc     [rbp+1C0h+key.m_length]
0x18018d151  lea     hostId, [rbp+1C0h+var_60]
0x18018d158  call    cs:__imp__o__ui64tow_s
0x18018d15e  test    eax, eax
0x18018d160  jz      short loc_18018D184
0x18018d162  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d169  lea     packageExtension, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d170  mov     ebx, 8000FFFFh
0x18018d175  mov     edx, 166h; lineNumber
0x18018d17a  mov     r9d, ebx; hr
0x18018d17d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d182  jmp     short loc_18018D19B
0x18018d184  lea     hostId, [rbp+1C0h+var_60]; value
0x18018d18b  lea     manager, [rsp+2C0h+key]; this
0x18018d190  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18018d195  mov     ebx, eax
0x18018d197  test    eax, eax
0x18018d199  jns     short loc_18018D1A5
0x18018d19b  mov     edx, 71h ; 'q'
0x18018d1a0  jmp     loc_18018D0B6
0x18018d1a5  mov     hostId, [rbp+1C0h+key.m_key]
0x18018d1ac  lea     rax, [rsp+2C0h+context]
0x18018d1b1  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018d1b6  lea     found, [rbp+1C0h+var_60.pRaw]
0x18018d1bd  xor     r8d, r8d
0x18018d1c0  mov     [rbp+1C0h+var_60.wrapper], rax
0x18018d1c7  mov     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x18018d1cc  mov     [rbp+1C0h+var_60.pRaw], r15
0x18018d1d3  mov     [rbp+1C0h+var_60.replace], 1
0x18018d1da  call    cs:__imp_SRCacheContext_OpenSubContext
0x18018d1e0  lea     manager, [rbp+1C0h+var_60]; this
0x18018d1e7  mov     ebx, eax
0x18018d1e9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018d1ee  test    ebx, ebx
0x18018d1f0  jns     short loc_18018D246
0x18018d1f2  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d1f9  lea     packageExtension, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d200  mov     r9d, ebx; hr
0x18018d203  mov     edx, 1B0h; lineNumber
0x18018d208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d20d  mov     edx, 75h ; 'u'; lineNumber
0x18018d212  mov     manager, [rbp+1C8h]; callerReturnAddress
0x18018d219  lea     packageExtension, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18018d220  mov     r9d, ebx; hr
0x18018d223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d228  mov     manager, [rsp+2C0h+context.m_cacheContext.__ptr_.__value_]
0x18018d22d  mov     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x18018d232  test    manager, manager
0x18018d235  jz      loc_18018D0CC
0x18018d23b  call    cs:__imp_SRCacheContext_Close
0x18018d241  jmp     loc_18018D0CC
0x18018d246  cmp     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x18018d24b  setnz   al
0x18018d24e  test    al, al
0x18018d250  jz      short loc_18018D27D
0x18018d252  lea     hostId, [rsp+2C0h+isEmpty]; isEmpty
0x18018d257  mov     [rsp+2C0h+isEmpty], r15b
0x18018d25c  lea     manager, [rsp+2C0h+context]; this
0x18018d261  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x18018d266  mov     ebx, eax
0x18018d268  test    eax, eax
0x18018d26a  jns     short loc_18018D273
0x18018d26c  mov     edx, 79h ; 'y'
0x18018d271  jmp     short loc_18018D212
0x18018d273  cmp     [rsp+2C0h+isEmpty], r15b
0x18018d278  setz    al
0x18018d27b  mov     [rdi], al
0x18018d27d  lea     hostId, aHostruntimeInd; "HostRuntime\\Index\\HostIdAndPackageExt"...
0x18018d284  lea     manager, [rsp+2C0h+indexContext]; this
0x18018d289  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18018d28e  mov     ebx, eax
0x18018d290  test    eax, eax
0x18018d292  jns     short loc_18018D29E
0x18018d294  mov     edx, 7Dh ; '}'
0x18018d299  jmp     loc_18018D212
0x18018d29e  mov     manager, [rsp+2C0h+context.m_cacheContext.__ptr_.__value_]
0x18018d2a3  mov     [rsp+2C0h+context.m_cacheContext.__ptr_.__value_], r15
0x18018d2a8  test    manager, manager
0x18018d2ab  jz      short loc_18018D2B3
0x18018d2ad  call    cs:__imp_SRCacheContext_Close
0x18018d2b3  mov     manager, [rsp+2C0h+key.m_largeKey.__ptr_.__value_]
0x18018d2b8  mov     [rsp+2C0h+key.m_largeKey.__ptr_.__value_], r15
0x18018d2bd  test    manager, manager
0x18018d2c0  jz      short loc_18018D2C8
0x18018d2c2  call    cs:__imp_SRCache_Free
0x18018d2c8  mov     manager, [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_]
0x18018d2cd  mov     [rsp+2C0h+indexContext.m_cacheContext.__ptr_.__value_], r15
0x18018d2d2  test    manager, manager
0x18018d2d5  jz      short loc_18018D2DD
0x18018d2d7  call    cs:__imp_SRCacheContext_Close
0x18018d2dd  xor     eax, eax
0x18018d2df  mov     manager, [rbp+1C0h+var_38]
0x18018d2e6  xor     manager, rsp; StackCookie
0x18018d2e9  call    __security_check_cookie
0x18018d2ee  add     rsp, 298h
0x18018d2f5  pop     r15
0x18018d2f7  pop     r14
0x18018d2f9  pop     rdi
0x18018d2fa  pop     rsi
0x18018d2fb  pop     rbx
0x18018d2fc  pop     rbp
0x18018d2fd  retn
```
