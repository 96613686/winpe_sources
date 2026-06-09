# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003d068`
- end: `0x18003d25c`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003a600`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d068`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d0f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d22e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d0f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d22e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d18c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d213`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d18c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d213`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d1cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d1cd`

## string_xrefs

- `0x18003d1e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d0d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18003d16a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
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
         L"Application\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 433;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
    v8 = 434;
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
    v11 = 437;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 438;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Application\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 440;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
0x18003d068  push    rbp
0x18003d06a  push    rbx
0x18003d06b  push    rsi
0x18003d06c  push    rdi
0x18003d06d  push    r14
0x18003d06f  push    r15
0x18003d071  lea     rbp, [rsp-168h]
0x18003d079  sub     rsp, 268h
0x18003d080  mov     rax, cs:__security_cookie
0x18003d087  xor     rax, rsp
0x18003d08a  mov     [rbp+190h+var_40], rax
0x18003d091  mov     r14, rdx
0x18003d094  mov     rsi, r9
0x18003d097  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003d09a  lea     r9, [rsp+290h+var_270]; bool *
0x18003d09f  mov     rdi, r8
0x18003d0a2  lea     rcx, [rsp+290h+var_268]; this
0x18003d0a7  xor     r15d, r15d
0x18003d0aa  lea     r8, aApplicationDat; "Application\\Data"
0x18003d0b1  mov     [rsp+290h+var_268], r15
0x18003d0b6  mov     [rsp+290h+var_270], r15b; int
0x18003d0bb  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003d0c0  mov     ebx, eax
0x18003d0c2  test    eax, eax
0x18003d0c4  jns     short loc_18003D103
0x18003d0c6  mov     edx, 1B1h; void *
0x18003d0cb  mov     rcx, [rbp+198h]; this
0x18003d0d2  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d0d9  mov     r9d, ebx; char *
0x18003d0dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d0e1  mov     rcx, [rsp+290h+var_268]
0x18003d0e6  mov     [rsp+290h+var_268], r15
0x18003d0eb  test    rcx, rcx
0x18003d0ee  jz      short loc_18003D0FC
0x18003d0f0  call    cs:__imp_SRCacheContext_Close
0x18003d0f7  nop     dword ptr [rax+rax+00h]
0x18003d0fc  mov     eax, ebx
0x18003d0fe  jmp     loc_18003D23C
0x18003d103  cmp     [rsp+290h+var_270], r15b
0x18003d108  jnz     short loc_18003D116
0x18003d10a  mov     ebx, 80670012h
0x18003d10f  mov     edx, 1B2h
0x18003d114  jmp     short loc_18003D0CB
0x18003d116  xor     edx, edx; Val
0x18003d118  mov     [rsp+290h+var_260], r15
0x18003d11d  mov     r8d, 200h; Size
0x18003d123  lea     rcx, [rsp+290h+var_258]; void *
0x18003d128  call    memset_0
0x18003d12d  lea     rax, [rsp+290h+var_258]
0x18003d132  mov     [rbp+190h+var_58], r15
0x18003d139  mov     rdx, r14; __int64
0x18003d13c  mov     [rbp+190h+var_48], rax
0x18003d143  lea     rcx, [rsp+290h+var_260]; this
0x18003d148  mov     [rbp+190h+var_50], 100h
0x18003d153  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003d158  mov     ebx, eax
0x18003d15a  test    eax, eax
0x18003d15c  jns     short loc_18003D19D
0x18003d15e  mov     edx, 1B5h; void *
0x18003d163  mov     rcx, [rbp+198h]; this
0x18003d16a  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d171  mov     r9d, ebx; char *
0x18003d174  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d179  mov     rcx, [rsp+290h+var_260]
0x18003d17e  mov     [rsp+290h+var_260], r15
0x18003d183  test    rcx, rcx
0x18003d186  jz      loc_18003D0E1
0x18003d18c  call    cs:__imp_SRCache_Free
0x18003d193  nop     dword ptr [rax+rax+00h]
0x18003d198  jmp     loc_18003D0E1
0x18003d19d  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003d1a4  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003d1a9  mov     r9, rsi; bool *
0x18003d1ac  mov     rcx, rdi; this
0x18003d1af  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003d1b4  mov     ebx, eax
0x18003d1b6  test    eax, eax
0x18003d1b8  jns     short loc_18003D1C1
0x18003d1ba  mov     edx, 1B6h
0x18003d1bf  jmp     short loc_18003D163
0x18003d1c1  mov     rcx, [rsp+290h+var_268]
0x18003d1c6  lea     rdx, aApplicationDat; "Application\\Data"
0x18003d1cd  call    cs:__imp_SRCacheContext_AddToCache
0x18003d1d4  nop     dword ptr [rax+rax+00h]
0x18003d1d9  mov     ebx, eax
0x18003d1db  test    eax, eax
0x18003d1dd  jns     short loc_18003D204
0x18003d1df  mov     rcx, [rbp+198h]; this
0x18003d1e6  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d1ed  mov     r9d, eax; char *
0x18003d1f0  mov     edx, 1A6h; void *
0x18003d1f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d1fa  mov     edx, 1B8h
0x18003d1ff  jmp     loc_18003D163
0x18003d204  mov     rcx, [rsp+290h+var_260]
0x18003d209  mov     [rsp+290h+var_260], r15
0x18003d20e  test    rcx, rcx
0x18003d211  jz      short loc_18003D21F
0x18003d213  call    cs:__imp_SRCache_Free
0x18003d21a  nop     dword ptr [rax+rax+00h]
0x18003d21f  mov     rcx, [rsp+290h+var_268]
0x18003d224  mov     [rsp+290h+var_268], r15
0x18003d229  test    rcx, rcx
0x18003d22c  jz      short loc_18003D23A
0x18003d22e  call    cs:__imp_SRCacheContext_Close
0x18003d235  nop     dword ptr [rax+rax+00h]
0x18003d23a  xor     eax, eax
0x18003d23c  mov     rcx, [rbp+190h+var_40]
0x18003d243  xor     rcx, rsp; StackCookie
0x18003d246  call    __security_check_cookie
0x18003d24b  add     rsp, 268h
0x18003d252  pop     r15
0x18003d254  pop     r14
0x18003d256  pop     rdi
0x18003d257  pop     rsi
0x18003d258  pop     rbx
0x18003d259  pop     rbp
0x18003d25a  retn
```
