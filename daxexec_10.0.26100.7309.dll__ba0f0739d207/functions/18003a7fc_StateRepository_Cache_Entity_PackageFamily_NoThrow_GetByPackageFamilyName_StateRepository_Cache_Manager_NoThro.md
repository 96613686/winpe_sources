# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18003a7fc`
- end: `0x18003aa8e`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18003ff30`
- `0x18009f318`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x18003a7fc`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003a882`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003a984`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003aa2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003aa62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003a882`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003a984`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003aa2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003aa62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003a9a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003a9a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003a91e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003aa47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003a91e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003aa47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003a9e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003a9e6`

## string_xrefs

- `0x18003a9bf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003a9ff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003a864`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18003a8f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18003a966`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  bool v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+248h] [rbp+148h]
  __int64 v24; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v25; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v18[0] = 0;
  v19 = 0;
  v5 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v19,
         a1,
         L"PackageFamily\\Index\\PackageFamilyName",
         v18);
  if ( v5 < 0 )
  {
    v6 = 193;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v5,
      *(int *)v18);
LABEL_4:
    v7 = v19;
    v19 = 0;
    if ( v7 )
      SRCacheContext_Close();
    return (unsigned int)v5;
  }
  if ( !v18[0] )
  {
    v5 = -2140733422;
    v6 = 194;
    goto LABEL_3;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = (unsigned __int16 *)v22;
  v24 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a2);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v9,
      *(int *)v18);
