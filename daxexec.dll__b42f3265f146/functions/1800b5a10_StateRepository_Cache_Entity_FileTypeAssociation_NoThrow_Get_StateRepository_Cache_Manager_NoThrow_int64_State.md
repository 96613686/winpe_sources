# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)

- ea: `0x1800b5a10`
- end: `0x1800b5c67`
- name: `?Get@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800b5928`

## callees

- `0x18000ff24`
- `0x1800b5a10`
- `0x1800bc4c4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5a99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5c4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5a99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5c4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5b33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5bc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5b33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5bc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5b76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5c05`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5b76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5c05`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b5ad1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b5ad1`

## string_xrefs

- `0x1800b5ab0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b5aca`: `Extension`
- `0x1800b5a32`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b5a79`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b5c1e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  int v8; // ebx
  bool *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  int Field_UInt32; // eax
  __int64 v14; // rdx
  int Field_String; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-28h]
  __int64 *v21; // [rsp+20h] [rbp-28h]
  __int64 v22; // [rsp+28h] [rbp-20h] BYREF
  char v23; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  __int64 v25; // [rsp+88h] [rbp+40h] BYREF

  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)v8;
  }
  v10 = a5;
  v25 = 0;
  v8 = StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v25,
         a5);
  if ( v8 < 0 )
  {
    v11 = 176;
    goto LABEL_6;
  }
  if ( *v10 )
  {
    if ( !a3 || (a3 & 1) != 0 )
    {
      Field_UInt32 = SRCacheContext_GetField_UInt32(v25, L"Extension", a4 + 1);
      v8 = Field_UInt32;
      if ( Field_UInt32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_UInt32,
          v20);
        v14 = 842;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
          (const char *)(unsigned int)v8,
          (int)v21);
        v11 = 181;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
          (const char *)(unsigned int)v8,
          v20);
        v12 = v25;
        v25 = 0;
        if ( v12 )
          SRCacheContext_Close();
        return (unsigned int)v8;
      }
      if ( !a3 )
        goto LABEL_23;
    }
    if ( (a3 & 2) != 0 )
    {
LABEL_23:
      v21 = a4 + 2;
      v22 = 0;
      v23 = 1;
      Field_String = SRCacheContext_GetField_String(v25, L"FileType", &v22);
      v8 = Field_String;
      if ( Field_String >= 0 )
        v8 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_String,
          (int)v21);
      if ( v23 )
      {
        v16 = *v21;
        *v21 = v22;
        if ( v16 )
          SRCache_Free();
      }
      if ( v8 < 0 )
      {
        v14 = 846;
        goto LABEL_33;
      }
      if ( !a3 )
        goto LABEL_25;
    }
    if ( (a3 & 4) != 0 )
    {
LABEL_25:
      v21 = a4 + 3;
      v22 = 0;
      v23 = 1;
      v17 = SRCacheContext_GetField_String(v25, L"ProgID", &v22);
      v8 = v17;
      if ( v17 >= 0 )
        v8 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v17,
          (int)v21);
      if ( v23 )
      {
        v18 = *v21;
        *v21 = v22;
        if ( v18 )
          SRCache_Free();
      }
      if ( v8 < 0 )
      {
        v14 = 850;
        goto LABEL_33;
      }
    }
    *a4 = a2;
  }
  v19 = v25;
  v25 = 0;
  if ( v19 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800b5a10  push    rbp
0x1800b5a12  push    rbx
0x1800b5a13  push    rsi
0x1800b5a14  push    rdi
0x1800b5a15  push    r14
0x1800b5a17  push    r15
0x1800b5a19  mov     rbp, rsp
0x1800b5a1c  sub     rsp, 48h
0x1800b5a20  mov     r14, r9
0x1800b5a23  mov     rdi, r8
0x1800b5a26  mov     r15, rdx
0x1800b5a29  test    rdx, rdx
0x1800b5a2c  jnz     short loc_1800B5A52
0x1800b5a2e  mov     rcx, [rbp+30h]; this
0x1800b5a32  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5a39  mov     ebx, 80070057h
0x1800b5a3e  mov     edx, 0ADh; void *
0x1800b5a43  mov     r9d, ebx; char *
0x1800b5a46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5a4b  mov     eax, ebx
0x1800b5a4d  jmp     loc_1800B5C59
0x1800b5a52  mov     rsi, [rbp+arg_20]
0x1800b5a56  lea     r8, [rbp+arg_8]; this
0x1800b5a5a  mov     r9, rsi; bool *
0x1800b5a5d  mov     [rbp+arg_8], 0
0x1800b5a65  call    ?Open@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800b5a6a  mov     ebx, eax
0x1800b5a6c  test    eax, eax
0x1800b5a6e  jns     short loc_1800B5AA7
0x1800b5a70  mov     edx, 0B0h; void *
0x1800b5a75  mov     rcx, [rbp+30h]; this
0x1800b5a79  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5a80  mov     r9d, ebx; char *
0x1800b5a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5a88  mov     rcx, [rbp+arg_8]
0x1800b5a8c  mov     [rbp+arg_8], 0
0x1800b5a94  test    rcx, rcx
0x1800b5a97  jz      short loc_1800B5A4B
0x1800b5a99  call    cs:__imp_SRCacheContext_Close
0x1800b5aa0  nop     dword ptr [rax+rax+00h]
0x1800b5aa5  jmp     short loc_1800B5A4B
0x1800b5aa7  cmp     byte ptr [rsi], 0
0x1800b5aaa  jz      loc_1800B5C3A
0x1800b5ab0  lea     rsi, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5ab7  test    rdi, rdi
0x1800b5aba  jz      short loc_1800B5AC2
0x1800b5abc  test    dil, 1
0x1800b5ac0  jz      short loc_1800B5B06
0x1800b5ac2  mov     rcx, [rbp+arg_8]
0x1800b5ac6  lea     r8, [r14+8]
0x1800b5aca  lea     rdx, aExtension; "Extension"
0x1800b5ad1  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b5ad8  nop     dword ptr [rax+rax+00h]
0x1800b5add  mov     ebx, eax
0x1800b5adf  test    eax, eax
0x1800b5ae1  jns     short loc_1800B5B01
0x1800b5ae3  mov     rcx, [rbp+30h]; this
0x1800b5ae7  mov     r9d, eax; char *
0x1800b5aea  mov     r8, rsi; unsigned int
0x1800b5aed  mov     edx, 221h; void *
0x1800b5af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5af7  mov     edx, 34Ah
0x1800b5afc  jmp     loc_1800B5C1A
0x1800b5b01  test    rdi, rdi
0x1800b5b04  jz      short loc_1800B5B10
0x1800b5b06  test    dil, 2
0x1800b5b0a  jz      loc_1800B5B95
0x1800b5b10  mov     rcx, [rbp+arg_8]
0x1800b5b14  lea     rax, [r14+10h]
0x1800b5b18  lea     r8, [rbp+var_20]
0x1800b5b1c  mov     [rbp+var_28], rax
0x1800b5b20  lea     rdx, aFiletype; "FileType"
0x1800b5b27  mov     [rbp+var_20], 0
0x1800b5b2f  mov     [rbp+var_18], 1
0x1800b5b33  call    cs:__imp_SRCacheContext_GetField_String
0x1800b5b3a  nop     dword ptr [rax+rax+00h]
0x1800b5b3f  mov     ebx, eax
0x1800b5b41  test    eax, eax
0x1800b5b43  jns     short loc_1800B5B5B
0x1800b5b45  mov     rcx, [rbp+30h]; this
0x1800b5b49  mov     r9d, eax; char *
0x1800b5b4c  mov     r8, rsi; unsigned int
0x1800b5b4f  mov     edx, 246h; void *
0x1800b5b54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5b59  jmp     short loc_1800B5B5D
0x1800b5b5b  xor     ebx, ebx
0x1800b5b5d  cmp     [rbp+var_18], 0
0x1800b5b61  jz      short loc_1800B5B82
0x1800b5b63  mov     rdx, [rbp+var_28]
0x1800b5b67  mov     rax, [rbp+var_20]
0x1800b5b6b  mov     rcx, [rdx]
0x1800b5b6e  mov     [rdx], rax
0x1800b5b71  test    rcx, rcx
0x1800b5b74  jz      short loc_1800B5B82
0x1800b5b76  call    cs:__imp_SRCache_Free
0x1800b5b7d  nop     dword ptr [rax+rax+00h]
0x1800b5b82  test    ebx, ebx
0x1800b5b84  jns     short loc_1800B5B90
0x1800b5b86  mov     edx, 34Eh
0x1800b5b8b  jmp     loc_1800B5C1A
0x1800b5b90  test    rdi, rdi
0x1800b5b93  jz      short loc_1800B5B9F
0x1800b5b95  test    dil, 4
0x1800b5b99  jz      loc_1800B5C37
0x1800b5b9f  mov     rcx, [rbp+arg_8]
0x1800b5ba3  lea     rax, [r14+18h]
0x1800b5ba7  lea     r8, [rbp+var_20]
0x1800b5bab  mov     [rbp+var_28], rax
0x1800b5baf  lea     rdx, aProgid; "ProgID"
0x1800b5bb6  mov     [rbp+var_20], 0
0x1800b5bbe  mov     [rbp+var_18], 1
0x1800b5bc2  call    cs:__imp_SRCacheContext_GetField_String
0x1800b5bc9  nop     dword ptr [rax+rax+00h]
0x1800b5bce  mov     ebx, eax
0x1800b5bd0  test    eax, eax
0x1800b5bd2  jns     short loc_1800B5BEA
0x1800b5bd4  mov     rcx, [rbp+30h]; this
0x1800b5bd8  mov     r9d, eax; char *
0x1800b5bdb  mov     r8, rsi; unsigned int
0x1800b5bde  mov     edx, 246h; void *
0x1800b5be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5be8  jmp     short loc_1800B5BEC
0x1800b5bea  xor     ebx, ebx
0x1800b5bec  cmp     [rbp+var_18], 0
0x1800b5bf0  jz      short loc_1800B5C11
0x1800b5bf2  mov     rdx, [rbp+var_28]
0x1800b5bf6  mov     rax, [rbp+var_20]
0x1800b5bfa  mov     rcx, [rdx]
0x1800b5bfd  mov     [rdx], rax
0x1800b5c00  test    rcx, rcx
0x1800b5c03  jz      short loc_1800B5C11
0x1800b5c05  call    cs:__imp_SRCache_Free
0x1800b5c0c  nop     dword ptr [rax+rax+00h]
0x1800b5c11  test    ebx, ebx
0x1800b5c13  jns     short loc_1800B5C37
0x1800b5c15  mov     edx, 352h; void *
0x1800b5c1a  mov     rcx, [rbp+30h]; this
0x1800b5c1e  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5c25  mov     r9d, ebx; char *
0x1800b5c28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5c2d  mov     edx, 0B5h
0x1800b5c32  jmp     loc_1800B5A75
0x1800b5c37  mov     [r14], r15
0x1800b5c3a  mov     rcx, [rbp+arg_8]
0x1800b5c3e  mov     [rbp+arg_8], 0
0x1800b5c46  test    rcx, rcx
0x1800b5c49  jz      short loc_1800B5C57
0x1800b5c4b  call    cs:__imp_SRCacheContext_Close
0x1800b5c52  nop     dword ptr [rax+rax+00h]
0x1800b5c57  xor     eax, eax
0x1800b5c59  add     rsp, 48h
0x1800b5c5d  pop     r15
0x1800b5c5f  pop     r14
0x1800b5c61  pop     rdi
0x1800b5c62  pop     rsi
0x1800b5c63  pop     rbx
0x1800b5c64  pop     rbp
0x1800b5c65  retn
```
