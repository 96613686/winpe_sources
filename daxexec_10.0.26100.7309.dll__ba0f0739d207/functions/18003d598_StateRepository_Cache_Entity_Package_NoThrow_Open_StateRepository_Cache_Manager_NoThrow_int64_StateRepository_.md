# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003d598`
- end: `0x18003d78c`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003a704`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d598`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d620`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d75e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d620`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d75e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d6bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d743`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d6bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d743`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d6fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d6fd`

## string_xrefs

- `0x18003d716`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d602`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003d69a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
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
         L"Package\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 1182;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v8 = 1183;
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
    v11 = 1186;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 1187;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Package\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 1189;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
0x18003d598  push    rbp
0x18003d59a  push    rbx
0x18003d59b  push    rsi
0x18003d59c  push    rdi
0x18003d59d  push    r14
0x18003d59f  push    r15
0x18003d5a1  lea     rbp, [rsp-168h]
0x18003d5a9  sub     rsp, 268h
0x18003d5b0  mov     rax, cs:__security_cookie
0x18003d5b7  xor     rax, rsp
0x18003d5ba  mov     [rbp+190h+var_40], rax
0x18003d5c1  mov     r14, rdx
0x18003d5c4  mov     rsi, r9
0x18003d5c7  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003d5ca  lea     r9, [rsp+290h+var_270]; bool *
0x18003d5cf  mov     rdi, r8
0x18003d5d2  lea     rcx, [rsp+290h+var_268]; this
0x18003d5d7  xor     r15d, r15d
0x18003d5da  lea     r8, aPackageData; "Package\\Data"
0x18003d5e1  mov     [rsp+290h+var_268], r15
0x18003d5e6  mov     [rsp+290h+var_270], r15b; int
0x18003d5eb  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003d5f0  mov     ebx, eax
0x18003d5f2  test    eax, eax
0x18003d5f4  jns     short loc_18003D633
0x18003d5f6  mov     edx, 49Eh; void *
0x18003d5fb  mov     rcx, [rbp+198h]; this
0x18003d602  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d609  mov     r9d, ebx; char *
0x18003d60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d611  mov     rcx, [rsp+290h+var_268]
0x18003d616  mov     [rsp+290h+var_268], r15
0x18003d61b  test    rcx, rcx
0x18003d61e  jz      short loc_18003D62C
0x18003d620  call    cs:__imp_SRCacheContext_Close
0x18003d627  nop     dword ptr [rax+rax+00h]
0x18003d62c  mov     eax, ebx
0x18003d62e  jmp     loc_18003D76C
0x18003d633  cmp     [rsp+290h+var_270], r15b
0x18003d638  jnz     short loc_18003D646
0x18003d63a  mov     ebx, 80670012h
0x18003d63f  mov     edx, 49Fh
0x18003d644  jmp     short loc_18003D5FB
0x18003d646  xor     edx, edx; Val
0x18003d648  mov     [rsp+290h+var_260], r15
0x18003d64d  mov     r8d, 200h; Size
0x18003d653  lea     rcx, [rsp+290h+var_258]; void *
0x18003d658  call    memset_0
0x18003d65d  lea     rax, [rsp+290h+var_258]
0x18003d662  mov     [rbp+190h+var_58], r15
0x18003d669  mov     rdx, r14; __int64
0x18003d66c  mov     [rbp+190h+var_48], rax
0x18003d673  lea     rcx, [rsp+290h+var_260]; this
0x18003d678  mov     [rbp+190h+var_50], 100h
0x18003d683  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003d688  mov     ebx, eax
0x18003d68a  test    eax, eax
0x18003d68c  jns     short loc_18003D6CD
0x18003d68e  mov     edx, 4A2h; void *
0x18003d693  mov     rcx, [rbp+198h]; this
0x18003d69a  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d6a1  mov     r9d, ebx; char *
0x18003d6a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d6a9  mov     rcx, [rsp+290h+var_260]
0x18003d6ae  mov     [rsp+290h+var_260], r15
0x18003d6b3  test    rcx, rcx
0x18003d6b6  jz      loc_18003D611
0x18003d6bc  call    cs:__imp_SRCache_Free
0x18003d6c3  nop     dword ptr [rax+rax+00h]
0x18003d6c8  jmp     loc_18003D611
0x18003d6cd  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003d6d4  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003d6d9  mov     r9, rsi; bool *
0x18003d6dc  mov     rcx, rdi; this
0x18003d6df  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003d6e4  mov     ebx, eax
0x18003d6e6  test    eax, eax
0x18003d6e8  jns     short loc_18003D6F1
0x18003d6ea  mov     edx, 4A3h
0x18003d6ef  jmp     short loc_18003D693
0x18003d6f1  mov     rcx, [rsp+290h+var_268]
0x18003d6f6  lea     rdx, aPackageData; "Package\\Data"
0x18003d6fd  call    cs:__imp_SRCacheContext_AddToCache
0x18003d704  nop     dword ptr [rax+rax+00h]
0x18003d709  mov     ebx, eax
0x18003d70b  test    eax, eax
0x18003d70d  jns     short loc_18003D734
0x18003d70f  mov     rcx, [rbp+198h]; this
0x18003d716  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d71d  mov     r9d, eax; char *
0x18003d720  mov     edx, 1A6h; void *
0x18003d725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d72a  mov     edx, 4A5h
0x18003d72f  jmp     loc_18003D693
0x18003d734  mov     rcx, [rsp+290h+var_260]
0x18003d739  mov     [rsp+290h+var_260], r15
0x18003d73e  test    rcx, rcx
0x18003d741  jz      short loc_18003D74F
0x18003d743  call    cs:__imp_SRCache_Free
0x18003d74a  nop     dword ptr [rax+rax+00h]
0x18003d74f  mov     rcx, [rsp+290h+var_268]
0x18003d754  mov     [rsp+290h+var_268], r15
0x18003d759  test    rcx, rcx
0x18003d75c  jz      short loc_18003D76A
0x18003d75e  call    cs:__imp_SRCacheContext_Close
0x18003d765  nop     dword ptr [rax+rax+00h]
0x18003d76a  xor     eax, eax
0x18003d76c  mov     rcx, [rbp+190h+var_40]
0x18003d773  xor     rcx, rsp; StackCookie
0x18003d776  call    __security_check_cookie
0x18003d77b  add     rsp, 268h
0x18003d782  pop     r15
0x18003d784  pop     r14
0x18003d786  pop     rdi
0x18003d787  pop     rsi
0x18003d788  pop     rbx
0x18003d789  pop     rbp
0x18003d78a  retn
```
