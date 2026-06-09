# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18003b3a4`
- end: `0x18003b699`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003b6a0`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x1800395bc`
- `0x18003b3a4`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b45b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b58d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b66b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b45b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b58d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b66b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003b5af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003b5af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b4f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b650`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b4f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b650`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003b5ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003b5ef`

## string_xrefs

- `0x18003b5c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003b608`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003b3e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003b43d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003b4d0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003b56b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
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
  if ( !a3 )
  {
    appended = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      *(int *)v20);
    return (unsigned int)appended;
  }
  v20[0] = 0;
  v21 = 0;
  appended = StateRepository::Cache::Context_NoThrow::Open(
               (StateRepository::Cache::Context_NoThrow *)&v21,
               a1,
               L"PackageExternalLocation\\Index\\UserAndPackage",
               v20);
  if ( appended < 0 )
  {
    v9 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v9 = 186;
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
    v11 = 189;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v11 = 190;
    goto LABEL_13;
  }
  appended = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( appended < 0 )
  {
    v11 = 191;
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
    v13 = 195;
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
      v13 = 198;
      goto LABEL_22;
    }
  }
  v16 = SRCacheContext_AddToCache(v21, L"PackageExternalLocation\\Index\\UserAndPackage");
  appended = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v20);
    v13 = 201;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x18003b3a4  push    rbp
0x18003b3a6  push    rbx
0x18003b3a7  push    rsi
0x18003b3a8  push    rdi
0x18003b3a9  push    r14
0x18003b3ab  push    r15
0x18003b3ad  lea     rbp, [rsp-178h]
0x18003b3b5  sub     rsp, 278h
0x18003b3bc  mov     rax, cs:__security_cookie
0x18003b3c3  xor     rax, rsp
0x18003b3c6  mov     [rbp+1A0h+var_40], rax
0x18003b3cd  xor     r15d, r15d
0x18003b3d0  mov     rsi, r9
0x18003b3d3  mov     [r9], r15
0x18003b3d6  mov     rdi, r8
0x18003b3d9  mov     r14, rdx
0x18003b3dc  test    r8, r8
0x18003b3df  jnz     short loc_18003B408
0x18003b3e1  mov     rcx, [rbp+1A8h]; this
0x18003b3e8  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b3ef  mov     ebx, 80070057h
0x18003b3f4  mov     edx, 0B5h; void *
0x18003b3f9  mov     r9d, ebx; char *
0x18003b3fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b401  mov     eax, ebx
0x18003b403  jmp     loc_18003B679
0x18003b408  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003b40b  mov     [rsp+2A0h+var_280], r15b; int
0x18003b410  lea     rcx, [rsp+2A0h+var_278]; this
0x18003b415  mov     [rsp+2A0h+var_278], r15
0x18003b41a  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003b41f  lea     r8, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18003b426  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003b42b  mov     ebx, eax
0x18003b42d  test    eax, eax
0x18003b42f  jns     short loc_18003B469
0x18003b431  mov     edx, 0B9h; void *
0x18003b436  mov     rcx, [rbp+1A8h]; this
0x18003b43d  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b444  mov     r9d, ebx; char *
0x18003b447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b44c  mov     rcx, [rsp+2A0h+var_278]
0x18003b451  mov     [rsp+2A0h+var_278], r15
0x18003b456  test    rcx, rcx
0x18003b459  jz      short loc_18003B401
0x18003b45b  call    cs:__imp_SRCacheContext_Close
0x18003b462  nop     dword ptr [rax+rax+00h]
0x18003b467  jmp     short loc_18003B401
0x18003b469  cmp     [rsp+2A0h+var_280], r15b
0x18003b46e  jnz     short loc_18003B47C
0x18003b470  mov     ebx, 80670012h
0x18003b475  mov     edx, 0BAh
0x18003b47a  jmp     short loc_18003B436
0x18003b47c  xor     edx, edx; Val
0x18003b47e  mov     [rsp+2A0h+var_260], r15
0x18003b483  mov     r8d, 200h; Size
0x18003b489  lea     rcx, [rsp+2A0h+var_258]; void *
0x18003b48e  call    memset_0
0x18003b493  lea     rax, [rsp+2A0h+var_258]
0x18003b498  mov     [rbp+1A0h+var_58], r15
0x18003b49f  mov     rdx, r14; __int64
0x18003b4a2  mov     [rbp+1A0h+var_48], rax
0x18003b4a9  lea     rcx, [rsp+2A0h+var_260]; this
0x18003b4ae  mov     [rbp+1A0h+var_50], 100h
0x18003b4b9  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003b4be  mov     ebx, eax
0x18003b4c0  test    eax, eax
0x18003b4c2  jns     short loc_18003B503
0x18003b4c4  mov     edx, 0BDh; void *
0x18003b4c9  mov     rcx, [rbp+1A8h]; this
0x18003b4d0  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b4d7  mov     r9d, ebx; char *
0x18003b4da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b4df  mov     rcx, [rsp+2A0h+var_260]
0x18003b4e4  mov     [rsp+2A0h+var_260], r15
0x18003b4e9  test    rcx, rcx
0x18003b4ec  jz      loc_18003B44C
0x18003b4f2  call    cs:__imp_SRCache_Free
0x18003b4f9  nop     dword ptr [rax+rax+00h]
0x18003b4fe  jmp     loc_18003B44C
0x18003b503  lea     rcx, [rsp+2A0h+var_260]; this
0x18003b508  call    ?AppendDelimiter@Key_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Key_NoThrow::AppendDelimiter(void)
0x18003b50d  mov     ebx, eax
0x18003b50f  test    eax, eax
0x18003b511  jns     short loc_18003B51A
0x18003b513  mov     edx, 0BEh
0x18003b518  jmp     short loc_18003B4C9
0x18003b51a  mov     rdx, rdi; __int64
0x18003b51d  lea     rcx, [rsp+2A0h+var_260]; this
0x18003b522  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003b527  mov     ebx, eax
0x18003b529  test    eax, eax
0x18003b52b  jns     short loc_18003B534
0x18003b52d  mov     edx, 0BFh
0x18003b532  jmp     short loc_18003B4C9
0x18003b534  mov     r8, [rbp+1A0h+var_48]; unsigned __int16 *
0x18003b53b  lea     r9, [rsp+2A0h+var_280]; bool *
0x18003b540  lea     rdx, [rsp+2A0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18003b545  mov     [rsp+2A0h+var_270], r15
0x18003b54a  lea     rcx, [rsp+2A0h+var_270]; this
0x18003b54f  mov     [rsp+2A0h+var_280], r15b; int
0x18003b554  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003b559  mov     ebx, eax
0x18003b55b  test    eax, eax
0x18003b55d  jns     short loc_18003B59E
0x18003b55f  mov     edx, 0C3h; void *
0x18003b564  mov     rcx, [rbp+1A8h]; this
0x18003b56b  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b572  mov     r9d, ebx; char *
0x18003b575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b57a  mov     rcx, [rsp+2A0h+var_270]
0x18003b57f  mov     [rsp+2A0h+var_270], r15
0x18003b584  test    rcx, rcx
0x18003b587  jz      loc_18003B4DF
0x18003b58d  call    cs:__imp_SRCacheContext_Close
0x18003b594  nop     dword ptr [rax+rax+00h]
0x18003b599  jmp     loc_18003B4DF
0x18003b59e  cmp     [rsp+2A0h+var_280], r15b
0x18003b5a3  jz      short loc_18003B5E3
0x18003b5a5  mov     rcx, [rsp+2A0h+var_270]
0x18003b5aa  mov     r8, rsi
0x18003b5ad  xor     edx, edx
0x18003b5af  call    cs:__imp_SRCacheContext_EnumerateData
0x18003b5b6  nop     dword ptr [rax+rax+00h]
0x18003b5bb  mov     ebx, eax
0x18003b5bd  test    eax, eax
0x18003b5bf  jns     short loc_18003B5E3
0x18003b5c1  mov     rcx, [rbp+1A8h]; this
0x18003b5c8  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b5cf  mov     r9d, eax; char *
0x18003b5d2  mov     edx, 2A6h; void *
0x18003b5d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b5dc  mov     edx, 0C6h
0x18003b5e1  jmp     short loc_18003B564
0x18003b5e3  mov     rcx, [rsp+2A0h+var_278]
0x18003b5e8  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18003b5ef  call    cs:__imp_SRCacheContext_AddToCache
0x18003b5f6  nop     dword ptr [rax+rax+00h]
0x18003b5fb  mov     ebx, eax
0x18003b5fd  test    eax, eax
0x18003b5ff  jns     short loc_18003B626
0x18003b601  mov     rcx, [rbp+1A8h]; this
0x18003b608  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b60f  mov     r9d, eax; char *
0x18003b612  mov     edx, 1A6h; void *
0x18003b617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b61c  mov     edx, 0C9h
0x18003b621  jmp     loc_18003B564
0x18003b626  mov     rcx, [rsp+2A0h+var_270]
0x18003b62b  mov     [rsp+2A0h+var_270], r15
0x18003b630  test    rcx, rcx
0x18003b633  jz      short loc_18003B641
0x18003b635  call    cs:__imp_SRCacheContext_Close
0x18003b63c  nop     dword ptr [rax+rax+00h]
0x18003b641  mov     rcx, [rsp+2A0h+var_260]
0x18003b646  mov     [rsp+2A0h+var_260], r15
0x18003b64b  test    rcx, rcx
0x18003b64e  jz      short loc_18003B65C
0x18003b650  call    cs:__imp_SRCache_Free
0x18003b657  nop     dword ptr [rax+rax+00h]
0x18003b65c  mov     rcx, [rsp+2A0h+var_278]
0x18003b661  mov     [rsp+2A0h+var_278], r15
0x18003b666  test    rcx, rcx
0x18003b669  jz      short loc_18003B677
0x18003b66b  call    cs:__imp_SRCacheContext_Close
0x18003b672  nop     dword ptr [rax+rax+00h]
0x18003b677  xor     eax, eax
0x18003b679  mov     rcx, [rbp+1A0h+var_40]
0x18003b680  xor     rcx, rsp; StackCookie
0x18003b683  call    __security_check_cookie
0x18003b688  add     rsp, 278h
0x18003b68f  pop     r15
0x18003b691  pop     r14
0x18003b693  pop     rdi
0x18003b694  pop     rsi
0x18003b695  pop     rbx
0x18003b696  pop     rbp
0x18003b697  retn
```
