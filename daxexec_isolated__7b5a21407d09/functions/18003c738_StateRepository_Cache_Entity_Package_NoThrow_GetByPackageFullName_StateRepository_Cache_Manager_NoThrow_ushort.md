# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18003c738`
- end: `0x18003c9ca`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18003f588`
- `0x18003f8a8`
- `0x18009a0b4`
- `0x1800ba1ec`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003c738`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c7be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c8c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c968`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c99e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c7be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c8c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c968`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c99e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c983`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c983`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003c8e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003c8e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003c922`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003c922`

## string_xrefs

- `0x18003c8fb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003c93b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003c7a0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003c833`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003c8a2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

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
    v6 = 1128;
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
    v6 = 1129;
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
      (void *)0x46C,
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
    v11 = 1136;
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
      v11 = 1139;
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
    v11 = 1142;
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
0x18003c738  push    rbp
0x18003c73a  push    rbx
0x18003c73b  push    rsi
0x18003c73c  push    rdi
0x18003c73d  push    r14
0x18003c73f  lea     rbp, [rsp-170h]
0x18003c747  sub     rsp, 270h
0x18003c74e  mov     rax, cs:__security_cookie
0x18003c755  xor     rax, rsp
0x18003c758  mov     [rbp+190h+var_30], rax
0x18003c75f  xor     r14d, r14d
0x18003c762  lea     r9, [rsp+290h+var_270]; bool *
0x18003c767  mov     rsi, rdx
0x18003c76a  mov     [r8], r14
0x18003c76d  mov     rdi, r8
0x18003c770  mov     [rsp+290h+var_270], r14b; int
0x18003c775  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003c778  mov     [rsp+290h+var_268], r14
0x18003c77d  lea     r8, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18003c784  lea     rcx, [rsp+290h+var_268]; this
0x18003c789  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003c78e  mov     ebx, eax
0x18003c790  test    eax, eax
0x18003c792  jns     short loc_18003C7D1
0x18003c794  mov     edx, 468h; void *
0x18003c799  mov     rcx, [rbp+198h]; this
0x18003c7a0  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c7a7  mov     r9d, ebx; char *
0x18003c7aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7af  mov     rcx, [rsp+290h+var_268]
0x18003c7b4  mov     [rsp+290h+var_268], r14
0x18003c7b9  test    rcx, rcx
0x18003c7bc  jz      short loc_18003C7CA
0x18003c7be  call    cs:__imp_SRCacheContext_Close
0x18003c7c5  nop     dword ptr [rax+rax+00h]
0x18003c7ca  mov     eax, ebx
0x18003c7cc  jmp     loc_18003C9AC
0x18003c7d1  cmp     [rsp+290h+var_270], r14b
0x18003c7d6  jnz     short loc_18003C7E4
0x18003c7d8  mov     ebx, 80670012h
0x18003c7dd  mov     edx, 469h
0x18003c7e2  jmp     short loc_18003C799
0x18003c7e4  xor     edx, edx; Val
0x18003c7e6  mov     [rsp+290h+var_250], r14
0x18003c7eb  mov     r8d, 200h; Size
0x18003c7f1  lea     rcx, [rsp+290h+var_248]; void *
0x18003c7f6  call    memset_0
0x18003c7fb  lea     rax, [rsp+290h+var_248]
0x18003c800  mov     [rbp+190h+var_48], r14
0x18003c807  mov     rdx, rsi; unsigned __int16 *
0x18003c80a  mov     [rbp+190h+var_38], rax
0x18003c811  lea     rcx, [rsp+290h+var_250]; this
0x18003c816  mov     [rbp+190h+var_40], 100h
0x18003c821  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003c826  mov     ebx, eax
0x18003c828  test    eax, eax
0x18003c82a  jns     short loc_18003C86B
0x18003c82c  mov     rcx, [rbp+198h]; this
0x18003c833  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c83a  mov     r9d, eax; char *
0x18003c83d  mov     edx, 46Ch; void *
0x18003c842  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c847  mov     rcx, [rsp+290h+var_250]
0x18003c84c  mov     [rsp+290h+var_250], r14
0x18003c851  test    rcx, rcx
0x18003c854  jz      loc_18003C7AF
0x18003c85a  call    cs:__imp_SRCache_Free
0x18003c861  nop     dword ptr [rax+rax+00h]
0x18003c866  jmp     loc_18003C7AF
0x18003c86b  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x18003c872  lea     r9, [rsp+290h+var_270]; bool *
0x18003c877  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003c87c  mov     [rsp+290h+var_260], r14
0x18003c881  lea     rcx, [rsp+290h+var_260]; this
0x18003c886  mov     [rsp+290h+var_270], r14b; int
0x18003c88b  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003c890  mov     ebx, eax
0x18003c892  test    eax, eax
0x18003c894  jns     short loc_18003C8D1
0x18003c896  mov     edx, 470h; void *
0x18003c89b  mov     rcx, [rbp+198h]; this
0x18003c8a2  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c8a9  mov     r9d, ebx; char *
0x18003c8ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c8b1  mov     rcx, [rsp+290h+var_260]
0x18003c8b6  mov     [rsp+290h+var_260], r14
0x18003c8bb  test    rcx, rcx
0x18003c8be  jz      short loc_18003C847
0x18003c8c0  call    cs:__imp_SRCacheContext_Close
0x18003c8c7  nop     dword ptr [rax+rax+00h]
0x18003c8cc  jmp     loc_18003C847
0x18003c8d1  cmp     [rsp+290h+var_270], r14b
0x18003c8d6  jz      short loc_18003C916
0x18003c8d8  mov     rcx, [rsp+290h+var_260]
0x18003c8dd  mov     r8, rdi
0x18003c8e0  xor     edx, edx
0x18003c8e2  call    cs:__imp_SRCacheContext_EnumerateData
0x18003c8e9  nop     dword ptr [rax+rax+00h]
0x18003c8ee  mov     ebx, eax
0x18003c8f0  test    eax, eax
0x18003c8f2  jns     short loc_18003C916
0x18003c8f4  mov     rcx, [rbp+198h]; this
0x18003c8fb  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c902  mov     r9d, eax; char *
0x18003c905  mov     edx, 2A6h; void *
0x18003c90a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c90f  mov     edx, 473h
0x18003c914  jmp     short loc_18003C89B
0x18003c916  mov     rcx, [rsp+290h+var_268]
0x18003c91b  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18003c922  call    cs:__imp_SRCacheContext_AddToCache
0x18003c929  nop     dword ptr [rax+rax+00h]
0x18003c92e  mov     ebx, eax
0x18003c930  test    eax, eax
0x18003c932  jns     short loc_18003C959
0x18003c934  mov     rcx, [rbp+198h]; this
0x18003c93b  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c942  mov     r9d, eax; char *
0x18003c945  mov     edx, 1A6h; void *
0x18003c94a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c94f  mov     edx, 476h
0x18003c954  jmp     loc_18003C89B
0x18003c959  mov     rcx, [rsp+290h+var_260]
0x18003c95e  mov     [rsp+290h+var_260], r14
0x18003c963  test    rcx, rcx
0x18003c966  jz      short loc_18003C974
0x18003c968  call    cs:__imp_SRCacheContext_Close
0x18003c96f  nop     dword ptr [rax+rax+00h]
0x18003c974  mov     rcx, [rsp+290h+var_250]
0x18003c979  mov     [rsp+290h+var_250], r14
0x18003c97e  test    rcx, rcx
0x18003c981  jz      short loc_18003C98F
0x18003c983  call    cs:__imp_SRCache_Free
0x18003c98a  nop     dword ptr [rax+rax+00h]
0x18003c98f  mov     rcx, [rsp+290h+var_268]
0x18003c994  mov     [rsp+290h+var_268], r14
0x18003c999  test    rcx, rcx
0x18003c99c  jz      short loc_18003C9AA
0x18003c99e  call    cs:__imp_SRCacheContext_Close
0x18003c9a5  nop     dword ptr [rax+rax+00h]
0x18003c9aa  xor     eax, eax
0x18003c9ac  mov     rcx, [rbp+190h+var_30]
0x18003c9b3  xor     rcx, rsp; StackCookie
0x18003c9b6  call    __security_check_cookie
0x18003c9bb  add     rsp, 270h
0x18003c9c2  pop     r14
0x18003c9c4  pop     rdi
0x18003c9c5  pop     rsi
0x18003c9c6  pop     rbx
0x18003c9c7  pop     rbp
0x18003c9c8  retn
```
