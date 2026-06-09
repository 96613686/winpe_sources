# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)

- ea: `0x1800b3e08`
- end: `0x1800b4068`
- name: `?Get@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800b3d0c`

## callees

- `0x18000e234`
- `0x1800b3e08`
- `0x1800ba6c8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b3f2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b3fb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b3f2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b3fb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3e96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b403f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3e96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b403f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b3ece`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b3ece`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3f70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3ffc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3f70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3ffc`

## string_xrefs

- `0x1800b3ead`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b3ec7`: `Extension`
- `0x1800b3e35`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b3e79`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b4015`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

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
  __int64 *v20; // [rsp+20h] [rbp-30h]
  __int64 v21; // [rsp+28h] [rbp-28h] BYREF
  char v22; // [rsp+30h] [rbp-20h]
  __int64 *v23; // [rsp+38h] [rbp-18h]
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  char v25; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v27; // [rsp+78h] [rbp+28h] BYREF

  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)0x80070057LL,
      (int)v20);
    return (unsigned int)v8;
  }
  v10 = a5;
  v27 = 0;
  v8 = StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v27,
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
      Field_UInt32 = SRCacheContext_GetField_UInt32(v27, L"Extension", a4 + 1);
      v8 = Field_UInt32;
      if ( Field_UInt32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_UInt32,
          (int)v20);
        v14 = 842;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
          (const char *)(unsigned int)v8,
          (int)v20);
        v11 = 181;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
          (const char *)(unsigned int)v8,
          (int)v20);
        v12 = v27;
        v27 = 0;
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
      v21 = 0;
      v20 = a4 + 2;
      v22 = 1;
      Field_String = SRCacheContext_GetField_String(v27, L"FileType", &v21);
      v8 = Field_String;
      if ( Field_String >= 0 )
        v8 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_String,
          (int)v20);
      if ( v22 )
      {
        v16 = *v20;
        *v20 = v21;
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
      v24 = 0;
      v23 = a4 + 3;
      v25 = 1;
      v17 = SRCacheContext_GetField_String(v27, L"ProgID", &v24);
      v8 = v17;
      if ( v17 >= 0 )
        v8 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v17,
          (int)v20);
      if ( v25 )
      {
        v18 = *v23;
        *v23 = v24;
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
  v19 = v27;
  v27 = 0;
  if ( v19 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800b3e08  mov     [rsp-18h+arg_0], rbx
0x1800b3e0d  mov     [rsp-18h+arg_10], rsi
0x1800b3e12  mov     [rsp-18h+arg_18], rdi
0x1800b3e17  push    rbp
0x1800b3e18  push    r14
0x1800b3e1a  push    r15
0x1800b3e1c  mov     rbp, rsp
0x1800b3e1f  sub     rsp, 50h
0x1800b3e23  mov     r14, r9
0x1800b3e26  mov     rdi, r8
0x1800b3e29  mov     r15, rdx
0x1800b3e2c  test    rdx, rdx
0x1800b3e2f  jnz     short loc_1800B3E55
0x1800b3e31  mov     rcx, [rbp+18h]; this
0x1800b3e35  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b3e3c  mov     ebx, 80070057h
0x1800b3e41  mov     edx, 0ADh; void *
0x1800b3e46  mov     r9d, ebx; char *
0x1800b3e49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3e4e  mov     eax, ebx
0x1800b3e50  jmp     loc_1800B404D
0x1800b3e55  mov     rsi, [rbp+arg_20]
0x1800b3e59  lea     r8, [rbp+arg_8]; this
0x1800b3e5d  and     [rbp+arg_8], 0
0x1800b3e62  mov     r9, rsi; bool *
0x1800b3e65  call    ?Open@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800b3e6a  mov     ebx, eax
0x1800b3e6c  test    eax, eax
0x1800b3e6e  jns     short loc_1800B3EA4
0x1800b3e70  mov     edx, 0B0h; void *
0x1800b3e75  mov     rcx, [rbp+18h]; this
0x1800b3e79  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b3e80  mov     r9d, ebx; char *
0x1800b3e83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3e88  mov     rcx, [rbp+arg_8]
0x1800b3e8c  and     [rbp+arg_8], 0
0x1800b3e91  test    rcx, rcx
0x1800b3e94  jz      short loc_1800B3E4E
0x1800b3e96  call    cs:__imp_SRCacheContext_Close
0x1800b3e9d  nop     dword ptr [rax+rax+00h]
0x1800b3ea2  jmp     short loc_1800B3E4E
0x1800b3ea4  cmp     byte ptr [rsi], 0
0x1800b3ea7  jz      loc_1800B4031
0x1800b3ead  lea     rsi, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b3eb4  test    rdi, rdi
0x1800b3eb7  jz      short loc_1800B3EBF
0x1800b3eb9  test    dil, 1
0x1800b3ebd  jz      short loc_1800B3F03
0x1800b3ebf  mov     rcx, [rbp+arg_8]
0x1800b3ec3  lea     r8, [r14+8]
0x1800b3ec7  lea     rdx, aExtension; "Extension"
0x1800b3ece  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b3ed5  nop     dword ptr [rax+rax+00h]
0x1800b3eda  mov     ebx, eax
0x1800b3edc  test    eax, eax
0x1800b3ede  jns     short loc_1800B3EFE
0x1800b3ee0  mov     rcx, [rbp+18h]; this
0x1800b3ee4  mov     r9d, eax; char *
0x1800b3ee7  mov     r8, rsi; unsigned int
0x1800b3eea  mov     edx, 221h; void *
0x1800b3eef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3ef4  mov     edx, 34Ah
0x1800b3ef9  jmp     loc_1800B4011
0x1800b3efe  test    rdi, rdi
0x1800b3f01  jz      short loc_1800B3F0D
0x1800b3f03  test    dil, 2
0x1800b3f07  jz      loc_1800B3F8F
0x1800b3f0d  mov     rcx, [rbp+arg_8]
0x1800b3f11  lea     rax, [r14+10h]
0x1800b3f15  and     [rbp+var_28], 0
0x1800b3f1a  lea     r8, [rbp+var_28]
0x1800b3f1e  lea     rdx, aFiletype; "FileType"
0x1800b3f25  mov     [rbp+var_30], rax
0x1800b3f29  mov     [rbp+var_20], 1
0x1800b3f2d  call    cs:__imp_SRCacheContext_GetField_String
0x1800b3f34  nop     dword ptr [rax+rax+00h]
0x1800b3f39  mov     ebx, eax
0x1800b3f3b  test    eax, eax
0x1800b3f3d  jns     short loc_1800B3F55
0x1800b3f3f  mov     rcx, [rbp+18h]; this
0x1800b3f43  mov     r9d, eax; char *
0x1800b3f46  mov     r8, rsi; unsigned int
0x1800b3f49  mov     edx, 246h; void *
0x1800b3f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3f53  jmp     short loc_1800B3F57
0x1800b3f55  xor     ebx, ebx
0x1800b3f57  cmp     [rbp+var_20], 0
0x1800b3f5b  jz      short loc_1800B3F7C
0x1800b3f5d  mov     rdx, [rbp+var_30]
0x1800b3f61  mov     rax, [rbp+var_28]
0x1800b3f65  mov     rcx, [rdx]
0x1800b3f68  mov     [rdx], rax
0x1800b3f6b  test    rcx, rcx
0x1800b3f6e  jz      short loc_1800B3F7C
0x1800b3f70  call    cs:__imp_SRCache_Free
0x1800b3f77  nop     dword ptr [rax+rax+00h]
0x1800b3f7c  test    ebx, ebx
0x1800b3f7e  jns     short loc_1800B3F8A
0x1800b3f80  mov     edx, 34Eh
0x1800b3f85  jmp     loc_1800B4011
0x1800b3f8a  test    rdi, rdi
0x1800b3f8d  jz      short loc_1800B3F99
0x1800b3f8f  test    dil, 4
0x1800b3f93  jz      loc_1800B402E
0x1800b3f99  mov     rcx, [rbp+arg_8]
0x1800b3f9d  lea     rax, [r14+18h]
0x1800b3fa1  and     [rbp+var_10], 0
0x1800b3fa6  lea     r8, [rbp+var_10]
0x1800b3faa  lea     rdx, aProgid; "ProgID"
0x1800b3fb1  mov     [rbp+var_18], rax
0x1800b3fb5  mov     [rbp+var_8], 1
0x1800b3fb9  call    cs:__imp_SRCacheContext_GetField_String
0x1800b3fc0  nop     dword ptr [rax+rax+00h]
0x1800b3fc5  mov     ebx, eax
0x1800b3fc7  test    eax, eax
0x1800b3fc9  jns     short loc_1800B3FE1
0x1800b3fcb  mov     rcx, [rbp+18h]; this
0x1800b3fcf  mov     r9d, eax; char *
0x1800b3fd2  mov     r8, rsi; unsigned int
0x1800b3fd5  mov     edx, 246h; void *
0x1800b3fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3fdf  jmp     short loc_1800B3FE3
0x1800b3fe1  xor     ebx, ebx
0x1800b3fe3  cmp     [rbp+var_8], 0
0x1800b3fe7  jz      short loc_1800B4008
0x1800b3fe9  mov     rdx, [rbp+var_18]
0x1800b3fed  mov     rax, [rbp+var_10]
0x1800b3ff1  mov     rcx, [rdx]
0x1800b3ff4  mov     [rdx], rax
0x1800b3ff7  test    rcx, rcx
0x1800b3ffa  jz      short loc_1800B4008
0x1800b3ffc  call    cs:__imp_SRCache_Free
0x1800b4003  nop     dword ptr [rax+rax+00h]
0x1800b4008  test    ebx, ebx
0x1800b400a  jns     short loc_1800B402E
0x1800b400c  mov     edx, 352h; void *
0x1800b4011  mov     rcx, [rbp+18h]; this
0x1800b4015  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b401c  mov     r9d, ebx; char *
0x1800b401f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4024  mov     edx, 0B5h
0x1800b4029  jmp     loc_1800B3E75
0x1800b402e  mov     [r14], r15
0x1800b4031  mov     rcx, [rbp+arg_8]
0x1800b4035  and     [rbp+arg_8], 0
0x1800b403a  test    rcx, rcx
0x1800b403d  jz      short loc_1800B404B
0x1800b403f  call    cs:__imp_SRCacheContext_Close
0x1800b4046  nop     dword ptr [rax+rax+00h]
0x1800b404b  xor     eax, eax
0x1800b404d  lea     r11, [rsp+50h+var_s0]
0x1800b4052  mov     rbx, [r11+20h]
0x1800b4056  mov     rsi, [r11+30h]
0x1800b405a  mov     rdi, [r11+38h]
0x1800b405e  mov     rsp, r11
0x1800b4061  pop     r15
0x1800b4063  pop     r14
0x1800b4065  pop     rbp
0x1800b4066  retn
```
