# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800bc2c8`
- end: `0x1800bc4bc`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b5828`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bc2c8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc350`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc48e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc350`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc48e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc3ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc473`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc3ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc473`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc42d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc42d`

## string_xrefs

- `0x1800bc446`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bc332`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bc3ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800bc30a`: `ApplicationExtension\Data`
- `0x1800bc426`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
         L"ApplicationExtension\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v8 = 365;
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
    v11 = 368;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 369;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"ApplicationExtension\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 371;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x1800bc2c8  push    rbp
0x1800bc2ca  push    rbx
0x1800bc2cb  push    rsi
0x1800bc2cc  push    rdi
0x1800bc2cd  push    r14
0x1800bc2cf  push    r15
0x1800bc2d1  lea     rbp, [rsp-168h]
0x1800bc2d9  sub     rsp, 268h
0x1800bc2e0  mov     rax, cs:__security_cookie
0x1800bc2e7  xor     rax, rsp
0x1800bc2ea  mov     [rbp+190h+var_40], rax
0x1800bc2f1  mov     r14, rdx
0x1800bc2f4  mov     rsi, r9
0x1800bc2f7  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800bc2fa  lea     r9, [rsp+290h+var_270]; bool *
0x1800bc2ff  mov     rdi, r8
0x1800bc302  lea     rcx, [rsp+290h+var_268]; this
0x1800bc307  xor     r15d, r15d
0x1800bc30a  lea     r8, aApplicationext_0; "ApplicationExtension\\Data"
0x1800bc311  mov     [rsp+290h+var_268], r15
0x1800bc316  mov     [rsp+290h+var_270], r15b; int
0x1800bc31b  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bc320  mov     ebx, eax
0x1800bc322  test    eax, eax
0x1800bc324  jns     short loc_1800BC363
0x1800bc326  mov     edx, 16Ch; void *
0x1800bc32b  mov     rcx, [rbp+198h]; this
0x1800bc332  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc339  mov     r9d, ebx; char *
0x1800bc33c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc341  mov     rcx, [rsp+290h+var_268]
0x1800bc346  mov     [rsp+290h+var_268], r15
0x1800bc34b  test    rcx, rcx
0x1800bc34e  jz      short loc_1800BC35C
0x1800bc350  call    cs:__imp_SRCacheContext_Close
0x1800bc357  nop     dword ptr [rax+rax+00h]
0x1800bc35c  mov     eax, ebx
0x1800bc35e  jmp     loc_1800BC49C
0x1800bc363  cmp     [rsp+290h+var_270], r15b
0x1800bc368  jnz     short loc_1800BC376
0x1800bc36a  mov     ebx, 80670012h
0x1800bc36f  mov     edx, 16Dh
0x1800bc374  jmp     short loc_1800BC32B
0x1800bc376  xor     edx, edx; Val
0x1800bc378  mov     [rsp+290h+var_260], r15
0x1800bc37d  mov     r8d, 200h; Size
0x1800bc383  lea     rcx, [rsp+290h+var_258]; void *
0x1800bc388  call    memset_0
0x1800bc38d  lea     rax, [rsp+290h+var_258]
0x1800bc392  mov     [rbp+190h+var_58], r15
0x1800bc399  mov     rdx, r14; __int64
0x1800bc39c  mov     [rbp+190h+var_48], rax
0x1800bc3a3  lea     rcx, [rsp+290h+var_260]; this
0x1800bc3a8  mov     [rbp+190h+var_50], 100h
0x1800bc3b3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bc3b8  mov     ebx, eax
0x1800bc3ba  test    eax, eax
0x1800bc3bc  jns     short loc_1800BC3FD
0x1800bc3be  mov     edx, 170h; void *
0x1800bc3c3  mov     rcx, [rbp+198h]; this
0x1800bc3ca  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc3d1  mov     r9d, ebx; char *
0x1800bc3d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc3d9  mov     rcx, [rsp+290h+var_260]
0x1800bc3de  mov     [rsp+290h+var_260], r15
0x1800bc3e3  test    rcx, rcx
0x1800bc3e6  jz      loc_1800BC341
0x1800bc3ec  call    cs:__imp_SRCache_Free
0x1800bc3f3  nop     dword ptr [rax+rax+00h]
0x1800bc3f8  jmp     loc_1800BC341
0x1800bc3fd  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bc404  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bc409  mov     r9, rsi; bool *
0x1800bc40c  mov     rcx, rdi; this
0x1800bc40f  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bc414  mov     ebx, eax
0x1800bc416  test    eax, eax
0x1800bc418  jns     short loc_1800BC421
0x1800bc41a  mov     edx, 171h
0x1800bc41f  jmp     short loc_1800BC3C3
0x1800bc421  mov     rcx, [rsp+290h+var_268]
0x1800bc426  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800bc42d  call    cs:__imp_SRCacheContext_AddToCache
0x1800bc434  nop     dword ptr [rax+rax+00h]
0x1800bc439  mov     ebx, eax
0x1800bc43b  test    eax, eax
0x1800bc43d  jns     short loc_1800BC464
0x1800bc43f  mov     rcx, [rbp+198h]; this
0x1800bc446  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc44d  mov     r9d, eax; char *
0x1800bc450  mov     edx, 1A6h; void *
0x1800bc455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc45a  mov     edx, 173h
0x1800bc45f  jmp     loc_1800BC3C3
0x1800bc464  mov     rcx, [rsp+290h+var_260]
0x1800bc469  mov     [rsp+290h+var_260], r15
0x1800bc46e  test    rcx, rcx
0x1800bc471  jz      short loc_1800BC47F
0x1800bc473  call    cs:__imp_SRCache_Free
0x1800bc47a  nop     dword ptr [rax+rax+00h]
0x1800bc47f  mov     rcx, [rsp+290h+var_268]
0x1800bc484  mov     [rsp+290h+var_268], r15
0x1800bc489  test    rcx, rcx
0x1800bc48c  jz      short loc_1800BC49A
0x1800bc48e  call    cs:__imp_SRCacheContext_Close
0x1800bc495  nop     dword ptr [rax+rax+00h]
0x1800bc49a  xor     eax, eax
0x1800bc49c  mov     rcx, [rbp+190h+var_40]
0x1800bc4a3  xor     rcx, rsp; StackCookie
0x1800bc4a6  call    __security_check_cookie
0x1800bc4ab  add     rsp, 268h
0x1800bc4b2  pop     r15
0x1800bc4b4  pop     r14
0x1800bc4b6  pop     rdi
0x1800bc4b7  pop     rsi
0x1800bc4b8  pop     rbx
0x1800bc4b9  pop     rbp
0x1800bc4ba  retn
```
