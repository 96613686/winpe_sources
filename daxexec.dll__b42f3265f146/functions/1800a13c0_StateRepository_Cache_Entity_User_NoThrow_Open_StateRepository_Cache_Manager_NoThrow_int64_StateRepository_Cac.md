# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800a13c0`
- end: `0x1800a16a6`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `742`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a0b04`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800a13c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1449`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1494`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1532`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a15a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a163a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1677`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1449`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1494`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1532`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a15a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a163a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1677`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a1516`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a158c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a161e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a165b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a1516`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a158c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a161e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a165b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800a15c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800a15c6`

## string_xrefs

- `0x1800a15e2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a1428`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a1473`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a14f5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a156b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a15fd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

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
0x1800a13c0  push    rbp
0x1800a13c2  push    rbx
0x1800a13c3  push    rsi
0x1800a13c4  push    rdi
0x1800a13c5  push    r14
0x1800a13c7  push    r15
0x1800a13c9  lea     rbp, [rsp-168h]
0x1800a13d1  sub     rsp, 268h
0x1800a13d8  mov     rax, cs:__security_cookie
0x1800a13df  xor     rax, rsp
0x1800a13e2  mov     [rbp+190h+var_40], rax
0x1800a13e9  mov     rsi, r9
0x1800a13ec  mov     rdi, r8
0x1800a13ef  mov     r14, rdx
0x1800a13f2  xor     r15d, r15d
0x1800a13f5  mov     [rsp+290h+var_268], r15
0x1800a13fa  mov     [rsp+290h+var_270], r15b; int
0x1800a13ff  lea     r9, [rsp+290h+var_270]; bool *
0x1800a1404  lea     r8, aUserData; "User\\Data"
0x1800a140b  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800a140e  lea     rcx, [rsp+290h+var_268]; this
0x1800a1413  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800a1418  mov     ebx, eax
0x1800a141a  test    eax, eax
0x1800a141c  jns     short loc_1800A145D
0x1800a141e  mov     rcx, [rbp+198h]; this
0x1800a1425  mov     r9d, eax; char *
0x1800a1428  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a142f  mov     edx, 10Bh; void *
0x1800a1434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1439  nop
0x1800a143a  mov     rcx, [rsp+290h+var_268]
0x1800a143f  mov     [rsp+290h+var_268], r15
0x1800a1444  test    rcx, rcx
0x1800a1447  jz      short loc_1800A1456
0x1800a1449  call    cs:__imp_SRCacheContext_Close
0x1800a1450  nop     dword ptr [rax+rax+00h]
0x1800a1455  nop
0x1800a1456  mov     eax, ebx
0x1800a1458  jmp     loc_1800A1686
0x1800a145d  cmp     [rsp+290h+var_270], r15b
0x1800a1462  jnz     short loc_1800A14A3
0x1800a1464  mov     rcx, [rbp+198h]; this
0x1800a146b  mov     ebx, 80670012h
0x1800a1470  mov     r9d, ebx; char *
0x1800a1473  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a147a  mov     edx, 10Ch; void *
0x1800a147f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1484  nop
0x1800a1485  mov     rcx, [rsp+290h+var_268]
0x1800a148a  mov     [rsp+290h+var_268], r15
0x1800a148f  test    rcx, rcx
0x1800a1492  jz      short loc_1800A14A1
0x1800a1494  call    cs:__imp_SRCacheContext_Close
0x1800a149b  nop     dword ptr [rax+rax+00h]
0x1800a14a0  nop
0x1800a14a1  jmp     short loc_1800A1456
0x1800a14a3  mov     [rsp+290h+var_260], r15
0x1800a14a8  xor     edx, edx; Val
0x1800a14aa  mov     r8d, 200h; Size
0x1800a14b0  lea     rcx, [rsp+290h+var_258]; void *
0x1800a14b5  call    memset_0
0x1800a14ba  mov     [rbp+190h+var_58], r15
0x1800a14c1  mov     [rbp+190h+var_50], 100h
0x1800a14cc  lea     rax, [rsp+290h+var_258]
0x1800a14d1  mov     [rbp+190h+var_48], rax
0x1800a14d8  mov     rdx, r14; __int64
0x1800a14db  lea     rcx, [rsp+290h+var_260]; this
0x1800a14e0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800a14e5  mov     ebx, eax
0x1800a14e7  test    eax, eax
0x1800a14e9  jns     short loc_1800A1544
0x1800a14eb  mov     rcx, [rbp+198h]; this
0x1800a14f2  mov     r9d, eax; char *
0x1800a14f5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a14fc  mov     edx, 10Fh; void *
0x1800a1501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1506  nop
0x1800a1507  mov     rcx, [rsp+290h+var_260]
0x1800a150c  mov     [rsp+290h+var_260], r15
0x1800a1511  test    rcx, rcx
0x1800a1514  jz      short loc_1800A1523
0x1800a1516  call    cs:__imp_SRCache_Free
0x1800a151d  nop     dword ptr [rax+rax+00h]
0x1800a1522  nop
0x1800a1523  mov     rcx, [rsp+290h+var_268]
0x1800a1528  mov     [rsp+290h+var_268], r15
0x1800a152d  test    rcx, rcx
0x1800a1530  jz      short loc_1800A153F
0x1800a1532  call    cs:__imp_SRCacheContext_Close
0x1800a1539  nop     dword ptr [rax+rax+00h]
0x1800a153e  nop
0x1800a153f  jmp     loc_1800A1456
0x1800a1544  mov     r9, rsi; bool *
0x1800a1547  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800a154e  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800a1553  mov     rcx, rdi; this
0x1800a1556  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800a155b  mov     ebx, eax
0x1800a155d  test    eax, eax
0x1800a155f  jns     short loc_1800A15BA
0x1800a1561  mov     rcx, [rbp+198h]; this
0x1800a1568  mov     r9d, eax; char *
0x1800a156b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1572  mov     edx, 110h; void *
0x1800a1577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a157c  nop
0x1800a157d  mov     rcx, [rsp+290h+var_260]
0x1800a1582  mov     [rsp+290h+var_260], r15
0x1800a1587  test    rcx, rcx
0x1800a158a  jz      short loc_1800A1599
0x1800a158c  call    cs:__imp_SRCache_Free
0x1800a1593  nop     dword ptr [rax+rax+00h]
0x1800a1598  nop
0x1800a1599  mov     rcx, [rsp+290h+var_268]
0x1800a159e  mov     [rsp+290h+var_268], r15
0x1800a15a3  test    rcx, rcx
0x1800a15a6  jz      short loc_1800A15B5
0x1800a15a8  call    cs:__imp_SRCacheContext_Close
0x1800a15af  nop     dword ptr [rax+rax+00h]
0x1800a15b4  nop
0x1800a15b5  jmp     loc_1800A1456
0x1800a15ba  lea     rdx, aUserData; "User\\Data"
0x1800a15c1  mov     rcx, [rsp+290h+var_268]
0x1800a15c6  call    cs:__imp_SRCacheContext_AddToCache
0x1800a15cd  nop     dword ptr [rax+rax+00h]
0x1800a15d2  mov     ebx, eax
0x1800a15d4  test    eax, eax
0x1800a15d6  jns     short loc_1800A164C
0x1800a15d8  mov     rcx, [rbp+198h]; this
0x1800a15df  mov     r9d, eax; char *
0x1800a15e2  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a15e9  mov     edx, 1A6h; void *
0x1800a15ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a15f3  mov     rcx, [rbp+198h]; this
0x1800a15fa  mov     r9d, ebx; char *
0x1800a15fd  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1604  mov     edx, 112h; void *
0x1800a1609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a160e  nop
0x1800a160f  mov     rcx, [rsp+290h+var_260]
0x1800a1614  mov     [rsp+290h+var_260], r15
0x1800a1619  test    rcx, rcx
0x1800a161c  jz      short loc_1800A162B
0x1800a161e  call    cs:__imp_SRCache_Free
0x1800a1625  nop     dword ptr [rax+rax+00h]
0x1800a162a  nop
0x1800a162b  mov     rcx, [rsp+290h+var_268]
0x1800a1630  mov     [rsp+290h+var_268], r15
0x1800a1635  test    rcx, rcx
0x1800a1638  jz      short loc_1800A1647
0x1800a163a  call    cs:__imp_SRCacheContext_Close
0x1800a1641  nop     dword ptr [rax+rax+00h]
0x1800a1646  nop
0x1800a1647  jmp     loc_1800A1456
0x1800a164c  mov     rcx, [rsp+290h+var_260]
0x1800a1651  mov     [rsp+290h+var_260], r15
0x1800a1656  test    rcx, rcx
0x1800a1659  jz      short loc_1800A1668
0x1800a165b  call    cs:__imp_SRCache_Free
0x1800a1662  nop     dword ptr [rax+rax+00h]
0x1800a1667  nop
0x1800a1668  mov     rcx, [rsp+290h+var_268]
0x1800a166d  mov     [rsp+290h+var_268], r15
0x1800a1672  test    rcx, rcx
0x1800a1675  jz      short loc_1800A1684
0x1800a1677  call    cs:__imp_SRCacheContext_Close
0x1800a167e  nop     dword ptr [rax+rax+00h]
0x1800a1683  nop
0x1800a1684  xor     eax, eax
0x1800a1686  mov     rcx, [rbp+190h+var_40]
0x1800a168d  xor     rcx, rsp; StackCookie
0x1800a1690  call    __security_check_cookie
0x1800a1695  add     rsp, 268h
0x1800a169c  pop     r15
0x1800a169e  pop     r14
0x1800a16a0  pop     rdi
0x1800a16a1  pop     rsi
0x1800a16a2  pop     rbx
0x1800a16a3  pop     rbp
0x1800a16a4  retn
```
