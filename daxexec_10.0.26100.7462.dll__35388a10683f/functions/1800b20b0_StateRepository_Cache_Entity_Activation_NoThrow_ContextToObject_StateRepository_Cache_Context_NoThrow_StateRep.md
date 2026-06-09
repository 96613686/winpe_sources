# StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)

- ea: `0x1800b20b0`
- end: `0x1800b253a`
- name: `?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b3a1c`

## callees

- `0x18000e234`
- `0x1800b20b0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2111`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b21f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b227f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2309`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2393`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b241d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b24a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2111`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b21f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b227f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2309`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2393`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b241d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b24a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b219c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b219c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2155`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2239`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b22c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b234d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b23d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2461`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b24ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2155`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2239`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b22c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b234d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b23d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2461`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b24ea`

## string_xrefs

- `0x1800b20d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b216e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800b24fe`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rcx
  int Field_String; // eax
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  int Field_UInt32; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  int v32; // ebx
  __int64 v33; // rcx
  __int64 *v34; // [rsp+20h] [rbp-20h]
  __int64 *v35; // [rsp+20h] [rbp-20h]
  __int64 v36; // [rsp+28h] [rbp-18h] BYREF
  char v37; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_13;
  v8 = *a1;
  v34 = a2 + 1;
  v36 = 0;
  v37 = 1;
  Field_String = SRCacheContext_GetField_String(v8, L"ActivationKey", &v36);
  v10 = Field_String;
  if ( Field_String >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v34);
  if ( v37 )
  {
    v11 = *v34;
    *v34 = v36;
    if ( v11 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 917;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v10,
      (int)v34);
    return (unsigned int)v10;
  }
  if ( a3 )
  {
LABEL_13:
    if ( (a3 & 2) == 0 )
      goto LABEL_17;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Flags", a2 + 2);
  v10 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v34);
    v12 = 921;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_17:
    if ( (a3 & 4) == 0 )
      goto LABEL_27;
  }
  v15 = *a1;
  v34 = a2 + 3;
  v36 = 0;
  v37 = 1;
  v16 = SRCacheContext_GetField_String(v15, L"HostId", &v36);
  v10 = v16;
  if ( v16 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      (int)v34);
  if ( v37 )
  {
    v17 = *v34;
    *v34 = v36;
    if ( v17 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 925;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_27:
    if ( (a3 & 8) == 0 )
      goto LABEL_37;
  }
  v18 = *a1;
  v34 = a2 + 4;
  v36 = 0;
  v37 = 1;
  v19 = SRCacheContext_GetField_String(v18, L"Executable", &v36);
  v10 = v19;
  if ( v19 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v19,
      (int)v34);
  if ( v37 )
  {
    v20 = *v34;
    *v34 = v36;
    if ( v20 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 929;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_37:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_47;
  }
  v21 = *a1;
  v34 = a2 + 5;
  v36 = 0;
  v37 = 1;
  v22 = SRCacheContext_GetField_String(v21, L"Entrypoint", &v36);
  v10 = v22;
  if ( v22 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v22,
      (int)v34);
  if ( v37 )
  {
    v23 = *v34;
    *v34 = v36;
    if ( v23 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 933;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_47:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_57;
  }
  v24 = *a1;
  v34 = a2 + 6;
  v36 = 0;
  v37 = 1;
  v25 = SRCacheContext_GetField_String(v24, L"RuntimeType", &v36);
  v10 = v25;
  if ( v25 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v25,
      (int)v34);
  if ( v37 )
  {
    v26 = *v34;
    *v34 = v36;
    if ( v26 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 937;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_57:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_67;
  }
  v27 = *a1;
  v34 = a2 + 7;
  v36 = 0;
  v37 = 1;
  v28 = SRCacheContext_GetField_String(v27, L"StartPage", &v36);
  v10 = v28;
  if ( v28 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v28,
      (int)v34);
  if ( v37 )
  {
    v29 = *v34;
    *v34 = v36;
    if ( v29 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 941;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_67:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_76;
  }
  v30 = *a1;
  v35 = a2 + 8;
  v36 = 0;
  v37 = 1;
  v31 = SRCacheContext_GetField_String(v30, L"ResourceGroup", &v36);
  v32 = v31;
  if ( v31 >= 0 )
    v32 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v31,
      (int)v35);
  if ( v37 )
  {
    v33 = *v35;
    *v35 = v36;
    if ( v33 )
      SRCache_Free();
  }
  if ( v32 >= 0 )
  {
LABEL_76:
    *a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v32,
      (int)v35);
    return (unsigned int)v32;
  }
}

```

## disassembly

```asm
0x1800b20b0  mov     [rsp-28h+arg_0], rbx
0x1800b20b5  mov     [rsp-28h+arg_8], rsi
0x1800b20ba  mov     [rsp-28h+arg_10], rdi
0x1800b20bf  push    rbp
0x1800b20c0  push    r12
0x1800b20c2  push    r13
0x1800b20c4  push    r14
0x1800b20c6  push    r15
0x1800b20c8  mov     rbp, rsp
0x1800b20cb  sub     rsp, 40h
0x1800b20cf  xor     r12d, r12d
0x1800b20d2  lea     r13, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b20d9  mov     r15, r9
0x1800b20dc  mov     rbx, r8
0x1800b20df  mov     rsi, rdx
0x1800b20e2  mov     r14, rcx
0x1800b20e5  test    r8, r8
0x1800b20e8  jz      short loc_1800B20F3
0x1800b20ea  test    bl, 1
0x1800b20ed  jz      loc_1800B2189
0x1800b20f3  mov     rcx, [rcx]
0x1800b20f6  lea     rax, [rdx+8]
0x1800b20fa  lea     rdx, aActivationkey; "ActivationKey"
0x1800b2101  mov     [rbp+var_20], rax
0x1800b2105  lea     r8, [rbp+var_18]
0x1800b2109  mov     [rbp+var_18], r12
0x1800b210d  mov     [rbp+var_10], 1
0x1800b2111  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2118  nop     dword ptr [rax+rax+00h]
0x1800b211d  mov     edi, eax
0x1800b211f  test    eax, eax
0x1800b2121  jns     short loc_1800B2139
0x1800b2123  mov     rcx, [rbp+28h]; this
0x1800b2127  mov     r9d, eax; char *
0x1800b212a  mov     r8, r13; unsigned int
0x1800b212d  mov     edx, 246h; void *
0x1800b2132  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2137  jmp     short loc_1800B213C
0x1800b2139  mov     edi, r12d
0x1800b213c  cmp     [rbp+var_10], r12b
0x1800b2140  jz      short loc_1800B2161
0x1800b2142  mov     rdx, [rbp+var_20]
0x1800b2146  mov     rax, [rbp+var_18]
0x1800b214a  mov     rcx, [rdx]
0x1800b214d  mov     [rdx], rax
0x1800b2150  test    rcx, rcx
0x1800b2153  jz      short loc_1800B2161
0x1800b2155  call    cs:__imp_SRCache_Free
0x1800b215c  nop     dword ptr [rax+rax+00h]
0x1800b2161  test    edi, edi
0x1800b2163  jns     short loc_1800B2184
0x1800b2165  mov     edx, 395h; void *
0x1800b216a  mov     rcx, [rbp+28h]; this
0x1800b216e  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b2175  mov     r9d, edi; char *
0x1800b2178  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b217d  mov     eax, edi
0x1800b217f  jmp     loc_1800B251B
0x1800b2184  test    rbx, rbx
0x1800b2187  jz      short loc_1800B218E
0x1800b2189  test    bl, 2
0x1800b218c  jz      short loc_1800B21CE
0x1800b218e  mov     rcx, [r14]
0x1800b2191  lea     r8, [rsi+10h]
0x1800b2195  lea     rdx, aFlags; "Flags"
0x1800b219c  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b21a3  nop     dword ptr [rax+rax+00h]
0x1800b21a8  mov     edi, eax
0x1800b21aa  test    eax, eax
0x1800b21ac  jns     short loc_1800B21C9
0x1800b21ae  mov     rcx, [rbp+28h]; this
0x1800b21b2  mov     r9d, eax; char *
0x1800b21b5  mov     r8, r13; unsigned int
0x1800b21b8  mov     edx, 221h; void *
0x1800b21bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b21c2  mov     edx, 399h
0x1800b21c7  jmp     short loc_1800B216A
0x1800b21c9  test    rbx, rbx
0x1800b21cc  jz      short loc_1800B21D7
0x1800b21ce  test    bl, 4
0x1800b21d1  jz      loc_1800B2258
0x1800b21d7  mov     rcx, [r14]
0x1800b21da  lea     rax, [rsi+18h]
0x1800b21de  lea     r8, [rbp+var_18]
0x1800b21e2  mov     [rbp+var_20], rax
0x1800b21e6  lea     rdx, aHostid; "HostId"
0x1800b21ed  mov     [rbp+var_18], r12
0x1800b21f1  mov     [rbp+var_10], 1
0x1800b21f5  call    cs:__imp_SRCacheContext_GetField_String
0x1800b21fc  nop     dword ptr [rax+rax+00h]
0x1800b2201  mov     edi, eax
0x1800b2203  test    eax, eax
0x1800b2205  jns     short loc_1800B221D
0x1800b2207  mov     rcx, [rbp+28h]; this
0x1800b220b  mov     r9d, eax; char *
0x1800b220e  mov     r8, r13; unsigned int
0x1800b2211  mov     edx, 246h; void *
0x1800b2216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b221b  jmp     short loc_1800B2220
0x1800b221d  mov     edi, r12d
0x1800b2220  cmp     [rbp+var_10], r12b
0x1800b2224  jz      short loc_1800B2245
0x1800b2226  mov     rdx, [rbp+var_20]
0x1800b222a  mov     rax, [rbp+var_18]
0x1800b222e  mov     rcx, [rdx]
0x1800b2231  mov     [rdx], rax
0x1800b2234  test    rcx, rcx
0x1800b2237  jz      short loc_1800B2245
0x1800b2239  call    cs:__imp_SRCache_Free
0x1800b2240  nop     dword ptr [rax+rax+00h]
0x1800b2245  test    edi, edi
0x1800b2247  jns     short loc_1800B2253
0x1800b2249  mov     edx, 39Dh
0x1800b224e  jmp     loc_1800B216A
0x1800b2253  test    rbx, rbx
0x1800b2256  jz      short loc_1800B2261
0x1800b2258  test    bl, 8
0x1800b225b  jz      loc_1800B22E2
0x1800b2261  mov     rcx, [r14]
0x1800b2264  lea     rax, [rsi+20h]
0x1800b2268  lea     r8, [rbp+var_18]
0x1800b226c  mov     [rbp+var_20], rax
0x1800b2270  lea     rdx, aExecutable; "Executable"
0x1800b2277  mov     [rbp+var_18], r12
0x1800b227b  mov     [rbp+var_10], 1
0x1800b227f  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2286  nop     dword ptr [rax+rax+00h]
0x1800b228b  mov     edi, eax
0x1800b228d  test    eax, eax
0x1800b228f  jns     short loc_1800B22A7
0x1800b2291  mov     rcx, [rbp+28h]; this
0x1800b2295  mov     r9d, eax; char *
0x1800b2298  mov     r8, r13; unsigned int
0x1800b229b  mov     edx, 246h; void *
0x1800b22a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b22a5  jmp     short loc_1800B22AA
0x1800b22a7  mov     edi, r12d
0x1800b22aa  cmp     [rbp+var_10], r12b
0x1800b22ae  jz      short loc_1800B22CF
0x1800b22b0  mov     rdx, [rbp+var_20]
0x1800b22b4  mov     rax, [rbp+var_18]
0x1800b22b8  mov     rcx, [rdx]
0x1800b22bb  mov     [rdx], rax
0x1800b22be  test    rcx, rcx
0x1800b22c1  jz      short loc_1800B22CF
0x1800b22c3  call    cs:__imp_SRCache_Free
0x1800b22ca  nop     dword ptr [rax+rax+00h]
0x1800b22cf  test    edi, edi
0x1800b22d1  jns     short loc_1800B22DD
0x1800b22d3  mov     edx, 3A1h
0x1800b22d8  jmp     loc_1800B216A
0x1800b22dd  test    rbx, rbx
0x1800b22e0  jz      short loc_1800B22EB
0x1800b22e2  test    bl, 10h
0x1800b22e5  jz      loc_1800B236C
0x1800b22eb  mov     rcx, [r14]
0x1800b22ee  lea     rax, [rsi+28h]
0x1800b22f2  lea     r8, [rbp+var_18]
0x1800b22f6  mov     [rbp+var_20], rax
0x1800b22fa  lea     rdx, aEntrypoint; "Entrypoint"
0x1800b2301  mov     [rbp+var_18], r12
0x1800b2305  mov     [rbp+var_10], 1
0x1800b2309  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2310  nop     dword ptr [rax+rax+00h]
0x1800b2315  mov     edi, eax
0x1800b2317  test    eax, eax
0x1800b2319  jns     short loc_1800B2331
0x1800b231b  mov     rcx, [rbp+28h]; this
0x1800b231f  mov     r9d, eax; char *
0x1800b2322  mov     r8, r13; unsigned int
0x1800b2325  mov     edx, 246h; void *
0x1800b232a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b232f  jmp     short loc_1800B2334
0x1800b2331  mov     edi, r12d
0x1800b2334  cmp     [rbp+var_10], r12b
0x1800b2338  jz      short loc_1800B2359
0x1800b233a  mov     rdx, [rbp+var_20]
0x1800b233e  mov     rax, [rbp+var_18]
0x1800b2342  mov     rcx, [rdx]
0x1800b2345  mov     [rdx], rax
0x1800b2348  test    rcx, rcx
0x1800b234b  jz      short loc_1800B2359
0x1800b234d  call    cs:__imp_SRCache_Free
0x1800b2354  nop     dword ptr [rax+rax+00h]
0x1800b2359  test    edi, edi
0x1800b235b  jns     short loc_1800B2367
0x1800b235d  mov     edx, 3A5h
0x1800b2362  jmp     loc_1800B216A
0x1800b2367  test    rbx, rbx
0x1800b236a  jz      short loc_1800B2375
0x1800b236c  test    bl, 20h
0x1800b236f  jz      loc_1800B23F6
0x1800b2375  mov     rcx, [r14]
0x1800b2378  lea     rax, [rsi+30h]
0x1800b237c  lea     r8, [rbp+var_18]
0x1800b2380  mov     [rbp+var_20], rax
0x1800b2384  lea     rdx, aRuntimetype; "RuntimeType"
0x1800b238b  mov     [rbp+var_18], r12
0x1800b238f  mov     [rbp+var_10], 1
0x1800b2393  call    cs:__imp_SRCacheContext_GetField_String
0x1800b239a  nop     dword ptr [rax+rax+00h]
0x1800b239f  mov     edi, eax
0x1800b23a1  test    eax, eax
0x1800b23a3  jns     short loc_1800B23BB
0x1800b23a5  mov     rcx, [rbp+28h]; this
0x1800b23a9  mov     r9d, eax; char *
0x1800b23ac  mov     r8, r13; unsigned int
0x1800b23af  mov     edx, 246h; void *
0x1800b23b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b23b9  jmp     short loc_1800B23BE
0x1800b23bb  mov     edi, r12d
0x1800b23be  cmp     [rbp+var_10], r12b
0x1800b23c2  jz      short loc_1800B23E3
0x1800b23c4  mov     rdx, [rbp+var_20]
0x1800b23c8  mov     rax, [rbp+var_18]
0x1800b23cc  mov     rcx, [rdx]
0x1800b23cf  mov     [rdx], rax
0x1800b23d2  test    rcx, rcx
0x1800b23d5  jz      short loc_1800B23E3
0x1800b23d7  call    cs:__imp_SRCache_Free
0x1800b23de  nop     dword ptr [rax+rax+00h]
0x1800b23e3  test    edi, edi
0x1800b23e5  jns     short loc_1800B23F1
0x1800b23e7  mov     edx, 3A9h
0x1800b23ec  jmp     loc_1800B216A
0x1800b23f1  test    rbx, rbx
0x1800b23f4  jz      short loc_1800B23FF
0x1800b23f6  test    bl, 40h
0x1800b23f9  jz      loc_1800B2480
0x1800b23ff  mov     rcx, [r14]
0x1800b2402  lea     rax, [rsi+38h]
0x1800b2406  lea     r8, [rbp+var_18]
0x1800b240a  mov     [rbp+var_20], rax
0x1800b240e  lea     rdx, aStartpage; "StartPage"
0x1800b2415  mov     [rbp+var_18], r12
0x1800b2419  mov     [rbp+var_10], 1
0x1800b241d  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2424  nop     dword ptr [rax+rax+00h]
0x1800b2429  mov     edi, eax
0x1800b242b  test    eax, eax
0x1800b242d  jns     short loc_1800B2445
0x1800b242f  mov     rcx, [rbp+28h]; this
0x1800b2433  mov     r9d, eax; char *
0x1800b2436  mov     r8, r13; unsigned int
0x1800b2439  mov     edx, 246h; void *
0x1800b243e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2443  jmp     short loc_1800B2448
0x1800b2445  mov     edi, r12d
0x1800b2448  cmp     [rbp+var_10], r12b
0x1800b244c  jz      short loc_1800B246D
0x1800b244e  mov     rdx, [rbp+var_20]
0x1800b2452  mov     rax, [rbp+var_18]
0x1800b2456  mov     rcx, [rdx]
0x1800b2459  mov     [rdx], rax
0x1800b245c  test    rcx, rcx
0x1800b245f  jz      short loc_1800B246D
0x1800b2461  call    cs:__imp_SRCache_Free
0x1800b2468  nop     dword ptr [rax+rax+00h]
0x1800b246d  test    edi, edi
0x1800b246f  jns     short loc_1800B247B
0x1800b2471  mov     edx, 3ADh
0x1800b2476  jmp     loc_1800B216A
0x1800b247b  test    rbx, rbx
0x1800b247e  jz      short loc_1800B2488
0x1800b2480  test    bl, bl
0x1800b2482  jns     loc_1800B2516
0x1800b2488  mov     rcx, [r14]
0x1800b248b  lea     rax, [rsi+40h]
0x1800b248f  lea     r8, [rbp+var_18]
0x1800b2493  mov     [rbp+var_20], rax
0x1800b2497  lea     rdx, aResourcegroup; "ResourceGroup"
0x1800b249e  mov     [rbp+var_18], r12
0x1800b24a2  mov     [rbp+var_10], 1
0x1800b24a6  call    cs:__imp_SRCacheContext_GetField_String
0x1800b24ad  nop     dword ptr [rax+rax+00h]
0x1800b24b2  mov     ebx, eax
0x1800b24b4  test    eax, eax
0x1800b24b6  jns     short loc_1800B24CE
0x1800b24b8  mov     rcx, [rbp+28h]; this
0x1800b24bc  mov     r9d, eax; char *
0x1800b24bf  mov     r8, r13; unsigned int
0x1800b24c2  mov     edx, 246h; void *
0x1800b24c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b24cc  jmp     short loc_1800B24D1
0x1800b24ce  mov     ebx, r12d
0x1800b24d1  cmp     [rbp+var_10], r12b
0x1800b24d5  jz      short loc_1800B24F6
0x1800b24d7  mov     rdx, [rbp+var_20]
0x1800b24db  mov     rax, [rbp+var_18]
0x1800b24df  mov     rcx, [rdx]
0x1800b24e2  mov     [rdx], rax
0x1800b24e5  test    rcx, rcx
0x1800b24e8  jz      short loc_1800B24F6
0x1800b24ea  call    cs:__imp_SRCache_Free
0x1800b24f1  nop     dword ptr [rax+rax+00h]
0x1800b24f6  test    ebx, ebx
0x1800b24f8  jns     short loc_1800B2516
0x1800b24fa  mov     rcx, [rbp+28h]; this
0x1800b24fe  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b2505  mov     r9d, ebx; char *
  ... truncated ...
```
