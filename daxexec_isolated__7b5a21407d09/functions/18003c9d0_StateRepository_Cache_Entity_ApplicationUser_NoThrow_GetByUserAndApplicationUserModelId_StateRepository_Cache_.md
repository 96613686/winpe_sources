# StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x18003c9d0`
- end: `0x18003ccc5`
- name: `?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003cccc`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003b19c`
- `0x18003b224`
- `0x18003c9d0`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ca87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cbb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cc61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cc97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ca87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cbb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cc61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cc97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003cb1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003cc7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003cb1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003cc7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003cbdb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003cbdb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003cc1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003cc1b`

## string_xrefs

- `0x18003cbf4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003cc34`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003ca14`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003ca69`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003cafc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003cb97`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
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
  if ( !a2 )
  {
    appended = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      *(int *)v20);
    return (unsigned int)appended;
  }
  v20[0] = 0;
  v21 = 0;
  appended = StateRepository::Cache::Context_NoThrow::Open(
               (StateRepository::Cache::Context_NoThrow *)&v21,
               a1,
               L"ApplicationUser\\Index\\UserAndApplicationUserModelId",
               v20);
  if ( appended < 0 )
  {
    v9 = 425;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
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
    v9 = 426;
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
    v11 = 429;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
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
    v11 = 430;
    goto LABEL_13;
  }
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( appended < 0 )
  {
    v11 = 431;
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
    v13 = 435;
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
      v13 = 438;
      goto LABEL_22;
    }
  }
  v16 = SRCacheContext_AddToCache(v21, L"ApplicationUser\\Index\\UserAndApplicationUserModelId");
  appended = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v20);
    v13 = 441;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
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
0x18003c9d0  push    rbp
0x18003c9d2  push    rbx
0x18003c9d3  push    rsi
0x18003c9d4  push    rdi
0x18003c9d5  push    r14
0x18003c9d7  push    r15
0x18003c9d9  lea     rbp, [rsp-178h]
0x18003c9e1  sub     rsp, 278h
0x18003c9e8  mov     rax, cs:__security_cookie
0x18003c9ef  xor     rax, rsp
0x18003c9f2  mov     [rbp+1A0h+var_40], rax
0x18003c9f9  xor     r15d, r15d
0x18003c9fc  mov     rsi, r9
0x18003c9ff  mov     [r9], r15
0x18003ca02  mov     r14, r8
0x18003ca05  mov     rdi, rdx
0x18003ca08  test    rdx, rdx
0x18003ca0b  jnz     short loc_18003CA34
0x18003ca0d  mov     rcx, [rbp+1A8h]; this
0x18003ca14  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ca1b  mov     ebx, 80070057h
0x18003ca20  mov     edx, 1A5h; void *
0x18003ca25  mov     r9d, ebx; char *
0x18003ca28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca2d  mov     eax, ebx
0x18003ca2f  jmp     loc_18003CCA5
0x18003ca34  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003ca37  mov     [rsp+2A0h+var_280], r15b; int
0x18003ca3c  lea     rcx, [rsp+2A0h+var_278]; this
0x18003ca41  mov     [rsp+2A0h+var_278], r15
0x18003ca46  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003ca4b  lea     r8, aApplicationuse_1; "ApplicationUser\\Index\\UserAndApplicat"...
0x18003ca52  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003ca57  mov     ebx, eax
0x18003ca59  test    eax, eax
0x18003ca5b  jns     short loc_18003CA95
0x18003ca5d  mov     edx, 1A9h; void *
0x18003ca62  mov     rcx, [rbp+1A8h]; this
0x18003ca69  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ca70  mov     r9d, ebx; char *
0x18003ca73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca78  mov     rcx, [rsp+2A0h+var_278]
0x18003ca7d  mov     [rsp+2A0h+var_278], r15
0x18003ca82  test    rcx, rcx
0x18003ca85  jz      short loc_18003CA2D
0x18003ca87  call    cs:__imp_SRCacheContext_Close
0x18003ca8e  nop     dword ptr [rax+rax+00h]
0x18003ca93  jmp     short loc_18003CA2D
0x18003ca95  cmp     [rsp+2A0h+var_280], r15b
0x18003ca9a  jnz     short loc_18003CAA8
0x18003ca9c  mov     ebx, 80670012h
0x18003caa1  mov     edx, 1AAh
0x18003caa6  jmp     short loc_18003CA62
0x18003caa8  xor     edx, edx; Val
0x18003caaa  mov     [rsp+2A0h+var_260], r15
0x18003caaf  mov     r8d, 200h; Size
0x18003cab5  lea     rcx, [rsp+2A0h+var_258]; void *
0x18003caba  call    memset_0
0x18003cabf  lea     rax, [rsp+2A0h+var_258]
0x18003cac4  mov     [rbp+1A0h+var_58], r15
0x18003cacb  mov     rdx, rdi; __int64
0x18003cace  mov     [rbp+1A0h+var_48], rax
0x18003cad5  lea     rcx, [rsp+2A0h+var_260]; this
0x18003cada  mov     [rbp+1A0h+var_50], 100h
0x18003cae5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003caea  mov     ebx, eax
0x18003caec  test    eax, eax
0x18003caee  jns     short loc_18003CB2F
0x18003caf0  mov     edx, 1ADh; void *
0x18003caf5  mov     rcx, [rbp+1A8h]; this
0x18003cafc  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cb03  mov     r9d, ebx; char *
0x18003cb06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb0b  mov     rcx, [rsp+2A0h+var_260]
0x18003cb10  mov     [rsp+2A0h+var_260], r15
0x18003cb15  test    rcx, rcx
0x18003cb18  jz      loc_18003CA78
0x18003cb1e  call    cs:__imp_SRCache_Free
0x18003cb25  nop     dword ptr [rax+rax+00h]
0x18003cb2a  jmp     loc_18003CA78
0x18003cb2f  lea     rcx, [rsp+2A0h+var_260]; this
0x18003cb34  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x18003cb39  mov     ebx, eax
0x18003cb3b  test    eax, eax
0x18003cb3d  jns     short loc_18003CB46
0x18003cb3f  mov     edx, 1AEh
0x18003cb44  jmp     short loc_18003CAF5
0x18003cb46  mov     rdx, r14; unsigned __int16 *
0x18003cb49  lea     rcx, [rsp+2A0h+var_260]; this
0x18003cb4e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003cb53  mov     ebx, eax
0x18003cb55  test    eax, eax
0x18003cb57  jns     short loc_18003CB60
0x18003cb59  mov     edx, 1AFh
0x18003cb5e  jmp     short loc_18003CAF5
0x18003cb60  mov     r8, [rbp+1A0h+var_48]; unsigned __int16 *
0x18003cb67  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003cb6c  lea     rdx, [rsp+2A0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18003cb71  mov     [rsp+2A0h+var_270], r15
0x18003cb76  lea     rcx, [rsp+2A0h+var_270]; this
0x18003cb7b  mov     [rsp+2A0h+var_280], r15b; int
0x18003cb80  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003cb85  mov     ebx, eax
0x18003cb87  test    eax, eax
0x18003cb89  jns     short loc_18003CBCA
0x18003cb8b  mov     edx, 1B3h; void *
0x18003cb90  mov     rcx, [rbp+1A8h]; this
0x18003cb97  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cb9e  mov     r9d, ebx; char *
0x18003cba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cba6  mov     rcx, [rsp+2A0h+var_270]
0x18003cbab  mov     [rsp+2A0h+var_270], r15
0x18003cbb0  test    rcx, rcx
0x18003cbb3  jz      loc_18003CB0B
0x18003cbb9  call    cs:__imp_SRCacheContext_Close
0x18003cbc0  nop     dword ptr [rax+rax+00h]
0x18003cbc5  jmp     loc_18003CB0B
0x18003cbca  cmp     [rsp+2A0h+var_280], r15b
0x18003cbcf  jz      short loc_18003CC0F
0x18003cbd1  mov     rcx, [rsp+2A0h+var_270]
0x18003cbd6  mov     r8, rsi
0x18003cbd9  xor     edx, edx
0x18003cbdb  call    cs:__imp_SRCacheContext_EnumerateData
0x18003cbe2  nop     dword ptr [rax+rax+00h]
0x18003cbe7  mov     ebx, eax
0x18003cbe9  test    eax, eax
0x18003cbeb  jns     short loc_18003CC0F
0x18003cbed  mov     rcx, [rbp+1A8h]; this
0x18003cbf4  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cbfb  mov     r9d, eax; char *
0x18003cbfe  mov     edx, 2A6h; void *
0x18003cc03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cc08  mov     edx, 1B6h
0x18003cc0d  jmp     short loc_18003CB90
0x18003cc0f  mov     rcx, [rsp+2A0h+var_278]
0x18003cc14  lea     rdx, aApplicationuse_1; "ApplicationUser\\Index\\UserAndApplicat"...
0x18003cc1b  call    cs:__imp_SRCacheContext_AddToCache
0x18003cc22  nop     dword ptr [rax+rax+00h]
0x18003cc27  mov     ebx, eax
0x18003cc29  test    eax, eax
0x18003cc2b  jns     short loc_18003CC52
0x18003cc2d  mov     rcx, [rbp+1A8h]; this
0x18003cc34  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cc3b  mov     r9d, eax; char *
0x18003cc3e  mov     edx, 1A6h; void *
0x18003cc43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cc48  mov     edx, 1B9h
0x18003cc4d  jmp     loc_18003CB90
0x18003cc52  mov     rcx, [rsp+2A0h+var_270]
0x18003cc57  mov     [rsp+2A0h+var_270], r15
0x18003cc5c  test    rcx, rcx
0x18003cc5f  jz      short loc_18003CC6D
0x18003cc61  call    cs:__imp_SRCacheContext_Close
0x18003cc68  nop     dword ptr [rax+rax+00h]
0x18003cc6d  mov     rcx, [rsp+2A0h+var_260]
0x18003cc72  mov     [rsp+2A0h+var_260], r15
0x18003cc77  test    rcx, rcx
0x18003cc7a  jz      short loc_18003CC88
0x18003cc7c  call    cs:__imp_SRCache_Free
0x18003cc83  nop     dword ptr [rax+rax+00h]
0x18003cc88  mov     rcx, [rsp+2A0h+var_278]
0x18003cc8d  mov     [rsp+2A0h+var_278], r15
0x18003cc92  test    rcx, rcx
0x18003cc95  jz      short loc_18003CCA3
0x18003cc97  call    cs:__imp_SRCacheContext_Close
0x18003cc9e  nop     dword ptr [rax+rax+00h]
0x18003cca3  xor     eax, eax
0x18003cca5  mov     rcx, [rbp+1A0h+var_40]
0x18003ccac  xor     rcx, rsp; StackCookie
0x18003ccaf  call    __security_check_cookie
0x18003ccb4  add     rsp, 278h
0x18003ccbb  pop     r15
0x18003ccbd  pop     r14
0x18003ccbf  pop     rdi
0x18003ccc0  pop     rsi
0x18003ccc1  pop     rbx
0x18003ccc2  pop     rbp
0x18003ccc3  retn
```
