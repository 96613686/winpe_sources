# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ba0d4`
- end: `0x1800ba2c8`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b3a1c`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x1800ba0d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba15c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba29a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba15c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba29a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba1f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba27f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba1f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba27f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba239`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba239`

## string_xrefs

- `0x1800ba252`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ba13e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800ba1d6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
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
         L"Activation\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
    v8 = 392;
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
    v11 = 395;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 396;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Activation\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 398;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
0x1800ba0d4  push    rbp
0x1800ba0d6  push    rbx
0x1800ba0d7  push    rsi
0x1800ba0d8  push    rdi
0x1800ba0d9  push    r14
0x1800ba0db  push    r15
0x1800ba0dd  lea     rbp, [rsp-168h]
0x1800ba0e5  sub     rsp, 268h
0x1800ba0ec  mov     rax, cs:__security_cookie
0x1800ba0f3  xor     rax, rsp
0x1800ba0f6  mov     [rbp+190h+var_40], rax
0x1800ba0fd  mov     r14, rdx
0x1800ba100  mov     rsi, r9
0x1800ba103  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba106  lea     r9, [rsp+290h+var_270]; bool *
0x1800ba10b  mov     rdi, r8
0x1800ba10e  lea     rcx, [rsp+290h+var_268]; this
0x1800ba113  xor     r15d, r15d
0x1800ba116  lea     r8, aActivationData; "Activation\\Data"
0x1800ba11d  mov     [rsp+290h+var_268], r15
0x1800ba122  mov     [rsp+290h+var_270], r15b; int
0x1800ba127  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800ba12c  mov     ebx, eax
0x1800ba12e  test    eax, eax
0x1800ba130  jns     short loc_1800BA16F
0x1800ba132  mov     edx, 187h; void *
0x1800ba137  mov     rcx, [rbp+198h]; this
0x1800ba13e  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba145  mov     r9d, ebx; char *
0x1800ba148  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba14d  mov     rcx, [rsp+290h+var_268]
0x1800ba152  mov     [rsp+290h+var_268], r15
0x1800ba157  test    rcx, rcx
0x1800ba15a  jz      short loc_1800BA168
0x1800ba15c  call    cs:__imp_SRCacheContext_Close
0x1800ba163  nop     dword ptr [rax+rax+00h]
0x1800ba168  mov     eax, ebx
0x1800ba16a  jmp     loc_1800BA2A8
0x1800ba16f  cmp     [rsp+290h+var_270], r15b
0x1800ba174  jnz     short loc_1800BA182
0x1800ba176  mov     ebx, 80670012h
0x1800ba17b  mov     edx, 188h
0x1800ba180  jmp     short loc_1800BA137
0x1800ba182  xor     edx, edx; Val
0x1800ba184  mov     [rsp+290h+var_260], r15
0x1800ba189  mov     r8d, 200h; Size
0x1800ba18f  lea     rcx, [rsp+290h+var_258]; void *
0x1800ba194  call    memset_0
0x1800ba199  lea     rax, [rsp+290h+var_258]
0x1800ba19e  mov     [rbp+190h+var_58], r15
0x1800ba1a5  mov     rdx, r14; __int64
0x1800ba1a8  mov     [rbp+190h+var_48], rax
0x1800ba1af  lea     rcx, [rsp+290h+var_260]; this
0x1800ba1b4  mov     [rbp+190h+var_50], 100h
0x1800ba1bf  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800ba1c4  mov     ebx, eax
0x1800ba1c6  test    eax, eax
0x1800ba1c8  jns     short loc_1800BA209
0x1800ba1ca  mov     edx, 18Bh; void *
0x1800ba1cf  mov     rcx, [rbp+198h]; this
0x1800ba1d6  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba1dd  mov     r9d, ebx; char *
0x1800ba1e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba1e5  mov     rcx, [rsp+290h+var_260]
0x1800ba1ea  mov     [rsp+290h+var_260], r15
0x1800ba1ef  test    rcx, rcx
0x1800ba1f2  jz      loc_1800BA14D
0x1800ba1f8  call    cs:__imp_SRCache_Free
0x1800ba1ff  nop     dword ptr [rax+rax+00h]
0x1800ba204  jmp     loc_1800BA14D
0x1800ba209  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800ba210  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800ba215  mov     r9, rsi; bool *
0x1800ba218  mov     rcx, rdi; this
0x1800ba21b  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800ba220  mov     ebx, eax
0x1800ba222  test    eax, eax
0x1800ba224  jns     short loc_1800BA22D
0x1800ba226  mov     edx, 18Ch
0x1800ba22b  jmp     short loc_1800BA1CF
0x1800ba22d  mov     rcx, [rsp+290h+var_268]
0x1800ba232  lea     rdx, aActivationData; "Activation\\Data"
0x1800ba239  call    cs:__imp_SRCacheContext_AddToCache
0x1800ba240  nop     dword ptr [rax+rax+00h]
0x1800ba245  mov     ebx, eax
0x1800ba247  test    eax, eax
0x1800ba249  jns     short loc_1800BA270
0x1800ba24b  mov     rcx, [rbp+198h]; this
0x1800ba252  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba259  mov     r9d, eax; char *
0x1800ba25c  mov     edx, 1A6h; void *
0x1800ba261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba266  mov     edx, 18Eh
0x1800ba26b  jmp     loc_1800BA1CF
0x1800ba270  mov     rcx, [rsp+290h+var_260]
0x1800ba275  mov     [rsp+290h+var_260], r15
0x1800ba27a  test    rcx, rcx
0x1800ba27d  jz      short loc_1800BA28B
0x1800ba27f  call    cs:__imp_SRCache_Free
0x1800ba286  nop     dword ptr [rax+rax+00h]
0x1800ba28b  mov     rcx, [rsp+290h+var_268]
0x1800ba290  mov     [rsp+290h+var_268], r15
0x1800ba295  test    rcx, rcx
0x1800ba298  jz      short loc_1800BA2A6
0x1800ba29a  call    cs:__imp_SRCacheContext_Close
0x1800ba2a1  nop     dword ptr [rax+rax+00h]
0x1800ba2a6  xor     eax, eax
0x1800ba2a8  mov     rcx, [rbp+190h+var_40]
0x1800ba2af  xor     rcx, rsp; StackCookie
0x1800ba2b2  call    __security_check_cookie
0x1800ba2b7  add     rsp, 268h
0x1800ba2be  pop     r15
0x1800ba2c0  pop     r14
0x1800ba2c2  pop     rdi
0x1800ba2c3  pop     rsi
0x1800ba2c4  pop     rbx
0x1800ba2c5  pop     rbp
0x1800ba2c6  retn
```
