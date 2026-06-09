# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180057758`
- end: `0x1800579b0`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `600`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c890`
- `0x1800543b0`
- `0x1800feaf4`

## callees

- `0x18000a690`
- `0x180057758`
- `0x18005b2c4`
- `0x1800d0f90`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800577b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800577b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800577e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800578bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005794b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800577e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800578bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005794b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800578a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057930`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800578a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180057930`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180057881`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180057881`

## string_xrefs

- `0x180057912`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18005797d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800578f2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180057995`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageFamily\\Data", 0, &v21);
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
    v17 = 257;
    goto LABEL_23;
  }
  if ( !v19 )
  {
    v8 = -2140733422;
    v17 = 258;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
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
    v14 = 261;
  }
  else
  {
    v18 = v5;
    v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v27);
    if ( v8 < 0 )
    {
      v14 = 262;
    }
    else
    {
      v10 = SRCacheContext_AddToCache(v19, L"PackageFamily\\Data");
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
      v14 = 264;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
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
0x180057758  push    rbp
0x18005775a  push    rbx
0x18005775b  push    rsi
0x18005775c  push    rdi
0x18005775d  push    r14
0x18005775f  push    r15
0x180057761  lea     rbp, [rsp-188h]
0x180057769  sub     rsp, 288h
0x180057770  mov     rax, cs:__security_cookie
0x180057777  xor     rax, rsp
0x18005777a  mov     [rbp+1B0h+var_40], rax
0x180057781  mov     rcx, [rcx]
0x180057784  lea     rax, [rsp+2B0h+var_280]
0x180057789  mov     rsi, r9
0x18005778c  mov     [rsp+2B0h+var_278], rax
0x180057791  mov     rdi, r8
0x180057794  mov     [rsp+2B0h+var_268], 1
0x180057799  mov     r14, rdx
0x18005779c  lea     r9, [rsp+2B0h+var_270]
0x1800577a1  xor     r15d, r15d
0x1800577a4  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x1800577ab  xor     r8d, r8d
0x1800577ae  mov     [rsp+2B0h+var_280], r15
0x1800577b3  mov     [rsp+2B0h+var_270], r15
0x1800577b8  call    cs:__imp_SRCacheContext_Open
0x1800577bf  nop     dword ptr [rax+rax+00h]
0x1800577c4  mov     ebx, eax
0x1800577c6  cmp     [rsp+2B0h+var_268], r15b
0x1800577cb  jz      short loc_1800577EE
0x1800577cd  mov     r8, [rsp+2B0h+var_278]
0x1800577d2  mov     rdx, [rsp+2B0h+var_270]
0x1800577d7  mov     rcx, [r8]
0x1800577da  mov     [r8], rdx
0x1800577dd  test    rcx, rcx
0x1800577e0  jz      short loc_1800577EE
0x1800577e2  call    cs:__imp_SRCacheContext_Close
0x1800577e9  nop     dword ptr [rax+rax+00h]
0x1800577ee  test    ebx, ebx
0x1800577f0  js      loc_18005798E
0x1800577f6  cmp     [rsp+2B0h+var_280], r15
0x1800577fb  setnz   al
0x1800577fe  test    al, al
0x180057800  jz      loc_18005796C
0x180057806  xor     edx, edx; Val
0x180057808  mov     [rsp+2B0h+var_260], r15
0x18005780d  mov     r8d, 200h; Size
0x180057813  lea     rcx, [rsp+2B0h+var_258]; void *
0x180057818  call    memset_0
0x18005781d  lea     rax, [rsp+2B0h+var_258]
0x180057822  mov     [rbp+1B0h+var_58], r15
0x180057829  mov     rdx, r14; unsigned __int64
0x18005782c  mov     [rbp+1B0h+var_48], rax
0x180057833  lea     rcx, [rsp+2B0h+var_260]; this
0x180057838  mov     [rbp+1B0h+var_50], 100h
0x180057843  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180057848  mov     ebx, eax
0x18005784a  test    eax, eax
0x18005784c  js      loc_180057965
0x180057852  mov     r8, [rbp+1B0h+var_48]
0x180057859  lea     rdx, [rsp+2B0h+var_280]
0x18005785e  mov     rcx, rdi
0x180057861  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x180057866  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18005786b  mov     ebx, eax
0x18005786d  test    eax, eax
0x18005786f  js      loc_18005795E
0x180057875  mov     rcx, [rsp+2B0h+var_280]
0x18005787a  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x180057881  call    cs:__imp_SRCacheContext_AddToCache
0x180057888  nop     dword ptr [rax+rax+00h]
0x18005788d  mov     ebx, eax
0x18005788f  test    eax, eax
0x180057891  js      short loc_1800578EB
0x180057893  mov     rcx, [rsp+2B0h+var_260]
0x180057898  mov     [rsp+2B0h+var_260], r15
0x18005789d  test    rcx, rcx
0x1800578a0  jz      short loc_1800578AE
0x1800578a2  call    cs:__imp_SRCache_Free
0x1800578a9  nop     dword ptr [rax+rax+00h]
0x1800578ae  mov     rcx, [rsp+2B0h+var_280]
0x1800578b3  mov     [rsp+2B0h+var_280], r15
0x1800578b8  test    rcx, rcx
0x1800578bb  jz      short loc_1800578C9
0x1800578bd  call    cs:__imp_SRCacheContext_Close
0x1800578c4  nop     dword ptr [rax+rax+00h]
0x1800578c9  xor     eax, eax
0x1800578cb  mov     rcx, [rbp+1B0h+var_40]
0x1800578d2  xor     rcx, rsp; StackCookie
0x1800578d5  call    __security_check_cookie
0x1800578da  add     rsp, 288h
0x1800578e1  pop     r15
0x1800578e3  pop     r14
0x1800578e5  pop     rdi
0x1800578e6  pop     rsi
0x1800578e7  pop     rbx
0x1800578e8  pop     rbp
0x1800578e9  retn
0x1800578eb  mov     rcx, [rbp+1B8h]; this
0x1800578f2  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800578f9  mov     r9d, ebx; char *
0x1800578fc  mov     edx, 1A6h; void *
0x180057901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057906  mov     edx, 108h; void *
0x18005790b  mov     rcx, [rbp+1B8h]; this
0x180057912  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180057919  mov     r9d, ebx; char *
0x18005791c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057921  mov     rcx, [rsp+2B0h+var_260]
0x180057926  mov     [rsp+2B0h+var_260], r15
0x18005792b  test    rcx, rcx
0x18005792e  jz      short loc_18005793C
0x180057930  call    cs:__imp_SRCache_Free
0x180057937  nop     dword ptr [rax+rax+00h]
0x18005793c  mov     rcx, [rsp+2B0h+var_280]
0x180057941  mov     [rsp+2B0h+var_280], r15
0x180057946  test    rcx, rcx
0x180057949  jz      short loc_180057957
0x18005794b  call    cs:__imp_SRCacheContext_Close
0x180057952  nop     dword ptr [rax+rax+00h]
0x180057957  mov     eax, ebx
0x180057959  jmp     loc_1800578CB
0x18005795e  mov     edx, 106h
0x180057963  jmp     short loc_18005790B
0x180057965  mov     edx, 105h
0x18005796a  jmp     short loc_18005790B
0x18005796c  mov     ebx, 80670012h
0x180057971  mov     edx, 102h; void *
0x180057976  mov     rcx, [rbp+1B8h]; this
0x18005797d  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180057984  mov     r9d, ebx; char *
0x180057987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005798c  jmp     short loc_18005793C
0x18005798e  mov     rcx, [rbp+1B8h]; this
0x180057995  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005799c  mov     r9d, ebx; char *
0x18005799f  mov     edx, 18Ch; void *
0x1800579a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800579a9  mov     edx, 101h
0x1800579ae  jmp     short loc_180057976
```
