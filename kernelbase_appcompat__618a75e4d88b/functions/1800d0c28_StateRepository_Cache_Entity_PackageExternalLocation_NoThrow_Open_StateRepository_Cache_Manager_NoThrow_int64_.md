# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800d0c28`
- end: `0x1800d0e83`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `603`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006bf30`
- `0x1800d0b3c`

## callees

- `0x18000a690`
- `0x18005b2c4`
- `0x1800d0c28`
- `0x1800d0f90`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d0c88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d0c88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0cb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0d8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0de2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0cb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0d8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0de2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0d72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0dc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0d72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0dc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800d0d4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800d0d4d`

## string_xrefs

- `0x1800d0da9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x1800d0e21`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x1800d0e43`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800d0e68`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x1800d0c28  push    rbp
0x1800d0c2a  push    rbx
0x1800d0c2b  push    rsi
0x1800d0c2c  push    rdi
0x1800d0c2d  push    r14
0x1800d0c2f  push    r15
0x1800d0c31  lea     rbp, [rsp-188h]
0x1800d0c39  sub     rsp, 288h
0x1800d0c40  mov     rax, cs:__security_cookie
0x1800d0c47  xor     rax, rsp
0x1800d0c4a  mov     [rbp+1B0h+var_40], rax
0x1800d0c51  mov     rcx, [rcx]
0x1800d0c54  lea     rax, [rsp+2B0h+var_280]
0x1800d0c59  mov     rsi, r9
0x1800d0c5c  mov     [rsp+2B0h+var_278], rax
0x1800d0c61  mov     rdi, r8
0x1800d0c64  mov     [rsp+2B0h+var_268], 1
0x1800d0c69  mov     r14, rdx
0x1800d0c6c  lea     r9, [rsp+2B0h+var_270]
0x1800d0c71  xor     r15d, r15d
0x1800d0c74  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800d0c7b  xor     r8d, r8d
0x1800d0c7e  mov     [rsp+2B0h+var_280], r15
0x1800d0c83  mov     [rsp+2B0h+var_270], r15
0x1800d0c88  call    cs:__imp_SRCacheContext_Open
0x1800d0c8f  nop     dword ptr [rax+rax+00h]
0x1800d0c94  mov     ebx, eax
0x1800d0c96  cmp     [rsp+2B0h+var_268], r15b
0x1800d0c9b  jz      short loc_1800D0CBE
0x1800d0c9d  mov     r8, [rsp+2B0h+var_278]
0x1800d0ca2  mov     rdx, [rsp+2B0h+var_270]
0x1800d0ca7  mov     rcx, [r8]
0x1800d0caa  mov     [r8], rdx
0x1800d0cad  test    rcx, rcx
0x1800d0cb0  jz      short loc_1800D0CBE
0x1800d0cb2  call    cs:__imp_SRCacheContext_Close
0x1800d0cb9  nop     dword ptr [rax+rax+00h]
0x1800d0cbe  test    ebx, ebx
0x1800d0cc0  js      loc_1800D0E61
0x1800d0cc6  cmp     [rsp+2B0h+var_280], r15
0x1800d0ccb  setnz   al
0x1800d0cce  test    al, al
0x1800d0cd0  jz      loc_1800D0E10
0x1800d0cd6  xor     edx, edx; Val
0x1800d0cd8  mov     [rsp+2B0h+var_260], r15
0x1800d0cdd  mov     r8d, 200h; Size
0x1800d0ce3  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800d0ce8  call    memset_0
0x1800d0ced  lea     rax, [rsp+2B0h+var_258]
0x1800d0cf2  mov     [rbp+1B0h+var_58], r15
0x1800d0cf9  mov     rdx, r14; unsigned __int64
0x1800d0cfc  mov     [rbp+1B0h+var_48], rax
0x1800d0d03  lea     rcx, [rsp+2B0h+var_260]; this
0x1800d0d08  mov     [rbp+1B0h+var_50], 100h
0x1800d0d13  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800d0d18  mov     ebx, eax
0x1800d0d1a  test    eax, eax
0x1800d0d1c  js      loc_1800D0E32
0x1800d0d22  mov     r8, [rbp+1B0h+var_48]
0x1800d0d29  lea     rdx, [rsp+2B0h+var_280]
0x1800d0d2e  mov     rcx, rdi
0x1800d0d31  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x1800d0d36  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800d0d3b  mov     ebx, eax
0x1800d0d3d  test    eax, eax
0x1800d0d3f  js      short loc_1800D0D9D
0x1800d0d41  mov     rcx, [rsp+2B0h+var_280]
0x1800d0d46  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800d0d4d  call    cs:__imp_SRCacheContext_AddToCache
0x1800d0d54  nop     dword ptr [rax+rax+00h]
0x1800d0d59  mov     ebx, eax
0x1800d0d5b  test    eax, eax
0x1800d0d5d  js      loc_1800D0E3C
0x1800d0d63  mov     rcx, [rsp+2B0h+var_260]
0x1800d0d68  mov     [rsp+2B0h+var_260], r15
0x1800d0d6d  test    rcx, rcx
0x1800d0d70  jz      short loc_1800D0D7E
0x1800d0d72  call    cs:__imp_SRCache_Free
0x1800d0d79  nop     dword ptr [rax+rax+00h]
0x1800d0d7e  mov     rcx, [rsp+2B0h+var_280]
0x1800d0d83  mov     [rsp+2B0h+var_280], r15
0x1800d0d88  test    rcx, rcx
0x1800d0d8b  jz      short loc_1800D0D99
0x1800d0d8d  call    cs:__imp_SRCacheContext_Close
0x1800d0d94  nop     dword ptr [rax+rax+00h]
0x1800d0d99  xor     eax, eax
0x1800d0d9b  jmp     short loc_1800D0DF0
0x1800d0d9d  mov     edx, 0FFh; void *
0x1800d0da2  mov     rcx, [rbp+1B8h]; this
0x1800d0da9  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d0db0  mov     r9d, ebx; char *
0x1800d0db3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0db8  mov     rcx, [rsp+2B0h+var_260]
0x1800d0dbd  mov     [rsp+2B0h+var_260], r15
0x1800d0dc2  test    rcx, rcx
0x1800d0dc5  jz      short loc_1800D0DD3
0x1800d0dc7  call    cs:__imp_SRCache_Free
0x1800d0dce  nop     dword ptr [rax+rax+00h]
0x1800d0dd3  mov     rcx, [rsp+2B0h+var_280]
0x1800d0dd8  mov     [rsp+2B0h+var_280], r15
0x1800d0ddd  test    rcx, rcx
0x1800d0de0  jz      short loc_1800D0DEE
0x1800d0de2  call    cs:__imp_SRCacheContext_Close
0x1800d0de9  nop     dword ptr [rax+rax+00h]
0x1800d0dee  mov     eax, ebx
0x1800d0df0  mov     rcx, [rbp+1B0h+var_40]
0x1800d0df7  xor     rcx, rsp; StackCookie
0x1800d0dfa  call    __security_check_cookie
0x1800d0dff  add     rsp, 288h
0x1800d0e06  pop     r15
0x1800d0e08  pop     r14
0x1800d0e0a  pop     rdi
0x1800d0e0b  pop     rsi
0x1800d0e0c  pop     rbx
0x1800d0e0d  pop     rbp
0x1800d0e0e  retn
0x1800d0e10  mov     ebx, 80670012h
0x1800d0e15  mov     edx, 0FBh; void *
0x1800d0e1a  mov     rcx, [rbp+1B8h]; this
0x1800d0e21  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d0e28  mov     r9d, ebx; char *
0x1800d0e2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0e30  jmp     short loc_1800D0DD3
0x1800d0e32  mov     edx, 0FEh
0x1800d0e37  jmp     loc_1800D0DA2
0x1800d0e3c  mov     rcx, [rbp+1B8h]; this
0x1800d0e43  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d0e4a  mov     r9d, ebx; char *
0x1800d0e4d  mov     edx, 1A6h; void *
0x1800d0e52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0e57  mov     edx, 101h
0x1800d0e5c  jmp     loc_1800D0DA2
0x1800d0e61  mov     rcx, [rbp+1B8h]; this
0x1800d0e68  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d0e6f  mov     r9d, ebx; char *
0x1800d0e72  mov     edx, 18Ch; void *
0x1800d0e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0e7c  mov     edx, 0FAh
0x1800d0e81  jmp     short loc_1800D0E1A
```
