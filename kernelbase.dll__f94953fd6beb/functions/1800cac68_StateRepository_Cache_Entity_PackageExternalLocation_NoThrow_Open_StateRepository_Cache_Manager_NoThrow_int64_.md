# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800cac68`
- end: `0x1800cae98`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `560`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ea40`
- `0x18009df60`
- `0x1800cab88`

## callees

- `0x18002f340`
- `0x180058768`
- `0x1800cac68`
- `0x1800caf60`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800cacc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800cacc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cacec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cadb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cadfe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cacec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cadb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800cadfe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cada0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cade9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cada0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800cade9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800cad81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800cad81`

## string_xrefs

- `0x1800cadcb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x1800cae36`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x1800cae58`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800cae7d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // esi
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v20 = &v19;
  v22 = 1;
  v19 = 0;
  v21 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageExternalLocation\\Data", 0, &v21);
  if ( v22 )
  {
    v9 = *v20;
    *v20 = v21;
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
      v18);
    v17 = 250;
    goto LABEL_21;
  }
  if ( !v19 )
  {
    v8 = -2140733422;
    v17 = 251;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v8,
      v18);
    goto LABEL_17;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  if ( v8 < 0 )
  {
    v14 = 254;
  }
  else
  {
    v18 = v5;
    v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v27);
    if ( v8 < 0 )
    {
      v14 = 255;
    }
    else
    {
      v10 = SRCacheContext_AddToCache(v19, L"PackageExternalLocation\\Data");
      v8 = v10;
      if ( v10 >= 0 )
      {
        v11 = v23;
        v23 = 0;
        if ( v11 )
          SRCache_Free(v11);
        v12 = v19;
        v19 = 0;
        if ( v12 )
          SRCacheContext_Close(v12);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v10,
        v5);
      v14 = 257;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
    (const char *)(unsigned int)v8,
    v18);
  v15 = v23;
  v23 = 0;
  if ( v15 )
    SRCache_Free(v15);
LABEL_17:
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800cac68  push    rbp
0x1800cac6a  push    rbx
0x1800cac6b  push    rsi
0x1800cac6c  push    rdi
0x1800cac6d  push    r14
0x1800cac6f  push    r15
0x1800cac71  lea     rbp, [rsp-188h]
0x1800cac79  sub     rsp, 288h
0x1800cac80  mov     rax, cs:__security_cookie
0x1800cac87  xor     rax, rsp
0x1800cac8a  mov     [rbp+1B0h+var_40], rax
0x1800cac91  mov     rcx, [rcx]
0x1800cac94  lea     rax, [rsp+2B0h+var_280]
0x1800cac99  mov     rsi, r9
0x1800cac9c  mov     [rsp+2B0h+var_278], rax
0x1800caca1  mov     rdi, r8
0x1800caca4  mov     [rsp+2B0h+var_268], 1
0x1800caca9  mov     r14, rdx
0x1800cacac  lea     r9, [rsp+2B0h+var_270]
0x1800cacb1  xor     r15d, r15d
0x1800cacb4  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800cacbb  xor     r8d, r8d
0x1800cacbe  mov     [rsp+2B0h+var_280], r15
0x1800cacc3  mov     [rsp+2B0h+var_270], r15
0x1800cacc8  call    cs:__imp_SRCacheContext_Open
0x1800cacce  mov     ebx, eax
0x1800cacd0  cmp     [rsp+2B0h+var_268], r15b
0x1800cacd5  jz      short loc_1800CACF2
0x1800cacd7  mov     r8, [rsp+2B0h+var_278]
0x1800cacdc  mov     rdx, [rsp+2B0h+var_270]
0x1800cace1  mov     rcx, [r8]
0x1800cace4  mov     [r8], rdx
0x1800cace7  test    rcx, rcx
0x1800cacea  jz      short loc_1800CACF2
0x1800cacec  call    cs:__imp_SRCacheContext_Close
0x1800cacf2  test    ebx, ebx
0x1800cacf4  js      loc_1800CAE76
0x1800cacfa  cmp     [rsp+2B0h+var_280], r15
0x1800cacff  setnz   al
0x1800cad02  test    al, al
0x1800cad04  jz      loc_1800CAE25
0x1800cad0a  xor     edx, edx; Val
0x1800cad0c  mov     [rsp+2B0h+var_260], r15
0x1800cad11  mov     r8d, 200h; Size
0x1800cad17  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800cad1c  call    memset_0
0x1800cad21  lea     rax, [rsp+2B0h+var_258]
0x1800cad26  mov     [rbp+1B0h+var_58], r15
0x1800cad2d  mov     rdx, r14; unsigned __int64
0x1800cad30  mov     [rbp+1B0h+var_48], rax
0x1800cad37  lea     rcx, [rsp+2B0h+var_260]; this
0x1800cad3c  mov     [rbp+1B0h+var_50], 100h
0x1800cad47  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800cad4c  mov     ebx, eax
0x1800cad4e  test    eax, eax
0x1800cad50  js      loc_1800CAE47
0x1800cad56  mov     r8, [rbp+1B0h+var_48]
0x1800cad5d  lea     rdx, [rsp+2B0h+var_280]
0x1800cad62  mov     rcx, rdi
0x1800cad65  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x1800cad6a  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800cad6f  mov     ebx, eax
0x1800cad71  test    eax, eax
0x1800cad73  js      short loc_1800CADBF
0x1800cad75  mov     rcx, [rsp+2B0h+var_280]
0x1800cad7a  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800cad81  call    cs:__imp_SRCacheContext_AddToCache
0x1800cad87  mov     ebx, eax
0x1800cad89  test    eax, eax
0x1800cad8b  js      loc_1800CAE51
0x1800cad91  mov     rcx, [rsp+2B0h+var_260]
0x1800cad96  mov     [rsp+2B0h+var_260], r15
0x1800cad9b  test    rcx, rcx
0x1800cad9e  jz      short loc_1800CADA6
0x1800cada0  call    cs:__imp_SRCache_Free
0x1800cada6  mov     rcx, [rsp+2B0h+var_280]
0x1800cadab  mov     [rsp+2B0h+var_280], r15
0x1800cadb0  test    rcx, rcx
0x1800cadb3  jz      short loc_1800CADBB
0x1800cadb5  call    cs:__imp_SRCacheContext_Close
0x1800cadbb  xor     eax, eax
0x1800cadbd  jmp     short loc_1800CAE06
0x1800cadbf  mov     edx, 0FFh; void *
0x1800cadc4  mov     rcx, [rbp+1B8h]; this
0x1800cadcb  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cadd2  mov     r9d, ebx; char *
0x1800cadd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cadda  mov     rcx, [rsp+2B0h+var_260]
0x1800caddf  mov     [rsp+2B0h+var_260], r15
0x1800cade4  test    rcx, rcx
0x1800cade7  jz      short loc_1800CADEF
0x1800cade9  call    cs:__imp_SRCache_Free
0x1800cadef  mov     rcx, [rsp+2B0h+var_280]
0x1800cadf4  mov     [rsp+2B0h+var_280], r15
0x1800cadf9  test    rcx, rcx
0x1800cadfc  jz      short loc_1800CAE04
0x1800cadfe  call    cs:__imp_SRCacheContext_Close
0x1800cae04  mov     eax, ebx
0x1800cae06  mov     rcx, [rbp+1B0h+var_40]
0x1800cae0d  xor     rcx, rsp; StackCookie
0x1800cae10  call    __security_check_cookie
0x1800cae15  add     rsp, 288h
0x1800cae1c  pop     r15
0x1800cae1e  pop     r14
0x1800cae20  pop     rdi
0x1800cae21  pop     rsi
0x1800cae22  pop     rbx
0x1800cae23  pop     rbp
0x1800cae24  retn
0x1800cae25  mov     ebx, 80670012h
0x1800cae2a  mov     edx, 0FBh; void *
0x1800cae2f  mov     rcx, [rbp+1B8h]; this
0x1800cae36  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cae3d  mov     r9d, ebx; char *
0x1800cae40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cae45  jmp     short loc_1800CADEF
0x1800cae47  mov     edx, 0FEh
0x1800cae4c  jmp     loc_1800CADC4
0x1800cae51  mov     rcx, [rbp+1B8h]; this
0x1800cae58  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cae5f  mov     r9d, ebx; char *
0x1800cae62  mov     edx, 1A6h; void *
0x1800cae67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cae6c  mov     edx, 101h
0x1800cae71  jmp     loc_1800CADC4
0x1800cae76  mov     rcx, [rbp+1B8h]; this
0x1800cae7d  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800cae84  mov     r9d, ebx; char *
0x1800cae87  mov     edx, 18Ch; void *
0x1800cae8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cae91  mov     edx, 0FAh
0x1800cae96  jmp     short loc_1800CAE2F
```
