# StateRepository::Cache::Entity::Protocol_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)

- ea: `0x1800b416c`
- end: `0x1800b43cc`
- name: `?Get@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b4070`

## callees

- `0x18000e234`
- `0x1800b416c`
- `0x1800ba8c4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4291`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b431d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b4291`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800b431d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b41fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b43a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b41fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b43a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4232`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800b4232`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b42d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4360`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b42d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b4360`

## string_xrefs

- `0x1800b4211`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800b422b`: `Extension`
- `0x1800b4199`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b41dd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b4379`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)0x80070057LL,
      (int)v20);
    return (unsigned int)v8;
  }
  v10 = a5;
  v27 = 0;
  v8 = StateRepository::Cache::Entity::Protocol_NoThrow::Open(
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
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
          (const char *)(unsigned int)v8,
          (int)v20);
        v11 = 181;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
      Field_String = SRCacheContext_GetField_String(v27, L"Name", &v21);
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
0x1800b416c  mov     [rsp-18h+arg_0], rbx
0x1800b4171  mov     [rsp-18h+arg_10], rsi
0x1800b4176  mov     [rsp-18h+arg_18], rdi
0x1800b417b  push    rbp
0x1800b417c  push    r14
0x1800b417e  push    r15
0x1800b4180  mov     rbp, rsp
0x1800b4183  sub     rsp, 50h
0x1800b4187  mov     r14, r9
0x1800b418a  mov     rdi, r8
0x1800b418d  mov     r15, rdx
0x1800b4190  test    rdx, rdx
0x1800b4193  jnz     short loc_1800B41B9
0x1800b4195  mov     rcx, [rbp+18h]; this
0x1800b4199  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b41a0  mov     ebx, 80070057h
0x1800b41a5  mov     edx, 0ADh; void *
0x1800b41aa  mov     r9d, ebx; char *
0x1800b41ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b41b2  mov     eax, ebx
0x1800b41b4  jmp     loc_1800B43B1
0x1800b41b9  mov     rsi, [rbp+arg_20]
0x1800b41bd  lea     r8, [rbp+arg_8]; this
0x1800b41c1  and     [rbp+arg_8], 0
0x1800b41c6  mov     r9, rsi; bool *
0x1800b41c9  call    ?Open@Protocol_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Protocol_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800b41ce  mov     ebx, eax
0x1800b41d0  test    eax, eax
0x1800b41d2  jns     short loc_1800B4208
0x1800b41d4  mov     edx, 0B0h; void *
0x1800b41d9  mov     rcx, [rbp+18h]; this
0x1800b41dd  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b41e4  mov     r9d, ebx; char *
0x1800b41e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b41ec  mov     rcx, [rbp+arg_8]
0x1800b41f0  and     [rbp+arg_8], 0
0x1800b41f5  test    rcx, rcx
0x1800b41f8  jz      short loc_1800B41B2
0x1800b41fa  call    cs:__imp_SRCacheContext_Close
0x1800b4201  nop     dword ptr [rax+rax+00h]
0x1800b4206  jmp     short loc_1800B41B2
0x1800b4208  cmp     byte ptr [rsi], 0
0x1800b420b  jz      loc_1800B4395
0x1800b4211  lea     rsi, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b4218  test    rdi, rdi
0x1800b421b  jz      short loc_1800B4223
0x1800b421d  test    dil, 1
0x1800b4221  jz      short loc_1800B4267
0x1800b4223  mov     rcx, [rbp+arg_8]
0x1800b4227  lea     r8, [r14+8]
0x1800b422b  lea     rdx, aExtension; "Extension"
0x1800b4232  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800b4239  nop     dword ptr [rax+rax+00h]
0x1800b423e  mov     ebx, eax
0x1800b4240  test    eax, eax
0x1800b4242  jns     short loc_1800B4262
0x1800b4244  mov     rcx, [rbp+18h]; this
0x1800b4248  mov     r9d, eax; char *
0x1800b424b  mov     r8, rsi; unsigned int
0x1800b424e  mov     edx, 221h; void *
0x1800b4253  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4258  mov     edx, 34Ah
0x1800b425d  jmp     loc_1800B4375
0x1800b4262  test    rdi, rdi
0x1800b4265  jz      short loc_1800B4271
0x1800b4267  test    dil, 2
0x1800b426b  jz      loc_1800B42F3
0x1800b4271  mov     rcx, [rbp+arg_8]
0x1800b4275  lea     rax, [r14+10h]
0x1800b4279  and     [rbp+var_28], 0
0x1800b427e  lea     r8, [rbp+var_28]
0x1800b4282  lea     rdx, aName; "Name"
0x1800b4289  mov     [rbp+var_30], rax
0x1800b428d  mov     [rbp+var_20], 1
0x1800b4291  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4298  nop     dword ptr [rax+rax+00h]
0x1800b429d  mov     ebx, eax
0x1800b429f  test    eax, eax
0x1800b42a1  jns     short loc_1800B42B9
0x1800b42a3  mov     rcx, [rbp+18h]; this
0x1800b42a7  mov     r9d, eax; char *
0x1800b42aa  mov     r8, rsi; unsigned int
0x1800b42ad  mov     edx, 246h; void *
0x1800b42b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b42b7  jmp     short loc_1800B42BB
0x1800b42b9  xor     ebx, ebx
0x1800b42bb  cmp     [rbp+var_20], 0
0x1800b42bf  jz      short loc_1800B42E0
0x1800b42c1  mov     rdx, [rbp+var_30]
0x1800b42c5  mov     rax, [rbp+var_28]
0x1800b42c9  mov     rcx, [rdx]
0x1800b42cc  mov     [rdx], rax
0x1800b42cf  test    rcx, rcx
0x1800b42d2  jz      short loc_1800B42E0
0x1800b42d4  call    cs:__imp_SRCache_Free
0x1800b42db  nop     dword ptr [rax+rax+00h]
0x1800b42e0  test    ebx, ebx
0x1800b42e2  jns     short loc_1800B42EE
0x1800b42e4  mov     edx, 34Eh
0x1800b42e9  jmp     loc_1800B4375
0x1800b42ee  test    rdi, rdi
0x1800b42f1  jz      short loc_1800B42FD
0x1800b42f3  test    dil, 4
0x1800b42f7  jz      loc_1800B4392
0x1800b42fd  mov     rcx, [rbp+arg_8]
0x1800b4301  lea     rax, [r14+18h]
0x1800b4305  and     [rbp+var_10], 0
0x1800b430a  lea     r8, [rbp+var_10]
0x1800b430e  lea     rdx, aProgid; "ProgID"
0x1800b4315  mov     [rbp+var_18], rax
0x1800b4319  mov     [rbp+var_8], 1
0x1800b431d  call    cs:__imp_SRCacheContext_GetField_String
0x1800b4324  nop     dword ptr [rax+rax+00h]
0x1800b4329  mov     ebx, eax
0x1800b432b  test    eax, eax
0x1800b432d  jns     short loc_1800B4345
0x1800b432f  mov     rcx, [rbp+18h]; this
0x1800b4333  mov     r9d, eax; char *
0x1800b4336  mov     r8, rsi; unsigned int
0x1800b4339  mov     edx, 246h; void *
0x1800b433e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4343  jmp     short loc_1800B4347
0x1800b4345  xor     ebx, ebx
0x1800b4347  cmp     [rbp+var_8], 0
0x1800b434b  jz      short loc_1800B436C
0x1800b434d  mov     rdx, [rbp+var_18]
0x1800b4351  mov     rax, [rbp+var_10]
0x1800b4355  mov     rcx, [rdx]
0x1800b4358  mov     [rdx], rax
0x1800b435b  test    rcx, rcx
0x1800b435e  jz      short loc_1800B436C
0x1800b4360  call    cs:__imp_SRCache_Free
0x1800b4367  nop     dword ptr [rax+rax+00h]
0x1800b436c  test    ebx, ebx
0x1800b436e  jns     short loc_1800B4392
0x1800b4370  mov     edx, 352h; void *
0x1800b4375  mov     rcx, [rbp+18h]; this
0x1800b4379  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b4380  mov     r9d, ebx; char *
0x1800b4383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4388  mov     edx, 0B5h
0x1800b438d  jmp     loc_1800B41D9
0x1800b4392  mov     [r14], r15
0x1800b4395  mov     rcx, [rbp+arg_8]
0x1800b4399  and     [rbp+arg_8], 0
0x1800b439e  test    rcx, rcx
0x1800b43a1  jz      short loc_1800B43AF
0x1800b43a3  call    cs:__imp_SRCacheContext_Close
0x1800b43aa  nop     dword ptr [rax+rax+00h]
0x1800b43af  xor     eax, eax
0x1800b43b1  lea     r11, [rsp+50h+var_s0]
0x1800b43b6  mov     rbx, [r11+20h]
0x1800b43ba  mov     rsi, [r11+30h]
0x1800b43be  mov     rdi, [r11+38h]
0x1800b43c2  mov     rsp, r11
0x1800b43c5  pop     r15
0x1800b43c7  pop     r14
0x1800b43c9  pop     rbp
0x1800b43ca  retn
```
