# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18009fd0c`
- end: `0x1800a005c`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `848`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18009f318`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x18009fd0c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fd7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fde3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fe2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ff4c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ffe9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0026`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fd7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fde3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fe2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009fecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ff4c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ffe9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0026`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009feb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ff30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ffcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a000a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009feb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ff30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ffcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a000a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009ff75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009ff75`

## string_xrefs

- `0x18009ff91`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009fd58`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18009fdc2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18009fe0d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18009fe92`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18009ff0f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18009ffac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

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
      (void *)0x787,
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
      (void *)0x78D,
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
      (void *)0x78E,
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
      (void *)0x791,
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
      (void *)0x794,
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
      (void *)0x79A,
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
0x18009fd0c  mov     [rsp-8+arg_18], rbx
0x18009fd11  push    rbp
0x18009fd12  push    rsi
0x18009fd13  push    rdi
0x18009fd14  push    r14
0x18009fd16  push    r15
0x18009fd18  lea     rbp, [rsp-160h]
0x18009fd20  sub     rsp, 260h
0x18009fd27  mov     rax, cs:__security_cookie
0x18009fd2e  xor     rax, rsp
0x18009fd31  mov     [rbp+180h+var_30], rax
0x18009fd38  mov     r14, r8
0x18009fd3b  mov     rsi, rdx
0x18009fd3e  mov     rbx, rcx
0x18009fd41  xor     r15d, r15d
0x18009fd44  test    r8, r8
0x18009fd47  jnz     short loc_18009FD70
0x18009fd49  mov     rcx, [rbp+188h]; this
0x18009fd50  mov     ebx, 80070057h
0x18009fd55  mov     r9d, ebx; char *
0x18009fd58  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fd5f  mov     edx, 787h; void *
0x18009fd64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fd69  mov     eax, ebx
0x18009fd6b  jmp     loc_1800A0035
0x18009fd70  mov     rcx, [rcx]
0x18009fd73  mov     [rbx], r15
0x18009fd76  test    rcx, rcx
0x18009fd79  jz      short loc_18009FD87
0x18009fd7b  call    cs:__imp_SRCacheContext_Close
0x18009fd82  nop     dword ptr [rax+rax+00h]
0x18009fd87  mov     [rbx+8], r15d
0x18009fd8b  mov     [rbx+10h], r15
0x18009fd8f  mov     [rsp+280h+var_258], r15
0x18009fd94  mov     [rsp+280h+var_260], r15b; int
0x18009fd99  lea     r9, [rsp+280h+var_260]; bool *
0x18009fd9e  lea     r8, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18009fda5  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18009fda8  lea     rcx, [rsp+280h+var_258]; this
0x18009fdad  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18009fdb2  mov     edi, eax
0x18009fdb4  test    eax, eax
0x18009fdb6  jns     short loc_18009FDF7
0x18009fdb8  mov     rcx, [rbp+188h]; this
0x18009fdbf  mov     r9d, eax; char *
0x18009fdc2  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fdc9  mov     edx, 78Dh; void *
0x18009fdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fdd3  nop
0x18009fdd4  mov     rcx, [rsp+280h+var_258]
0x18009fdd9  mov     [rsp+280h+var_258], r15
0x18009fdde  test    rcx, rcx
0x18009fde1  jz      short loc_18009FDF0
0x18009fde3  call    cs:__imp_SRCacheContext_Close
0x18009fdea  nop     dword ptr [rax+rax+00h]
0x18009fdef  nop
0x18009fdf0  mov     eax, edi
0x18009fdf2  jmp     loc_1800A0035
0x18009fdf7  cmp     [rsp+280h+var_260], r15b
0x18009fdfc  jnz     short loc_18009FE40
0x18009fdfe  mov     rcx, [rbp+188h]; this
0x18009fe05  mov     ebx, 80670012h
0x18009fe0a  mov     r9d, ebx; char *
0x18009fe0d  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fe14  mov     edx, 78Eh; void *
0x18009fe19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fe1e  nop
0x18009fe1f  mov     rcx, [rsp+280h+var_258]
0x18009fe24  mov     [rsp+280h+var_258], r15
0x18009fe29  test    rcx, rcx
0x18009fe2c  jz      short loc_18009FE3B
0x18009fe2e  call    cs:__imp_SRCacheContext_Close
0x18009fe35  nop     dword ptr [rax+rax+00h]
0x18009fe3a  nop
0x18009fe3b  jmp     loc_18009FD69
0x18009fe40  mov     [rsp+280h+var_250], r15
0x18009fe45  xor     edx, edx; Val
0x18009fe47  mov     r8d, 200h; Size
0x18009fe4d  lea     rcx, [rsp+280h+var_248]; void *
0x18009fe52  call    memset_0
0x18009fe57  mov     [rbp+180h+var_48], r15
0x18009fe5e  mov     [rbp+180h+var_40], 100h
0x18009fe69  lea     rax, [rsp+280h+var_248]
0x18009fe6e  mov     [rbp+180h+var_38], rax
0x18009fe75  mov     rdx, r14; __int64
0x18009fe78  lea     rcx, [rsp+280h+var_250]; this
0x18009fe7d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18009fe82  mov     edi, eax
0x18009fe84  test    eax, eax
0x18009fe86  jns     short loc_18009FEE1
0x18009fe88  mov     rcx, [rbp+188h]; this
0x18009fe8f  mov     r9d, eax; char *
0x18009fe92  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009fe99  mov     edx, 791h; void *
0x18009fe9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fea3  nop
0x18009fea4  mov     rcx, [rsp+280h+var_250]
0x18009fea9  mov     [rsp+280h+var_250], r15
0x18009feae  test    rcx, rcx
0x18009feb1  jz      short loc_18009FEC0
0x18009feb3  call    cs:__imp_SRCache_Free
0x18009feba  nop     dword ptr [rax+rax+00h]
0x18009febf  nop
0x18009fec0  mov     rcx, [rsp+280h+var_258]
0x18009fec5  mov     [rsp+280h+var_258], r15
0x18009feca  test    rcx, rcx
0x18009fecd  jz      short loc_18009FEDC
0x18009fecf  call    cs:__imp_SRCacheContext_Close
0x18009fed6  nop     dword ptr [rax+rax+00h]
0x18009fedb  nop
0x18009fedc  jmp     loc_18009FDF0
0x18009fee1  mov     [rsp+280h+var_260], r15b; int
0x18009fee6  lea     r9, [rsp+280h+var_260]; bool *
0x18009feeb  mov     r8, [rbp+180h+var_38]; unsigned __int16 *
0x18009fef2  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x18009fef7  mov     rcx, rbx; this
0x18009fefa  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18009feff  mov     edi, eax
0x18009ff01  test    eax, eax
0x18009ff03  jns     short loc_18009FF5E
0x18009ff05  mov     rcx, [rbp+188h]; this
0x18009ff0c  mov     r9d, eax; char *
0x18009ff0f  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009ff16  mov     edx, 794h; void *
0x18009ff1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ff20  nop
0x18009ff21  mov     rcx, [rsp+280h+var_250]
0x18009ff26  mov     [rsp+280h+var_250], r15
0x18009ff2b  test    rcx, rcx
0x18009ff2e  jz      short loc_18009FF3D
0x18009ff30  call    cs:__imp_SRCache_Free
0x18009ff37  nop     dword ptr [rax+rax+00h]
0x18009ff3c  nop
0x18009ff3d  mov     rcx, [rsp+280h+var_258]
0x18009ff42  mov     [rsp+280h+var_258], r15
0x18009ff47  test    rcx, rcx
0x18009ff4a  jz      short loc_18009FF59
0x18009ff4c  call    cs:__imp_SRCacheContext_Close
0x18009ff53  nop     dword ptr [rax+rax+00h]
0x18009ff58  nop
0x18009ff59  jmp     loc_18009FDF0
0x18009ff5e  cmp     [rsp+280h+var_260], r15b
0x18009ff63  jz      short loc_18009FF69
0x18009ff65  mov     [rbx+10h], rsi
0x18009ff69  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18009ff70  mov     rcx, [rsp+280h+var_258]
0x18009ff75  call    cs:__imp_SRCacheContext_AddToCache
0x18009ff7c  nop     dword ptr [rax+rax+00h]
0x18009ff81  mov     ebx, eax
0x18009ff83  test    eax, eax
0x18009ff85  jns     short loc_18009FFFB
0x18009ff87  mov     rcx, [rbp+188h]; this
0x18009ff8e  mov     r9d, eax; char *
0x18009ff91  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009ff98  mov     edx, 1A6h; void *
0x18009ff9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ffa2  mov     rcx, [rbp+188h]; this
0x18009ffa9  mov     r9d, ebx; char *
0x18009ffac  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009ffb3  mov     edx, 79Ah; void *
0x18009ffb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ffbd  nop
0x18009ffbe  mov     rcx, [rsp+280h+var_250]
0x18009ffc3  mov     [rsp+280h+var_250], r15
0x18009ffc8  test    rcx, rcx
0x18009ffcb  jz      short loc_18009FFDA
0x18009ffcd  call    cs:__imp_SRCache_Free
0x18009ffd4  nop     dword ptr [rax+rax+00h]
0x18009ffd9  nop
0x18009ffda  mov     rcx, [rsp+280h+var_258]
0x18009ffdf  mov     [rsp+280h+var_258], r15
0x18009ffe4  test    rcx, rcx
0x18009ffe7  jz      short loc_18009FFF6
0x18009ffe9  call    cs:__imp_SRCacheContext_Close
0x18009fff0  nop     dword ptr [rax+rax+00h]
0x18009fff5  nop
0x18009fff6  jmp     loc_18009FD69
0x18009fffb  mov     rcx, [rsp+280h+var_250]
0x1800a0000  mov     [rsp+280h+var_250], r15
0x1800a0005  test    rcx, rcx
0x1800a0008  jz      short loc_1800A0017
0x1800a000a  call    cs:__imp_SRCache_Free
0x1800a0011  nop     dword ptr [rax+rax+00h]
0x1800a0016  nop
0x1800a0017  mov     rcx, [rsp+280h+var_258]
0x1800a001c  mov     [rsp+280h+var_258], r15
0x1800a0021  test    rcx, rcx
0x1800a0024  jz      short loc_1800A0033
0x1800a0026  call    cs:__imp_SRCacheContext_Close
0x1800a002d  nop     dword ptr [rax+rax+00h]
0x1800a0032  nop
0x1800a0033  xor     eax, eax
0x1800a0035  mov     rcx, [rbp+180h+var_30]
0x1800a003c  xor     rcx, rsp; StackCookie
0x1800a003f  call    __security_check_cookie
0x1800a0044  mov     rbx, [rsp+280h+arg_18]
0x1800a004c  add     rsp, 260h
0x1800a0053  pop     r15
0x1800a0055  pop     r14
0x1800a0057  pop     rdi
0x1800a0058  pop     rsi
0x1800a0059  pop     rbp
0x1800a005a  retn
```
