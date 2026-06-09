# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18003aa94`
- end: `0x18003ad26`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003ad2c`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x18003aa94`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ab1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ac1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003acc4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003acfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ab1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ac1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003acc4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003acfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003ac3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003ac3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abb6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003acdf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abb6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003acdf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003ac7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003ac7e`

## string_xrefs

- `0x18003ac57`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003ac97`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003aafc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003ab8f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003abfe`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
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
         L"Package\\Index\\PackageFullName",
         v18);
  if ( v5 < 0 )
  {
    v6 = 1118;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v6 = 1119;
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
      (void *)0x462,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v11 = 1126;
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
      v11 = 1129;
      goto LABEL_15;
    }
  }
  v14 = SRCacheContext_AddToCache(v19, L"Package\\Index\\PackageFullName");
  v5 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      *(int *)v18);
    v11 = 1132;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
0x18003aa94  push    rbp
0x18003aa96  push    rbx
0x18003aa97  push    rsi
0x18003aa98  push    rdi
0x18003aa99  push    r14
0x18003aa9b  lea     rbp, [rsp-170h]
0x18003aaa3  sub     rsp, 270h
0x18003aaaa  mov     rax, cs:__security_cookie
0x18003aab1  xor     rax, rsp
0x18003aab4  mov     [rbp+190h+var_30], rax
0x18003aabb  xor     r14d, r14d
0x18003aabe  lea     r9, [rsp+290h+var_270]; bool *
0x18003aac3  mov     rsi, rdx
0x18003aac6  mov     [r8], r14
0x18003aac9  mov     rdi, r8
0x18003aacc  mov     [rsp+290h+var_270], r14b; int
0x18003aad1  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003aad4  mov     [rsp+290h+var_268], r14
0x18003aad9  lea     r8, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18003aae0  lea     rcx, [rsp+290h+var_268]; this
0x18003aae5  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003aaea  mov     ebx, eax
0x18003aaec  test    eax, eax
0x18003aaee  jns     short loc_18003AB2D
0x18003aaf0  mov     edx, 45Eh; void *
0x18003aaf5  mov     rcx, [rbp+198h]; this
0x18003aafc  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ab03  mov     r9d, ebx; char *
0x18003ab06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab0b  mov     rcx, [rsp+290h+var_268]
0x18003ab10  mov     [rsp+290h+var_268], r14
0x18003ab15  test    rcx, rcx
0x18003ab18  jz      short loc_18003AB26
0x18003ab1a  call    cs:__imp_SRCacheContext_Close
0x18003ab21  nop     dword ptr [rax+rax+00h]
0x18003ab26  mov     eax, ebx
0x18003ab28  jmp     loc_18003AD08
0x18003ab2d  cmp     [rsp+290h+var_270], r14b
0x18003ab32  jnz     short loc_18003AB40
0x18003ab34  mov     ebx, 80670012h
0x18003ab39  mov     edx, 45Fh
0x18003ab3e  jmp     short loc_18003AAF5
0x18003ab40  xor     edx, edx; Val
0x18003ab42  mov     [rsp+290h+var_250], r14
0x18003ab47  mov     r8d, 200h; Size
0x18003ab4d  lea     rcx, [rsp+290h+var_248]; void *
0x18003ab52  call    memset_0
0x18003ab57  lea     rax, [rsp+290h+var_248]
0x18003ab5c  mov     [rbp+190h+var_48], r14
0x18003ab63  mov     rdx, rsi; unsigned __int16 *
0x18003ab66  mov     [rbp+190h+var_38], rax
0x18003ab6d  lea     rcx, [rsp+290h+var_250]; this
0x18003ab72  mov     [rbp+190h+var_40], 100h
0x18003ab7d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003ab82  mov     ebx, eax
0x18003ab84  test    eax, eax
0x18003ab86  jns     short loc_18003ABC7
0x18003ab88  mov     rcx, [rbp+198h]; this
0x18003ab8f  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ab96  mov     r9d, eax; char *
0x18003ab99  mov     edx, 462h; void *
0x18003ab9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aba3  mov     rcx, [rsp+290h+var_250]
0x18003aba8  mov     [rsp+290h+var_250], r14
0x18003abad  test    rcx, rcx
0x18003abb0  jz      loc_18003AB0B
0x18003abb6  call    cs:__imp_SRCache_Free
0x18003abbd  nop     dword ptr [rax+rax+00h]
0x18003abc2  jmp     loc_18003AB0B
0x18003abc7  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x18003abce  lea     r9, [rsp+290h+var_270]; bool *
0x18003abd3  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003abd8  mov     [rsp+290h+var_260], r14
0x18003abdd  lea     rcx, [rsp+290h+var_260]; this
0x18003abe2  mov     [rsp+290h+var_270], r14b; int
0x18003abe7  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003abec  mov     ebx, eax
0x18003abee  test    eax, eax
0x18003abf0  jns     short loc_18003AC2D
0x18003abf2  mov     edx, 466h; void *
0x18003abf7  mov     rcx, [rbp+198h]; this
0x18003abfe  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ac05  mov     r9d, ebx; char *
0x18003ac08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac0d  mov     rcx, [rsp+290h+var_260]
0x18003ac12  mov     [rsp+290h+var_260], r14
0x18003ac17  test    rcx, rcx
0x18003ac1a  jz      short loc_18003ABA3
0x18003ac1c  call    cs:__imp_SRCacheContext_Close
0x18003ac23  nop     dword ptr [rax+rax+00h]
0x18003ac28  jmp     loc_18003ABA3
0x18003ac2d  cmp     [rsp+290h+var_270], r14b
0x18003ac32  jz      short loc_18003AC72
0x18003ac34  mov     rcx, [rsp+290h+var_260]
0x18003ac39  mov     r8, rdi
0x18003ac3c  xor     edx, edx
0x18003ac3e  call    cs:__imp_SRCacheContext_EnumerateData
0x18003ac45  nop     dword ptr [rax+rax+00h]
0x18003ac4a  mov     ebx, eax
0x18003ac4c  test    eax, eax
0x18003ac4e  jns     short loc_18003AC72
0x18003ac50  mov     rcx, [rbp+198h]; this
0x18003ac57  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ac5e  mov     r9d, eax; char *
0x18003ac61  mov     edx, 2A6h; void *
0x18003ac66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac6b  mov     edx, 469h
0x18003ac70  jmp     short loc_18003ABF7
0x18003ac72  mov     rcx, [rsp+290h+var_268]
0x18003ac77  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18003ac7e  call    cs:__imp_SRCacheContext_AddToCache
0x18003ac85  nop     dword ptr [rax+rax+00h]
0x18003ac8a  mov     ebx, eax
0x18003ac8c  test    eax, eax
0x18003ac8e  jns     short loc_18003ACB5
0x18003ac90  mov     rcx, [rbp+198h]; this
0x18003ac97  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ac9e  mov     r9d, eax; char *
0x18003aca1  mov     edx, 1A6h; void *
0x18003aca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003acab  mov     edx, 46Ch
0x18003acb0  jmp     loc_18003ABF7
0x18003acb5  mov     rcx, [rsp+290h+var_260]
0x18003acba  mov     [rsp+290h+var_260], r14
0x18003acbf  test    rcx, rcx
0x18003acc2  jz      short loc_18003ACD0
0x18003acc4  call    cs:__imp_SRCacheContext_Close
0x18003accb  nop     dword ptr [rax+rax+00h]
0x18003acd0  mov     rcx, [rsp+290h+var_250]
0x18003acd5  mov     [rsp+290h+var_250], r14
0x18003acda  test    rcx, rcx
0x18003acdd  jz      short loc_18003ACEB
0x18003acdf  call    cs:__imp_SRCache_Free
0x18003ace6  nop     dword ptr [rax+rax+00h]
0x18003aceb  mov     rcx, [rsp+290h+var_268]
0x18003acf0  mov     [rsp+290h+var_268], r14
0x18003acf5  test    rcx, rcx
0x18003acf8  jz      short loc_18003AD06
0x18003acfa  call    cs:__imp_SRCacheContext_Close
0x18003ad01  nop     dword ptr [rax+rax+00h]
0x18003ad06  xor     eax, eax
0x18003ad08  mov     rcx, [rbp+190h+var_30]
0x18003ad0f  xor     rcx, rsp; StackCookie
0x18003ad12  call    __security_check_cookie
0x18003ad17  add     rsp, 270h
0x18003ad1e  pop     r14
0x18003ad20  pop     rdi
0x18003ad21  pop     rsi
0x18003ad22  pop     rbx
0x18003ad23  pop     rbp
0x18003ad24  retn
```
