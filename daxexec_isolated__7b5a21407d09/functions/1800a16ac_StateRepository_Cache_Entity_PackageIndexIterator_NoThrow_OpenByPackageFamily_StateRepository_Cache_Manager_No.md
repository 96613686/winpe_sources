# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1800a16ac`
- end: `0x1800a19fc`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `848`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a0c70`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800a16ac`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a171b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1783`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a17ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a186f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a18ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1989`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a19c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a171b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1783`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a17ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a186f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a18ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1989`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a19c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a1853`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a18d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a196d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a19aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a1853`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a18d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a196d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a19aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800a1915`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800a1915`

## string_xrefs

- `0x1800a1931`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a16f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a1762`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a17ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a1832`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a18af`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a194c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  bool v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v27[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+238h] [rbp+138h]
  __int64 v29; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v30; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      *(int *)v24);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v25 = 0;
  v24[0] = 0;
  v9 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         a2,
         L"Package\\Index\\PackageFamily",
         v24);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v9,
      *(int *)v24);
    v11 = v25;
    v25 = 0;
    if ( v11 )
      SRCacheContext_Close();
    return v10;
  }
  if ( !v24[0] )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80670012LL,
      *(int *)v24);
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return v6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v29 = 256;
  v30 = (unsigned __int16 *)v27;
  v13 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a3);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v24);
    v14 = v26;
    v26 = 0;
    if ( v14 )
      SRCache_Free();
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SRCacheContext_Close();
    return v10;
  }
  v24[0] = 0;
  v16 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
          this,
          (struct StateRepository::Cache::Context_NoThrow *)&v25,
          v30,
          v24);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v24);
    v17 = v26;
    v26 = 0;
    if ( v17 )
      SRCache_Free();
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCacheContext_Close();
    return v10;
  }
  if ( v24[0] )
    *((_QWORD *)this + 2) = a2;
  v19 = SRCacheContext_AddToCache(v25, L"Package\\Index\\PackageFamily");
  v6 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v19,
      *(int *)v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      *(int *)v24);
    v20 = v26;
    v26 = 0;
    if ( v20 )
      SRCache_Free();
    v21 = v25;
    v25 = 0;
    if ( v21 )
      SRCacheContext_Close();
    return v6;
  }
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SRCache_Free();
  v23 = v25;
  v25 = 0;
  if ( v23 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800a16ac  mov     [rsp-8+arg_18], rbx
0x1800a16b1  push    rbp
0x1800a16b2  push    rsi
0x1800a16b3  push    rdi
0x1800a16b4  push    r14
0x1800a16b6  push    r15
0x1800a16b8  lea     rbp, [rsp-160h]
0x1800a16c0  sub     rsp, 260h
0x1800a16c7  mov     rax, cs:__security_cookie
0x1800a16ce  xor     rax, rsp
0x1800a16d1  mov     [rbp+180h+var_30], rax
0x1800a16d8  mov     r14, r8
0x1800a16db  mov     rsi, rdx
0x1800a16de  mov     rbx, rcx
0x1800a16e1  xor     r15d, r15d
0x1800a16e4  test    r8, r8
0x1800a16e7  jnz     short loc_1800A1710
0x1800a16e9  mov     rcx, [rbp+188h]; this
0x1800a16f0  mov     ebx, 80070057h
0x1800a16f5  mov     r9d, ebx; char *
0x1800a16f8  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a16ff  mov     edx, 792h; void *
0x1800a1704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1709  mov     eax, ebx
0x1800a170b  jmp     loc_1800A19D5
0x1800a1710  mov     rcx, [rcx]
0x1800a1713  mov     [rbx], r15
0x1800a1716  test    rcx, rcx
0x1800a1719  jz      short loc_1800A1727
0x1800a171b  call    cs:__imp_SRCacheContext_Close
0x1800a1722  nop     dword ptr [rax+rax+00h]
0x1800a1727  mov     [rbx+8], r15d
0x1800a172b  mov     [rbx+10h], r15
0x1800a172f  mov     [rsp+280h+var_258], r15
0x1800a1734  mov     [rsp+280h+var_260], r15b; int
0x1800a1739  lea     r9, [rsp+280h+var_260]; bool *
0x1800a173e  lea     r8, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x1800a1745  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800a1748  lea     rcx, [rsp+280h+var_258]; this
0x1800a174d  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800a1752  mov     edi, eax
0x1800a1754  test    eax, eax
0x1800a1756  jns     short loc_1800A1797
0x1800a1758  mov     rcx, [rbp+188h]; this
0x1800a175f  mov     r9d, eax; char *
0x1800a1762  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1769  mov     edx, 798h; void *
0x1800a176e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1773  nop
0x1800a1774  mov     rcx, [rsp+280h+var_258]
0x1800a1779  mov     [rsp+280h+var_258], r15
0x1800a177e  test    rcx, rcx
0x1800a1781  jz      short loc_1800A1790
0x1800a1783  call    cs:__imp_SRCacheContext_Close
0x1800a178a  nop     dword ptr [rax+rax+00h]
0x1800a178f  nop
0x1800a1790  mov     eax, edi
0x1800a1792  jmp     loc_1800A19D5
0x1800a1797  cmp     [rsp+280h+var_260], r15b
0x1800a179c  jnz     short loc_1800A17E0
0x1800a179e  mov     rcx, [rbp+188h]; this
0x1800a17a5  mov     ebx, 80670012h
0x1800a17aa  mov     r9d, ebx; char *
0x1800a17ad  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a17b4  mov     edx, 799h; void *
0x1800a17b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a17be  nop
0x1800a17bf  mov     rcx, [rsp+280h+var_258]
0x1800a17c4  mov     [rsp+280h+var_258], r15
0x1800a17c9  test    rcx, rcx
0x1800a17cc  jz      short loc_1800A17DB
0x1800a17ce  call    cs:__imp_SRCacheContext_Close
0x1800a17d5  nop     dword ptr [rax+rax+00h]
0x1800a17da  nop
0x1800a17db  jmp     loc_1800A1709
0x1800a17e0  mov     [rsp+280h+var_250], r15
0x1800a17e5  xor     edx, edx; Val
0x1800a17e7  mov     r8d, 200h; Size
0x1800a17ed  lea     rcx, [rsp+280h+var_248]; void *
0x1800a17f2  call    memset_0
0x1800a17f7  mov     [rbp+180h+var_48], r15
0x1800a17fe  mov     [rbp+180h+var_40], 100h
0x1800a1809  lea     rax, [rsp+280h+var_248]
0x1800a180e  mov     [rbp+180h+var_38], rax
0x1800a1815  mov     rdx, r14; __int64
0x1800a1818  lea     rcx, [rsp+280h+var_250]; this
0x1800a181d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800a1822  mov     edi, eax
0x1800a1824  test    eax, eax
0x1800a1826  jns     short loc_1800A1881
0x1800a1828  mov     rcx, [rbp+188h]; this
0x1800a182f  mov     r9d, eax; char *
0x1800a1832  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1839  mov     edx, 79Ch; void *
0x1800a183e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1843  nop
0x1800a1844  mov     rcx, [rsp+280h+var_250]
0x1800a1849  mov     [rsp+280h+var_250], r15
0x1800a184e  test    rcx, rcx
0x1800a1851  jz      short loc_1800A1860
0x1800a1853  call    cs:__imp_SRCache_Free
0x1800a185a  nop     dword ptr [rax+rax+00h]
0x1800a185f  nop
0x1800a1860  mov     rcx, [rsp+280h+var_258]
0x1800a1865  mov     [rsp+280h+var_258], r15
0x1800a186a  test    rcx, rcx
0x1800a186d  jz      short loc_1800A187C
0x1800a186f  call    cs:__imp_SRCacheContext_Close
0x1800a1876  nop     dword ptr [rax+rax+00h]
0x1800a187b  nop
0x1800a187c  jmp     loc_1800A1790
0x1800a1881  mov     [rsp+280h+var_260], r15b; int
0x1800a1886  lea     r9, [rsp+280h+var_260]; bool *
0x1800a188b  mov     r8, [rbp+180h+var_38]; unsigned __int16 *
0x1800a1892  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x1800a1897  mov     rcx, rbx; this
0x1800a189a  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800a189f  mov     edi, eax
0x1800a18a1  test    eax, eax
0x1800a18a3  jns     short loc_1800A18FE
0x1800a18a5  mov     rcx, [rbp+188h]; this
0x1800a18ac  mov     r9d, eax; char *
0x1800a18af  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a18b6  mov     edx, 79Fh; void *
0x1800a18bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a18c0  nop
0x1800a18c1  mov     rcx, [rsp+280h+var_250]
0x1800a18c6  mov     [rsp+280h+var_250], r15
0x1800a18cb  test    rcx, rcx
0x1800a18ce  jz      short loc_1800A18DD
0x1800a18d0  call    cs:__imp_SRCache_Free
0x1800a18d7  nop     dword ptr [rax+rax+00h]
0x1800a18dc  nop
0x1800a18dd  mov     rcx, [rsp+280h+var_258]
0x1800a18e2  mov     [rsp+280h+var_258], r15
0x1800a18e7  test    rcx, rcx
0x1800a18ea  jz      short loc_1800A18F9
0x1800a18ec  call    cs:__imp_SRCacheContext_Close
0x1800a18f3  nop     dword ptr [rax+rax+00h]
0x1800a18f8  nop
0x1800a18f9  jmp     loc_1800A1790
0x1800a18fe  cmp     [rsp+280h+var_260], r15b
0x1800a1903  jz      short loc_1800A1909
0x1800a1905  mov     [rbx+10h], rsi
0x1800a1909  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x1800a1910  mov     rcx, [rsp+280h+var_258]
0x1800a1915  call    cs:__imp_SRCacheContext_AddToCache
0x1800a191c  nop     dword ptr [rax+rax+00h]
0x1800a1921  mov     ebx, eax
0x1800a1923  test    eax, eax
0x1800a1925  jns     short loc_1800A199B
0x1800a1927  mov     rcx, [rbp+188h]; this
0x1800a192e  mov     r9d, eax; char *
0x1800a1931  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1938  mov     edx, 1A6h; void *
0x1800a193d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1942  mov     rcx, [rbp+188h]; this
0x1800a1949  mov     r9d, ebx; char *
0x1800a194c  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1953  mov     edx, 7A5h; void *
0x1800a1958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a195d  nop
0x1800a195e  mov     rcx, [rsp+280h+var_250]
0x1800a1963  mov     [rsp+280h+var_250], r15
0x1800a1968  test    rcx, rcx
0x1800a196b  jz      short loc_1800A197A
0x1800a196d  call    cs:__imp_SRCache_Free
0x1800a1974  nop     dword ptr [rax+rax+00h]
0x1800a1979  nop
0x1800a197a  mov     rcx, [rsp+280h+var_258]
0x1800a197f  mov     [rsp+280h+var_258], r15
0x1800a1984  test    rcx, rcx
0x1800a1987  jz      short loc_1800A1996
0x1800a1989  call    cs:__imp_SRCacheContext_Close
0x1800a1990  nop     dword ptr [rax+rax+00h]
0x1800a1995  nop
0x1800a1996  jmp     loc_1800A1709
0x1800a199b  mov     rcx, [rsp+280h+var_250]
0x1800a19a0  mov     [rsp+280h+var_250], r15
0x1800a19a5  test    rcx, rcx
0x1800a19a8  jz      short loc_1800A19B7
0x1800a19aa  call    cs:__imp_SRCache_Free
0x1800a19b1  nop     dword ptr [rax+rax+00h]
0x1800a19b6  nop
0x1800a19b7  mov     rcx, [rsp+280h+var_258]
0x1800a19bc  mov     [rsp+280h+var_258], r15
0x1800a19c1  test    rcx, rcx
0x1800a19c4  jz      short loc_1800A19D3
0x1800a19c6  call    cs:__imp_SRCacheContext_Close
0x1800a19cd  nop     dword ptr [rax+rax+00h]
0x1800a19d2  nop
0x1800a19d3  xor     eax, eax
0x1800a19d5  mov     rcx, [rbp+180h+var_30]
0x1800a19dc  xor     rcx, rsp; StackCookie
0x1800a19df  call    __security_check_cookie
0x1800a19e4  mov     rbx, [rsp+280h+arg_18]
0x1800a19ec  add     rsp, 260h
0x1800a19f3  pop     r15
0x1800a19f5  pop     r14
0x1800a19f7  pop     rdi
0x1800a19f8  pop     rsi
0x1800a19f9  pop     rbp
0x1800a19fa  retn
```
