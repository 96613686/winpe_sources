# StateRepository::Cache::Entity::Protocol_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ba8c4`
- end: `0x1800baab8`
- name: `?Open@Protocol_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b416c`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x1800ba8c4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba94c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800baa8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba94c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800baa8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba9e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800baa6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba9e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800baa6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800baa29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800baa29`

## string_xrefs

- `0x1800baa42`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ba92e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800ba9c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800ba906`: `Protocol\Data`
- `0x1800baa22`: `Protocol\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *this,
        bool *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  bool v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+238h] [rbp+138h]
  __int64 v21; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v22; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v17 = 0;
  v16[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         a1,
         L"Protocol\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v16);
LABEL_4:
    v9 = v17;
    v17 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v7;
  }
  if ( !v16[0] )
  {
    v7 = -2140733422;
    v8 = 278;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v22 = (unsigned __int16 *)v19;
  v21 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, a2);
  if ( v7 < 0 )
  {
    v11 = 281;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 282;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Protocol\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 284;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v16);
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v18;
  v18 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = v17;
  v17 = 0;
  if ( v15 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800ba8c4  push    rbp
0x1800ba8c6  push    rbx
0x1800ba8c7  push    rsi
0x1800ba8c8  push    rdi
0x1800ba8c9  push    r14
0x1800ba8cb  push    r15
0x1800ba8cd  lea     rbp, [rsp-168h]
0x1800ba8d5  sub     rsp, 268h
0x1800ba8dc  mov     rax, cs:__security_cookie
0x1800ba8e3  xor     rax, rsp
0x1800ba8e6  mov     [rbp+190h+var_40], rax
0x1800ba8ed  mov     r14, rdx
0x1800ba8f0  mov     rsi, r9
0x1800ba8f3  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba8f6  lea     r9, [rsp+290h+var_270]; bool *
0x1800ba8fb  mov     rdi, r8
0x1800ba8fe  lea     rcx, [rsp+290h+var_268]; this
0x1800ba903  xor     r15d, r15d
0x1800ba906  lea     r8, aProtocolData; "Protocol\\Data"
0x1800ba90d  mov     [rsp+290h+var_268], r15
0x1800ba912  mov     [rsp+290h+var_270], r15b; int
0x1800ba917  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800ba91c  mov     ebx, eax
0x1800ba91e  test    eax, eax
0x1800ba920  jns     short loc_1800BA95F
0x1800ba922  mov     edx, 115h; void *
0x1800ba927  mov     rcx, [rbp+198h]; this
0x1800ba92e  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba935  mov     r9d, ebx; char *
0x1800ba938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba93d  mov     rcx, [rsp+290h+var_268]
0x1800ba942  mov     [rsp+290h+var_268], r15
0x1800ba947  test    rcx, rcx
0x1800ba94a  jz      short loc_1800BA958
0x1800ba94c  call    cs:__imp_SRCacheContext_Close
0x1800ba953  nop     dword ptr [rax+rax+00h]
0x1800ba958  mov     eax, ebx
0x1800ba95a  jmp     loc_1800BAA98
0x1800ba95f  cmp     [rsp+290h+var_270], r15b
0x1800ba964  jnz     short loc_1800BA972
0x1800ba966  mov     ebx, 80670012h
0x1800ba96b  mov     edx, 116h
0x1800ba970  jmp     short loc_1800BA927
0x1800ba972  xor     edx, edx; Val
0x1800ba974  mov     [rsp+290h+var_260], r15
0x1800ba979  mov     r8d, 200h; Size
0x1800ba97f  lea     rcx, [rsp+290h+var_258]; void *
0x1800ba984  call    memset_0
0x1800ba989  lea     rax, [rsp+290h+var_258]
0x1800ba98e  mov     [rbp+190h+var_58], r15
0x1800ba995  mov     rdx, r14; __int64
0x1800ba998  mov     [rbp+190h+var_48], rax
0x1800ba99f  lea     rcx, [rsp+290h+var_260]; this
0x1800ba9a4  mov     [rbp+190h+var_50], 100h
0x1800ba9af  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800ba9b4  mov     ebx, eax
0x1800ba9b6  test    eax, eax
0x1800ba9b8  jns     short loc_1800BA9F9
0x1800ba9ba  mov     edx, 119h; void *
0x1800ba9bf  mov     rcx, [rbp+198h]; this
0x1800ba9c6  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba9cd  mov     r9d, ebx; char *
0x1800ba9d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba9d5  mov     rcx, [rsp+290h+var_260]
0x1800ba9da  mov     [rsp+290h+var_260], r15
0x1800ba9df  test    rcx, rcx
0x1800ba9e2  jz      loc_1800BA93D
0x1800ba9e8  call    cs:__imp_SRCache_Free
0x1800ba9ef  nop     dword ptr [rax+rax+00h]
0x1800ba9f4  jmp     loc_1800BA93D
0x1800ba9f9  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800baa00  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800baa05  mov     r9, rsi; bool *
0x1800baa08  mov     rcx, rdi; this
0x1800baa0b  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800baa10  mov     ebx, eax
0x1800baa12  test    eax, eax
0x1800baa14  jns     short loc_1800BAA1D
0x1800baa16  mov     edx, 11Ah
0x1800baa1b  jmp     short loc_1800BA9BF
0x1800baa1d  mov     rcx, [rsp+290h+var_268]
0x1800baa22  lea     rdx, aProtocolData; "Protocol\\Data"
0x1800baa29  call    cs:__imp_SRCacheContext_AddToCache
0x1800baa30  nop     dword ptr [rax+rax+00h]
0x1800baa35  mov     ebx, eax
0x1800baa37  test    eax, eax
0x1800baa39  jns     short loc_1800BAA60
0x1800baa3b  mov     rcx, [rbp+198h]; this
0x1800baa42  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800baa49  mov     r9d, eax; char *
0x1800baa4c  mov     edx, 1A6h; void *
0x1800baa51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baa56  mov     edx, 11Ch
0x1800baa5b  jmp     loc_1800BA9BF
0x1800baa60  mov     rcx, [rsp+290h+var_260]
0x1800baa65  mov     [rsp+290h+var_260], r15
0x1800baa6a  test    rcx, rcx
0x1800baa6d  jz      short loc_1800BAA7B
0x1800baa6f  call    cs:__imp_SRCache_Free
0x1800baa76  nop     dword ptr [rax+rax+00h]
0x1800baa7b  mov     rcx, [rsp+290h+var_268]
0x1800baa80  mov     [rsp+290h+var_268], r15
0x1800baa85  test    rcx, rcx
0x1800baa88  jz      short loc_1800BAA96
0x1800baa8a  call    cs:__imp_SRCacheContext_Close
0x1800baa91  nop     dword ptr [rax+rax+00h]
0x1800baa96  xor     eax, eax
0x1800baa98  mov     rcx, [rbp+190h+var_40]
0x1800baa9f  xor     rcx, rsp; StackCookie
0x1800baaa2  call    __security_check_cookie
0x1800baaa7  add     rsp, 268h
0x1800baaae  pop     r15
0x1800baab0  pop     r14
0x1800baab2  pop     rdi
0x1800baab3  pop     rsi
0x1800baab4  pop     rbx
0x1800baab5  pop     rbp
0x1800baab6  retn
```
