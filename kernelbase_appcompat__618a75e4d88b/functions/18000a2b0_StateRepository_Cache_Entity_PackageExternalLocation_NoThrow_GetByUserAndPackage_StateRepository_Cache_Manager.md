# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18000a2b0`
- end: `0x18000a683`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `979`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180009e40`
- `0x18000a208`
- `0x18006bf30`

## callees

- `0x18000a2b0`
- `0x18000a690`
- `0x18000a8e4`
- `0x18005b2c4`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000a583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000a583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a40e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a40e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a31c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a31c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a346`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a438`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a48c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a4c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a56b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a346`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a438`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a48c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a4c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a56b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a4a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a550`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a4a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a550`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000a46b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000a46b`

## string_xrefs

- `0x18000a517`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a5ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a5ef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a636`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a4f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a5a0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a60a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a65b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  unsigned __int16 v10; // dx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v24[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  int *v26; // [rsp+30h] [rbp-D0h]
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  char v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+258h] [rbp+158h]
  __int64 v32; // [rsp+260h] [rbp+160h]
  _BYTE *v33; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      v24[0]);
    return (unsigned int)v8;
  }
  v7 = *(_QWORD *)a1;
  v26 = v24;
  *(_QWORD *)v24 = 0;
  v27 = 0;
  v28 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageExternalLocation\\Index\\UserAndPackage", 0, &v27);
  if ( v28 )
  {
    v9 = *(_QWORD *)v26;
    *(_QWORD *)v26 = v27;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v23 = 185;
    goto LABEL_36;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    v23 = 186;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
LABEL_28:
    v20 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v20 )
      SRCacheContext_Close(v20);
    return (unsigned int)v8;
  }
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v31 = 0;
  v33 = v30;
  v32 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v29, a2);
  if ( v8 < 0 )
  {
    v22 = 189;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
LABEL_26:
    v19 = v29;
    v29 = 0;
    if ( v19 )
      SRCache_Free(v19);
    goto LABEL_28;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v29, v10);
  if ( v8 < 0 )
  {
    v22 = 190;
    goto LABEL_34;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v29, a3);
  if ( v8 < 0 )
  {
    v22 = 191;
    goto LABEL_34;
  }
  v26 = (int *)&v25;
  v25 = 0;
  v27 = 0;
  v28 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v24, v33, 0, &v27);
  if ( v28 )
  {
    v11 = *(_QWORD *)v26;
    *(_QWORD *)v26 = v27;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v17 = 195;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCacheContext_Close(v18);
    goto LABEL_26;
  }
  if ( v25 )
  {
    v21 = SRCacheContext_EnumerateData(v25, 0, a4);
    v8 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v21,
        v24[0]);
      v17 = 198;
      goto LABEL_24;
    }
  }
  v12 = SRCacheContext_AddToCache(*(_QWORD *)v24, L"PackageExternalLocation\\Index\\UserAndPackage");
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v24[0]);
    v17 = 201;
    goto LABEL_24;
  }
  v13 = v25;
  v25 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  v14 = v29;
  v29 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18000a2b0  push    rbp
0x18000a2b2  push    rbx
0x18000a2b3  push    rsi
0x18000a2b4  push    rdi
0x18000a2b5  push    r14
0x18000a2b7  push    r15
0x18000a2b9  lea     rbp, [rsp-188h]
0x18000a2c1  sub     rsp, 288h
0x18000a2c8  mov     rax, cs:__security_cookie
0x18000a2cf  xor     rax, rsp
0x18000a2d2  mov     [rbp+1B0h+var_40], rax
0x18000a2d9  xor     r15d, r15d
0x18000a2dc  mov     rsi, r9
0x18000a2df  mov     [r9], r15
0x18000a2e2  mov     rdi, r8
0x18000a2e5  mov     r14, rdx
0x18000a2e8  test    r8, r8
0x18000a2eb  jz      loc_18000A62F
0x18000a2f1  mov     rcx, [rcx]
0x18000a2f4  lea     rax, [rsp+2B0h+var_290]
0x18000a2f9  lea     r9, [rsp+2B0h+var_278]
0x18000a2fe  mov     [rsp+2B0h+var_280], rax
0x18000a303  xor     r8d, r8d
0x18000a306  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18000a30b  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18000a312  mov     [rsp+2B0h+var_278], r15
0x18000a317  mov     [rsp+2B0h+var_270], 1
0x18000a31c  call    cs:__imp_SRCacheContext_Open
0x18000a323  nop     dword ptr [rax+rax+00h]
0x18000a328  mov     ebx, eax
0x18000a32a  cmp     [rsp+2B0h+var_270], r15b
0x18000a32f  jz      short loc_18000A352
0x18000a331  mov     r8, [rsp+2B0h+var_280]
0x18000a336  mov     rdx, [rsp+2B0h+var_278]
0x18000a33b  mov     rcx, [r8]
0x18000a33e  mov     [r8], rdx
0x18000a341  test    rcx, rcx
0x18000a344  jz      short loc_18000A352
0x18000a346  call    cs:__imp_SRCacheContext_Close
0x18000a34d  nop     dword ptr [rax+rax+00h]
0x18000a352  test    ebx, ebx
0x18000a354  js      loc_18000A654
0x18000a35a  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18000a35f  setnz   al
0x18000a362  test    al, al
0x18000a364  jz      loc_18000A5DE
0x18000a36a  xor     edx, edx; Val
0x18000a36c  mov     [rsp+2B0h+var_260], r15
0x18000a371  mov     r8d, 200h; Size
0x18000a377  lea     rcx, [rsp+2B0h+var_258]; void *
0x18000a37c  call    memset_0
0x18000a381  lea     rax, [rsp+2B0h+var_258]
0x18000a386  mov     [rbp+1B0h+var_58], r15
0x18000a38d  mov     rdx, r14; unsigned __int64
0x18000a390  mov     [rbp+1B0h+var_48], rax
0x18000a397  lea     rcx, [rsp+2B0h+var_260]; this
0x18000a39c  mov     [rbp+1B0h+var_50], 100h
0x18000a3a7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18000a3ac  mov     ebx, eax
0x18000a3ae  test    eax, eax
0x18000a3b0  js      loc_18000A5BE
0x18000a3b6  lea     rcx, [rsp+2B0h+var_260]; this
0x18000a3bb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18000a3c0  mov     ebx, eax
0x18000a3c2  test    eax, eax
0x18000a3c4  js      loc_18000A679
0x18000a3ca  mov     rdx, rdi; unsigned __int64
0x18000a3cd  lea     rcx, [rsp+2B0h+var_260]; this
0x18000a3d2  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18000a3d7  mov     ebx, eax
0x18000a3d9  test    eax, eax
0x18000a3db  js      loc_18000A628
0x18000a3e1  mov     rdx, [rbp+1B0h+var_48]
0x18000a3e8  lea     rax, [rsp+2B0h+var_288]
0x18000a3ed  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a3f2  lea     r9, [rsp+2B0h+var_278]
0x18000a3f7  xor     r8d, r8d
0x18000a3fa  mov     [rsp+2B0h+var_280], rax
0x18000a3ff  mov     [rsp+2B0h+var_288], r15
0x18000a404  mov     [rsp+2B0h+var_278], r15
0x18000a409  mov     [rsp+2B0h+var_270], 1
0x18000a40e  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000a415  nop     dword ptr [rax+rax+00h]
0x18000a41a  mov     ebx, eax
0x18000a41c  cmp     [rsp+2B0h+var_270], r15b
0x18000a421  jz      short loc_18000A444
0x18000a423  mov     r8, [rsp+2B0h+var_280]
0x18000a428  mov     rdx, [rsp+2B0h+var_278]
0x18000a42d  mov     rcx, [r8]
0x18000a430  mov     [r8], rdx
0x18000a433  test    rcx, rcx
0x18000a436  jz      short loc_18000A444
0x18000a438  call    cs:__imp_SRCacheContext_Close
0x18000a43f  nop     dword ptr [rax+rax+00h]
0x18000a444  test    ebx, ebx
0x18000a446  js      loc_18000A603
0x18000a44c  mov     rcx, [rsp+2B0h+var_288]
0x18000a451  test    rcx, rcx
0x18000a454  setnz   al
0x18000a457  test    al, al
0x18000a459  jnz     loc_18000A57E
0x18000a45f  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a464  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18000a46b  call    cs:__imp_SRCacheContext_AddToCache
0x18000a472  nop     dword ptr [rax+rax+00h]
0x18000a477  mov     ebx, eax
0x18000a479  test    eax, eax
0x18000a47b  js      short loc_18000A4F0
0x18000a47d  mov     rcx, [rsp+2B0h+var_288]
0x18000a482  mov     [rsp+2B0h+var_288], r15
0x18000a487  test    rcx, rcx
0x18000a48a  jz      short loc_18000A498
0x18000a48c  call    cs:__imp_SRCacheContext_Close
0x18000a493  nop     dword ptr [rax+rax+00h]
0x18000a498  mov     rcx, [rsp+2B0h+var_260]
0x18000a49d  mov     [rsp+2B0h+var_260], r15
0x18000a4a2  test    rcx, rcx
0x18000a4a5  jz      short loc_18000A4B3
0x18000a4a7  call    cs:__imp_SRCache_Free
0x18000a4ae  nop     dword ptr [rax+rax+00h]
0x18000a4b3  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a4b8  mov     qword ptr [rsp+2B0h+var_290], r15
0x18000a4bd  test    rcx, rcx
0x18000a4c0  jz      short loc_18000A4CE
0x18000a4c2  call    cs:__imp_SRCacheContext_Close
0x18000a4c9  nop     dword ptr [rax+rax+00h]
0x18000a4ce  xor     eax, eax
0x18000a4d0  mov     rcx, [rbp+1B0h+var_40]
0x18000a4d7  xor     rcx, rsp; StackCookie
0x18000a4da  call    __security_check_cookie
0x18000a4df  add     rsp, 288h
0x18000a4e6  pop     r15
0x18000a4e8  pop     r14
0x18000a4ea  pop     rdi
0x18000a4eb  pop     rsi
0x18000a4ec  pop     rbx
0x18000a4ed  pop     rbp
0x18000a4ee  retn
0x18000a4f0  mov     rcx, [rbp+1B8h]; this
0x18000a4f7  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a4fe  mov     r9d, ebx; char *
0x18000a501  mov     edx, 1A6h; void *
0x18000a506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a50b  mov     edx, 0C9h; void *
0x18000a510  mov     rcx, [rbp+1B8h]; this
0x18000a517  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a51e  mov     r9d, ebx; char *
0x18000a521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a526  mov     rcx, [rsp+2B0h+var_288]
0x18000a52b  mov     [rsp+2B0h+var_288], r15
0x18000a530  test    rcx, rcx
0x18000a533  jz      short loc_18000A541
0x18000a535  call    cs:__imp_SRCacheContext_Close
0x18000a53c  nop     dword ptr [rax+rax+00h]
0x18000a541  mov     rcx, [rsp+2B0h+var_260]
0x18000a546  mov     [rsp+2B0h+var_260], r15
0x18000a54b  test    rcx, rcx
0x18000a54e  jz      short loc_18000A55C
0x18000a550  call    cs:__imp_SRCache_Free
0x18000a557  nop     dword ptr [rax+rax+00h]
0x18000a55c  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000a561  mov     qword ptr [rsp+2B0h+var_290], r15
0x18000a566  test    rcx, rcx
0x18000a569  jz      short loc_18000A577
0x18000a56b  call    cs:__imp_SRCacheContext_Close
0x18000a572  nop     dword ptr [rax+rax+00h]
0x18000a577  mov     eax, ebx
0x18000a579  jmp     loc_18000A4D0
0x18000a57e  mov     r8, rsi
0x18000a581  xor     edx, edx
0x18000a583  call    cs:__imp_SRCacheContext_EnumerateData
0x18000a58a  nop     dword ptr [rax+rax+00h]
0x18000a58f  mov     ebx, eax
0x18000a591  test    eax, eax
0x18000a593  jns     loc_18000A45F
0x18000a599  mov     rcx, [rbp+1B8h]; this
0x18000a5a0  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a5a7  mov     r9d, eax; char *
0x18000a5aa  mov     edx, 2A6h; void *
0x18000a5af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5b4  mov     edx, 0C6h
0x18000a5b9  jmp     loc_18000A510
0x18000a5be  mov     edx, 0BDh; void *
0x18000a5c3  mov     rcx, [rbp+1B8h]; this
0x18000a5ca  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a5d1  mov     r9d, ebx; char *
0x18000a5d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5d9  jmp     loc_18000A541
0x18000a5de  mov     ebx, 80670012h
0x18000a5e3  mov     edx, 0BAh; void *
0x18000a5e8  mov     rcx, [rbp+1B8h]; this
0x18000a5ef  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a5f6  mov     r9d, ebx; char *
0x18000a5f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5fe  jmp     loc_18000A55C
0x18000a603  mov     rcx, [rbp+1B8h]; this
0x18000a60a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a611  mov     r9d, ebx; char *
0x18000a614  mov     edx, 1B0h; void *
0x18000a619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a61e  mov     edx, 0C3h
0x18000a623  jmp     loc_18000A510
0x18000a628  mov     edx, 0BFh
0x18000a62d  jmp     short loc_18000A5C3
0x18000a62f  mov     rcx, [rbp+1B8h]; this
0x18000a636  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a63d  mov     ebx, 80070057h
0x18000a642  mov     edx, 0B5h; void *
0x18000a647  mov     r9d, ebx; char *
0x18000a64a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a64f  jmp     loc_18000A577
0x18000a654  mov     rcx, [rbp+1B8h]; this
0x18000a65b  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a662  mov     r9d, ebx; char *
0x18000a665  mov     edx, 18Ch; void *
0x18000a66a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a66f  mov     edx, 0B9h
0x18000a674  jmp     loc_18000A5E8
0x18000a679  mov     edx, 0BEh
0x18000a67e  jmp     loc_18000A5C3
```
