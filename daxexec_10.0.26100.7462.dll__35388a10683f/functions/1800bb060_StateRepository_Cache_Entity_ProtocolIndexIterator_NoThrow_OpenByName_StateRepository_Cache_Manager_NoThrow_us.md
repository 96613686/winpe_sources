# StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800bb060`
- end: `0x1800bb2fa`
- name: `?OpenByName@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `666`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b5598`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x18003d264`
- `0x18003d794`
- `0x1800bb060`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb0a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb10a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb153`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb2c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb0a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb10a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb153`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb2c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb1dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb28a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb2aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb1dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb28a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb2aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bb22f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bb22f`

## string_xrefs

- `0x1800bb248`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bb0b8`: `Protocol\Index\Name`
- `0x1800bb228`: `Protocol\Index\Name`
- `0x1800bb0e7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bb12b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bb1ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bb263`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByName(
        StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  int v7; // eax
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  bool v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+238h] [rbp+138h]
  __int64 v24; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v25; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v20 = 0;
  v19[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v20,
         a2,
         L"Protocol\\Index\\Name",
         v19);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v19);
LABEL_5:
    v9 = v20;
    v20 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v8;
  }
  if ( !v19[0] )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)0x80670012LL,
      *(int *)v19);
LABEL_10:
    v12 = v20;
    v20 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return v11;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = (unsigned __int16 *)v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a3);
  if ( v8 < 0 )
  {
    v13 = 613;
    goto LABEL_15;
  }
  v19[0] = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v20,
         v25,
         v19);
  if ( v8 < 0 )
  {
    v13 = 616;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v8,
      *(int *)v19);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_5;
  }
  if ( v19[0] )
    *((_QWORD *)this + 2) = a2;
  v15 = SRCacheContext_AddToCache(v20, L"Protocol\\Index\\Name");
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      *(int *)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)v11,
      *(int *)v19);
    v16 = v21;
    v21 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_10;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = v20;
  v20 = 0;
  if ( v18 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800bb060  mov     [rsp-8+arg_18], rbx
0x1800bb065  push    rbp
0x1800bb066  push    rsi
0x1800bb067  push    rdi
0x1800bb068  push    r14
0x1800bb06a  push    r15
0x1800bb06c  lea     rbp, [rsp-160h]
0x1800bb074  sub     rsp, 260h
0x1800bb07b  mov     rax, cs:__security_cookie
0x1800bb082  xor     rax, rsp
0x1800bb085  mov     [rbp+180h+var_30], rax
0x1800bb08c  mov     rbx, rcx
0x1800bb08f  xor     r15d, r15d
0x1800bb092  mov     rcx, [rcx]
0x1800bb095  mov     r14, r8
0x1800bb098  mov     rsi, rdx
0x1800bb09b  mov     [rbx], r15
0x1800bb09e  test    rcx, rcx
0x1800bb0a1  jz      short loc_1800BB0AF
0x1800bb0a3  call    cs:__imp_SRCacheContext_Close
0x1800bb0aa  nop     dword ptr [rax+rax+00h]
0x1800bb0af  lea     r9, [rsp+280h+var_260]; bool *
0x1800bb0b4  mov     [rbx+8], r15d
0x1800bb0b8  lea     r8, aProtocolIndexN; "Protocol\\Index\\Name"
0x1800bb0bf  mov     [rbx+10h], r15
0x1800bb0c3  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800bb0c6  mov     [rsp+280h+var_258], r15
0x1800bb0cb  lea     rcx, [rsp+280h+var_258]; this
0x1800bb0d0  mov     [rsp+280h+var_260], r15b; int
0x1800bb0d5  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bb0da  mov     edi, eax
0x1800bb0dc  test    eax, eax
0x1800bb0de  jns     short loc_1800BB11D
0x1800bb0e0  mov     rcx, [rbp+188h]; this
0x1800bb0e7  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bb0ee  mov     r9d, eax; char *
0x1800bb0f1  mov     edx, 261h; void *
0x1800bb0f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb0fb  mov     rcx, [rsp+280h+var_258]
0x1800bb100  mov     [rsp+280h+var_258], r15
0x1800bb105  test    rcx, rcx
0x1800bb108  jz      short loc_1800BB116
0x1800bb10a  call    cs:__imp_SRCacheContext_Close
0x1800bb111  nop     dword ptr [rax+rax+00h]
0x1800bb116  mov     eax, edi
0x1800bb118  jmp     loc_1800BB2D3
0x1800bb11d  cmp     [rsp+280h+var_260], r15b
0x1800bb122  jnz     short loc_1800BB166
0x1800bb124  mov     rcx, [rbp+188h]; this
0x1800bb12b  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bb132  mov     ebx, 80670012h
0x1800bb137  mov     edx, 262h; void *
0x1800bb13c  mov     r9d, ebx; char *
0x1800bb13f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb144  mov     rcx, [rsp+280h+var_258]
0x1800bb149  mov     [rsp+280h+var_258], r15
0x1800bb14e  test    rcx, rcx
0x1800bb151  jz      short loc_1800BB15F
0x1800bb153  call    cs:__imp_SRCacheContext_Close
0x1800bb15a  nop     dword ptr [rax+rax+00h]
0x1800bb15f  mov     eax, ebx
0x1800bb161  jmp     loc_1800BB2D3
0x1800bb166  xor     edx, edx; Val
0x1800bb168  mov     [rsp+280h+var_250], r15
0x1800bb16d  mov     r8d, 200h; Size
0x1800bb173  lea     rcx, [rsp+280h+var_248]; void *
0x1800bb178  call    memset_0
0x1800bb17d  lea     rax, [rsp+280h+var_248]
0x1800bb182  mov     [rbp+180h+var_48], r15
0x1800bb189  mov     rdx, r14; unsigned __int16 *
0x1800bb18c  mov     [rbp+180h+var_38], rax
0x1800bb193  lea     rcx, [rsp+280h+var_250]; this
0x1800bb198  mov     [rbp+180h+var_40], 100h
0x1800bb1a3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800bb1a8  mov     edi, eax
0x1800bb1aa  test    eax, eax
0x1800bb1ac  jns     short loc_1800BB1ED
0x1800bb1ae  mov     edx, 265h; void *
0x1800bb1b3  mov     rcx, [rbp+188h]; this
0x1800bb1ba  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bb1c1  mov     r9d, edi; char *
0x1800bb1c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb1c9  mov     rcx, [rsp+280h+var_250]
0x1800bb1ce  mov     [rsp+280h+var_250], r15
0x1800bb1d3  test    rcx, rcx
0x1800bb1d6  jz      loc_1800BB0FB
0x1800bb1dc  call    cs:__imp_SRCache_Free
0x1800bb1e3  nop     dword ptr [rax+rax+00h]
0x1800bb1e8  jmp     loc_1800BB0FB
0x1800bb1ed  mov     r8, [rbp+180h+var_38]; unsigned __int16 *
0x1800bb1f4  lea     r9, [rsp+280h+var_260]; bool *
0x1800bb1f9  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x1800bb1fe  mov     [rsp+280h+var_260], r15b; int
0x1800bb203  mov     rcx, rbx; this
0x1800bb206  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bb20b  mov     edi, eax
0x1800bb20d  test    eax, eax
0x1800bb20f  jns     short loc_1800BB218
0x1800bb211  mov     edx, 268h
0x1800bb216  jmp     short loc_1800BB1B3
0x1800bb218  cmp     [rsp+280h+var_260], r15b
0x1800bb21d  jz      short loc_1800BB223
0x1800bb21f  mov     [rbx+10h], rsi
0x1800bb223  mov     rcx, [rsp+280h+var_258]
0x1800bb228  lea     rdx, aProtocolIndexN; "Protocol\\Index\\Name"
0x1800bb22f  call    cs:__imp_SRCacheContext_AddToCache
0x1800bb236  nop     dword ptr [rax+rax+00h]
0x1800bb23b  mov     ebx, eax
0x1800bb23d  test    eax, eax
0x1800bb23f  jns     short loc_1800BB29B
0x1800bb241  mov     rcx, [rbp+188h]; this
0x1800bb248  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bb24f  mov     r9d, eax; char *
0x1800bb252  mov     edx, 1A6h; void *
0x1800bb257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb25c  mov     rcx, [rbp+188h]; this
0x1800bb263  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bb26a  mov     r9d, ebx; char *
0x1800bb26d  mov     edx, 26Eh; void *
0x1800bb272  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb277  mov     rcx, [rsp+280h+var_250]
0x1800bb27c  mov     [rsp+280h+var_250], r15
0x1800bb281  test    rcx, rcx
0x1800bb284  jz      loc_1800BB144
0x1800bb28a  call    cs:__imp_SRCache_Free
0x1800bb291  nop     dword ptr [rax+rax+00h]
0x1800bb296  jmp     loc_1800BB144
0x1800bb29b  mov     rcx, [rsp+280h+var_250]
0x1800bb2a0  mov     [rsp+280h+var_250], r15
0x1800bb2a5  test    rcx, rcx
0x1800bb2a8  jz      short loc_1800BB2B6
0x1800bb2aa  call    cs:__imp_SRCache_Free
0x1800bb2b1  nop     dword ptr [rax+rax+00h]
0x1800bb2b6  mov     rcx, [rsp+280h+var_258]
0x1800bb2bb  mov     [rsp+280h+var_258], r15
0x1800bb2c0  test    rcx, rcx
0x1800bb2c3  jz      short loc_1800BB2D1
0x1800bb2c5  call    cs:__imp_SRCacheContext_Close
0x1800bb2cc  nop     dword ptr [rax+rax+00h]
0x1800bb2d1  xor     eax, eax
0x1800bb2d3  mov     rcx, [rbp+180h+var_30]
0x1800bb2da  xor     rcx, rsp; StackCookie
0x1800bb2dd  call    __security_check_cookie
0x1800bb2e2  mov     rbx, [rsp+280h+arg_18]
0x1800bb2ea  add     rsp, 260h
0x1800bb2f1  pop     r15
0x1800bb2f3  pop     r14
0x1800bb2f5  pop     rdi
0x1800bb2f6  pop     rsi
0x1800bb2f7  pop     rbp
0x1800bb2f8  retn
```
