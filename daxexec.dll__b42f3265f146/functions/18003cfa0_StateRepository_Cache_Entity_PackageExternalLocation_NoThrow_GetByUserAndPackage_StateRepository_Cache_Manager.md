# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18003cfa0`
- end: `0x18003d295`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003d29c`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003b224`
- `0x18003cfa0`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d057`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d189`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d231`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d267`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d057`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d189`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d231`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d267`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d0ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d24c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d0ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d24c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003d1ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003d1ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d1eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d1eb`

## string_xrefs

- `0x18003d1c4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d204`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003cfe4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003d039`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003d0cc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003d167`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  int appended; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool v20[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a4 = 0;
  if ( !a3 )
  {
    appended = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      *(int *)v20);
    return (unsigned int)appended;
  }
  v20[0] = 0;
  v21 = 0;
  appended = StateRepository::Cache::Context_NoThrow::Open(
               (StateRepository::Cache::Context_NoThrow *)&v21,
               a1,
               L"PackageExternalLocation\\Index\\UserAndPackage",
               v20);
  if ( appended < 0 )
  {
    v9 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v20);
LABEL_7:
    v10 = v21;
    v21 = 0;
    if ( v10 )
      SRCacheContext_Close();
    return (unsigned int)appended;
  }
  if ( !v20[0] )
  {
    appended = -2140733422;
    v9 = 186;
    goto LABEL_6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = (unsigned __int16 *)v24;
  v26 = 256;
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  if ( appended < 0 )
  {
    v11 = 189;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v20);
LABEL_14:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_7;
  }
  appended = StateRepository::Cache::Key_NoThrow::AppendDelimiter((StateRepository::Cache::Key_NoThrow *)&v23);
  if ( appended < 0 )
  {
    v11 = 190;
    goto LABEL_13;
  }
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( appended < 0 )
  {
    v11 = 191;
    goto LABEL_13;
  }
  v22 = 0;
  v20[0] = 0;
  appended = StateRepository::Cache::Context_NoThrow::OpenSubContext(
               (StateRepository::Cache::Context_NoThrow *)&v22,
               (struct StateRepository::Cache::Context_NoThrow *)&v21,
               v27,
               v20);
  if ( appended < 0 )
  {
    v13 = 195;
    goto LABEL_22;
  }
  if ( v20[0] )
  {
    v15 = SRCacheContext_EnumerateData(v22, 0, a4);
    appended = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v15,
        *(int *)v20);
      v13 = 198;
      goto LABEL_22;
    }
  }
  v16 = SRCacheContext_AddToCache(v21, L"PackageExternalLocation\\Index\\UserAndPackage");
  appended = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v20);
    v13 = 201;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)appended,
      *(int *)v20);
    v14 = v22;
    v22 = 0;
    if ( v14 )
      SRCacheContext_Close();
    goto LABEL_14;
  }
  v17 = v22;
  v22 = 0;
  if ( v17 )
    SRCacheContext_Close();
  v18 = v23;
  v23 = 0;
  if ( v18 )
    SRCache_Free();
  v19 = v21;
  v21 = 0;
  if ( v19 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18003cfa0  push    rbp
0x18003cfa2  push    rbx
0x18003cfa3  push    rsi
0x18003cfa4  push    rdi
0x18003cfa5  push    r14
0x18003cfa7  push    r15
0x18003cfa9  lea     rbp, [rsp-178h]
0x18003cfb1  sub     rsp, 278h
0x18003cfb8  mov     rax, cs:__security_cookie
0x18003cfbf  xor     rax, rsp
0x18003cfc2  mov     [rbp+1A0h+var_40], rax
0x18003cfc9  xor     r15d, r15d
0x18003cfcc  mov     rsi, r9
0x18003cfcf  mov     [r9], r15
0x18003cfd2  mov     rdi, r8
0x18003cfd5  mov     r14, rdx
0x18003cfd8  test    r8, r8
0x18003cfdb  jnz     short loc_18003D004
0x18003cfdd  mov     rcx, [rbp+1A8h]; this
0x18003cfe4  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cfeb  mov     ebx, 80070057h
0x18003cff0  mov     edx, 0B5h; void *
0x18003cff5  mov     r9d, ebx; char *
0x18003cff8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cffd  mov     eax, ebx
0x18003cfff  jmp     loc_18003D275
0x18003d004  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003d007  mov     [rsp+2A0h+var_280], r15b; int
0x18003d00c  lea     rcx, [rsp+2A0h+var_278]; this
0x18003d011  mov     [rsp+2A0h+var_278], r15
0x18003d016  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003d01b  lea     r8, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18003d022  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003d027  mov     ebx, eax
0x18003d029  test    eax, eax
0x18003d02b  jns     short loc_18003D065
0x18003d02d  mov     edx, 0B9h; void *
0x18003d032  mov     rcx, [rbp+1A8h]; this
0x18003d039  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d040  mov     r9d, ebx; char *
0x18003d043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d048  mov     rcx, [rsp+2A0h+var_278]
0x18003d04d  mov     [rsp+2A0h+var_278], r15
0x18003d052  test    rcx, rcx
0x18003d055  jz      short loc_18003CFFD
0x18003d057  call    cs:__imp_SRCacheContext_Close
0x18003d05e  nop     dword ptr [rax+rax+00h]
0x18003d063  jmp     short loc_18003CFFD
0x18003d065  cmp     [rsp+2A0h+var_280], r15b
0x18003d06a  jnz     short loc_18003D078
0x18003d06c  mov     ebx, 80670012h
0x18003d071  mov     edx, 0BAh
0x18003d076  jmp     short loc_18003D032
0x18003d078  xor     edx, edx; Val
0x18003d07a  mov     [rsp+2A0h+var_260], r15
0x18003d07f  mov     r8d, 200h; Size
0x18003d085  lea     rcx, [rsp+2A0h+var_258]; void *
0x18003d08a  call    memset_0
0x18003d08f  lea     rax, [rsp+2A0h+var_258]
0x18003d094  mov     [rbp+1A0h+var_58], r15
0x18003d09b  mov     rdx, r14; __int64
0x18003d09e  mov     [rbp+1A0h+var_48], rax
0x18003d0a5  lea     rcx, [rsp+2A0h+var_260]; this
0x18003d0aa  mov     [rbp+1A0h+var_50], 100h
0x18003d0b5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003d0ba  mov     ebx, eax
0x18003d0bc  test    eax, eax
0x18003d0be  jns     short loc_18003D0FF
0x18003d0c0  mov     edx, 0BDh; void *
0x18003d0c5  mov     rcx, [rbp+1A8h]; this
0x18003d0cc  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d0d3  mov     r9d, ebx; char *
0x18003d0d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d0db  mov     rcx, [rsp+2A0h+var_260]
0x18003d0e0  mov     [rsp+2A0h+var_260], r15
0x18003d0e5  test    rcx, rcx
0x18003d0e8  jz      loc_18003D048
0x18003d0ee  call    cs:__imp_SRCache_Free
0x18003d0f5  nop     dword ptr [rax+rax+00h]
0x18003d0fa  jmp     loc_18003D048
0x18003d0ff  lea     rcx, [rsp+2A0h+var_260]; this
0x18003d104  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x18003d109  mov     ebx, eax
0x18003d10b  test    eax, eax
0x18003d10d  jns     short loc_18003D116
0x18003d10f  mov     edx, 0BEh
0x18003d114  jmp     short loc_18003D0C5
0x18003d116  mov     rdx, rdi; __int64
0x18003d119  lea     rcx, [rsp+2A0h+var_260]; this
0x18003d11e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003d123  mov     ebx, eax
0x18003d125  test    eax, eax
0x18003d127  jns     short loc_18003D130
0x18003d129  mov     edx, 0BFh
0x18003d12e  jmp     short loc_18003D0C5
0x18003d130  mov     r8, [rbp+1A0h+var_48]; unsigned __int16 *
0x18003d137  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003d13c  lea     rdx, [rsp+2A0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18003d141  mov     [rsp+2A0h+var_270], r15
0x18003d146  lea     rcx, [rsp+2A0h+var_270]; this
0x18003d14b  mov     [rsp+2A0h+var_280], r15b; int
0x18003d150  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003d155  mov     ebx, eax
0x18003d157  test    eax, eax
0x18003d159  jns     short loc_18003D19A
0x18003d15b  mov     edx, 0C3h; void *
0x18003d160  mov     rcx, [rbp+1A8h]; this
0x18003d167  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d16e  mov     r9d, ebx; char *
0x18003d171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d176  mov     rcx, [rsp+2A0h+var_270]
0x18003d17b  mov     [rsp+2A0h+var_270], r15
0x18003d180  test    rcx, rcx
0x18003d183  jz      loc_18003D0DB
0x18003d189  call    cs:__imp_SRCacheContext_Close
0x18003d190  nop     dword ptr [rax+rax+00h]
0x18003d195  jmp     loc_18003D0DB
0x18003d19a  cmp     [rsp+2A0h+var_280], r15b
0x18003d19f  jz      short loc_18003D1DF
0x18003d1a1  mov     rcx, [rsp+2A0h+var_270]
0x18003d1a6  mov     r8, rsi
0x18003d1a9  xor     edx, edx
0x18003d1ab  call    cs:__imp_SRCacheContext_EnumerateData
0x18003d1b2  nop     dword ptr [rax+rax+00h]
0x18003d1b7  mov     ebx, eax
0x18003d1b9  test    eax, eax
0x18003d1bb  jns     short loc_18003D1DF
0x18003d1bd  mov     rcx, [rbp+1A8h]; this
0x18003d1c4  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d1cb  mov     r9d, eax; char *
0x18003d1ce  mov     edx, 2A6h; void *
0x18003d1d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d1d8  mov     edx, 0C6h
0x18003d1dd  jmp     short loc_18003D160
0x18003d1df  mov     rcx, [rsp+2A0h+var_278]
0x18003d1e4  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18003d1eb  call    cs:__imp_SRCacheContext_AddToCache
0x18003d1f2  nop     dword ptr [rax+rax+00h]
0x18003d1f7  mov     ebx, eax
0x18003d1f9  test    eax, eax
0x18003d1fb  jns     short loc_18003D222
0x18003d1fd  mov     rcx, [rbp+1A8h]; this
0x18003d204  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d20b  mov     r9d, eax; char *
0x18003d20e  mov     edx, 1A6h; void *
0x18003d213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d218  mov     edx, 0C9h
0x18003d21d  jmp     loc_18003D160
0x18003d222  mov     rcx, [rsp+2A0h+var_270]
0x18003d227  mov     [rsp+2A0h+var_270], r15
0x18003d22c  test    rcx, rcx
0x18003d22f  jz      short loc_18003D23D
0x18003d231  call    cs:__imp_SRCacheContext_Close
0x18003d238  nop     dword ptr [rax+rax+00h]
0x18003d23d  mov     rcx, [rsp+2A0h+var_260]
0x18003d242  mov     [rsp+2A0h+var_260], r15
0x18003d247  test    rcx, rcx
0x18003d24a  jz      short loc_18003D258
0x18003d24c  call    cs:__imp_SRCache_Free
0x18003d253  nop     dword ptr [rax+rax+00h]
0x18003d258  mov     rcx, [rsp+2A0h+var_278]
0x18003d25d  mov     [rsp+2A0h+var_278], r15
0x18003d262  test    rcx, rcx
0x18003d265  jz      short loc_18003D273
0x18003d267  call    cs:__imp_SRCacheContext_Close
0x18003d26e  nop     dword ptr [rax+rax+00h]
0x18003d273  xor     eax, eax
0x18003d275  mov     rcx, [rbp+1A0h+var_40]
0x18003d27c  xor     rcx, rsp; StackCookie
0x18003d27f  call    __security_check_cookie
0x18003d284  add     rsp, 278h
0x18003d28b  pop     r15
0x18003d28d  pop     r14
0x18003d28f  pop     rdi
0x18003d290  pop     rsi
0x18003d291  pop     rbx
0x18003d292  pop     rbp
0x18003d293  retn
```
