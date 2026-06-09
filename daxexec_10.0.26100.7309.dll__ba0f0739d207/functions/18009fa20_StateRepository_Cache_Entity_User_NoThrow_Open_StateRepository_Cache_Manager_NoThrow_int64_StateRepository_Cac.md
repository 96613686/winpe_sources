# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18009fa20`
- end: `0x18009fd06`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `742`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18009efbc`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x18009fa20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009faa9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009faf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fb92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fc08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fc9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fcd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009faa9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009faf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fb92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fc08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fc9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fcd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fb76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fbec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fc7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fcbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fb76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fbec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fc7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009fcbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009fc26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009fc26`

## string_xrefs

- `0x18009fc42`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009fa88`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009fad3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009fb55`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009fbcb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009fc5d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *this,
        bool *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  bool v23[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+238h] [rbp+138h]
  __int64 v28; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v29; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v24 = 0;
  v23[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         a1,
         L"User\\Data",
         v23);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v23);
    v9 = v24;
    v24 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return v8;
  }
  if ( !v23[0] )
  {
    v8 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)0x80670012LL,
      *(int *)v23);
    v11 = v24;
    v24 = 0;
    if ( v11 )
      SRCacheContext_Close();
    return v8;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v28 = 256;
  v29 = (unsigned __int16 *)v26;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v12,
      *(int *)v23);
    v13 = v25;
    v25 = 0;
    if ( v13 )
      SRCache_Free();
    v14 = v24;
    v24 = 0;
    if ( v14 )
      SRCacheContext_Close();
    return v8;
  }
  v15 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
          this,
          (struct StateRepository::Cache::Context_NoThrow *)&v24,
          v29,
          a4);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v15,
      *(int *)v23);
    v16 = v25;
    v25 = 0;
    if ( v16 )
      SRCache_Free();
    v17 = v24;
    v24 = 0;
    if ( v17 )
      SRCacheContext_Close();
    return v8;
  }
  v18 = SRCacheContext_AddToCache(v24, L"User\\Data");
  v8 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v18,
      *(int *)v23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v8,
      *(int *)v23);
    v19 = v25;
    v25 = 0;
    if ( v19 )
      SRCache_Free();
    v20 = v24;
    v24 = 0;
    if ( v20 )
      SRCacheContext_Close();
    return v8;
  }
  v21 = v25;
  v25 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = v24;
  v24 = 0;
  if ( v22 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18009fa20  push    rbp
0x18009fa22  push    rbx
0x18009fa23  push    rsi
0x18009fa24  push    rdi
0x18009fa25  push    r14
0x18009fa27  push    r15
0x18009fa29  lea     rbp, [rsp-168h]
0x18009fa31  sub     rsp, 268h
0x18009fa38  mov     rax, cs:__security_cookie
0x18009fa3f  xor     rax, rsp
0x18009fa42  mov     [rbp+190h+var_40], rax
0x18009fa49  mov     rsi, r9
0x18009fa4c  mov     rdi, r8
0x18009fa4f  mov     r14, rdx
0x18009fa52  xor     r15d, r15d
0x18009fa55  mov     [rsp+290h+var_268], r15
0x18009fa5a  mov     [rsp+290h+var_270], r15b; int
0x18009fa5f  lea     r9, [rsp+290h+var_270]; bool *
0x18009fa64  lea     r8, aUserData; "User\\Data"
0x18009fa6b  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18009fa6e  lea     rcx, [rsp+290h+var_268]; this
0x18009fa73  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18009fa78  mov     ebx, eax
0x18009fa7a  test    eax, eax
0x18009fa7c  jns     short loc_18009FABD
0x18009fa7e  mov     rcx, [rbp+198h]; this
0x18009fa85  mov     r9d, eax; char *
0x18009fa88  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fa8f  mov     edx, 10Bh; void *
0x18009fa94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fa99  nop
0x18009fa9a  mov     rcx, [rsp+290h+var_268]
0x18009fa9f  mov     [rsp+290h+var_268], r15
0x18009faa4  test    rcx, rcx
0x18009faa7  jz      short loc_18009FAB6
0x18009faa9  call    cs:__imp_SRCacheContext_Close
0x18009fab0  nop     dword ptr [rax+rax+00h]
0x18009fab5  nop
0x18009fab6  mov     eax, ebx
0x18009fab8  jmp     loc_18009FCE6
0x18009fabd  cmp     [rsp+290h+var_270], r15b
0x18009fac2  jnz     short loc_18009FB03
0x18009fac4  mov     rcx, [rbp+198h]; this
0x18009facb  mov     ebx, 80670012h
0x18009fad0  mov     r9d, ebx; char *
0x18009fad3  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fada  mov     edx, 10Ch; void *
0x18009fadf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fae4  nop
0x18009fae5  mov     rcx, [rsp+290h+var_268]
0x18009faea  mov     [rsp+290h+var_268], r15
0x18009faef  test    rcx, rcx
0x18009faf2  jz      short loc_18009FB01
0x18009faf4  call    cs:__imp_SRCacheContext_Close
0x18009fafb  nop     dword ptr [rax+rax+00h]
0x18009fb00  nop
0x18009fb01  jmp     short loc_18009FAB6
0x18009fb03  mov     [rsp+290h+var_260], r15
0x18009fb08  xor     edx, edx; Val
0x18009fb0a  mov     r8d, 200h; Size
0x18009fb10  lea     rcx, [rsp+290h+var_258]; void *
0x18009fb15  call    memset_0
0x18009fb1a  mov     [rbp+190h+var_58], r15
0x18009fb21  mov     [rbp+190h+var_50], 100h
0x18009fb2c  lea     rax, [rsp+290h+var_258]
0x18009fb31  mov     [rbp+190h+var_48], rax
0x18009fb38  mov     rdx, r14; __int64
0x18009fb3b  lea     rcx, [rsp+290h+var_260]; this
0x18009fb40  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18009fb45  mov     ebx, eax
0x18009fb47  test    eax, eax
0x18009fb49  jns     short loc_18009FBA4
0x18009fb4b  mov     rcx, [rbp+198h]; this
0x18009fb52  mov     r9d, eax; char *
0x18009fb55  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fb5c  mov     edx, 10Fh; void *
0x18009fb61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fb66  nop
0x18009fb67  mov     rcx, [rsp+290h+var_260]
0x18009fb6c  mov     [rsp+290h+var_260], r15
0x18009fb71  test    rcx, rcx
0x18009fb74  jz      short loc_18009FB83
0x18009fb76  call    cs:__imp_SRCache_Free
0x18009fb7d  nop     dword ptr [rax+rax+00h]
0x18009fb82  nop
0x18009fb83  mov     rcx, [rsp+290h+var_268]
0x18009fb88  mov     [rsp+290h+var_268], r15
0x18009fb8d  test    rcx, rcx
0x18009fb90  jz      short loc_18009FB9F
0x18009fb92  call    cs:__imp_SRCacheContext_Close
0x18009fb99  nop     dword ptr [rax+rax+00h]
0x18009fb9e  nop
0x18009fb9f  jmp     loc_18009FAB6
0x18009fba4  mov     r9, rsi; bool *
0x18009fba7  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18009fbae  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18009fbb3  mov     rcx, rdi; this
0x18009fbb6  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18009fbbb  mov     ebx, eax
0x18009fbbd  test    eax, eax
0x18009fbbf  jns     short loc_18009FC1A
0x18009fbc1  mov     rcx, [rbp+198h]; this
0x18009fbc8  mov     r9d, eax; char *
0x18009fbcb  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fbd2  mov     edx, 110h; void *
0x18009fbd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fbdc  nop
0x18009fbdd  mov     rcx, [rsp+290h+var_260]
0x18009fbe2  mov     [rsp+290h+var_260], r15
0x18009fbe7  test    rcx, rcx
0x18009fbea  jz      short loc_18009FBF9
0x18009fbec  call    cs:__imp_SRCache_Free
0x18009fbf3  nop     dword ptr [rax+rax+00h]
0x18009fbf8  nop
0x18009fbf9  mov     rcx, [rsp+290h+var_268]
0x18009fbfe  mov     [rsp+290h+var_268], r15
0x18009fc03  test    rcx, rcx
0x18009fc06  jz      short loc_18009FC15
0x18009fc08  call    cs:__imp_SRCacheContext_Close
0x18009fc0f  nop     dword ptr [rax+rax+00h]
0x18009fc14  nop
0x18009fc15  jmp     loc_18009FAB6
0x18009fc1a  lea     rdx, aUserData; "User\\Data"
0x18009fc21  mov     rcx, [rsp+290h+var_268]
0x18009fc26  call    cs:__imp_SRCacheContext_AddToCache
0x18009fc2d  nop     dword ptr [rax+rax+00h]
0x18009fc32  mov     ebx, eax
0x18009fc34  test    eax, eax
0x18009fc36  jns     short loc_18009FCAC
0x18009fc38  mov     rcx, [rbp+198h]; this
0x18009fc3f  mov     r9d, eax; char *
0x18009fc42  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fc49  mov     edx, 1A6h; void *
0x18009fc4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fc53  mov     rcx, [rbp+198h]; this
0x18009fc5a  mov     r9d, ebx; char *
0x18009fc5d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fc64  mov     edx, 112h; void *
0x18009fc69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fc6e  nop
0x18009fc6f  mov     rcx, [rsp+290h+var_260]
0x18009fc74  mov     [rsp+290h+var_260], r15
0x18009fc79  test    rcx, rcx
0x18009fc7c  jz      short loc_18009FC8B
0x18009fc7e  call    cs:__imp_SRCache_Free
0x18009fc85  nop     dword ptr [rax+rax+00h]
0x18009fc8a  nop
0x18009fc8b  mov     rcx, [rsp+290h+var_268]
0x18009fc90  mov     [rsp+290h+var_268], r15
0x18009fc95  test    rcx, rcx
0x18009fc98  jz      short loc_18009FCA7
0x18009fc9a  call    cs:__imp_SRCacheContext_Close
0x18009fca1  nop     dword ptr [rax+rax+00h]
0x18009fca6  nop
0x18009fca7  jmp     loc_18009FAB6
0x18009fcac  mov     rcx, [rsp+290h+var_260]
0x18009fcb1  mov     [rsp+290h+var_260], r15
0x18009fcb6  test    rcx, rcx
0x18009fcb9  jz      short loc_18009FCC8
0x18009fcbb  call    cs:__imp_SRCache_Free
0x18009fcc2  nop     dword ptr [rax+rax+00h]
0x18009fcc7  nop
0x18009fcc8  mov     rcx, [rsp+290h+var_268]
0x18009fccd  mov     [rsp+290h+var_268], r15
0x18009fcd2  test    rcx, rcx
0x18009fcd5  jz      short loc_18009FCE4
0x18009fcd7  call    cs:__imp_SRCacheContext_Close
0x18009fcde  nop     dword ptr [rax+rax+00h]
0x18009fce3  nop
0x18009fce4  xor     eax, eax
0x18009fce6  mov     rcx, [rbp+190h+var_40]
0x18009fced  xor     rcx, rsp; StackCookie
0x18009fcf0  call    __security_check_cookie
0x18009fcf5  add     rsp, 268h
0x18009fcfc  pop     r15
0x18009fcfe  pop     r14
0x18009fd00  pop     rdi
0x18009fd01  pop     rsi
0x18009fd02  pop     rbx
0x18009fd03  pop     rbp
0x18009fd04  retn
```
