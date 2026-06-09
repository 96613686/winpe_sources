# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003d39c`
- end: `0x18003d590`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003b6a0`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d39c`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d424`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d562`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d424`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d562`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d4c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d547`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d4c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d547`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d501`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d501`

## string_xrefs

- `0x18003d51a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d406`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003d49e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
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
         L"PackageExternalLocation\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v8 = 251;
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
    v11 = 254;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 255;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"PackageExternalLocation\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 257;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x18003d39c  push    rbp
0x18003d39e  push    rbx
0x18003d39f  push    rsi
0x18003d3a0  push    rdi
0x18003d3a1  push    r14
0x18003d3a3  push    r15
0x18003d3a5  lea     rbp, [rsp-168h]
0x18003d3ad  sub     rsp, 268h
0x18003d3b4  mov     rax, cs:__security_cookie
0x18003d3bb  xor     rax, rsp
0x18003d3be  mov     [rbp+190h+var_40], rax
0x18003d3c5  mov     r14, rdx
0x18003d3c8  mov     rsi, r9
0x18003d3cb  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003d3ce  lea     r9, [rsp+290h+var_270]; bool *
0x18003d3d3  mov     rdi, r8
0x18003d3d6  lea     rcx, [rsp+290h+var_268]; this
0x18003d3db  xor     r15d, r15d
0x18003d3de  lea     r8, aPackageexterna; "PackageExternalLocation\\Data"
0x18003d3e5  mov     [rsp+290h+var_268], r15
0x18003d3ea  mov     [rsp+290h+var_270], r15b; int
0x18003d3ef  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003d3f4  mov     ebx, eax
0x18003d3f6  test    eax, eax
0x18003d3f8  jns     short loc_18003D437
0x18003d3fa  mov     edx, 0FAh; void *
0x18003d3ff  mov     rcx, [rbp+198h]; this
0x18003d406  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d40d  mov     r9d, ebx; char *
0x18003d410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d415  mov     rcx, [rsp+290h+var_268]
0x18003d41a  mov     [rsp+290h+var_268], r15
0x18003d41f  test    rcx, rcx
0x18003d422  jz      short loc_18003D430
0x18003d424  call    cs:__imp_SRCacheContext_Close
0x18003d42b  nop     dword ptr [rax+rax+00h]
0x18003d430  mov     eax, ebx
0x18003d432  jmp     loc_18003D570
0x18003d437  cmp     [rsp+290h+var_270], r15b
0x18003d43c  jnz     short loc_18003D44A
0x18003d43e  mov     ebx, 80670012h
0x18003d443  mov     edx, 0FBh
0x18003d448  jmp     short loc_18003D3FF
0x18003d44a  xor     edx, edx; Val
0x18003d44c  mov     [rsp+290h+var_260], r15
0x18003d451  mov     r8d, 200h; Size
0x18003d457  lea     rcx, [rsp+290h+var_258]; void *
0x18003d45c  call    memset_0
0x18003d461  lea     rax, [rsp+290h+var_258]
0x18003d466  mov     [rbp+190h+var_58], r15
0x18003d46d  mov     rdx, r14; __int64
0x18003d470  mov     [rbp+190h+var_48], rax
0x18003d477  lea     rcx, [rsp+290h+var_260]; this
0x18003d47c  mov     [rbp+190h+var_50], 100h
0x18003d487  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003d48c  mov     ebx, eax
0x18003d48e  test    eax, eax
0x18003d490  jns     short loc_18003D4D1
0x18003d492  mov     edx, 0FEh; void *
0x18003d497  mov     rcx, [rbp+198h]; this
0x18003d49e  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d4a5  mov     r9d, ebx; char *
0x18003d4a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d4ad  mov     rcx, [rsp+290h+var_260]
0x18003d4b2  mov     [rsp+290h+var_260], r15
0x18003d4b7  test    rcx, rcx
0x18003d4ba  jz      loc_18003D415
0x18003d4c0  call    cs:__imp_SRCache_Free
0x18003d4c7  nop     dword ptr [rax+rax+00h]
0x18003d4cc  jmp     loc_18003D415
0x18003d4d1  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003d4d8  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003d4dd  mov     r9, rsi; bool *
0x18003d4e0  mov     rcx, rdi; this
0x18003d4e3  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003d4e8  mov     ebx, eax
0x18003d4ea  test    eax, eax
0x18003d4ec  jns     short loc_18003D4F5
0x18003d4ee  mov     edx, 0FFh
0x18003d4f3  jmp     short loc_18003D497
0x18003d4f5  mov     rcx, [rsp+290h+var_268]
0x18003d4fa  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18003d501  call    cs:__imp_SRCacheContext_AddToCache
0x18003d508  nop     dword ptr [rax+rax+00h]
0x18003d50d  mov     ebx, eax
0x18003d50f  test    eax, eax
0x18003d511  jns     short loc_18003D538
0x18003d513  mov     rcx, [rbp+198h]; this
0x18003d51a  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d521  mov     r9d, eax; char *
0x18003d524  mov     edx, 1A6h; void *
0x18003d529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d52e  mov     edx, 101h
0x18003d533  jmp     loc_18003D497
0x18003d538  mov     rcx, [rsp+290h+var_260]
0x18003d53d  mov     [rsp+290h+var_260], r15
0x18003d542  test    rcx, rcx
0x18003d545  jz      short loc_18003D553
0x18003d547  call    cs:__imp_SRCache_Free
0x18003d54e  nop     dword ptr [rax+rax+00h]
0x18003d553  mov     rcx, [rsp+290h+var_268]
0x18003d558  mov     [rsp+290h+var_268], r15
0x18003d55d  test    rcx, rcx
0x18003d560  jz      short loc_18003D56E
0x18003d562  call    cs:__imp_SRCacheContext_Close
0x18003d569  nop     dword ptr [rax+rax+00h]
0x18003d56e  xor     eax, eax
0x18003d570  mov     rcx, [rbp+190h+var_40]
0x18003d577  xor     rcx, rsp; StackCookie
0x18003d57a  call    __security_check_cookie
0x18003d57f  add     rsp, 268h
0x18003d586  pop     r15
0x18003d588  pop     r14
0x18003d58a  pop     rdi
0x18003d58b  pop     rsi
0x18003d58c  pop     rbx
0x18003d58d  pop     rbp
0x18003d58e  retn
```
