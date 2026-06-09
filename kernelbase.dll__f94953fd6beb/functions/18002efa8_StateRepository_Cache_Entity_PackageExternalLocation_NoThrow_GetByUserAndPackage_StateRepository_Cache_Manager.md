# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18002efa8`
- end: `0x18002f332`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `906`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ea40`
- `0x18002ef00`
- `0x18009df60`

## callees

- `0x18002efa8`
- `0x18002f340`
- `0x18002f620`
- `0x180058768`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002f238`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002f238`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002f0fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002f0fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002f014`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002f014`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f038`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f11e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f166`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f190`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f1fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f038`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f11e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f166`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f190`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f1fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f17b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f211`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f17b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002f211`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002f14b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002f14b`

## string_xrefs

- `0x18002f1de`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002f279`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002f29e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002f2e5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002f1be`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002f24f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002f2b9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002f30a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x18002efa8  push    rbp
0x18002efaa  push    rbx
0x18002efab  push    rsi
0x18002efac  push    rdi
0x18002efad  push    r14
0x18002efaf  push    r15
0x18002efb1  lea     rbp, [rsp-188h]
0x18002efb9  sub     rsp, 288h
0x18002efc0  mov     rax, cs:__security_cookie
0x18002efc7  xor     rax, rsp
0x18002efca  mov     [rbp+1B0h+var_40], rax
0x18002efd1  xor     r15d, r15d
0x18002efd4  mov     rsi, r9
0x18002efd7  mov     [r9], r15
0x18002efda  mov     rdi, r8
0x18002efdd  mov     r14, rdx
0x18002efe0  test    r8, r8
0x18002efe3  jz      loc_18002F2DE
0x18002efe9  mov     rcx, [rcx]
0x18002efec  lea     rax, [rsp+2B0h+var_290]
0x18002eff1  lea     r9, [rsp+2B0h+var_278]
0x18002eff6  mov     [rsp+2B0h+var_280], rax
0x18002effb  xor     r8d, r8d
0x18002effe  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18002f003  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002f00a  mov     [rsp+2B0h+var_278], r15
0x18002f00f  mov     [rsp+2B0h+var_270], 1
0x18002f014  call    cs:__imp_SRCacheContext_Open
0x18002f01a  mov     ebx, eax
0x18002f01c  cmp     [rsp+2B0h+var_270], r15b
0x18002f021  jz      short loc_18002F03E
0x18002f023  mov     r8, [rsp+2B0h+var_280]
0x18002f028  mov     rdx, [rsp+2B0h+var_278]
0x18002f02d  mov     rcx, [r8]
0x18002f030  mov     [r8], rdx
0x18002f033  test    rcx, rcx
0x18002f036  jz      short loc_18002F03E
0x18002f038  call    cs:__imp_SRCacheContext_Close
0x18002f03e  test    ebx, ebx
0x18002f040  js      loc_18002F303
0x18002f046  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18002f04b  setnz   al
0x18002f04e  test    al, al
0x18002f050  jz      loc_18002F28D
0x18002f056  xor     edx, edx; Val
0x18002f058  mov     [rsp+2B0h+var_260], r15
0x18002f05d  mov     r8d, 200h; Size
0x18002f063  lea     rcx, [rsp+2B0h+var_258]; void *
0x18002f068  call    memset_0
0x18002f06d  lea     rax, [rsp+2B0h+var_258]
0x18002f072  mov     [rbp+1B0h+var_58], r15
0x18002f079  mov     rdx, r14; unsigned __int64
0x18002f07c  mov     [rbp+1B0h+var_48], rax
0x18002f083  lea     rcx, [rsp+2B0h+var_260]; this
0x18002f088  mov     [rbp+1B0h+var_50], 100h
0x18002f093  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002f098  mov     ebx, eax
0x18002f09a  test    eax, eax
0x18002f09c  js      loc_18002F26D
0x18002f0a2  lea     rcx, [rsp+2B0h+var_260]; this
0x18002f0a7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18002f0ac  mov     ebx, eax
0x18002f0ae  test    eax, eax
0x18002f0b0  js      loc_18002F328
0x18002f0b6  mov     rdx, rdi; unsigned __int64
0x18002f0b9  lea     rcx, [rsp+2B0h+var_260]; this
0x18002f0be  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002f0c3  mov     ebx, eax
0x18002f0c5  test    eax, eax
0x18002f0c7  js      loc_18002F2D7
0x18002f0cd  mov     rdx, [rbp+1B0h+var_48]
0x18002f0d4  lea     rax, [rsp+2B0h+var_288]
0x18002f0d9  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002f0de  lea     r9, [rsp+2B0h+var_278]
0x18002f0e3  xor     r8d, r8d
0x18002f0e6  mov     [rsp+2B0h+var_280], rax
0x18002f0eb  mov     [rsp+2B0h+var_288], r15
0x18002f0f0  mov     [rsp+2B0h+var_278], r15
0x18002f0f5  mov     [rsp+2B0h+var_270], 1
0x18002f0fa  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002f100  mov     ebx, eax
0x18002f102  cmp     [rsp+2B0h+var_270], r15b
0x18002f107  jz      short loc_18002F124
0x18002f109  mov     r8, [rsp+2B0h+var_280]
0x18002f10e  mov     rdx, [rsp+2B0h+var_278]
0x18002f113  mov     rcx, [r8]
0x18002f116  mov     [r8], rdx
0x18002f119  test    rcx, rcx
0x18002f11c  jz      short loc_18002F124
0x18002f11e  call    cs:__imp_SRCacheContext_Close
0x18002f124  test    ebx, ebx
0x18002f126  js      loc_18002F2B2
0x18002f12c  mov     rcx, [rsp+2B0h+var_288]
0x18002f131  test    rcx, rcx
0x18002f134  setnz   al
0x18002f137  test    al, al
0x18002f139  jnz     loc_18002F233
0x18002f13f  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002f144  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18002f14b  call    cs:__imp_SRCacheContext_AddToCache
0x18002f151  mov     ebx, eax
0x18002f153  test    eax, eax
0x18002f155  js      short loc_18002F1B7
0x18002f157  mov     rcx, [rsp+2B0h+var_288]
0x18002f15c  mov     [rsp+2B0h+var_288], r15
0x18002f161  test    rcx, rcx
0x18002f164  jz      short loc_18002F16C
0x18002f166  call    cs:__imp_SRCacheContext_Close
0x18002f16c  mov     rcx, [rsp+2B0h+var_260]
0x18002f171  mov     [rsp+2B0h+var_260], r15
0x18002f176  test    rcx, rcx
0x18002f179  jz      short loc_18002F181
0x18002f17b  call    cs:__imp_SRCache_Free
0x18002f181  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002f186  mov     qword ptr [rsp+2B0h+var_290], r15
0x18002f18b  test    rcx, rcx
0x18002f18e  jz      short loc_18002F196
0x18002f190  call    cs:__imp_SRCacheContext_Close
0x18002f196  xor     eax, eax
0x18002f198  mov     rcx, [rbp+1B0h+var_40]
0x18002f19f  xor     rcx, rsp; StackCookie
0x18002f1a2  call    __security_check_cookie
0x18002f1a7  add     rsp, 288h
0x18002f1ae  pop     r15
0x18002f1b0  pop     r14
0x18002f1b2  pop     rdi
0x18002f1b3  pop     rsi
0x18002f1b4  pop     rbx
0x18002f1b5  pop     rbp
0x18002f1b6  retn
0x18002f1b7  mov     rcx, [rbp+1B8h]; this
0x18002f1be  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f1c5  mov     r9d, ebx; char *
0x18002f1c8  mov     edx, 1A6h; void *
0x18002f1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f1d2  mov     edx, 0C9h; void *
0x18002f1d7  mov     rcx, [rbp+1B8h]; this
0x18002f1de  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f1e5  mov     r9d, ebx; char *
0x18002f1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f1ed  mov     rcx, [rsp+2B0h+var_288]
0x18002f1f2  mov     [rsp+2B0h+var_288], r15
0x18002f1f7  test    rcx, rcx
0x18002f1fa  jz      short loc_18002F202
0x18002f1fc  call    cs:__imp_SRCacheContext_Close
0x18002f202  mov     rcx, [rsp+2B0h+var_260]
0x18002f207  mov     [rsp+2B0h+var_260], r15
0x18002f20c  test    rcx, rcx
0x18002f20f  jz      short loc_18002F217
0x18002f211  call    cs:__imp_SRCache_Free
0x18002f217  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18002f21c  mov     qword ptr [rsp+2B0h+var_290], r15
0x18002f221  test    rcx, rcx
0x18002f224  jz      short loc_18002F22C
0x18002f226  call    cs:__imp_SRCacheContext_Close
0x18002f22c  mov     eax, ebx
0x18002f22e  jmp     loc_18002F198
0x18002f233  mov     r8, rsi
0x18002f236  xor     edx, edx
0x18002f238  call    cs:__imp_SRCacheContext_EnumerateData
0x18002f23e  mov     ebx, eax
0x18002f240  test    eax, eax
0x18002f242  jns     loc_18002F13F
0x18002f248  mov     rcx, [rbp+1B8h]; this
0x18002f24f  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f256  mov     r9d, eax; char *
0x18002f259  mov     edx, 2A6h; void *
0x18002f25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f263  mov     edx, 0C6h
0x18002f268  jmp     loc_18002F1D7
0x18002f26d  mov     edx, 0BDh; void *
0x18002f272  mov     rcx, [rbp+1B8h]; this
0x18002f279  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f280  mov     r9d, ebx; char *
0x18002f283  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f288  jmp     loc_18002F202
0x18002f28d  mov     ebx, 80670012h
0x18002f292  mov     edx, 0BAh; void *
0x18002f297  mov     rcx, [rbp+1B8h]; this
0x18002f29e  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f2a5  mov     r9d, ebx; char *
0x18002f2a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2ad  jmp     loc_18002F217
0x18002f2b2  mov     rcx, [rbp+1B8h]; this
0x18002f2b9  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f2c0  mov     r9d, ebx; char *
0x18002f2c3  mov     edx, 1B0h; void *
0x18002f2c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2cd  mov     edx, 0C3h
0x18002f2d2  jmp     loc_18002F1D7
0x18002f2d7  mov     edx, 0BFh
0x18002f2dc  jmp     short loc_18002F272
0x18002f2de  mov     rcx, [rbp+1B8h]; this
0x18002f2e5  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f2ec  mov     ebx, 80070057h
0x18002f2f1  mov     edx, 0B5h; void *
0x18002f2f6  mov     r9d, ebx; char *
0x18002f2f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2fe  jmp     loc_18002F22C
0x18002f303  mov     rcx, [rbp+1B8h]; this
0x18002f30a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f311  mov     r9d, ebx; char *
0x18002f314  mov     edx, 18Ch; void *
0x18002f319  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f31e  mov     edx, 0B9h
0x18002f323  jmp     loc_18002F297
0x18002f328  mov     edx, 0BEh
0x18002f32d  jmp     loc_18002F272
```
