# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18003c4a0`
- end: `0x18003c732`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180041d10`
- `0x1800a0c70`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003c4a0`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c526`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c628`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c6d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c706`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c526`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c628`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c6d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c706`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c5c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c6eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c5c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c6eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003c64a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003c64a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003c68a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003c68a`

## string_xrefs

- `0x18003c663`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003c6a3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003c508`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18003c59b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18003c60a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

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
0x18003c4a0  push    rbp
0x18003c4a2  push    rbx
0x18003c4a3  push    rsi
0x18003c4a4  push    rdi
0x18003c4a5  push    r14
0x18003c4a7  lea     rbp, [rsp-170h]
0x18003c4af  sub     rsp, 270h
0x18003c4b6  mov     rax, cs:__security_cookie
0x18003c4bd  xor     rax, rsp
0x18003c4c0  mov     [rbp+190h+var_30], rax
0x18003c4c7  xor     r14d, r14d
0x18003c4ca  lea     r9, [rsp+290h+var_270]; bool *
0x18003c4cf  mov     rsi, rdx
0x18003c4d2  mov     [r8], r14
0x18003c4d5  mov     rdi, r8
0x18003c4d8  mov     [rsp+290h+var_270], r14b; int
0x18003c4dd  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003c4e0  mov     [rsp+290h+var_268], r14
0x18003c4e5  lea     r8, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18003c4ec  lea     rcx, [rsp+290h+var_268]; this
0x18003c4f1  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003c4f6  mov     ebx, eax
0x18003c4f8  test    eax, eax
0x18003c4fa  jns     short loc_18003C539
0x18003c4fc  mov     edx, 0C1h; void *
0x18003c501  mov     rcx, [rbp+198h]; this
0x18003c508  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c50f  mov     r9d, ebx; char *
0x18003c512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c517  mov     rcx, [rsp+290h+var_268]
0x18003c51c  mov     [rsp+290h+var_268], r14
0x18003c521  test    rcx, rcx
0x18003c524  jz      short loc_18003C532
0x18003c526  call    cs:__imp_SRCacheContext_Close
0x18003c52d  nop     dword ptr [rax+rax+00h]
0x18003c532  mov     eax, ebx
0x18003c534  jmp     loc_18003C714
0x18003c539  cmp     [rsp+290h+var_270], r14b
0x18003c53e  jnz     short loc_18003C54C
0x18003c540  mov     ebx, 80670012h
0x18003c545  mov     edx, 0C2h
0x18003c54a  jmp     short loc_18003C501
0x18003c54c  xor     edx, edx; Val
0x18003c54e  mov     [rsp+290h+var_250], r14
0x18003c553  mov     r8d, 200h; Size
0x18003c559  lea     rcx, [rsp+290h+var_248]; void *
0x18003c55e  call    memset_0
0x18003c563  lea     rax, [rsp+290h+var_248]
0x18003c568  mov     [rbp+190h+var_48], r14
0x18003c56f  mov     rdx, rsi; unsigned __int16 *
0x18003c572  mov     [rbp+190h+var_38], rax
0x18003c579  lea     rcx, [rsp+290h+var_250]; this
0x18003c57e  mov     [rbp+190h+var_40], 100h
0x18003c589  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003c58e  mov     ebx, eax
0x18003c590  test    eax, eax
0x18003c592  jns     short loc_18003C5D3
0x18003c594  mov     rcx, [rbp+198h]; this
0x18003c59b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c5a2  mov     r9d, eax; char *
0x18003c5a5  mov     edx, 0C5h; void *
0x18003c5aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5af  mov     rcx, [rsp+290h+var_250]
0x18003c5b4  mov     [rsp+290h+var_250], r14
0x18003c5b9  test    rcx, rcx
0x18003c5bc  jz      loc_18003C517
0x18003c5c2  call    cs:__imp_SRCache_Free
0x18003c5c9  nop     dword ptr [rax+rax+00h]
0x18003c5ce  jmp     loc_18003C517
0x18003c5d3  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x18003c5da  lea     r9, [rsp+290h+var_270]; bool *
0x18003c5df  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003c5e4  mov     [rsp+290h+var_260], r14
0x18003c5e9  lea     rcx, [rsp+290h+var_260]; this
0x18003c5ee  mov     [rsp+290h+var_270], r14b; int
0x18003c5f3  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003c5f8  mov     ebx, eax
0x18003c5fa  test    eax, eax
0x18003c5fc  jns     short loc_18003C639
0x18003c5fe  mov     edx, 0C9h; void *
0x18003c603  mov     rcx, [rbp+198h]; this
0x18003c60a  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c611  mov     r9d, ebx; char *
0x18003c614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c619  mov     rcx, [rsp+290h+var_260]
0x18003c61e  mov     [rsp+290h+var_260], r14
0x18003c623  test    rcx, rcx
0x18003c626  jz      short loc_18003C5AF
0x18003c628  call    cs:__imp_SRCacheContext_Close
0x18003c62f  nop     dword ptr [rax+rax+00h]
0x18003c634  jmp     loc_18003C5AF
0x18003c639  cmp     [rsp+290h+var_270], r14b
0x18003c63e  jz      short loc_18003C67E
0x18003c640  mov     rcx, [rsp+290h+var_260]
0x18003c645  mov     r8, rdi
0x18003c648  xor     edx, edx
0x18003c64a  call    cs:__imp_SRCacheContext_EnumerateData
0x18003c651  nop     dword ptr [rax+rax+00h]
0x18003c656  mov     ebx, eax
0x18003c658  test    eax, eax
0x18003c65a  jns     short loc_18003C67E
0x18003c65c  mov     rcx, [rbp+198h]; this
0x18003c663  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c66a  mov     r9d, eax; char *
0x18003c66d  mov     edx, 2A6h; void *
0x18003c672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c677  mov     edx, 0CCh
0x18003c67c  jmp     short loc_18003C603
0x18003c67e  mov     rcx, [rsp+290h+var_268]
0x18003c683  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18003c68a  call    cs:__imp_SRCacheContext_AddToCache
0x18003c691  nop     dword ptr [rax+rax+00h]
0x18003c696  mov     ebx, eax
0x18003c698  test    eax, eax
0x18003c69a  jns     short loc_18003C6C1
0x18003c69c  mov     rcx, [rbp+198h]; this
0x18003c6a3  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c6aa  mov     r9d, eax; char *
0x18003c6ad  mov     edx, 1A6h; void *
0x18003c6b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c6b7  mov     edx, 0CFh
0x18003c6bc  jmp     loc_18003C603
0x18003c6c1  mov     rcx, [rsp+290h+var_260]
0x18003c6c6  mov     [rsp+290h+var_260], r14
0x18003c6cb  test    rcx, rcx
0x18003c6ce  jz      short loc_18003C6DC
0x18003c6d0  call    cs:__imp_SRCacheContext_Close
0x18003c6d7  nop     dword ptr [rax+rax+00h]
0x18003c6dc  mov     rcx, [rsp+290h+var_250]
0x18003c6e1  mov     [rsp+290h+var_250], r14
0x18003c6e6  test    rcx, rcx
0x18003c6e9  jz      short loc_18003C6F7
0x18003c6eb  call    cs:__imp_SRCache_Free
0x18003c6f2  nop     dword ptr [rax+rax+00h]
0x18003c6f7  mov     rcx, [rsp+290h+var_268]
0x18003c6fc  mov     [rsp+290h+var_268], r14
0x18003c701  test    rcx, rcx
0x18003c704  jz      short loc_18003C712
0x18003c706  call    cs:__imp_SRCacheContext_Close
0x18003c70d  nop     dword ptr [rax+rax+00h]
0x18003c712  xor     eax, eax
0x18003c714  mov     rcx, [rbp+190h+var_30]
0x18003c71b  xor     rcx, rsp; StackCookie
0x18003c71e  call    __security_check_cookie
0x18003c723  add     rsp, 270h
0x18003c72a  pop     r14
0x18003c72c  pop     rdi
0x18003c72d  pop     rsi
0x18003c72e  pop     rbx
0x18003c72f  pop     rbp
0x18003c730  retn
```
