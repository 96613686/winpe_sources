# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x180019588`
- end: `0x18001968e`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180063308`
- `0x1800a6818`

## callees

- `0x180019588`
- `0x180019694`
- `0x180019aac`
- `0x180019e3c`
- `0x18002c8d0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001961c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019673`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001961c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019673`

## string_xrefs

- `0x18001963c`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180019653`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  bool *v5; // rsi
  int v9; // ebx
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rdx
  bool *v13; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  bool *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]

  v5 = a5;
  v19 = 0;
  *a5 = 0;
  v9 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(a1, a2, &v19);
  if ( v9 < 0 )
  {
    v15 = 1165;
  }
  else
  {
    v10 = v19;
    if ( !v19 )
      return 0;
    a5 = 0;
    v11 = StateRepository::Cache::Entity::Package_NoThrow::Open(
            a1,
            v19,
            (struct StateRepository::Cache::Context_NoThrow *)&a5,
            v5);
    v9 = v11;
    if ( v11 < 0 )
    {
      v18 = 1110;
    }
    else
    {
      if ( !*v5
        || (v11 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&a5, a4, a3, v10), v9 = v11, v11 >= 0) )
      {
        v13 = a5;
        a5 = 0;
        if ( v13 )
          SRCacheContext_Close(v13, v12);
        return 0;
      }
      v18 = 1115;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v11,
      v19);
    v17 = a5;
    a5 = 0;
    if ( v17 )
      SRCacheContext_Close(v17, v16);
    v15 = 1168;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
    (const char *)(unsigned int)v9,
    v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019588  push    rbp
0x18001958a  push    rbx
0x18001958b  push    rsi
0x18001958c  push    rdi
0x18001958d  push    r12
0x18001958f  push    r14
0x180019591  push    r15
0x180019593  mov     rbp, rsp
0x180019596  sub     rsp, 30h
0x18001959a  mov     rsi, [rbp+arg_20]
0x18001959e  mov     r12, r8
0x1800195a1  lea     r8, [rbp+var_10]; __int64 *
0x1800195a5  mov     [rbp+var_10], 0
0x1800195ad  mov     r15, r9
0x1800195b0  mov     r14, rcx
0x1800195b3  mov     byte ptr [rsi], 0
0x1800195b6  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800195bb  mov     ebx, eax
0x1800195bd  test    eax, eax
0x1800195bf  js      short loc_180019633
0x1800195c1  mov     rdi, [rbp+var_10]
0x1800195c5  test    rdi, rdi
0x1800195c8  jz      short loc_180019622
0x1800195ca  mov     r9, rsi; bool *
0x1800195cd  mov     [rbp+arg_20], 0
0x1800195d5  lea     r8, [rbp+arg_20]; struct StateRepository::Cache::Context_NoThrow *
0x1800195d9  mov     rdx, rdi; __int64
0x1800195dc  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800195df  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800195e4  mov     ebx, eax
0x1800195e6  test    eax, eax
0x1800195e8  js      loc_180019680
0x1800195ee  cmp     byte ptr [rsi], 0
0x1800195f1  jz      short loc_18001960B
0x1800195f3  mov     r9, rdi
0x1800195f6  lea     rcx, [rbp+arg_20]
0x1800195fa  mov     r8, r12
0x1800195fd  mov     rdx, r15
0x180019600  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180019605  mov     ebx, eax
0x180019607  test    eax, eax
0x180019609  js      short loc_180019687
0x18001960b  mov     rcx, [rbp+arg_20]
0x18001960f  mov     [rbp+arg_20], 0
0x180019617  test    rcx, rcx
0x18001961a  jz      short loc_180019622
0x18001961c  call    cs:__imp_SRCacheContext_Close
0x180019622  xor     eax, eax
0x180019624  add     rsp, 30h
0x180019628  pop     r15
0x18001962a  pop     r14
0x18001962c  pop     r12
0x18001962e  pop     rdi
0x18001962f  pop     rsi
0x180019630  pop     rbx
0x180019631  pop     rbp
0x180019632  retn
0x180019633  mov     edx, 48Dh; void *
0x180019638  mov     rcx, [rbp+38h]; this
0x18001963c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019643  mov     r9d, ebx; char *
0x180019646  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001964b  mov     eax, ebx
0x18001964d  jmp     short loc_180019624
0x18001964f  mov     rcx, [rbp+38h]; this
0x180019653  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001965a  mov     r9d, eax; char *
0x18001965d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019662  mov     rcx, [rbp+arg_20]
0x180019666  mov     [rbp+arg_20], 0
0x18001966e  test    rcx, rcx
0x180019671  jz      short loc_180019679
0x180019673  call    cs:__imp_SRCacheContext_Close
0x180019679  mov     edx, 490h
0x18001967e  jmp     short loc_180019638
0x180019680  mov     edx, 456h; void *
0x180019685  jmp     short loc_18001964F
0x180019687  mov     edx, 45Bh
0x18001968c  jmp     short loc_18001964F
```
