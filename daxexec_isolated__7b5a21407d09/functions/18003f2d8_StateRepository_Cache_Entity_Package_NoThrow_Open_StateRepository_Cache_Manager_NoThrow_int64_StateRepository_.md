# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003f2d8`
- end: `0x18003f4cc`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003c3a0`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f2d8`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f360`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f49e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f360`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003f49e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f3fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f3fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003f483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003f43d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003f43d`

## string_xrefs

- `0x18003f456`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003f342`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003f3da`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

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
    v8 = 1192;
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
    v8 = 1193;
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
    v11 = 1196;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 1197;
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
    v11 = 1199;
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
0x18003f2d8  push    rbp
0x18003f2da  push    rbx
0x18003f2db  push    rsi
0x18003f2dc  push    rdi
0x18003f2dd  push    r14
0x18003f2df  push    r15
0x18003f2e1  lea     rbp, [rsp-168h]
0x18003f2e9  sub     rsp, 268h
0x18003f2f0  mov     rax, cs:__security_cookie
0x18003f2f7  xor     rax, rsp
0x18003f2fa  mov     [rbp+190h+var_40], rax
0x18003f301  mov     r14, rdx
0x18003f304  mov     rsi, r9
0x18003f307  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003f30a  lea     r9, [rsp+290h+var_270]; bool *
0x18003f30f  mov     rdi, r8
0x18003f312  lea     rcx, [rsp+290h+var_268]; this
0x18003f317  xor     r15d, r15d
0x18003f31a  lea     r8, aPackageData; "Package\\Data"
0x18003f321  mov     [rsp+290h+var_268], r15
0x18003f326  mov     [rsp+290h+var_270], r15b; int
0x18003f32b  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003f330  mov     ebx, eax
0x18003f332  test    eax, eax
0x18003f334  jns     short loc_18003F373
0x18003f336  mov     edx, 4A8h; void *
0x18003f33b  mov     rcx, [rbp+198h]; this
0x18003f342  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003f349  mov     r9d, ebx; char *
0x18003f34c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f351  mov     rcx, [rsp+290h+var_268]
0x18003f356  mov     [rsp+290h+var_268], r15
0x18003f35b  test    rcx, rcx
0x18003f35e  jz      short loc_18003F36C
0x18003f360  call    cs:__imp_SRCacheContext_Close
0x18003f367  nop     dword ptr [rax+rax+00h]
0x18003f36c  mov     eax, ebx
0x18003f36e  jmp     loc_18003F4AC
0x18003f373  cmp     [rsp+290h+var_270], r15b
0x18003f378  jnz     short loc_18003F386
0x18003f37a  mov     ebx, 80670012h
0x18003f37f  mov     edx, 4A9h
0x18003f384  jmp     short loc_18003F33B
0x18003f386  xor     edx, edx; Val
0x18003f388  mov     [rsp+290h+var_260], r15
0x18003f38d  mov     r8d, 200h; Size
0x18003f393  lea     rcx, [rsp+290h+var_258]; void *
0x18003f398  call    memset_0
0x18003f39d  lea     rax, [rsp+290h+var_258]
0x18003f3a2  mov     [rbp+190h+var_58], r15
0x18003f3a9  mov     rdx, r14; __int64
0x18003f3ac  mov     [rbp+190h+var_48], rax
0x18003f3b3  lea     rcx, [rsp+290h+var_260]; this
0x18003f3b8  mov     [rbp+190h+var_50], 100h
0x18003f3c3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003f3c8  mov     ebx, eax
0x18003f3ca  test    eax, eax
0x18003f3cc  jns     short loc_18003F40D
0x18003f3ce  mov     edx, 4ACh; void *
0x18003f3d3  mov     rcx, [rbp+198h]; this
0x18003f3da  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003f3e1  mov     r9d, ebx; char *
0x18003f3e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f3e9  mov     rcx, [rsp+290h+var_260]
0x18003f3ee  mov     [rsp+290h+var_260], r15
0x18003f3f3  test    rcx, rcx
0x18003f3f6  jz      loc_18003F351
0x18003f3fc  call    cs:__imp_SRCache_Free
0x18003f403  nop     dword ptr [rax+rax+00h]
0x18003f408  jmp     loc_18003F351
0x18003f40d  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003f414  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003f419  mov     r9, rsi; bool *
0x18003f41c  mov     rcx, rdi; this
0x18003f41f  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003f424  mov     ebx, eax
0x18003f426  test    eax, eax
0x18003f428  jns     short loc_18003F431
0x18003f42a  mov     edx, 4ADh
0x18003f42f  jmp     short loc_18003F3D3
0x18003f431  mov     rcx, [rsp+290h+var_268]
0x18003f436  lea     rdx, aPackageData; "Package\\Data"
0x18003f43d  call    cs:__imp_SRCacheContext_AddToCache
0x18003f444  nop     dword ptr [rax+rax+00h]
0x18003f449  mov     ebx, eax
0x18003f44b  test    eax, eax
0x18003f44d  jns     short loc_18003F474
0x18003f44f  mov     rcx, [rbp+198h]; this
0x18003f456  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003f45d  mov     r9d, eax; char *
0x18003f460  mov     edx, 1A6h; void *
0x18003f465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f46a  mov     edx, 4AFh
0x18003f46f  jmp     loc_18003F3D3
0x18003f474  mov     rcx, [rsp+290h+var_260]
0x18003f479  mov     [rsp+290h+var_260], r15
0x18003f47e  test    rcx, rcx
0x18003f481  jz      short loc_18003F48F
0x18003f483  call    cs:__imp_SRCache_Free
0x18003f48a  nop     dword ptr [rax+rax+00h]
0x18003f48f  mov     rcx, [rsp+290h+var_268]
0x18003f494  mov     [rsp+290h+var_268], r15
0x18003f499  test    rcx, rcx
0x18003f49c  jz      short loc_18003F4AA
0x18003f49e  call    cs:__imp_SRCacheContext_Close
0x18003f4a5  nop     dword ptr [rax+rax+00h]
0x18003f4aa  xor     eax, eax
0x18003f4ac  mov     rcx, [rbp+190h+var_40]
0x18003f4b3  xor     rcx, rsp; StackCookie
0x18003f4b6  call    __security_check_cookie
0x18003f4bb  add     rsp, 268h
0x18003f4c2  pop     r15
0x18003f4c4  pop     r14
0x18003f4c6  pop     rdi
0x18003f4c7  pop     rsi
0x18003f4c8  pop     rbx
0x18003f4c9  pop     rbp
0x18003f4ca  retn
```
