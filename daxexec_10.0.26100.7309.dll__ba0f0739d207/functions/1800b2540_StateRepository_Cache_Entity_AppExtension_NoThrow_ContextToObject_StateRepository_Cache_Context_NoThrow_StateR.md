# StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,__int64)

- ea: `0x1800b2540`
- end: `0x1800b28d1`
- name: `?ContextToObject@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b76c0`

## callees

- `0x18000e234`
- `0x1800b2540`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2589`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2625`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b269f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2719`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2793`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2589`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2625`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b269f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2719`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2793`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b27fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b27fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b25d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2667`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b26e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b275b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b27d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2893`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b25d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2667`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b26e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b275b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b27d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2893`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b284f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b284f`

## string_xrefs

- `0x1800b2595`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b25f1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b27f6`: `Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  int Field_String; // eax
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  int Field_UInt32; // eax
  __int64 v26; // rcx
  int Field_Binary; // eax
  __int64 v28; // rcx
  __int64 *v29; // [rsp+20h] [rbp-20h]
  __int64 v30; // [rsp+28h] [rbp-18h] BYREF
  char v31; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v31 = 1;
  v29 = a2 + 1;
  v6 = *a1;
  v30 = 0;
  Field_String = SRCacheContext_GetField_String(v6, L"Name", &v30);
  v9 = Field_String;
  if ( Field_String >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v29);
  if ( v31 )
  {
    v10 = *v29;
    *v29 = v30;
    if ( v10 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 718;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v9,
      (int)v29);
    return (unsigned int)v9;
  }
  v13 = *a1;
  v29 = a2 + 2;
  v30 = 0;
  v31 = 1;
  v14 = SRCacheContext_GetField_String(v13, L"Id", &v30);
  v9 = v14;
  if ( v14 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      (int)v29);
  if ( v31 )
  {
    v15 = *v29;
    *v29 = v30;
    if ( v15 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 722;
    goto LABEL_9;
  }
  v16 = *a1;
  v29 = a2 + 3;
  v30 = 0;
  v31 = 1;
  v17 = SRCacheContext_GetField_String(v16, L"PublicFolder", &v30);
  v9 = v17;
  if ( v17 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      (int)v29);
  if ( v31 )
  {
    v18 = *v29;
    *v29 = v30;
    if ( v18 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 726;
    goto LABEL_9;
  }
  v19 = *a1;
  v29 = a2 + 4;
  v30 = 0;
  v31 = 1;
  v20 = SRCacheContext_GetField_String(v19, L"DisplayName", &v30);
  v9 = v20;
  if ( v20 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v20,
      (int)v29);
  if ( v31 )
  {
    v21 = *v29;
    *v29 = v30;
    if ( v21 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 730;
    goto LABEL_9;
  }
  v22 = *a1;
  v29 = a2 + 5;
  v30 = 0;
  v31 = 1;
  v23 = SRCacheContext_GetField_String(v22, L"Description", &v30);
  v9 = v23;
  if ( v23 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v23,
      (int)v29);
  if ( v31 )
  {
    v24 = *v29;
    *v29 = v30;
    if ( v24 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 734;
    goto LABEL_9;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Extension", a2 + 6);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v29);
    v11 = 738;
    goto LABEL_9;
  }
  v26 = *a1;
  v29 = a2 + 7;
  v30 = 0;
  v31 = 1;
  Field_Binary = SRCacheContext_GetField_Binary(v26, L"_Dictionary", a2 + 8, &v30);
  v9 = Field_Binary;
  if ( Field_Binary >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_Binary,
      (int)v29);
  if ( v31 )
  {
    v28 = *v29;
    *v29 = v30;
    if ( v28 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v11 = 742;
    goto LABEL_9;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x1800b2540  mov     [rsp-28h+arg_0], rbx
0x1800b2545  mov     [rsp-28h+arg_8], rsi
0x1800b254a  mov     [rsp-28h+arg_10], rdi
0x1800b254f  push    rbp
0x1800b2550  push    r12
0x1800b2552  push    r13
0x1800b2554  push    r14
0x1800b2556  push    r15
0x1800b2558  mov     rbp, rsp
0x1800b255b  sub     rsp, 40h
0x1800b255f  lea     rax, [rdx+8]
0x1800b2563  mov     [rbp+var_10], 1
0x1800b2567  mov     rdi, rdx
0x1800b256a  mov     [rbp+var_20], rax
0x1800b256e  mov     rsi, rcx
0x1800b2571  lea     rdx, aName; "Name"
0x1800b2578  mov     rcx, [rcx]
0x1800b257b  lea     r8, [rbp+var_18]
0x1800b257f  xor     r15d, r15d
0x1800b2582  mov     r14, r9
0x1800b2585  mov     [rbp+var_18], r15
0x1800b2589  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2590  nop     dword ptr [rax+rax+00h]
0x1800b2595  lea     r12, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b259c  mov     r13d, 246h
0x1800b25a2  mov     ebx, eax
0x1800b25a4  test    eax, eax
0x1800b25a6  jns     short loc_1800B25BC
0x1800b25a8  mov     rcx, [rbp+28h]; this
0x1800b25ac  mov     r9d, eax; char *
0x1800b25af  mov     r8, r12; unsigned int
0x1800b25b2  mov     edx, r13d; void *
0x1800b25b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b25ba  jmp     short loc_1800B25BF
0x1800b25bc  mov     ebx, r15d
0x1800b25bf  cmp     [rbp+var_10], r15b
0x1800b25c3  jz      short loc_1800B25E4
0x1800b25c5  mov     rdx, [rbp+var_20]
0x1800b25c9  mov     rax, [rbp+var_18]
0x1800b25cd  mov     rcx, [rdx]
0x1800b25d0  mov     [rdx], rax
0x1800b25d3  test    rcx, rcx
0x1800b25d6  jz      short loc_1800B25E4
0x1800b25d8  call    cs:__imp_SRCache_Free
0x1800b25df  nop     dword ptr [rax+rax+00h]
0x1800b25e4  test    ebx, ebx
0x1800b25e6  jns     short loc_1800B2607
0x1800b25e8  mov     edx, 2CEh; void *
0x1800b25ed  mov     rcx, [rbp+28h]; this
0x1800b25f1  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b25f8  mov     r9d, ebx; char *
0x1800b25fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2600  mov     eax, ebx
0x1800b2602  jmp     loc_1800B28B2
0x1800b2607  mov     rcx, [rsi]
0x1800b260a  lea     rax, [rdi+10h]
0x1800b260e  lea     r8, [rbp+var_18]
0x1800b2612  mov     [rbp+var_20], rax
0x1800b2616  lea     rdx, aId; "Id"
0x1800b261d  mov     [rbp+var_18], r15
0x1800b2621  mov     [rbp+var_10], 1
0x1800b2625  call    cs:__imp_SRCacheContext_GetField_String
0x1800b262c  nop     dword ptr [rax+rax+00h]
0x1800b2631  mov     ebx, eax
0x1800b2633  test    eax, eax
0x1800b2635  jns     short loc_1800B264B
0x1800b2637  mov     rcx, [rbp+28h]; this
0x1800b263b  mov     r9d, eax; char *
0x1800b263e  mov     r8, r12; unsigned int
0x1800b2641  mov     edx, r13d; void *
0x1800b2644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2649  jmp     short loc_1800B264E
0x1800b264b  mov     ebx, r15d
0x1800b264e  cmp     [rbp+var_10], r15b
0x1800b2652  jz      short loc_1800B2673
0x1800b2654  mov     rdx, [rbp+var_20]
0x1800b2658  mov     rax, [rbp+var_18]
0x1800b265c  mov     rcx, [rdx]
0x1800b265f  mov     [rdx], rax
0x1800b2662  test    rcx, rcx
0x1800b2665  jz      short loc_1800B2673
0x1800b2667  call    cs:__imp_SRCache_Free
0x1800b266e  nop     dword ptr [rax+rax+00h]
0x1800b2673  test    ebx, ebx
0x1800b2675  jns     short loc_1800B2681
0x1800b2677  mov     edx, 2D2h
0x1800b267c  jmp     loc_1800B25ED
0x1800b2681  mov     rcx, [rsi]
0x1800b2684  lea     rax, [rdi+18h]
0x1800b2688  lea     r8, [rbp+var_18]
0x1800b268c  mov     [rbp+var_20], rax
0x1800b2690  lea     rdx, aPublicfolder; "PublicFolder"
0x1800b2697  mov     [rbp+var_18], r15
0x1800b269b  mov     [rbp+var_10], 1
0x1800b269f  call    cs:__imp_SRCacheContext_GetField_String
0x1800b26a6  nop     dword ptr [rax+rax+00h]
0x1800b26ab  mov     ebx, eax
0x1800b26ad  test    eax, eax
0x1800b26af  jns     short loc_1800B26C5
0x1800b26b1  mov     rcx, [rbp+28h]; this
0x1800b26b5  mov     r9d, eax; char *
0x1800b26b8  mov     r8, r12; unsigned int
0x1800b26bb  mov     edx, r13d; void *
0x1800b26be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b26c3  jmp     short loc_1800B26C8
0x1800b26c5  mov     ebx, r15d
0x1800b26c8  cmp     [rbp+var_10], r15b
0x1800b26cc  jz      short loc_1800B26ED
0x1800b26ce  mov     rdx, [rbp+var_20]
0x1800b26d2  mov     rax, [rbp+var_18]
0x1800b26d6  mov     rcx, [rdx]
0x1800b26d9  mov     [rdx], rax
0x1800b26dc  test    rcx, rcx
0x1800b26df  jz      short loc_1800B26ED
0x1800b26e1  call    cs:__imp_SRCache_Free
0x1800b26e8  nop     dword ptr [rax+rax+00h]
0x1800b26ed  test    ebx, ebx
0x1800b26ef  jns     short loc_1800B26FB
0x1800b26f1  mov     edx, 2D6h
0x1800b26f6  jmp     loc_1800B25ED
0x1800b26fb  mov     rcx, [rsi]
0x1800b26fe  lea     rax, [rdi+20h]
0x1800b2702  lea     r8, [rbp+var_18]
0x1800b2706  mov     [rbp+var_20], rax
0x1800b270a  lea     rdx, aDisplayname; "DisplayName"
0x1800b2711  mov     [rbp+var_18], r15
0x1800b2715  mov     [rbp+var_10], 1
0x1800b2719  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2720  nop     dword ptr [rax+rax+00h]
0x1800b2725  mov     ebx, eax
0x1800b2727  test    eax, eax
0x1800b2729  jns     short loc_1800B273F
0x1800b272b  mov     rcx, [rbp+28h]; this
0x1800b272f  mov     r9d, eax; char *
0x1800b2732  mov     r8, r12; unsigned int
0x1800b2735  mov     edx, r13d; void *
0x1800b2738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b273d  jmp     short loc_1800B2742
0x1800b273f  mov     ebx, r15d
0x1800b2742  cmp     [rbp+var_10], r15b
0x1800b2746  jz      short loc_1800B2767
0x1800b2748  mov     rdx, [rbp+var_20]
0x1800b274c  mov     rax, [rbp+var_18]
0x1800b2750  mov     rcx, [rdx]
0x1800b2753  mov     [rdx], rax
0x1800b2756  test    rcx, rcx
0x1800b2759  jz      short loc_1800B2767
0x1800b275b  call    cs:__imp_SRCache_Free
0x1800b2762  nop     dword ptr [rax+rax+00h]
0x1800b2767  test    ebx, ebx
0x1800b2769  jns     short loc_1800B2775
0x1800b276b  mov     edx, 2DAh
0x1800b2770  jmp     loc_1800B25ED
0x1800b2775  mov     rcx, [rsi]
0x1800b2778  lea     rax, [rdi+28h]
0x1800b277c  lea     r8, [rbp+var_18]
0x1800b2780  mov     [rbp+var_20], rax
0x1800b2784  lea     rdx, aDescription; "Description"
0x1800b278b  mov     [rbp+var_18], r15
0x1800b278f  mov     [rbp+var_10], 1
0x1800b2793  call    cs:__imp_SRCacheContext_GetField_String
0x1800b279a  nop     dword ptr [rax+rax+00h]
0x1800b279f  mov     ebx, eax
0x1800b27a1  test    eax, eax
0x1800b27a3  jns     short loc_1800B27B9
0x1800b27a5  mov     rcx, [rbp+28h]; this
0x1800b27a9  mov     r9d, eax; char *
0x1800b27ac  mov     r8, r12; unsigned int
0x1800b27af  mov     edx, r13d; void *
0x1800b27b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b27b7  jmp     short loc_1800B27BC
0x1800b27b9  mov     ebx, r15d
0x1800b27bc  cmp     [rbp+var_10], r15b
0x1800b27c0  jz      short loc_1800B27E1
0x1800b27c2  mov     rdx, [rbp+var_20]
0x1800b27c6  mov     rax, [rbp+var_18]
0x1800b27ca  mov     rcx, [rdx]
0x1800b27cd  mov     [rdx], rax
0x1800b27d0  test    rcx, rcx
0x1800b27d3  jz      short loc_1800B27E1
0x1800b27d5  call    cs:__imp_SRCache_Free
0x1800b27dc  nop     dword ptr [rax+rax+00h]
0x1800b27e1  test    ebx, ebx
0x1800b27e3  jns     short loc_1800B27EF
0x1800b27e5  mov     edx, 2DEh
0x1800b27ea  jmp     loc_1800B25ED
0x1800b27ef  mov     rcx, [rsi]
0x1800b27f2  lea     r8, [rdi+30h]
0x1800b27f6  lea     rdx, aExtension; "Extension"
0x1800b27fd  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b2804  nop     dword ptr [rax+rax+00h]
0x1800b2809  mov     ebx, eax
0x1800b280b  test    eax, eax
0x1800b280d  jns     short loc_1800B282D
0x1800b280f  mov     rcx, [rbp+28h]; this
0x1800b2813  mov     r9d, eax; char *
0x1800b2816  mov     r8, r12; unsigned int
0x1800b2819  mov     edx, 221h; void *
0x1800b281e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2823  mov     edx, 2E2h
0x1800b2828  jmp     loc_1800B25ED
0x1800b282d  mov     rcx, [rsi]
0x1800b2830  lea     rax, [rdi+38h]
0x1800b2834  lea     r8, [rdi+40h]
0x1800b2838  mov     [rbp+var_20], rax
0x1800b283c  lea     r9, [rbp+var_18]
0x1800b2840  mov     [rbp+var_18], r15
0x1800b2844  lea     rdx, aDictionary; "_Dictionary"
0x1800b284b  mov     [rbp+var_10], 1
0x1800b284f  call    cs:__imp_SRCacheContext_GetField_Binary
0x1800b2856  nop     dword ptr [rax+rax+00h]
0x1800b285b  mov     ebx, eax
0x1800b285d  test    eax, eax
0x1800b285f  jns     short loc_1800B2877
0x1800b2861  mov     rcx, [rbp+28h]; this
0x1800b2865  mov     r9d, eax; char *
0x1800b2868  mov     r8, r12; unsigned int
0x1800b286b  mov     edx, 24Fh; void *
0x1800b2870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2875  jmp     short loc_1800B287A
0x1800b2877  mov     ebx, r15d
0x1800b287a  cmp     [rbp+var_10], r15b
0x1800b287e  jz      short loc_1800B289F
0x1800b2880  mov     rdx, [rbp+var_20]
0x1800b2884  mov     rax, [rbp+var_18]
0x1800b2888  mov     rcx, [rdx]
0x1800b288b  mov     [rdx], rax
0x1800b288e  test    rcx, rcx
0x1800b2891  jz      short loc_1800B289F
0x1800b2893  call    cs:__imp_SRCache_Free
0x1800b289a  nop     dword ptr [rax+rax+00h]
0x1800b289f  test    ebx, ebx
0x1800b28a1  jns     short loc_1800B28AD
0x1800b28a3  mov     edx, 2E6h
0x1800b28a8  jmp     loc_1800B25ED
0x1800b28ad  mov     [rdi], r14
0x1800b28b0  xor     eax, eax
0x1800b28b2  lea     r11, [rsp+40h+var_s0]
0x1800b28b7  mov     rbx, [r11+30h]
0x1800b28bb  mov     rsi, [r11+38h]
0x1800b28bf  mov     rdi, [r11+40h]
0x1800b28c3  mov     rsp, r11
0x1800b28c6  pop     r15
0x1800b28c8  pop     r14
0x1800b28ca  pop     r13
0x1800b28cc  pop     r12
0x1800b28ce  pop     rbp
0x1800b28cf  retn
```
