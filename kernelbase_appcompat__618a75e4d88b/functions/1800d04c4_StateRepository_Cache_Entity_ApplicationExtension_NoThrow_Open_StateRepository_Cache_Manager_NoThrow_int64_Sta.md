# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800d04c4`
- end: `0x1800d071f`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `603`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800d03d4`

## callees

- `0x18000a690`
- `0x18005b2c4`
- `0x1800d04c4`
- `0x1800d0f90`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d0524`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d0524`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d054e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d067e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d054e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d0629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d067e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d060e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0663`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d060e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0663`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800d05e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800d05e9`

## string_xrefs

- `0x1800d0510`: `ApplicationExtension\Data`
- `0x1800d05e2`: `ApplicationExtension\Data`
- `0x1800d0645`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800d06bd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800d06d5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800d0704`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v21);
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
    v17 = 364;
    goto LABEL_21;
  }
  if ( !v19 )
  {
    v8 = -2140733422;
    v17 = 365;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v14 = 368;
  }
  else
  {
    v18 = v5;
    v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v27);
    if ( v8 < 0 )
    {
      v14 = 369;
    }
    else
    {
      v10 = SRCacheContext_AddToCache(v19, L"ApplicationExtension\\Data");
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
      v14 = 371;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x1800d04c4  push    rbp
0x1800d04c6  push    rbx
0x1800d04c7  push    rsi
0x1800d04c8  push    rdi
0x1800d04c9  push    r14
0x1800d04cb  push    r15
0x1800d04cd  lea     rbp, [rsp-188h]
0x1800d04d5  sub     rsp, 288h
0x1800d04dc  mov     rax, cs:__security_cookie
0x1800d04e3  xor     rax, rsp
0x1800d04e6  mov     [rbp+1B0h+var_40], rax
0x1800d04ed  mov     rcx, [rcx]
0x1800d04f0  lea     rax, [rsp+2B0h+var_280]
0x1800d04f5  mov     rsi, r9
0x1800d04f8  mov     [rsp+2B0h+var_278], rax
0x1800d04fd  mov     rdi, r8
0x1800d0500  mov     [rsp+2B0h+var_268], 1
0x1800d0505  mov     r14, rdx
0x1800d0508  lea     r9, [rsp+2B0h+var_270]
0x1800d050d  xor     r15d, r15d
0x1800d0510  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800d0517  xor     r8d, r8d
0x1800d051a  mov     [rsp+2B0h+var_280], r15
0x1800d051f  mov     [rsp+2B0h+var_270], r15
0x1800d0524  call    cs:__imp_SRCacheContext_Open
0x1800d052b  nop     dword ptr [rax+rax+00h]
0x1800d0530  mov     ebx, eax
0x1800d0532  cmp     [rsp+2B0h+var_268], r15b
0x1800d0537  jz      short loc_1800D055A
0x1800d0539  mov     r8, [rsp+2B0h+var_278]
0x1800d053e  mov     rdx, [rsp+2B0h+var_270]
0x1800d0543  mov     rcx, [r8]
0x1800d0546  mov     [r8], rdx
0x1800d0549  test    rcx, rcx
0x1800d054c  jz      short loc_1800D055A
0x1800d054e  call    cs:__imp_SRCacheContext_Close
0x1800d0555  nop     dword ptr [rax+rax+00h]
0x1800d055a  test    ebx, ebx
0x1800d055c  js      loc_1800D06FD
0x1800d0562  cmp     [rsp+2B0h+var_280], r15
0x1800d0567  setnz   al
0x1800d056a  test    al, al
0x1800d056c  jz      loc_1800D06AC
0x1800d0572  xor     edx, edx; Val
0x1800d0574  mov     [rsp+2B0h+var_260], r15
0x1800d0579  mov     r8d, 200h; Size
0x1800d057f  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800d0584  call    memset_0
0x1800d0589  lea     rax, [rsp+2B0h+var_258]
0x1800d058e  mov     [rbp+1B0h+var_58], r15
0x1800d0595  mov     rdx, r14; unsigned __int64
0x1800d0598  mov     [rbp+1B0h+var_48], rax
0x1800d059f  lea     rcx, [rsp+2B0h+var_260]; this
0x1800d05a4  mov     [rbp+1B0h+var_50], 100h
0x1800d05af  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800d05b4  mov     ebx, eax
0x1800d05b6  test    eax, eax
0x1800d05b8  js      short loc_1800D0639
0x1800d05ba  mov     r8, [rbp+1B0h+var_48]
0x1800d05c1  lea     rdx, [rsp+2B0h+var_280]
0x1800d05c6  mov     rcx, rdi
0x1800d05c9  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x1800d05ce  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800d05d3  mov     ebx, eax
0x1800d05d5  test    eax, eax
0x1800d05d7  js      loc_1800D06F3
0x1800d05dd  mov     rcx, [rsp+2B0h+var_280]
0x1800d05e2  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800d05e9  call    cs:__imp_SRCacheContext_AddToCache
0x1800d05f0  nop     dword ptr [rax+rax+00h]
0x1800d05f5  mov     ebx, eax
0x1800d05f7  test    eax, eax
0x1800d05f9  js      loc_1800D06CE
0x1800d05ff  mov     rcx, [rsp+2B0h+var_260]
0x1800d0604  mov     [rsp+2B0h+var_260], r15
0x1800d0609  test    rcx, rcx
0x1800d060c  jz      short loc_1800D061A
0x1800d060e  call    cs:__imp_SRCache_Free
0x1800d0615  nop     dword ptr [rax+rax+00h]
0x1800d061a  mov     rcx, [rsp+2B0h+var_280]
0x1800d061f  mov     [rsp+2B0h+var_280], r15
0x1800d0624  test    rcx, rcx
0x1800d0627  jz      short loc_1800D0635
0x1800d0629  call    cs:__imp_SRCacheContext_Close
0x1800d0630  nop     dword ptr [rax+rax+00h]
0x1800d0635  xor     eax, eax
0x1800d0637  jmp     short loc_1800D068C
0x1800d0639  mov     edx, 170h; void *
0x1800d063e  mov     rcx, [rbp+1B8h]; this
0x1800d0645  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d064c  mov     r9d, ebx; char *
0x1800d064f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0654  mov     rcx, [rsp+2B0h+var_260]
0x1800d0659  mov     [rsp+2B0h+var_260], r15
0x1800d065e  test    rcx, rcx
0x1800d0661  jz      short loc_1800D066F
0x1800d0663  call    cs:__imp_SRCache_Free
0x1800d066a  nop     dword ptr [rax+rax+00h]
0x1800d066f  mov     rcx, [rsp+2B0h+var_280]
0x1800d0674  mov     [rsp+2B0h+var_280], r15
0x1800d0679  test    rcx, rcx
0x1800d067c  jz      short loc_1800D068A
0x1800d067e  call    cs:__imp_SRCacheContext_Close
0x1800d0685  nop     dword ptr [rax+rax+00h]
0x1800d068a  mov     eax, ebx
0x1800d068c  mov     rcx, [rbp+1B0h+var_40]
0x1800d0693  xor     rcx, rsp; StackCookie
0x1800d0696  call    __security_check_cookie
0x1800d069b  add     rsp, 288h
0x1800d06a2  pop     r15
0x1800d06a4  pop     r14
0x1800d06a6  pop     rdi
0x1800d06a7  pop     rsi
0x1800d06a8  pop     rbx
0x1800d06a9  pop     rbp
0x1800d06aa  retn
0x1800d06ac  mov     ebx, 80670012h
0x1800d06b1  mov     edx, 16Dh; void *
0x1800d06b6  mov     rcx, [rbp+1B8h]; this
0x1800d06bd  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d06c4  mov     r9d, ebx; char *
0x1800d06c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d06cc  jmp     short loc_1800D066F
0x1800d06ce  mov     rcx, [rbp+1B8h]; this
0x1800d06d5  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d06dc  mov     r9d, ebx; char *
0x1800d06df  mov     edx, 1A6h; void *
0x1800d06e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d06e9  mov     edx, 173h
0x1800d06ee  jmp     loc_1800D063E
0x1800d06f3  mov     edx, 171h
0x1800d06f8  jmp     loc_1800D063E
0x1800d06fd  mov     rcx, [rbp+1B8h]; this
0x1800d0704  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800d070b  mov     r9d, ebx; char *
0x1800d070e  mov     edx, 18Ch; void *
0x1800d0713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0718  mov     edx, 16Ch
0x1800d071d  jmp     short loc_1800D06B6
```
