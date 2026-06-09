# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180064528`
- end: `0x18006483a`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `786`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180062a00`

## callees

- `0x18001a140`
- `0x18002c8d0`
- `0x180064528`
- `0x1800862f0`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006463a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064722`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006463a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180064722`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800645aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006464f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800646c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006470d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006479e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800645aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006464f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800646c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006470d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006479e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180064586`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180064586`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180064749`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180064749`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800646a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800646a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800646ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800646ee`

## string_xrefs

- `0x18006475c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800647d5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800647f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006481c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180064617`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18006477c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800647ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v29 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v25 = 0;
  v27 = v25;
  v28 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v28);
  if ( v29 )
  {
    v7 = v28;
    v8 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v8 )
      SRCacheContext_Close(v8, v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v24 = 193;
    goto LABEL_31;
  }
  if ( !*(_QWORD *)v25 )
  {
    v6 = -2140733422;
    v24 = 194;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v25[0]);
LABEL_10:
    v12 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v10);
    return v6;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v9,
      v25[0]);
LABEL_8:
    v11 = v30;
    v30 = 0;
    if ( v11 )
      SRCache_Free();
    goto LABEL_10;
  }
  v27 = (int *)&v26;
  v26 = 0;
  v28 = 0;
  v29 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v34, 0, &v28);
  if ( v29 )
  {
    v14 = v28;
    v15 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v15 )
      SRCacheContext_Close(v15, v14);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v22 = 201;
    goto LABEL_28;
  }
  if ( v26 )
  {
    v21 = SRCacheContext_EnumerateData(v26, 0, a3);
    v6 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v21,
        v25[0]);
      v22 = 204;
      goto LABEL_28;
    }
  }
  v16 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"PackageFamily\\Index\\PackageFamilyName");
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      v25[0]);
    v22 = 207;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v25[0]);
    v23 = v26;
    v26 = 0;
    if ( v23 )
      SRCacheContext_Close(v23, v10);
    goto LABEL_8;
  }
  v18 = v26;
  v26 = 0;
  if ( v18 )
    SRCacheContext_Close(v18, v17);
  v19 = v30;
  v30 = 0;
  if ( v19 )
    SRCache_Free();
  v20 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v20 )
    SRCacheContext_Close(v20, v17);
  return 0;
}

