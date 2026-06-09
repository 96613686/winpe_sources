# StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ba2d0`
- end: `0x1800ba4c4`
- name: `?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b76c0`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x1800ba2d0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba358`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba496`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba358`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba496`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba3f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba47b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba3f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba47b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba435`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba435`

## string_xrefs

- `0x1800ba44e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ba312`: `AppExtension\Data`
- `0x1800ba42e`: `AppExtension\Data`
- `0x1800ba33a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800ba3d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::Open(
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
         L"AppExtension\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
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
    v8 = 312;
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
    v11 = 315;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 316;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"AppExtension\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 318;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
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
0x1800ba2d0  push    rbp
0x1800ba2d2  push    rbx
0x1800ba2d3  push    rsi
0x1800ba2d4  push    rdi
0x1800ba2d5  push    r14
0x1800ba2d7  push    r15
0x1800ba2d9  lea     rbp, [rsp-168h]
0x1800ba2e1  sub     rsp, 268h
0x1800ba2e8  mov     rax, cs:__security_cookie
0x1800ba2ef  xor     rax, rsp
0x1800ba2f2  mov     [rbp+190h+var_40], rax
0x1800ba2f9  mov     r14, rdx
0x1800ba2fc  mov     rsi, r9
0x1800ba2ff  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba302  lea     r9, [rsp+290h+var_270]; bool *
0x1800ba307  mov     rdi, r8
0x1800ba30a  lea     rcx, [rsp+290h+var_268]; this
0x1800ba30f  xor     r15d, r15d
0x1800ba312  lea     r8, aAppextensionDa; "AppExtension\\Data"
0x1800ba319  mov     [rsp+290h+var_268], r15
0x1800ba31e  mov     [rsp+290h+var_270], r15b; int
0x1800ba323  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800ba328  mov     ebx, eax
0x1800ba32a  test    eax, eax
0x1800ba32c  jns     short loc_1800BA36B
0x1800ba32e  mov     edx, 137h; void *
0x1800ba333  mov     rcx, [rbp+198h]; this
0x1800ba33a  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba341  mov     r9d, ebx; char *
0x1800ba344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba349  mov     rcx, [rsp+290h+var_268]
0x1800ba34e  mov     [rsp+290h+var_268], r15
0x1800ba353  test    rcx, rcx
0x1800ba356  jz      short loc_1800BA364
0x1800ba358  call    cs:__imp_SRCacheContext_Close
0x1800ba35f  nop     dword ptr [rax+rax+00h]
0x1800ba364  mov     eax, ebx
0x1800ba366  jmp     loc_1800BA4A4
0x1800ba36b  cmp     [rsp+290h+var_270], r15b
0x1800ba370  jnz     short loc_1800BA37E
0x1800ba372  mov     ebx, 80670012h
0x1800ba377  mov     edx, 138h
0x1800ba37c  jmp     short loc_1800BA333
0x1800ba37e  xor     edx, edx; Val
0x1800ba380  mov     [rsp+290h+var_260], r15
0x1800ba385  mov     r8d, 200h; Size
0x1800ba38b  lea     rcx, [rsp+290h+var_258]; void *
0x1800ba390  call    memset_0
0x1800ba395  lea     rax, [rsp+290h+var_258]
0x1800ba39a  mov     [rbp+190h+var_58], r15
0x1800ba3a1  mov     rdx, r14; __int64
0x1800ba3a4  mov     [rbp+190h+var_48], rax
0x1800ba3ab  lea     rcx, [rsp+290h+var_260]; this
0x1800ba3b0  mov     [rbp+190h+var_50], 100h
0x1800ba3bb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800ba3c0  mov     ebx, eax
0x1800ba3c2  test    eax, eax
0x1800ba3c4  jns     short loc_1800BA405
0x1800ba3c6  mov     edx, 13Bh; void *
0x1800ba3cb  mov     rcx, [rbp+198h]; this
0x1800ba3d2  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba3d9  mov     r9d, ebx; char *
0x1800ba3dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba3e1  mov     rcx, [rsp+290h+var_260]
0x1800ba3e6  mov     [rsp+290h+var_260], r15
0x1800ba3eb  test    rcx, rcx
0x1800ba3ee  jz      loc_1800BA349
0x1800ba3f4  call    cs:__imp_SRCache_Free
0x1800ba3fb  nop     dword ptr [rax+rax+00h]
0x1800ba400  jmp     loc_1800BA349
0x1800ba405  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800ba40c  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800ba411  mov     r9, rsi; bool *
0x1800ba414  mov     rcx, rdi; this
0x1800ba417  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800ba41c  mov     ebx, eax
0x1800ba41e  test    eax, eax
0x1800ba420  jns     short loc_1800BA429
0x1800ba422  mov     edx, 13Ch
0x1800ba427  jmp     short loc_1800BA3CB
0x1800ba429  mov     rcx, [rsp+290h+var_268]
0x1800ba42e  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x1800ba435  call    cs:__imp_SRCacheContext_AddToCache
0x1800ba43c  nop     dword ptr [rax+rax+00h]
0x1800ba441  mov     ebx, eax
0x1800ba443  test    eax, eax
0x1800ba445  jns     short loc_1800BA46C
0x1800ba447  mov     rcx, [rbp+198h]; this
0x1800ba44e  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba455  mov     r9d, eax; char *
0x1800ba458  mov     edx, 1A6h; void *
0x1800ba45d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba462  mov     edx, 13Eh
0x1800ba467  jmp     loc_1800BA3CB
0x1800ba46c  mov     rcx, [rsp+290h+var_260]
0x1800ba471  mov     [rsp+290h+var_260], r15
0x1800ba476  test    rcx, rcx
0x1800ba479  jz      short loc_1800BA487
0x1800ba47b  call    cs:__imp_SRCache_Free
0x1800ba482  nop     dword ptr [rax+rax+00h]
0x1800ba487  mov     rcx, [rsp+290h+var_268]
0x1800ba48c  mov     [rsp+290h+var_268], r15
0x1800ba491  test    rcx, rcx
0x1800ba494  jz      short loc_1800BA4A2
0x1800ba496  call    cs:__imp_SRCacheContext_Close
0x1800ba49d  nop     dword ptr [rax+rax+00h]
0x1800ba4a2  xor     eax, eax
0x1800ba4a4  mov     rcx, [rbp+190h+var_40]
0x1800ba4ab  xor     rcx, rsp; StackCookie
0x1800ba4ae  call    __security_check_cookie
0x1800ba4b3  add     rsp, 268h
0x1800ba4ba  pop     r15
0x1800ba4bc  pop     r14
0x1800ba4be  pop     rdi
0x1800ba4bf  pop     rsi
0x1800ba4c0  pop     rbx
0x1800ba4c1  pop     rbp
0x1800ba4c2  retn
```
