# StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)

- ea: `0x18003b0d4`
- end: `0x18003b23d`
- name: `?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `361`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18003b244`
- `0x1800b52fc`
- `0x1800b5598`

## callees

- `0x18000e234`
- `0x18003add8`
- `0x18003b0d4`
- `0x18003ce6c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b1f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b21b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b1f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b21b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18003b18c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18003b18c`

## string_xrefs

- `0x18003b1a2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003b10b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003b1ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003b1da`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        ...)
{
  bool *v3; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rdx
  bool *v8; // rdi
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool **v13; // rsi
  int Field_UInt32; // eax
  __int64 v15; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  int savedregsa; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v19; // [rsp+58h] [rbp+38h] BYREF
  va_list va; // [rsp+58h] [rbp+38h]
  bool **v21; // [rsp+60h] [rbp+40h]
  bool *v22; // [rsp+68h] [rbp+48h] BYREF
  va_list va1; // [rsp+68h] [rbp+48h]
  va_list va2; // [rsp+70h] [rbp+50h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v19 = va_arg(va1, _QWORD);
  v21 = va_arg(va1, bool **);
  va_copy(va2, va1);
  v22 = va_arg(va2, bool *);
  v3 = v22;
  *v22 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 465;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)v5,
      savedregs);
    return v5;
  }
  v22 = 0;
  v5 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
         a1,
         a2,
         a3,
         (__int64 *)va1);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 468;
    goto LABEL_3;
  }
  v8 = v22;
  if ( v22 )
  {
    v19 = 0;
    v9 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
           a1,
           (__int64)v22,
           (struct StateRepository::Cache::Context_NoThrow *)va,
           v3);
    v5 = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v11 = 274;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)v10,
        savedregs);
      v15 = v19;
      v19 = 0;
      if ( v15 )
        SRCacheContext_Close();
      v6 = 471;
      goto LABEL_3;
    }
    v12 = v19;
    if ( *v3 )
    {
      v13 = v21;
      Field_UInt32 = SRCacheContext_GetField_UInt32(v19, L"Application", v21 + 3);
      v5 = Field_UInt32;
      if ( Field_UInt32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_UInt32,
          savedregs);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45D,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
          (const char *)v5,
          savedregsa);
        v10 = v5;
        v11 = 279;
        goto LABEL_12;
      }
      v12 = v19;
      *v13 = v8;
    }
    v19 = 0;
    if ( v12 )
      SRCacheContext_Close();
  }
  return 0;
}

```

## disassembly

```asm
0x18003b0d4  mov     [rsp-18h+arg_0], rbx
0x18003b0d9  mov     [rsp-18h+arg_8], rsi
0x18003b0de  mov     [rsp-18h+arg_18], r9
0x18003b0e3  push    rbp
0x18003b0e4  push    rdi
0x18003b0e5  push    r14; int
0x18003b0e7  mov     rbp, rsp
0x18003b0ea  sub     rsp, 20h
0x18003b0ee  mov     rsi, [rbp+arg_28]
0x18003b0f2  mov     r14, rcx
0x18003b0f5  mov     byte ptr [rsi], 0
0x18003b0f8  test    rdx, rdx
0x18003b0fb  jnz     short loc_18003B121
0x18003b0fd  mov     ebx, 80070057h
0x18003b102  mov     edx, 1D1h; void *
0x18003b107  mov     rcx, [rbp+18h]; this
0x18003b10b  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b112  mov     r9d, ebx; char *
0x18003b115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b11a  mov     eax, ebx
0x18003b11c  jmp     loc_18003B229
0x18003b121  and     [rbp+arg_28], 0
0x18003b126  lea     r9, [rbp+arg_28]; __int64 *
0x18003b12a  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)
0x18003b12f  mov     ebx, eax
0x18003b131  test    eax, eax
0x18003b133  jns     short loc_18003B13C
0x18003b135  mov     edx, 1D4h
0x18003b13a  jmp     short loc_18003B107
0x18003b13c  mov     rdi, [rbp+arg_28]
0x18003b140  test    rdi, rdi
0x18003b143  jz      loc_18003B227
0x18003b149  and     [rbp+arg_18], 0
0x18003b14e  lea     r8, [rbp+arg_18]; this
0x18003b152  mov     r9, rsi; bool *
0x18003b155  mov     rdx, rdi; __int64
0x18003b158  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18003b15b  call    ?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18003b160  mov     ebx, eax
0x18003b162  test    eax, eax
0x18003b164  jns     short loc_18003B170
0x18003b166  mov     r9d, eax
0x18003b169  mov     edx, 112h
0x18003b16e  jmp     short loc_18003B1D6
0x18003b170  cmp     byte ptr [rsi], 0
0x18003b173  mov     rcx, [rbp+arg_18]
0x18003b177  jz      loc_18003B211
0x18003b17d  mov     rsi, [rbp+arg_20]
0x18003b181  lea     rdx, aApplication; "Application"
0x18003b188  lea     r8, [rsi+18h]
0x18003b18c  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18003b193  nop     dword ptr [rax+rax+00h]
0x18003b198  mov     ebx, eax
0x18003b19a  test    eax, eax
0x18003b19c  jns     short loc_18003B20A
0x18003b19e  mov     rcx, [rbp+18h]; this
0x18003b1a2  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b1a9  mov     r9d, eax; char *
0x18003b1ac  mov     edx, 221h; void *
0x18003b1b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1b6  mov     rcx, [rbp+18h]; this
0x18003b1ba  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b1c1  mov     r9d, ebx; char *
0x18003b1c4  mov     edx, 45Dh; void *
0x18003b1c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1ce  mov     r9d, ebx; char *
0x18003b1d1  mov     edx, 117h; void *
0x18003b1d6  mov     rcx, [rbp+18h]; this
0x18003b1da  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1e6  mov     rcx, [rbp+arg_18]
0x18003b1ea  and     [rbp+arg_18], 0
0x18003b1ef  test    rcx, rcx
0x18003b1f2  jz      short loc_18003B200
0x18003b1f4  call    cs:__imp_SRCacheContext_Close
0x18003b1fb  nop     dword ptr [rax+rax+00h]
0x18003b200  mov     edx, 1D7h
0x18003b205  jmp     loc_18003B107
0x18003b20a  mov     rcx, [rbp+arg_18]
0x18003b20e  mov     [rsi], rdi
0x18003b211  and     [rbp+arg_18], 0
0x18003b216  test    rcx, rcx
0x18003b219  jz      short loc_18003B227
0x18003b21b  call    cs:__imp_SRCacheContext_Close
0x18003b222  nop     dword ptr [rax+rax+00h]
0x18003b227  xor     eax, eax
0x18003b229  mov     rbx, [rsp+20h+arg_0]
0x18003b22e  mov     rsi, [rsp+20h+arg_8]
0x18003b233  add     rsp, 20h
0x18003b237  pop     r14
0x18003b239  pop     rdi
0x18003b23a  pop     rbp
0x18003b23b  retn
```
