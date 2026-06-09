# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)

- ea: `0x1800b49f8`
- end: `0x1800b4e3c`
- name: `?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b5828`

## callees

- `0x18000ff24`
- `0x1800b49f8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4b37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4c0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4c99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4d25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4b37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4c0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4c99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4d25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4b7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4c4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4cdc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4d68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4dfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4b7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4c4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4cdc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4d68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4dfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4a35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4a92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4ad7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4bac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4a35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4a92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4ad7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4bac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b4db8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x1800b4db8`

## string_xrefs

- `0x1800b4a0a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b4d12`: `CurrentDirectoryPath`
- `0x1800b4a64`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800b4e0f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

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
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

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
  v31 = a2 + 3;
  v33 = 0;
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
  v31 = a2 + 5;
  v33 = 0;
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
  v31 = a2 + 6;
  v33 = 0;
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
  v31 = a2 + 7;
  v33 = 0;
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
  v32 = a2 + 8;
  v33 = 0;
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
0x1800b49f8  push    rbp
0x1800b49fa  push    rbx
0x1800b49fb  push    rsi
0x1800b49fc  push    rdi
0x1800b49fd  push    r13
0x1800b49ff  push    r14
0x1800b4a01  push    r15
0x1800b4a03  mov     rbp, rsp
0x1800b4a06  sub     rsp, 40h
0x1800b4a0a  lea     r13, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b4a11  mov     r15, r9
0x1800b4a14  mov     rbx, r8
0x1800b4a17  mov     rsi, rdx
0x1800b4a1a  mov     r14, rcx
0x1800b4a1d  test    r8, r8
0x1800b4a20  jz      short loc_1800B4A27
0x1800b4a22  test    bl, 1
0x1800b4a25  jz      short loc_1800B4A7F
0x1800b4a27  mov     rcx, [rcx]
0x1800b4a2a  lea     r8, [rdx+8]
0x1800b4a2e  lea     rdx, aApplication; "Application"
0x1800b4a35  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b4a3c  nop     dword ptr [rax+rax+00h]
0x1800b4a41  mov     edi, eax
0x1800b4a43  test    eax, eax
0x1800b4a45  jns     short loc_1800B4A7A
0x1800b4a47  mov     rcx, [rbp+38h]; this
0x1800b4a4b  mov     r9d, eax; char *
0x1800b4a4e  mov     r8, r13; unsigned int
0x1800b4a51  mov     edx, 221h; void *
0x1800b4a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4a5b  mov     edx, 3CEh; void *
0x1800b4a60  mov     rcx, [rbp+38h]; this
0x1800b4a64  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b4a6b  mov     r9d, edi; char *
0x1800b4a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4a73  mov     eax, edi
0x1800b4a75  jmp     loc_1800B4E2C
0x1800b4a7a  test    rbx, rbx
0x1800b4a7d  jz      short loc_1800B4A84
0x1800b4a7f  test    bl, 2
0x1800b4a82  jz      short loc_1800B4AC4
0x1800b4a84  mov     rcx, [r14]
0x1800b4a87  lea     r8, [rsi+10h]
0x1800b4a8b  lea     rdx, aIndex; "Index"
0x1800b4a92  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b4a99  nop     dword ptr [rax+rax+00h]
0x1800b4a9e  mov     edi, eax
0x1800b4aa0  test    eax, eax
0x1800b4aa2  jns     short loc_1800B4ABF
0x1800b4aa4  mov     rcx, [rbp+38h]; this
0x1800b4aa8  mov     r9d, eax; char *
0x1800b4aab  mov     r8, r13; unsigned int
0x1800b4aae  mov     edx, 221h; void *
0x1800b4ab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4ab8  mov     edx, 3D2h
0x1800b4abd  jmp     short loc_1800B4A60
0x1800b4abf  test    rbx, rbx
0x1800b4ac2  jz      short loc_1800B4AC9
0x1800b4ac4  test    bl, 4
0x1800b4ac7  jz      short loc_1800B4B0C
0x1800b4ac9  mov     rcx, [r14]
0x1800b4acc  lea     r8, [rsi+14h]
0x1800b4ad0  lea     rdx, aFlags; "Flags"
0x1800b4ad7  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b4ade  nop     dword ptr [rax+rax+00h]
0x1800b4ae3  mov     edi, eax
0x1800b4ae5  test    eax, eax
0x1800b4ae7  jns     short loc_1800B4B07
0x1800b4ae9  mov     rcx, [rbp+38h]; this
0x1800b4aed  mov     r9d, eax; char *
0x1800b4af0  mov     r8, r13; unsigned int
0x1800b4af3  mov     edx, 221h; void *
0x1800b4af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4afd  mov     edx, 3D6h
0x1800b4b02  jmp     loc_1800B4A60
0x1800b4b07  test    rbx, rbx
0x1800b4b0a  jz      short loc_1800B4B15
0x1800b4b0c  test    bl, 8
0x1800b4b0f  jz      loc_1800B4B99
0x1800b4b15  mov     rcx, [r14]
0x1800b4b18  lea     rax, [rsi+18h]
0x1800b4b1c  lea     r8, [rbp+var_18]
0x1800b4b20  mov     [rbp+var_20], rax
0x1800b4b24  lea     rdx, aCategory; "Category"
0x1800b4b2b  mov     [rbp+var_18], 0
0x1800b4b33  mov     [rbp+var_10], 1
0x1800b4b37  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4b3e  nop     dword ptr [rax+rax+00h]
0x1800b4b43  mov     edi, eax
0x1800b4b45  test    eax, eax
0x1800b4b47  jns     short loc_1800B4B5F
0x1800b4b49  mov     rcx, [rbp+38h]; this
0x1800b4b4d  mov     r9d, eax; char *
0x1800b4b50  mov     r8, r13; unsigned int
0x1800b4b53  mov     edx, 246h; void *
0x1800b4b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4b5d  jmp     short loc_1800B4B61
0x1800b4b5f  xor     edi, edi
0x1800b4b61  cmp     [rbp+var_10], 0
0x1800b4b65  jz      short loc_1800B4B86
0x1800b4b67  mov     rdx, [rbp+var_20]
0x1800b4b6b  mov     rax, [rbp+var_18]
0x1800b4b6f  mov     rcx, [rdx]
0x1800b4b72  mov     [rdx], rax
0x1800b4b75  test    rcx, rcx
0x1800b4b78  jz      short loc_1800B4B86
0x1800b4b7a  call    cs:__imp_SRCache_Free
0x1800b4b81  nop     dword ptr [rax+rax+00h]
0x1800b4b86  test    edi, edi
0x1800b4b88  jns     short loc_1800B4B94
0x1800b4b8a  mov     edx, 3DAh
0x1800b4b8f  jmp     loc_1800B4A60
0x1800b4b94  test    rbx, rbx
0x1800b4b97  jz      short loc_1800B4B9E
0x1800b4b99  test    bl, 10h
0x1800b4b9c  jz      short loc_1800B4BE1
0x1800b4b9e  mov     rcx, [r14]
0x1800b4ba1  lea     r8, [rsi+20h]
0x1800b4ba5  lea     rdx, aActivation; "Activation"
0x1800b4bac  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b4bb3  nop     dword ptr [rax+rax+00h]
0x1800b4bb8  mov     edi, eax
0x1800b4bba  test    eax, eax
0x1800b4bbc  jns     short loc_1800B4BDC
0x1800b4bbe  mov     rcx, [rbp+38h]; this
0x1800b4bc2  mov     r9d, eax; char *
0x1800b4bc5  mov     r8, r13; unsigned int
0x1800b4bc8  mov     edx, 221h; void *
0x1800b4bcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4bd2  mov     edx, 3DEh
0x1800b4bd7  jmp     loc_1800B4A60
0x1800b4bdc  test    rbx, rbx
0x1800b4bdf  jz      short loc_1800B4BEA
0x1800b4be1  test    bl, 20h
0x1800b4be4  jz      loc_1800B4C6E
0x1800b4bea  mov     rcx, [r14]
0x1800b4bed  lea     rax, [rsi+28h]
0x1800b4bf1  lea     r8, [rbp+var_18]
0x1800b4bf5  mov     [rbp+var_20], rax
0x1800b4bf9  lea     rdx, aHostid; "HostId"
0x1800b4c00  mov     [rbp+var_18], 0
0x1800b4c08  mov     [rbp+var_10], 1
0x1800b4c0c  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4c13  nop     dword ptr [rax+rax+00h]
0x1800b4c18  mov     edi, eax
0x1800b4c1a  test    eax, eax
0x1800b4c1c  jns     short loc_1800B4C34
0x1800b4c1e  mov     rcx, [rbp+38h]; this
0x1800b4c22  mov     r9d, eax; char *
0x1800b4c25  mov     r8, r13; unsigned int
0x1800b4c28  mov     edx, 246h; void *
0x1800b4c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4c32  jmp     short loc_1800B4C36
0x1800b4c34  xor     edi, edi
0x1800b4c36  cmp     [rbp+var_10], 0
0x1800b4c3a  jz      short loc_1800B4C5B
0x1800b4c3c  mov     rdx, [rbp+var_20]
0x1800b4c40  mov     rax, [rbp+var_18]
0x1800b4c44  mov     rcx, [rdx]
0x1800b4c47  mov     [rdx], rax
0x1800b4c4a  test    rcx, rcx
0x1800b4c4d  jz      short loc_1800B4C5B
0x1800b4c4f  call    cs:__imp_SRCache_Free
0x1800b4c56  nop     dword ptr [rax+rax+00h]
0x1800b4c5b  test    edi, edi
0x1800b4c5d  jns     short loc_1800B4C69
0x1800b4c5f  mov     edx, 3E2h
0x1800b4c64  jmp     loc_1800B4A60
0x1800b4c69  test    rbx, rbx
0x1800b4c6c  jz      short loc_1800B4C77
0x1800b4c6e  test    bl, 40h
0x1800b4c71  jz      loc_1800B4CFB
0x1800b4c77  mov     rcx, [r14]
0x1800b4c7a  lea     rax, [rsi+30h]
0x1800b4c7e  lea     r8, [rbp+var_18]
0x1800b4c82  mov     [rbp+var_20], rax
0x1800b4c86  lea     rdx, aParameters; "Parameters"
0x1800b4c8d  mov     [rbp+var_18], 0
0x1800b4c95  mov     [rbp+var_10], 1
0x1800b4c99  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4ca0  nop     dword ptr [rax+rax+00h]
0x1800b4ca5  mov     edi, eax
0x1800b4ca7  test    eax, eax
0x1800b4ca9  jns     short loc_1800B4CC1
0x1800b4cab  mov     rcx, [rbp+38h]; this
0x1800b4caf  mov     r9d, eax; char *
0x1800b4cb2  mov     r8, r13; unsigned int
0x1800b4cb5  mov     edx, 246h; void *
0x1800b4cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4cbf  jmp     short loc_1800B4CC3
0x1800b4cc1  xor     edi, edi
0x1800b4cc3  cmp     [rbp+var_10], 0
0x1800b4cc7  jz      short loc_1800B4CE8
0x1800b4cc9  mov     rdx, [rbp+var_20]
0x1800b4ccd  mov     rax, [rbp+var_18]
0x1800b4cd1  mov     rcx, [rdx]
0x1800b4cd4  mov     [rdx], rax
0x1800b4cd7  test    rcx, rcx
0x1800b4cda  jz      short loc_1800B4CE8
0x1800b4cdc  call    cs:__imp_SRCache_Free
0x1800b4ce3  nop     dword ptr [rax+rax+00h]
0x1800b4ce8  test    edi, edi
0x1800b4cea  jns     short loc_1800B4CF6
0x1800b4cec  mov     edx, 3E6h
0x1800b4cf1  jmp     loc_1800B4A60
0x1800b4cf6  test    rbx, rbx
0x1800b4cf9  jz      short loc_1800B4D03
0x1800b4cfb  test    bl, bl
0x1800b4cfd  jns     loc_1800B4D87
0x1800b4d03  mov     rcx, [r14]
0x1800b4d06  lea     rax, [rsi+38h]
0x1800b4d0a  lea     r8, [rbp+var_18]
0x1800b4d0e  mov     [rbp+var_20], rax
0x1800b4d12  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x1800b4d19  mov     [rbp+var_18], 0
0x1800b4d21  mov     [rbp+var_10], 1
0x1800b4d25  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4d2c  nop     dword ptr [rax+rax+00h]
0x1800b4d31  mov     edi, eax
0x1800b4d33  test    eax, eax
0x1800b4d35  jns     short loc_1800B4D4D
0x1800b4d37  mov     rcx, [rbp+38h]; this
0x1800b4d3b  mov     r9d, eax; char *
0x1800b4d3e  mov     r8, r13; unsigned int
0x1800b4d41  mov     edx, 246h; void *
0x1800b4d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4d4b  jmp     short loc_1800B4D4F
0x1800b4d4d  xor     edi, edi
0x1800b4d4f  cmp     [rbp+var_10], 0
0x1800b4d53  jz      short loc_1800B4D74
0x1800b4d55  mov     rdx, [rbp+var_20]
0x1800b4d59  mov     rax, [rbp+var_18]
0x1800b4d5d  mov     rcx, [rdx]
0x1800b4d60  mov     [rdx], rax
0x1800b4d63  test    rcx, rcx
0x1800b4d66  jz      short loc_1800B4D74
0x1800b4d68  call    cs:__imp_SRCache_Free
0x1800b4d6f  nop     dword ptr [rax+rax+00h]
0x1800b4d74  test    edi, edi
0x1800b4d76  jns     short loc_1800B4D82
0x1800b4d78  mov     edx, 3EAh
0x1800b4d7d  jmp     loc_1800B4A60
0x1800b4d82  test    rbx, rbx
0x1800b4d85  jz      short loc_1800B4D92
0x1800b4d87  bt      rbx, 8
0x1800b4d8c  jnb     loc_1800B4E27
0x1800b4d92  mov     rcx, [r14]
0x1800b4d95  lea     rax, [rsi+40h]
0x1800b4d99  lea     r8, [rsi+48h]
0x1800b4d9d  mov     [rbp+var_20], rax
0x1800b4da1  lea     r9, [rbp+var_18]
0x1800b4da5  mov     [rbp+var_18], 0
0x1800b4dad  lea     rdx, aDictionary; "_Dictionary"
0x1800b4db4  mov     [rbp+var_10], 1
0x1800b4db8  call    cs:__imp_SRCacheContext_GetField_Binary
0x1800b4dbf  nop     dword ptr [rax+rax+00h]
0x1800b4dc4  mov     ebx, eax
0x1800b4dc6  test    eax, eax
0x1800b4dc8  jns     short loc_1800B4DE0
0x1800b4dca  mov     rcx, [rbp+38h]; this
0x1800b4dce  mov     r9d, eax; char *
0x1800b4dd1  mov     r8, r13; unsigned int
0x1800b4dd4  mov     edx, 24Fh; void *
0x1800b4dd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4dde  jmp     short loc_1800B4DE2
0x1800b4de0  xor     ebx, ebx
0x1800b4de2  cmp     [rbp+var_10], 0
0x1800b4de6  jz      short loc_1800B4E07
0x1800b4de8  mov     rdx, [rbp+var_20]
0x1800b4dec  mov     rax, [rbp+var_18]
0x1800b4df0  mov     rcx, [rdx]
0x1800b4df3  mov     [rdx], rax
0x1800b4df6  test    rcx, rcx
0x1800b4df9  jz      short loc_1800B4E07
0x1800b4dfb  call    cs:__imp_SRCache_Free
0x1800b4e02  nop     dword ptr [rax+rax+00h]
0x1800b4e07  test    ebx, ebx
0x1800b4e09  jns     short loc_1800B4E27
0x1800b4e0b  mov     rcx, [rbp+38h]; this
0x1800b4e0f  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b4e16  mov     r9d, ebx; char *
0x1800b4e19  mov     edx, 3EEh; void *
0x1800b4e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4e23  mov     eax, ebx
0x1800b4e25  jmp     short loc_1800B4E2C
0x1800b4e27  mov     [rsi], r15
0x1800b4e2a  xor     eax, eax
0x1800b4e2c  add     rsp, 40h
0x1800b4e30  pop     r15
0x1800b4e32  pop     r14
0x1800b4e34  pop     r13
0x1800b4e36  pop     rdi
0x1800b4e37  pop     rsi
0x1800b4e38  pop     rbx
0x1800b4e39  pop     rbp
0x1800b4e3a  retn
```
