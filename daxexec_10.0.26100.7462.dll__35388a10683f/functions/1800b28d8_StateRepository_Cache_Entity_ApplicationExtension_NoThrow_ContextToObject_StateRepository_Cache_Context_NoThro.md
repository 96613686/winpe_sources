# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)

- ea: `0x1800b28d8`
- end: `0x1800b2d29`
- name: `?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b3c14`

## callees

- `0x18000e234`
- `0x1800b28d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2a21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2af3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2b7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2c06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2a21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2af3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2b7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b2c06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b2922`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b297f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b29c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b2a96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b2922`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b297f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b29c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b2a96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2a64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2b36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2bc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2c49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2cd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2a64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2b36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2bc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2c49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b2cd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b2c96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b2c96`

## string_xrefs

- `0x1800b28f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b2bf7`: `CurrentDirectoryPath`
- `0x1800b2951`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800b2ced`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  int Field_UInt32; // eax
  int v9; // edi
  __int64 v10; // rdx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int Field_String; // eax
  __int64 v16; // rcx
  int v17; // eax
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
  int Field_Binary; // eax
  int v29; // ebx
  __int64 v30; // rcx
  __int64 *v31; // [rsp+20h] [rbp-20h]
  __int64 *v32; // [rsp+20h] [rbp-20h]
  __int64 v33; // [rsp+28h] [rbp-18h] BYREF
  char v34; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_7;
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Application", a2 + 1);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v31);
    v10 = 974;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v9,
      (int)v31);
    return (unsigned int)v9;
  }
  if ( a3 )
  {
LABEL_7:
    if ( (a3 & 2) == 0 )
      goto LABEL_11;
  }
  v12 = SRCacheContext_GetField_UInt32(*a1, L"Index", a2 + 2);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      (int)v31);
    v10 = 978;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_11:
    if ( (a3 & 4) == 0 )
      goto LABEL_15;
  }
  v13 = SRCacheContext_GetField_UInt32(*a1, L"Flags", (char *)a2 + 20);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      (int)v31);
    v10 = 982;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_15:
    if ( (a3 & 8) == 0 )
      goto LABEL_25;
  }
  v14 = *a1;
  v33 = 0;
  v31 = a2 + 3;
  v34 = 1;
  Field_String = SRCacheContext_GetField_String(v14, L"Category", &v33);
  v9 = Field_String;
  if ( Field_String >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v31);
  if ( v34 )
  {
    v16 = *v31;
    *v31 = v33;
    if ( v16 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v10 = 986;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_25:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_29;
  }
  v17 = SRCacheContext_GetField_UInt32(*a1, L"Activation", a2 + 4);
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      (int)v31);
    v10 = 990;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_29:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_39;
  }
  v18 = *a1;
  v33 = 0;
  v31 = a2 + 5;
  v34 = 1;
  v19 = SRCacheContext_GetField_String(v18, L"HostId", &v33);
  v9 = v19;
  if ( v19 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v19,
      (int)v31);
  if ( v34 )
  {
    v20 = *v31;
    *v31 = v33;
    if ( v20 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v10 = 994;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_39:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_49;
  }
  v21 = *a1;
  v33 = 0;
  v31 = a2 + 6;
  v34 = 1;
  v22 = SRCacheContext_GetField_String(v21, L"Parameters", &v33);
  v9 = v22;
  if ( v22 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v22,
      (int)v31);
  if ( v34 )
  {
    v23 = *v31;
    *v31 = v33;
    if ( v23 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v10 = 998;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_49:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_59;
  }
  v24 = *a1;
  v33 = 0;
  v31 = a2 + 7;
  v34 = 1;
  v25 = SRCacheContext_GetField_String(v24, L"CurrentDirectoryPath", &v33);
  v9 = v25;
  if ( v25 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v25,
      (int)v31);
  if ( v34 )
  {
    v26 = *v31;
    *v31 = v33;
    if ( v26 )
      SRCache_Free();
  }
  if ( v9 < 0 )
  {
    v10 = 1002;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_59:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_68;
  }
  v27 = *a1;
  v33 = 0;
  v32 = a2 + 8;
  v34 = 1;
  Field_Binary = SRCacheContext_GetField_Binary(v27, L"_Dictionary", a2 + 9, &v33);
  v29 = Field_Binary;
  if ( Field_Binary >= 0 )
    v29 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_Binary,
      (int)v32);
  if ( v34 )
  {
    v30 = *v32;
    *v32 = v33;
    if ( v30 )
      SRCache_Free();
  }
  if ( v29 >= 0 )
  {
LABEL_68:
    *a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EE,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v29,
      (int)v32);
    return (unsigned int)v29;
  }
}

```

