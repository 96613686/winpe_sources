# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)

- ea: `0x1800a0b04`
- end: `0x1800a0c6a`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800a0c70`

## callees

- `0x18000ff24`
- `0x18003d520`
- `0x1800a02ec`
- `0x1800a0b04`
- `0x1800a13c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0bb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0c25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0c4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0bb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0c25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a0c4d`

## string_xrefs

- `0x1800a0b41`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a0b8f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a0c02`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        _QWORD *a4,
        bool *a5)
{
  bool *v7; // rsi
  int v8; // ebx
  __int64 v9; // rdx
  bool *v11; // rdi
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+30h]
  __int64 v21; // [rsp+70h] [rbp+48h] BYREF

  v21 = a3;
  v7 = a5;
  *a5 = 0;
  a5 = 0;
  v8 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, a2, (__int64 *)&a5);
  if ( v8 < 0 )
  {
    v9 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v8,
      v19);
    return (unsigned int)v8;
  }
  v11 = a5;
  if ( a5 )
  {
    v21 = 0;
    v12 = StateRepository::Cache::Entity::User_NoThrow::Open(
            a1,
            (__int64)a5,
            (struct StateRepository::Cache::Context_NoThrow *)&v21,
            v7);
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)v12,
        v19);
      v14 = v21;
      v21 = 0;
      if ( v14 )
        SRCacheContext_Close();
LABEL_16:
      v9 = 248;
      goto LABEL_3;
    }
    if ( *v7 )
    {
      v16 = StateRepository::Cache::Entity::User_NoThrow::ContextToObject(&v21, a4, v13, (__int64)v11);
      v8 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          (const char *)(unsigned int)v16,
          v19);
        v17 = v21;
        v21 = 0;
        if ( v17 )
          SRCacheContext_Close();
        goto LABEL_16;
      }
      v18 = v21;
      v21 = 0;
      if ( v18 )
        SRCacheContext_Close();
    }
    else
    {
      v15 = v21;
      v21 = 0;
      if ( v15 )
        SRCacheContext_Close();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a0b04  mov     [rsp-30h+arg_10], r8
0x1800a0b09  push    rbp
0x1800a0b0a  push    rbx
0x1800a0b0b  push    rsi
0x1800a0b0c  push    rdi
0x1800a0b0d  push    r14
0x1800a0b0f  push    r15
0x1800a0b11  mov     rbp, rsp
0x1800a0b14  sub     rsp, 28h
0x1800a0b18  mov     r15, r9
0x1800a0b1b  mov     r14, rcx
0x1800a0b1e  mov     rsi, [rbp+arg_20]
0x1800a0b22  mov     byte ptr [rsi], 0
0x1800a0b25  mov     [rbp+arg_20], 0
0x1800a0b2d  lea     r8, [rbp+arg_20]; __int64 *
0x1800a0b31  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800a0b36  mov     ebx, eax
0x1800a0b38  test    eax, eax
0x1800a0b3a  jns     short loc_1800A0B5B
0x1800a0b3c  mov     edx, 0F5h; void *
0x1800a0b41  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0b48  mov     r9d, ebx; char *
0x1800a0b4b  mov     rcx, [rbp+30h]; this
0x1800a0b4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0b54  mov     eax, ebx
0x1800a0b56  jmp     loc_1800A0C5C
0x1800a0b5b  mov     rdi, [rbp+arg_20]
0x1800a0b5f  test    rdi, rdi
0x1800a0b62  jz      loc_1800A0C5A
0x1800a0b68  mov     [rbp+arg_10], 0
0x1800a0b70  mov     r9, rsi; bool *
0x1800a0b73  lea     r8, [rbp+arg_10]; this
0x1800a0b77  mov     rdx, rdi; __int64
0x1800a0b7a  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800a0b7d  call    ?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800a0b82  mov     ebx, eax
0x1800a0b84  test    eax, eax
0x1800a0b86  jns     short loc_1800A0BC1
0x1800a0b88  mov     rcx, [rbp+30h]; this
0x1800a0b8c  mov     r9d, eax; char *
0x1800a0b8f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0b96  mov     edx, 9Bh; void *
0x1800a0b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0ba0  nop
0x1800a0ba1  mov     rcx, [rbp+arg_10]
0x1800a0ba5  mov     [rbp+arg_10], 0
0x1800a0bad  test    rcx, rcx
0x1800a0bb0  jz      short loc_1800A0BBF
0x1800a0bb2  call    cs:__imp_SRCacheContext_Close
0x1800a0bb9  nop     dword ptr [rax+rax+00h]
0x1800a0bbe  nop
0x1800a0bbf  jmp     short loc_1800A0C32
0x1800a0bc1  cmp     byte ptr [rsi], 0
0x1800a0bc4  jnz     short loc_1800A0BE6
0x1800a0bc6  mov     rcx, [rbp+arg_10]
0x1800a0bca  mov     [rbp+arg_10], 0
0x1800a0bd2  test    rcx, rcx
0x1800a0bd5  jz      short loc_1800A0BE4
0x1800a0bd7  call    cs:__imp_SRCacheContext_Close
0x1800a0bde  nop     dword ptr [rax+rax+00h]
0x1800a0be3  nop
0x1800a0be4  jmp     short loc_1800A0C5A
0x1800a0be6  mov     r9, rdi
0x1800a0be9  mov     rdx, r15
0x1800a0bec  lea     rcx, [rbp+arg_10]
0x1800a0bf0  call    ?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)
0x1800a0bf5  mov     ebx, eax
0x1800a0bf7  test    eax, eax
0x1800a0bf9  jns     short loc_1800A0C3C
0x1800a0bfb  mov     rcx, [rbp+30h]; this
0x1800a0bff  mov     r9d, eax; char *
0x1800a0c02  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0c09  mov     edx, 0A0h; void *
0x1800a0c0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0c13  nop
0x1800a0c14  mov     rcx, [rbp+arg_10]
0x1800a0c18  mov     [rbp+arg_10], 0
0x1800a0c20  test    rcx, rcx
0x1800a0c23  jz      short loc_1800A0C32
0x1800a0c25  call    cs:__imp_SRCacheContext_Close
0x1800a0c2c  nop     dword ptr [rax+rax+00h]
0x1800a0c31  nop
0x1800a0c32  mov     edx, 0F8h
0x1800a0c37  jmp     loc_1800A0B41
0x1800a0c3c  mov     rcx, [rbp+arg_10]
0x1800a0c40  mov     [rbp+arg_10], 0
0x1800a0c48  test    rcx, rcx
0x1800a0c4b  jz      short loc_1800A0C5A
0x1800a0c4d  call    cs:__imp_SRCacheContext_Close
0x1800a0c54  nop     dword ptr [rax+rax+00h]
0x1800a0c59  nop
0x1800a0c5a  xor     eax, eax
0x1800a0c5c  add     rsp, 28h
0x1800a0c60  pop     r15
0x1800a0c62  pop     r14
0x1800a0c64  pop     rdi
0x1800a0c65  pop     rsi
0x1800a0c66  pop     rbx
0x1800a0c67  pop     rbp
0x1800a0c68  retn
```
