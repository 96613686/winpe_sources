# StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800bce5c`
- end: `0x1800bd0f6`
- name: `?OpenByName@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `666`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b738c`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bce5c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bce9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcf06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcf4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bd0c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bce9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcf06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcf4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bd0c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcfd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bd086`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bd0a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcfd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bd086`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bd0a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bd02b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bd02b`

## string_xrefs

- `0x1800bd044`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bcee3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bcf27`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bcfb6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bd05f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bceb4`: `Protocol\Index\Name`
- `0x1800bd024`: `Protocol\Index\Name`

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
0x1800bce5c  mov     [rsp-8+arg_18], rbx
0x1800bce61  push    rbp
0x1800bce62  push    rsi
0x1800bce63  push    rdi
0x1800bce64  push    r14
0x1800bce66  push    r15
0x1800bce68  lea     rbp, [rsp-160h]
0x1800bce70  sub     rsp, 260h
0x1800bce77  mov     rax, cs:__security_cookie
0x1800bce7e  xor     rax, rsp
0x1800bce81  mov     [rbp+180h+var_30], rax
0x1800bce88  mov     rbx, rcx
0x1800bce8b  xor     r15d, r15d
0x1800bce8e  mov     rcx, [rcx]
0x1800bce91  mov     r14, r8
0x1800bce94  mov     rsi, rdx
0x1800bce97  mov     [rbx], r15
0x1800bce9a  test    rcx, rcx
0x1800bce9d  jz      short loc_1800BCEAB
0x1800bce9f  call    cs:__imp_SRCacheContext_Close
0x1800bcea6  nop     dword ptr [rax+rax+00h]
0x1800bceab  lea     r9, [rsp+280h+var_260]; bool *
0x1800bceb0  mov     [rbx+8], r15d
0x1800bceb4  lea     r8, aProtocolIndexN; "Protocol\\Index\\Name"
0x1800bcebb  mov     [rbx+10h], r15
0x1800bcebf  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800bcec2  mov     [rsp+280h+var_258], r15
0x1800bcec7  lea     rcx, [rsp+280h+var_258]; this
0x1800bcecc  mov     [rsp+280h+var_260], r15b; int
0x1800bced1  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bced6  mov     edi, eax
0x1800bced8  test    eax, eax
0x1800bceda  jns     short loc_1800BCF19
0x1800bcedc  mov     rcx, [rbp+188h]; this
0x1800bcee3  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bceea  mov     r9d, eax; char *
0x1800bceed  mov     edx, 261h; void *
0x1800bcef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcef7  mov     rcx, [rsp+280h+var_258]
0x1800bcefc  mov     [rsp+280h+var_258], r15
0x1800bcf01  test    rcx, rcx
0x1800bcf04  jz      short loc_1800BCF12
0x1800bcf06  call    cs:__imp_SRCacheContext_Close
0x1800bcf0d  nop     dword ptr [rax+rax+00h]
0x1800bcf12  mov     eax, edi
0x1800bcf14  jmp     loc_1800BD0CF
0x1800bcf19  cmp     [rsp+280h+var_260], r15b
0x1800bcf1e  jnz     short loc_1800BCF62
0x1800bcf20  mov     rcx, [rbp+188h]; this
0x1800bcf27  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcf2e  mov     ebx, 80670012h
0x1800bcf33  mov     edx, 262h; void *
0x1800bcf38  mov     r9d, ebx; char *
0x1800bcf3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcf40  mov     rcx, [rsp+280h+var_258]
0x1800bcf45  mov     [rsp+280h+var_258], r15
0x1800bcf4a  test    rcx, rcx
0x1800bcf4d  jz      short loc_1800BCF5B
0x1800bcf4f  call    cs:__imp_SRCacheContext_Close
0x1800bcf56  nop     dword ptr [rax+rax+00h]
0x1800bcf5b  mov     eax, ebx
0x1800bcf5d  jmp     loc_1800BD0CF
0x1800bcf62  xor     edx, edx; Val
0x1800bcf64  mov     [rsp+280h+var_250], r15
0x1800bcf69  mov     r8d, 200h; Size
0x1800bcf6f  lea     rcx, [rsp+280h+var_248]; void *
0x1800bcf74  call    memset_0
0x1800bcf79  lea     rax, [rsp+280h+var_248]
0x1800bcf7e  mov     [rbp+180h+var_48], r15
0x1800bcf85  mov     rdx, r14; unsigned __int16 *
0x1800bcf88  mov     [rbp+180h+var_38], rax
0x1800bcf8f  lea     rcx, [rsp+280h+var_250]; this
0x1800bcf94  mov     [rbp+180h+var_40], 100h
0x1800bcf9f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800bcfa4  mov     edi, eax
0x1800bcfa6  test    eax, eax
0x1800bcfa8  jns     short loc_1800BCFE9
0x1800bcfaa  mov     edx, 265h; void *
0x1800bcfaf  mov     rcx, [rbp+188h]; this
0x1800bcfb6  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcfbd  mov     r9d, edi; char *
0x1800bcfc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcfc5  mov     rcx, [rsp+280h+var_250]
0x1800bcfca  mov     [rsp+280h+var_250], r15
0x1800bcfcf  test    rcx, rcx
0x1800bcfd2  jz      loc_1800BCEF7
0x1800bcfd8  call    cs:__imp_SRCache_Free
0x1800bcfdf  nop     dword ptr [rax+rax+00h]
0x1800bcfe4  jmp     loc_1800BCEF7
0x1800bcfe9  mov     r8, [rbp+180h+var_38]; unsigned __int16 *
0x1800bcff0  lea     r9, [rsp+280h+var_260]; bool *
0x1800bcff5  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x1800bcffa  mov     [rsp+280h+var_260], r15b; int
0x1800bcfff  mov     rcx, rbx; this
0x1800bd002  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bd007  mov     edi, eax
0x1800bd009  test    eax, eax
0x1800bd00b  jns     short loc_1800BD014
0x1800bd00d  mov     edx, 268h
0x1800bd012  jmp     short loc_1800BCFAF
0x1800bd014  cmp     [rsp+280h+var_260], r15b
0x1800bd019  jz      short loc_1800BD01F
0x1800bd01b  mov     [rbx+10h], rsi
0x1800bd01f  mov     rcx, [rsp+280h+var_258]
0x1800bd024  lea     rdx, aProtocolIndexN; "Protocol\\Index\\Name"
0x1800bd02b  call    cs:__imp_SRCacheContext_AddToCache
0x1800bd032  nop     dword ptr [rax+rax+00h]
0x1800bd037  mov     ebx, eax
0x1800bd039  test    eax, eax
0x1800bd03b  jns     short loc_1800BD097
0x1800bd03d  mov     rcx, [rbp+188h]; this
0x1800bd044  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bd04b  mov     r9d, eax; char *
0x1800bd04e  mov     edx, 1A6h; void *
0x1800bd053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd058  mov     rcx, [rbp+188h]; this
0x1800bd05f  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bd066  mov     r9d, ebx; char *
0x1800bd069  mov     edx, 26Eh; void *
0x1800bd06e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd073  mov     rcx, [rsp+280h+var_250]
0x1800bd078  mov     [rsp+280h+var_250], r15
0x1800bd07d  test    rcx, rcx
0x1800bd080  jz      loc_1800BCF40
0x1800bd086  call    cs:__imp_SRCache_Free
0x1800bd08d  nop     dword ptr [rax+rax+00h]
0x1800bd092  jmp     loc_1800BCF40
0x1800bd097  mov     rcx, [rsp+280h+var_250]
0x1800bd09c  mov     [rsp+280h+var_250], r15
0x1800bd0a1  test    rcx, rcx
0x1800bd0a4  jz      short loc_1800BD0B2
0x1800bd0a6  call    cs:__imp_SRCache_Free
0x1800bd0ad  nop     dword ptr [rax+rax+00h]
0x1800bd0b2  mov     rcx, [rsp+280h+var_258]
0x1800bd0b7  mov     [rsp+280h+var_258], r15
0x1800bd0bc  test    rcx, rcx
0x1800bd0bf  jz      short loc_1800BD0CD
0x1800bd0c1  call    cs:__imp_SRCacheContext_Close
0x1800bd0c8  nop     dword ptr [rax+rax+00h]
0x1800bd0cd  xor     eax, eax
0x1800bd0cf  mov     rcx, [rbp+180h+var_30]
0x1800bd0d6  xor     rcx, rsp; StackCookie
0x1800bd0d9  call    __security_check_cookie
0x1800bd0de  mov     rbx, [rsp+280h+arg_18]
0x1800bd0e6  add     rsp, 260h
0x1800bd0ed  pop     r15
0x1800bd0ef  pop     r14
0x1800bd0f1  pop     rdi
0x1800bd0f2  pop     rsi
0x1800bd0f3  pop     rbp
0x1800bd0f4  retn
```