## disassembly

```asm
0x1800b28d8  mov     rax, rsp
0x1800b28db  mov     [rax+8], rbx
0x1800b28df  mov     [rax+10h], rsi
0x1800b28e3  mov     [rax+18h], rdi
0x1800b28e7  mov     [rax+20h], r13
0x1800b28eb  push    rbp
0x1800b28ec  push    r14
0x1800b28ee  push    r15
0x1800b28f0  mov     rbp, rsp
0x1800b28f3  sub     rsp, 40h
0x1800b28f7  lea     r13, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b28fe  mov     r15, r9
0x1800b2901  mov     rbx, r8
0x1800b2904  mov     rsi, rdx
0x1800b2907  mov     r14, rcx
0x1800b290a  test    r8, r8
0x1800b290d  jz      short loc_1800B2914
0x1800b290f  test    bl, 1
0x1800b2912  jz      short loc_1800B296C
0x1800b2914  mov     rcx, [rcx]
0x1800b2917  lea     r8, [rdx+8]
0x1800b291b  lea     rdx, aApplication; "Application"
0x1800b2922  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b2929  nop     dword ptr [rax+rax+00h]
0x1800b292e  mov     edi, eax
0x1800b2930  test    eax, eax
0x1800b2932  jns     short loc_1800B2967
0x1800b2934  mov     rcx, [rbp+18h]; this
0x1800b2938  mov     r9d, eax; char *
0x1800b293b  mov     r8, r13; unsigned int
0x1800b293e  mov     edx, 221h; void *
0x1800b2943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2948  mov     edx, 3CEh; void *
0x1800b294d  mov     rcx, [rbp+18h]; this
0x1800b2951  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b2958  mov     r9d, edi; char *
0x1800b295b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2960  mov     eax, edi
0x1800b2962  jmp     loc_1800B2D0A
0x1800b2967  test    rbx, rbx
0x1800b296a  jz      short loc_1800B2971
0x1800b296c  test    bl, 2
0x1800b296f  jz      short loc_1800B29B1
0x1800b2971  mov     rcx, [r14]
0x1800b2974  lea     r8, [rsi+10h]
0x1800b2978  lea     rdx, aIndex; "Index"
0x1800b297f  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b2986  nop     dword ptr [rax+rax+00h]
0x1800b298b  mov     edi, eax
0x1800b298d  test    eax, eax
0x1800b298f  jns     short loc_1800B29AC
0x1800b2991  mov     rcx, [rbp+18h]; this
0x1800b2995  mov     r9d, eax; char *
0x1800b2998  mov     r8, r13; unsigned int
0x1800b299b  mov     edx, 221h; void *
0x1800b29a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b29a5  mov     edx, 3D2h
0x1800b29aa  jmp     short loc_1800B294D
0x1800b29ac  test    rbx, rbx
0x1800b29af  jz      short loc_1800B29B6
0x1800b29b1  test    bl, 4
0x1800b29b4  jz      short loc_1800B29F9
0x1800b29b6  mov     rcx, [r14]
0x1800b29b9  lea     r8, [rsi+14h]
0x1800b29bd  lea     rdx, aFlags; "Flags"
0x1800b29c4  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b29cb  nop     dword ptr [rax+rax+00h]
0x1800b29d0  mov     edi, eax
0x1800b29d2  test    eax, eax
0x1800b29d4  jns     short loc_1800B29F4
0x1800b29d6  mov     rcx, [rbp+18h]; this
0x1800b29da  mov     r9d, eax; char *
0x1800b29dd  mov     r8, r13; unsigned int
0x1800b29e0  mov     edx, 221h; void *
0x1800b29e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b29ea  mov     edx, 3D6h
0x1800b29ef  jmp     loc_1800B294D
0x1800b29f4  test    rbx, rbx
0x1800b29f7  jz      short loc_1800B2A02
0x1800b29f9  test    bl, 8
0x1800b29fc  jz      loc_1800B2A83
0x1800b2a02  mov     rcx, [r14]
0x1800b2a05  lea     rax, [rsi+18h]
0x1800b2a09  and     [rbp+var_18], 0
0x1800b2a0e  lea     r8, [rbp+var_18]
0x1800b2a12  lea     rdx, aCategory; "Category"
0x1800b2a19  mov     [rbp+var_20], rax
0x1800b2a1d  mov     [rbp+var_10], 1
0x1800b2a21  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2a28  nop     dword ptr [rax+rax+00h]
0x1800b2a2d  mov     edi, eax
0x1800b2a2f  test    eax, eax
0x1800b2a31  jns     short loc_1800B2A49
0x1800b2a33  mov     rcx, [rbp+18h]; this
0x1800b2a37  mov     r9d, eax; char *
0x1800b2a3a  mov     r8, r13; unsigned int
0x1800b2a3d  mov     edx, 246h; void *
0x1800b2a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2a47  jmp     short loc_1800B2A4B
0x1800b2a49  xor     edi, edi
0x1800b2a4b  cmp     [rbp+var_10], 0
0x1800b2a4f  jz      short loc_1800B2A70
0x1800b2a51  mov     rdx, [rbp+var_20]
0x1800b2a55  mov     rax, [rbp+var_18]
0x1800b2a59  mov     rcx, [rdx]
0x1800b2a5c  mov     [rdx], rax
0x1800b2a5f  test    rcx, rcx
0x1800b2a62  jz      short loc_1800B2A70
0x1800b2a64  call    cs:__imp_SRCache_Free
0x1800b2a6b  nop     dword ptr [rax+rax+00h]
0x1800b2a70  test    edi, edi
0x1800b2a72  jns     short loc_1800B2A7E
0x1800b2a74  mov     edx, 3DAh
0x1800b2a79  jmp     loc_1800B294D
0x1800b2a7e  test    rbx, rbx
0x1800b2a81  jz      short loc_1800B2A88
0x1800b2a83  test    bl, 10h
0x1800b2a86  jz      short loc_1800B2ACB
0x1800b2a88  mov     rcx, [r14]
0x1800b2a8b  lea     r8, [rsi+20h]
0x1800b2a8f  lea     rdx, aActivation; "Activation"
0x1800b2a96  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b2a9d  nop     dword ptr [rax+rax+00h]
0x1800b2aa2  mov     edi, eax
0x1800b2aa4  test    eax, eax
0x1800b2aa6  jns     short loc_1800B2AC6
0x1800b2aa8  mov     rcx, [rbp+18h]; this
0x1800b2aac  mov     r9d, eax; char *
0x1800b2aaf  mov     r8, r13; unsigned int
0x1800b2ab2  mov     edx, 221h; void *
0x1800b2ab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2abc  mov     edx, 3DEh
0x1800b2ac1  jmp     loc_1800B294D
0x1800b2ac6  test    rbx, rbx
0x1800b2ac9  jz      short loc_1800B2AD4
0x1800b2acb  test    bl, 20h
0x1800b2ace  jz      loc_1800B2B55
0x1800b2ad4  mov     rcx, [r14]
0x1800b2ad7  lea     rax, [rsi+28h]
0x1800b2adb  and     [rbp+var_18], 0
0x1800b2ae0  lea     r8, [rbp+var_18]
0x1800b2ae4  lea     rdx, aHostid; "HostId"
0x1800b2aeb  mov     [rbp+var_20], rax
0x1800b2aef  mov     [rbp+var_10], 1
0x1800b2af3  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2afa  nop     dword ptr [rax+rax+00h]
0x1800b2aff  mov     edi, eax
0x1800b2b01  test    eax, eax
0x1800b2b03  jns     short loc_1800B2B1B
0x1800b2b05  mov     rcx, [rbp+18h]; this
0x1800b2b09  mov     r9d, eax; char *
0x1800b2b0c  mov     r8, r13; unsigned int
0x1800b2b0f  mov     edx, 246h; void *
0x1800b2b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2b19  jmp     short loc_1800B2B1D
0x1800b2b1b  xor     edi, edi
0x1800b2b1d  cmp     [rbp+var_10], 0
0x1800b2b21  jz      short loc_1800B2B42
0x1800b2b23  mov     rdx, [rbp+var_20]
0x1800b2b27  mov     rax, [rbp+var_18]
0x1800b2b2b  mov     rcx, [rdx]
0x1800b2b2e  mov     [rdx], rax
0x1800b2b31  test    rcx, rcx
0x1800b2b34  jz      short loc_1800B2B42
0x1800b2b36  call    cs:__imp_SRCache_Free
0x1800b2b3d  nop     dword ptr [rax+rax+00h]
0x1800b2b42  test    edi, edi
0x1800b2b44  jns     short loc_1800B2B50
0x1800b2b46  mov     edx, 3E2h
0x1800b2b4b  jmp     loc_1800B294D
0x1800b2b50  test    rbx, rbx
0x1800b2b53  jz      short loc_1800B2B5E
0x1800b2b55  test    bl, 40h
0x1800b2b58  jz      loc_1800B2BDF
0x1800b2b5e  mov     rcx, [r14]
0x1800b2b61  lea     rax, [rsi+30h]
0x1800b2b65  and     [rbp+var_18], 0
0x1800b2b6a  lea     r8, [rbp+var_18]
0x1800b2b6e  lea     rdx, aParameters; "Parameters"
0x1800b2b75  mov     [rbp+var_20], rax
0x1800b2b79  mov     [rbp+var_10], 1
0x1800b2b7d  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2b84  nop     dword ptr [rax+rax+00h]
0x1800b2b89  mov     edi, eax
0x1800b2b8b  test    eax, eax
0x1800b2b8d  jns     short loc_1800B2BA5
0x1800b2b8f  mov     rcx, [rbp+18h]; this
0x1800b2b93  mov     r9d, eax; char *
0x1800b2b96  mov     r8, r13; unsigned int
0x1800b2b99  mov     edx, 246h; void *
0x1800b2b9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2ba3  jmp     short loc_1800B2BA7
0x1800b2ba5  xor     edi, edi
0x1800b2ba7  cmp     [rbp+var_10], 0
0x1800b2bab  jz      short loc_1800B2BCC
0x1800b2bad  mov     rdx, [rbp+var_20]
0x1800b2bb1  mov     rax, [rbp+var_18]
0x1800b2bb5  mov     rcx, [rdx]
0x1800b2bb8  mov     [rdx], rax
0x1800b2bbb  test    rcx, rcx
0x1800b2bbe  jz      short loc_1800B2BCC
0x1800b2bc0  call    cs:__imp_SRCache_Free
0x1800b2bc7  nop     dword ptr [rax+rax+00h]
0x1800b2bcc  test    edi, edi
0x1800b2bce  jns     short loc_1800B2BDA
0x1800b2bd0  mov     edx, 3E6h
0x1800b2bd5  jmp     loc_1800B294D
0x1800b2bda  test    rbx, rbx
0x1800b2bdd  jz      short loc_1800B2BE7
0x1800b2bdf  test    bl, bl
0x1800b2be1  jns     loc_1800B2C68
0x1800b2be7  mov     rcx, [r14]
0x1800b2bea  lea     rax, [rsi+38h]
0x1800b2bee  and     [rbp+var_18], 0
0x1800b2bf3  lea     r8, [rbp+var_18]
0x1800b2bf7  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x1800b2bfe  mov     [rbp+var_20], rax
0x1800b2c02  mov     [rbp+var_10], 1
0x1800b2c06  call    cs:__imp_SRCacheContext_GetField_String
0x1800b2c0d  nop     dword ptr [rax+rax+00h]
0x1800b2c12  mov     edi, eax
0x1800b2c14  test    eax, eax
0x1800b2c16  jns     short loc_1800B2C2E
0x1800b2c18  mov     rcx, [rbp+18h]; this
0x1800b2c1c  mov     r9d, eax; char *
0x1800b2c1f  mov     r8, r13; unsigned int
0x1800b2c22  mov     edx, 246h; void *
0x1800b2c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2c2c  jmp     short loc_1800B2C30
0x1800b2c2e  xor     edi, edi
0x1800b2c30  cmp     [rbp+var_10], 0
0x1800b2c34  jz      short loc_1800B2C55
0x1800b2c36  mov     rdx, [rbp+var_20]
0x1800b2c3a  mov     rax, [rbp+var_18]
0x1800b2c3e  mov     rcx, [rdx]
0x1800b2c41  mov     [rdx], rax
0x1800b2c44  test    rcx, rcx
0x1800b2c47  jz      short loc_1800B2C55
0x1800b2c49  call    cs:__imp_SRCache_Free
0x1800b2c50  nop     dword ptr [rax+rax+00h]
0x1800b2c55  test    edi, edi
0x1800b2c57  jns     short loc_1800B2C63
0x1800b2c59  mov     edx, 3EAh
0x1800b2c5e  jmp     loc_1800B294D
0x1800b2c63  test    rbx, rbx
0x1800b2c66  jz      short loc_1800B2C73
0x1800b2c68  bt      rbx, 8
0x1800b2c6d  jnb     loc_1800B2D05
0x1800b2c73  mov     rcx, [r14]
0x1800b2c76  lea     rax, [rsi+40h]
0x1800b2c7a  and     [rbp+var_18], 0
0x1800b2c7f  lea     r8, [rsi+48h]
0x1800b2c83  lea     r9, [rbp+var_18]
0x1800b2c87  mov     [rbp+var_20], rax
0x1800b2c8b  lea     rdx, aDictionary; "_Dictionary"
0x1800b2c92  mov     [rbp+var_10], 1
0x1800b2c96  call    cs:__imp_SRCacheContext_GetField_Binary
0x1800b2c9d  nop     dword ptr [rax+rax+00h]
0x1800b2ca2  mov     ebx, eax
0x1800b2ca4  test    eax, eax
0x1800b2ca6  jns     short loc_1800B2CBE
0x1800b2ca8  mov     rcx, [rbp+18h]; this
0x1800b2cac  mov     r9d, eax; char *
0x1800b2caf  mov     r8, r13; unsigned int
0x1800b2cb2  mov     edx, 24Fh; void *
0x1800b2cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2cbc  jmp     short loc_1800B2CC0
0x1800b2cbe  xor     ebx, ebx
0x1800b2cc0  cmp     [rbp+var_10], 0
0x1800b2cc4  jz      short loc_1800B2CE5
0x1800b2cc6  mov     rdx, [rbp+var_20]
0x1800b2cca  mov     rax, [rbp+var_18]
0x1800b2cce  mov     rcx, [rdx]
0x1800b2cd1  mov     [rdx], rax
0x1800b2cd4  test    rcx, rcx
0x1800b2cd7  jz      short loc_1800B2CE5
0x1800b2cd9  call    cs:__imp_SRCache_Free
0x1800b2ce0  nop     dword ptr [rax+rax+00h]
0x1800b2ce5  test    ebx, ebx
0x1800b2ce7  jns     short loc_1800B2D05
0x1800b2ce9  mov     rcx, [rbp+18h]; this
0x1800b2ced  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b2cf4  mov     r9d, ebx; char *
0x1800b2cf7  mov     edx, 3EEh; void *
0x1800b2cfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2d01  mov     eax, ebx
0x1800b2d03  jmp     short loc_1800B2D0A
0x1800b2d05  mov     [rsi], r15
0x1800b2d08  xor     eax, eax
0x1800b2d0a  mov     rbx, [rsp+40h+arg_0]
0x1800b2d0f  mov     rsi, [rsp+40h+arg_8]
0x1800b2d14  mov     rdi, [rsp+40h+arg_10]
0x1800b2d19  mov     r13, [rsp+40h+arg_18]
0x1800b2d1e  add     rsp, 40h
0x1800b2d22  pop     r15
0x1800b2d24  pop     r14
0x1800b2d26  pop     rbp
0x1800b2d27  retn
```
