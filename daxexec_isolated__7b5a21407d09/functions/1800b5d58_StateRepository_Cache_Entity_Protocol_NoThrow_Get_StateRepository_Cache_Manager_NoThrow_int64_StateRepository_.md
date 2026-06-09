# StateRepository::Cache::Entity::Protocol_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)

- ea: `0x1800b5d58`
- end: `0x1800b5faf`
- name: `?Get@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b5c70`

## callees

- `0x18000ff24`
- `0x1800b5d58`
- `0x1800bc6c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5de1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5f93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5de1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5f93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5e7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5f0a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5e7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b5f0a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5ebe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5f4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5ebe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5f4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b5e19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b5e19`

## string_xrefs

- `0x1800b5df8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b5e12`: `Extension`
- `0x1800b5d7a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b5dc1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b5f66`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::Get(
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)v8;
  }
  v10 = a5;
  v25 = 0;
  v8 = StateRepository::Cache::Entity::Protocol_NoThrow::Open(
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
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
          (const char *)(unsigned int)v8,
          (int)v21);
        v11 = 181;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
      Field_String = SRCacheContext_GetField_String(v25, L"Name", &v22);
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
0x1800b5d58  push    rbp
0x1800b5d5a  push    rbx
0x1800b5d5b  push    rsi
0x1800b5d5c  push    rdi
0x1800b5d5d  push    r14
0x1800b5d5f  push    r15
0x1800b5d61  mov     rbp, rsp
0x1800b5d64  sub     rsp, 48h
0x1800b5d68  mov     r14, r9
0x1800b5d6b  mov     rdi, r8
0x1800b5d6e  mov     r15, rdx
0x1800b5d71  test    rdx, rdx
0x1800b5d74  jnz     short loc_1800B5D9A
0x1800b5d76  mov     rcx, [rbp+30h]; this
0x1800b5d7a  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5d81  mov     ebx, 80070057h
0x1800b5d86  mov     edx, 0ADh; void *
0x1800b5d8b  mov     r9d, ebx; char *
0x1800b5d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5d93  mov     eax, ebx
0x1800b5d95  jmp     loc_1800B5FA1
0x1800b5d9a  mov     rsi, [rbp+arg_20]
0x1800b5d9e  lea     r8, [rbp+arg_8]; this
0x1800b5da2  mov     r9, rsi; bool *
0x1800b5da5  mov     [rbp+arg_8], 0
0x1800b5dad  call    ?Open@Protocol_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Protocol_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800b5db2  mov     ebx, eax
0x1800b5db4  test    eax, eax
0x1800b5db6  jns     short loc_1800B5DEF
0x1800b5db8  mov     edx, 0B0h; void *
0x1800b5dbd  mov     rcx, [rbp+30h]; this
0x1800b5dc1  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5dc8  mov     r9d, ebx; char *
0x1800b5dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5dd0  mov     rcx, [rbp+arg_8]
0x1800b5dd4  mov     [rbp+arg_8], 0
0x1800b5ddc  test    rcx, rcx
0x1800b5ddf  jz      short loc_1800B5D93
0x1800b5de1  call    cs:__imp_SRCacheContext_Close
0x1800b5de8  nop     dword ptr [rax+rax+00h]
0x1800b5ded  jmp     short loc_1800B5D93
0x1800b5def  cmp     byte ptr [rsi], 0
0x1800b5df2  jz      loc_1800B5F82
0x1800b5df8  lea     rsi, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5dff  test    rdi, rdi
0x1800b5e02  jz      short loc_1800B5E0A
0x1800b5e04  test    dil, 1
0x1800b5e08  jz      short loc_1800B5E4E
0x1800b5e0a  mov     rcx, [rbp+arg_8]
0x1800b5e0e  lea     r8, [r14+8]
0x1800b5e12  lea     rdx, aExtension; "Extension"
0x1800b5e19  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b5e20  nop     dword ptr [rax+rax+00h]
0x1800b5e25  mov     ebx, eax
0x1800b5e27  test    eax, eax
0x1800b5e29  jns     short loc_1800B5E49
0x1800b5e2b  mov     rcx, [rbp+30h]; this
0x1800b5e2f  mov     r9d, eax; char *
0x1800b5e32  mov     r8, rsi; unsigned int
0x1800b5e35  mov     edx, 221h; void *
0x1800b5e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5e3f  mov     edx, 34Ah
0x1800b5e44  jmp     loc_1800B5F62
0x1800b5e49  test    rdi, rdi
0x1800b5e4c  jz      short loc_1800B5E58
0x1800b5e4e  test    dil, 2
0x1800b5e52  jz      loc_1800B5EDD
0x1800b5e58  mov     rcx, [rbp+arg_8]
0x1800b5e5c  lea     rax, [r14+10h]
0x1800b5e60  lea     r8, [rbp+var_20]
0x1800b5e64  mov     [rbp+var_28], rax
0x1800b5e68  lea     rdx, aName; "Name"
0x1800b5e6f  mov     [rbp+var_20], 0
0x1800b5e77  mov     [rbp+var_18], 1
0x1800b5e7b  call    cs:__imp_SRCacheContext_GetField_String
0x1800b5e82  nop     dword ptr [rax+rax+00h]
0x1800b5e87  mov     ebx, eax
0x1800b5e89  test    eax, eax
0x1800b5e8b  jns     short loc_1800B5EA3
0x1800b5e8d  mov     rcx, [rbp+30h]; this
0x1800b5e91  mov     r9d, eax; char *
0x1800b5e94  mov     r8, rsi; unsigned int
0x1800b5e97  mov     edx, 246h; void *
0x1800b5e9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5ea1  jmp     short loc_1800B5EA5
0x1800b5ea3  xor     ebx, ebx
0x1800b5ea5  cmp     [rbp+var_18], 0
0x1800b5ea9  jz      short loc_1800B5ECA
0x1800b5eab  mov     rdx, [rbp+var_28]
0x1800b5eaf  mov     rax, [rbp+var_20]
0x1800b5eb3  mov     rcx, [rdx]
0x1800b5eb6  mov     [rdx], rax
0x1800b5eb9  test    rcx, rcx
0x1800b5ebc  jz      short loc_1800B5ECA
0x1800b5ebe  call    cs:__imp_SRCache_Free
0x1800b5ec5  nop     dword ptr [rax+rax+00h]
0x1800b5eca  test    ebx, ebx
0x1800b5ecc  jns     short loc_1800B5ED8
0x1800b5ece  mov     edx, 34Eh
0x1800b5ed3  jmp     loc_1800B5F62
0x1800b5ed8  test    rdi, rdi
0x1800b5edb  jz      short loc_1800B5EE7
0x1800b5edd  test    dil, 4
0x1800b5ee1  jz      loc_1800B5F7F
0x1800b5ee7  mov     rcx, [rbp+arg_8]
0x1800b5eeb  lea     rax, [r14+18h]
0x1800b5eef  lea     r8, [rbp+var_20]
0x1800b5ef3  mov     [rbp+var_28], rax
0x1800b5ef7  lea     rdx, aProgid; "ProgID"
0x1800b5efe  mov     [rbp+var_20], 0
0x1800b5f06  mov     [rbp+var_18], 1
0x1800b5f0a  call    cs:__imp_SRCacheContext_GetField_String
0x1800b5f11  nop     dword ptr [rax+rax+00h]
0x1800b5f16  mov     ebx, eax
0x1800b5f18  test    eax, eax
0x1800b5f1a  jns     short loc_1800B5F32
0x1800b5f1c  mov     rcx, [rbp+30h]; this
0x1800b5f20  mov     r9d, eax; char *
0x1800b5f23  mov     r8, rsi; unsigned int
0x1800b5f26  mov     edx, 246h; void *
0x1800b5f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5f30  jmp     short loc_1800B5F34
0x1800b5f32  xor     ebx, ebx
0x1800b5f34  cmp     [rbp+var_18], 0
0x1800b5f38  jz      short loc_1800B5F59
0x1800b5f3a  mov     rdx, [rbp+var_28]
0x1800b5f3e  mov     rax, [rbp+var_20]
0x1800b5f42  mov     rcx, [rdx]
0x1800b5f45  mov     [rdx], rax
0x1800b5f48  test    rcx, rcx
0x1800b5f4b  jz      short loc_1800B5F59
0x1800b5f4d  call    cs:__imp_SRCache_Free
0x1800b5f54  nop     dword ptr [rax+rax+00h]
0x1800b5f59  test    ebx, ebx
0x1800b5f5b  jns     short loc_1800B5F7F
0x1800b5f5d  mov     edx, 352h; void *
0x1800b5f62  mov     rcx, [rbp+30h]; this
0x1800b5f66  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5f6d  mov     r9d, ebx; char *
0x1800b5f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5f75  mov     edx, 0B5h
0x1800b5f7a  jmp     loc_1800B5DBD
0x1800b5f7f  mov     [r14], r15
0x1800b5f82  mov     rcx, [rbp+arg_8]
0x1800b5f86  mov     [rbp+arg_8], 0
0x1800b5f8e  test    rcx, rcx
0x1800b5f91  jz      short loc_1800B5F9F
0x1800b5f93  call    cs:__imp_SRCacheContext_Close
0x1800b5f9a  nop     dword ptr [rax+rax+00h]
0x1800b5f9f  xor     eax, eax
0x1800b5fa1  add     rsp, 48h
0x1800b5fa5  pop     r15
0x1800b5fa7  pop     r14
0x1800b5fa9  pop     rdi
0x1800b5faa  pop     rsi
0x1800b5fab  pop     rbx
0x1800b5fac  pop     rbp
0x1800b5fad  retn
```