```

## disassembly

```asm
0x180064528  push    rbp
0x18006452a  push    rbx
0x18006452b  push    rsi
0x18006452c  push    rdi
0x18006452d  push    r14
0x18006452f  lea     rbp, [rsp-180h]
0x180064537  sub     rsp, 280h
0x18006453e  mov     rax, cs:__security_cookie
0x180064545  xor     rax, rsp
0x180064548  mov     [rbp+1A0h+var_30], rax
0x18006454f  xor     r14d, r14d
0x180064552  mov     [rsp+2A0h+var_260], 1
0x180064557  mov     [r8], r14
0x18006455a  lea     rax, [rsp+2A0h+var_280]
0x18006455f  mov     rcx, [rcx]
0x180064562  lea     r9, [rsp+2A0h+var_268]
0x180064567  mov     rdi, r8
0x18006456a  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18006456f  mov     rsi, rdx
0x180064572  mov     [rsp+2A0h+var_270], rax
0x180064577  xor     r8d, r8d
0x18006457a  mov     [rsp+2A0h+var_268], r14
0x18006457f  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x180064586  call    cs:__imp_SRCacheContext_Open
0x18006458c  mov     ebx, eax
0x18006458e  cmp     [rsp+2A0h+var_260], r14b
0x180064593  jz      short loc_1800645B0
0x180064595  mov     r8, [rsp+2A0h+var_270]
0x18006459a  mov     rdx, [rsp+2A0h+var_268]
0x18006459f  mov     rcx, [r8]
0x1800645a2  mov     [r8], rdx
0x1800645a5  test    rcx, rcx
0x1800645a8  jz      short loc_1800645B0
0x1800645aa  call    cs:__imp_SRCacheContext_Close
0x1800645b0  test    ebx, ebx
0x1800645b2  js      loc_1800647CE
0x1800645b8  cmp     qword ptr [rsp+2A0h+var_280], r14
0x1800645bd  setnz   al
0x1800645c0  test    al, al
0x1800645c2  jz      loc_1800647A9
0x1800645c8  xor     edx, edx; Val
0x1800645ca  mov     [rsp+2A0h+var_250], r14
0x1800645cf  mov     r8d, 200h; Size
0x1800645d5  lea     rcx, [rsp+2A0h+var_248]; void *
0x1800645da  call    memset_0
0x1800645df  lea     rax, [rsp+2A0h+var_248]
0x1800645e4  mov     [rbp+1A0h+var_48], r14
0x1800645eb  mov     rdx, rsi; unsigned __int16 *
0x1800645ee  mov     [rbp+1A0h+var_38], rax
0x1800645f5  lea     rcx, [rsp+2A0h+var_250]; this
0x1800645fa  mov     [rbp+1A0h+var_40], 100h
0x180064605  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18006460a  mov     ebx, eax
0x18006460c  test    eax, eax
0x18006460e  jns     short loc_180064674
0x180064610  mov     rcx, [rbp+1A8h]; this
0x180064617  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006461e  mov     r9d, eax; char *
0x180064621  mov     edx, 0C5h; void *
0x180064626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006462b  mov     rcx, [rsp+2A0h+var_250]
0x180064630  mov     [rsp+2A0h+var_250], r14
0x180064635  test    rcx, rcx
0x180064638  jz      short loc_180064640
0x18006463a  call    cs:__imp_SRCache_Free
0x180064640  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180064645  mov     qword ptr [rsp+2A0h+var_280], r14
0x18006464a  test    rcx, rcx
0x18006464d  jz      short loc_180064655
0x18006464f  call    cs:__imp_SRCacheContext_Close
0x180064655  mov     eax, ebx
0x180064657  mov     rcx, [rbp+1A0h+var_30]
0x18006465e  xor     rcx, rsp; StackCookie
0x180064661  call    __security_check_cookie
0x180064666  add     rsp, 280h
0x18006466d  pop     r14
0x18006466f  pop     rdi
0x180064670  pop     rsi
0x180064671  pop     rbx
0x180064672  pop     rbp
0x180064673  retn
0x180064674  mov     rdx, [rbp+1A0h+var_38]
0x18006467b  lea     rax, [rsp+2A0h+var_278]
0x180064680  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180064685  lea     r9, [rsp+2A0h+var_268]
0x18006468a  xor     r8d, r8d
0x18006468d  mov     [rsp+2A0h+var_270], rax
0x180064692  mov     [rsp+2A0h+var_278], r14
0x180064697  mov     [rsp+2A0h+var_268], r14
0x18006469c  mov     [rsp+2A0h+var_260], 1
0x1800646a1  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800646a7  mov     ebx, eax
0x1800646a9  cmp     [rsp+2A0h+var_260], r14b
0x1800646ae  jz      short loc_1800646CB
0x1800646b0  mov     r8, [rsp+2A0h+var_270]
0x1800646b5  mov     rdx, [rsp+2A0h+var_268]
0x1800646ba  mov     rcx, [r8]
0x1800646bd  mov     [r8], rdx
0x1800646c0  test    rcx, rcx
0x1800646c3  jz      short loc_1800646CB
0x1800646c5  call    cs:__imp_SRCacheContext_Close
0x1800646cb  test    ebx, ebx
0x1800646cd  js      loc_1800647F0
0x1800646d3  mov     rcx, [rsp+2A0h+var_278]
0x1800646d8  test    rcx, rcx
0x1800646db  setnz   al
0x1800646de  test    al, al
0x1800646e0  jnz     short loc_180064744
0x1800646e2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800646e7  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x1800646ee  call    cs:__imp_SRCacheContext_AddToCache
0x1800646f4  mov     ebx, eax
0x1800646f6  test    eax, eax
0x1800646f8  js      loc_180064815
0x1800646fe  mov     rcx, [rsp+2A0h+var_278]
0x180064703  mov     [rsp+2A0h+var_278], r14
0x180064708  test    rcx, rcx
0x18006470b  jz      short loc_180064713
0x18006470d  call    cs:__imp_SRCacheContext_Close
0x180064713  mov     rcx, [rsp+2A0h+var_250]
0x180064718  mov     [rsp+2A0h+var_250], r14
0x18006471d  test    rcx, rcx
0x180064720  jz      short loc_180064728
0x180064722  call    cs:__imp_SRCache_Free
0x180064728  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18006472d  mov     qword ptr [rsp+2A0h+var_280], r14
0x180064732  test    rcx, rcx
0x180064735  jz      short loc_18006473D
0x180064737  call    cs:__imp_SRCacheContext_Close
0x18006473d  xor     eax, eax
0x18006473f  jmp     loc_180064657
0x180064744  mov     r8, rdi
0x180064747  xor     edx, edx
0x180064749  call    cs:__imp_SRCacheContext_EnumerateData
0x18006474f  mov     ebx, eax
0x180064751  test    eax, eax
0x180064753  jns     short loc_1800646E2
0x180064755  mov     rcx, [rbp+1A8h]; this
0x18006475c  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064763  mov     r9d, eax; char *
0x180064766  mov     edx, 2A6h; void *
0x18006476b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064770  mov     edx, 0CCh; void *
0x180064775  mov     rcx, [rbp+1A8h]; this
0x18006477c  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064783  mov     r9d, ebx; char *
0x180064786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006478b  mov     rcx, [rsp+2A0h+var_278]
0x180064790  mov     [rsp+2A0h+var_278], r14
0x180064795  test    rcx, rcx
0x180064798  jz      loc_18006462B
0x18006479e  call    cs:__imp_SRCacheContext_Close
0x1800647a4  jmp     loc_18006462B
0x1800647a9  mov     ebx, 80670012h
0x1800647ae  mov     edx, 0C2h; void *
0x1800647b3  mov     rcx, [rbp+1A8h]; this
0x1800647ba  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800647c1  mov     r9d, ebx; char *
0x1800647c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800647c9  jmp     loc_180064640
0x1800647ce  mov     rcx, [rbp+1A8h]; this
0x1800647d5  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800647dc  mov     r9d, ebx; char *
0x1800647df  mov     edx, 18Ch; void *
0x1800647e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800647e9  mov     edx, 0C1h
0x1800647ee  jmp     short loc_1800647B3
0x1800647f0  mov     rcx, [rbp+1A8h]; this
0x1800647f7  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800647fe  mov     r9d, ebx; char *
0x180064801  mov     edx, 1B0h; void *
0x180064806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006480b  mov     edx, 0C9h
0x180064810  jmp     loc_180064775
0x180064815  mov     rcx, [rbp+1A8h]; this
0x18006481c  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064823  mov     r9d, ebx; char *
0x180064826  mov     edx, 1A6h; void *
0x18006482b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064830  mov     edx, 0CFh
0x180064835  jmp     loc_180064775
```