LABEL_11:
    v10 = v21;
    v21 = 0;
    if ( v10 )
      SRCache_Free();
    goto LABEL_4;
  }
  v20 = 0;
  v18[0] = 0;
  v5 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         (StateRepository::Cache::Context_NoThrow *)&v20,
         (struct StateRepository::Cache::Context_NoThrow *)&v19,
         v25,
         v18);
  if ( v5 < 0 )
  {
    v11 = 201;
    goto LABEL_15;
  }
  if ( v18[0] )
  {
    v13 = SRCacheContext_EnumerateData(v20, 0, a3);
    v5 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v13,
        *(int *)v18);
      v11 = 204;
      goto LABEL_15;
    }
  }
  v14 = SRCacheContext_AddToCache(v19, L"PackageFamily\\Index\\PackageFamilyName");
  v5 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      *(int *)v18);
    v11 = 207;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v5,
      *(int *)v18);
    v12 = v20;
    v20 = 0;
    if ( v12 )
      SRCacheContext_Close();
    goto LABEL_11;
  }
  v15 = v20;
  v20 = 0;
  if ( v15 )
    SRCacheContext_Close();
  v16 = v21;
  v21 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = v19;
  v19 = 0;
  if ( v17 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18003a7fc  push    rbp
0x18003a7fe  push    rbx
0x18003a7ff  push    rsi
0x18003a800  push    rdi
0x18003a801  push    r14
0x18003a803  lea     rbp, [rsp-170h]
0x18003a80b  sub     rsp, 270h
0x18003a812  mov     rax, cs:__security_cookie
0x18003a819  xor     rax, rsp
0x18003a81c  mov     [rbp+190h+var_30], rax
0x18003a823  xor     r14d, r14d
0x18003a826  lea     r9, [rsp+290h+var_270]; bool *
0x18003a82b  mov     rsi, rdx
0x18003a82e  mov     [r8], r14
0x18003a831  mov     rdi, r8
0x18003a834  mov     [rsp+290h+var_270], r14b; int
0x18003a839  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003a83c  mov     [rsp+290h+var_268], r14
0x18003a841  lea     r8, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18003a848  lea     rcx, [rsp+290h+var_268]; this
0x18003a84d  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003a852  mov     ebx, eax
0x18003a854  test    eax, eax
0x18003a856  jns     short loc_18003A895
0x18003a858  mov     edx, 0C1h; void *
0x18003a85d  mov     rcx, [rbp+198h]; this
0x18003a864  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003a86b  mov     r9d, ebx; char *
0x18003a86e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a873  mov     rcx, [rsp+290h+var_268]
0x18003a878  mov     [rsp+290h+var_268], r14
0x18003a87d  test    rcx, rcx
0x18003a880  jz      short loc_18003A88E
0x18003a882  call    cs:__imp_SRCacheContext_Close
0x18003a889  nop     dword ptr [rax+rax+00h]
0x18003a88e  mov     eax, ebx
0x18003a890  jmp     loc_18003AA70
0x18003a895  cmp     [rsp+290h+var_270], r14b
0x18003a89a  jnz     short loc_18003A8A8
0x18003a89c  mov     ebx, 80670012h
0x18003a8a1  mov     edx, 0C2h
0x18003a8a6  jmp     short loc_18003A85D
0x18003a8a8  xor     edx, edx; Val
0x18003a8aa  mov     [rsp+290h+var_250], r14
0x18003a8af  mov     r8d, 200h; Size
0x18003a8b5  lea     rcx, [rsp+290h+var_248]; void *
0x18003a8ba  call    memset_0
0x18003a8bf  lea     rax, [rsp+290h+var_248]
0x18003a8c4  mov     [rbp+190h+var_48], r14
0x18003a8cb  mov     rdx, rsi; unsigned __int16 *
0x18003a8ce  mov     [rbp+190h+var_38], rax
0x18003a8d5  lea     rcx, [rsp+290h+var_250]; this
0x18003a8da  mov     [rbp+190h+var_40], 100h
0x18003a8e5  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003a8ea  mov     ebx, eax
0x18003a8ec  test    eax, eax
0x18003a8ee  jns     short loc_18003A92F
0x18003a8f0  mov     rcx, [rbp+198h]; this
0x18003a8f7  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003a8fe  mov     r9d, eax; char *
0x18003a901  mov     edx, 0C5h; void *
0x18003a906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a90b  mov     rcx, [rsp+290h+var_250]
0x18003a910  mov     [rsp+290h+var_250], r14
0x18003a915  test    rcx, rcx
0x18003a918  jz      loc_18003A873
0x18003a91e  call    cs:__imp_SRCache_Free
0x18003a925  nop     dword ptr [rax+rax+00h]
0x18003a92a  jmp     loc_18003A873
0x18003a92f  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x18003a936  lea     r9, [rsp+290h+var_270]; bool *
0x18003a93b  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003a940  mov     [rsp+290h+var_260], r14
0x18003a945  lea     rcx, [rsp+290h+var_260]; this
0x18003a94a  mov     [rsp+290h+var_270], r14b; int
0x18003a94f  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003a954  mov     ebx, eax
0x18003a956  test    eax, eax
0x18003a958  jns     short loc_18003A995
0x18003a95a  mov     edx, 0C9h; void *
0x18003a95f  mov     rcx, [rbp+198h]; this
0x18003a966  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003a96d  mov     r9d, ebx; char *
0x18003a970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a975  mov     rcx, [rsp+290h+var_260]
0x18003a97a  mov     [rsp+290h+var_260], r14
0x18003a97f  test    rcx, rcx
0x18003a982  jz      short loc_18003A90B
0x18003a984  call    cs:__imp_SRCacheContext_Close
0x18003a98b  nop     dword ptr [rax+rax+00h]
0x18003a990  jmp     loc_18003A90B
0x18003a995  cmp     [rsp+290h+var_270], r14b
0x18003a99a  jz      short loc_18003A9DA
0x18003a99c  mov     rcx, [rsp+290h+var_260]
0x18003a9a1  mov     r8, rdi
0x18003a9a4  xor     edx, edx
0x18003a9a6  call    cs:__imp_SRCacheContext_EnumerateData
0x18003a9ad  nop     dword ptr [rax+rax+00h]
0x18003a9b2  mov     ebx, eax
0x18003a9b4  test    eax, eax
0x18003a9b6  jns     short loc_18003A9DA
0x18003a9b8  mov     rcx, [rbp+198h]; this
0x18003a9bf  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003a9c6  mov     r9d, eax; char *
0x18003a9c9  mov     edx, 2A6h; void *
0x18003a9ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a9d3  mov     edx, 0CCh
0x18003a9d8  jmp     short loc_18003A95F
0x18003a9da  mov     rcx, [rsp+290h+var_268]
0x18003a9df  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18003a9e6  call    cs:__imp_SRCacheContext_AddToCache
0x18003a9ed  nop     dword ptr [rax+rax+00h]
0x18003a9f2  mov     ebx, eax
0x18003a9f4  test    eax, eax
0x18003a9f6  jns     short loc_18003AA1D
0x18003a9f8  mov     rcx, [rbp+198h]; this
0x18003a9ff  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003aa06  mov     r9d, eax; char *
0x18003aa09  mov     edx, 1A6h; void *
0x18003aa0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa13  mov     edx, 0CFh
0x18003aa18  jmp     loc_18003A95F
0x18003aa1d  mov     rcx, [rsp+290h+var_260]
0x18003aa22  mov     [rsp+290h+var_260], r14
0x18003aa27  test    rcx, rcx
0x18003aa2a  jz      short loc_18003AA38
0x18003aa2c  call    cs:__imp_SRCacheContext_Close
0x18003aa33  nop     dword ptr [rax+rax+00h]
0x18003aa38  mov     rcx, [rsp+290h+var_250]
0x18003aa3d  mov     [rsp+290h+var_250], r14
0x18003aa42  test    rcx, rcx
0x18003aa45  jz      short loc_18003AA53
0x18003aa47  call    cs:__imp_SRCache_Free
0x18003aa4e  nop     dword ptr [rax+rax+00h]
0x18003aa53  mov     rcx, [rsp+290h+var_268]
0x18003aa58  mov     [rsp+290h+var_268], r14
0x18003aa5d  test    rcx, rcx
0x18003aa60  jz      short loc_18003AA6E
0x18003aa62  call    cs:__imp_SRCacheContext_Close
0x18003aa69  nop     dword ptr [rax+rax+00h]
0x18003aa6e  xor     eax, eax
0x18003aa70  mov     rcx, [rbp+190h+var_30]
0x18003aa77  xor     rcx, rsp; StackCookie
0x18003aa7a  call    __security_check_cookie
0x18003aa7f  add     rsp, 270h
0x18003aa86  pop     r14
0x18003aa88  pop     rdi
0x18003aa89  pop     rsi
0x18003aa8a  pop     rbx
0x18003aa8b  pop     rbp
0x18003aa8c  retn
```
