# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18003d520`
- end: `0x18003d7b2`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18003d45c`
- `0x1800a0b04`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003d520`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d5a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d6a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d750`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d786`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d5a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d6a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d750`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d786`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d642`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d76b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d642`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d76b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003d6ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003d6ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003d70a`

## string_xrefs

- `0x18003d6e3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d723`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d588`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18003d61b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18003d68a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18003d565`: `User\Index\UserSid`
- `0x18003d703`: `User\Index\UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  bool v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+248h] [rbp+148h]
  __int64 v24; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v25; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v18[0] = 0;
  v19 = 0;
  v5 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v19,
         a1,
         L"User\\Index\\UserSid",
         v18);
  if ( v5 < 0 )
  {
    v6 = 185;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v5,
      *(int *)v18);
LABEL_4:
    v7 = v19;
    v19 = 0;
    if ( v7 )
      SRCacheContext_Close();
    return (unsigned int)v5;
  }
  if ( !v18[0] )
  {
    v5 = -2140733422;
    v6 = 186;
    goto LABEL_3;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = (unsigned __int16 *)v22;
  v24 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a2);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v9,
      *(int *)v18);
LABEL_11:
    v10 = v21;
    v21 = 0;
    if ( v10 )
      SRCache_Free();
    goto LABEL_4;
  }
  v20 = 0;
  v18[0] = 0;
  v5 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         (StateRepository::Cache::Context_NoThrow *)&v20,
         (struct StateRepository::Cache::Context_NoThrow *)&v19,
         v25,
         v18);
  if ( v5 < 0 )
  {
    v11 = 193;
    goto LABEL_15;
  }
  if ( v18[0] )
  {
    v13 = SRCacheContext_EnumerateData(v20, 0, a3);
    v5 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v13,
        *(int *)v18);
      v11 = 196;
      goto LABEL_15;
    }
  }
  v14 = SRCacheContext_AddToCache(v19, L"User\\Index\\UserSid");
  v5 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      *(int *)v18);
    v11 = 199;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v5,
      *(int *)v18);
    v12 = v20;
    v20 = 0;
    if ( v12 )
      SRCacheContext_Close();
    goto LABEL_11;
  }
  v15 = v20;
  v20 = 0;
  if ( v15 )
    SRCacheContext_Close();
  v16 = v21;
  v21 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = v19;
  v19 = 0;
  if ( v17 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18003d520  push    rbp
0x18003d522  push    rbx
0x18003d523  push    rsi
0x18003d524  push    rdi
0x18003d525  push    r14
0x18003d527  lea     rbp, [rsp-170h]
0x18003d52f  sub     rsp, 270h
0x18003d536  mov     rax, cs:__security_cookie
0x18003d53d  xor     rax, rsp
0x18003d540  mov     [rbp+190h+var_30], rax
0x18003d547  xor     r14d, r14d
0x18003d54a  lea     r9, [rsp+290h+var_270]; bool *
0x18003d54f  mov     rsi, rdx
0x18003d552  mov     [r8], r14
0x18003d555  mov     rdi, r8
0x18003d558  mov     [rsp+290h+var_270], r14b; int
0x18003d55d  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003d560  mov     [rsp+290h+var_268], r14
0x18003d565  lea     r8, aUserIndexUsers; "User\\Index\\UserSid"
0x18003d56c  lea     rcx, [rsp+290h+var_268]; this
0x18003d571  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003d576  mov     ebx, eax
0x18003d578  test    eax, eax
0x18003d57a  jns     short loc_18003D5B9
0x18003d57c  mov     edx, 0B9h; void *
0x18003d581  mov     rcx, [rbp+198h]; this
0x18003d588  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d58f  mov     r9d, ebx; char *
0x18003d592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d597  mov     rcx, [rsp+290h+var_268]
0x18003d59c  mov     [rsp+290h+var_268], r14
0x18003d5a1  test    rcx, rcx
0x18003d5a4  jz      short loc_18003D5B2
0x18003d5a6  call    cs:__imp_SRCacheContext_Close
0x18003d5ad  nop     dword ptr [rax+rax+00h]
0x18003d5b2  mov     eax, ebx
0x18003d5b4  jmp     loc_18003D794
0x18003d5b9  cmp     [rsp+290h+var_270], r14b
0x18003d5be  jnz     short loc_18003D5CC
0x18003d5c0  mov     ebx, 80670012h
0x18003d5c5  mov     edx, 0BAh
0x18003d5ca  jmp     short loc_18003D581
0x18003d5cc  xor     edx, edx; Val
0x18003d5ce  mov     [rsp+290h+var_250], r14
0x18003d5d3  mov     r8d, 200h; Size
0x18003d5d9  lea     rcx, [rsp+290h+var_248]; void *
0x18003d5de  call    memset_0
0x18003d5e3  lea     rax, [rsp+290h+var_248]
0x18003d5e8  mov     [rbp+190h+var_48], r14
0x18003d5ef  mov     rdx, rsi; unsigned __int16 *
0x18003d5f2  mov     [rbp+190h+var_38], rax
0x18003d5f9  lea     rcx, [rsp+290h+var_250]; this
0x18003d5fe  mov     [rbp+190h+var_40], 100h
0x18003d609  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003d60e  mov     ebx, eax
0x18003d610  test    eax, eax
0x18003d612  jns     short loc_18003D653
0x18003d614  mov     rcx, [rbp+198h]; this
0x18003d61b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d622  mov     r9d, eax; char *
0x18003d625  mov     edx, 0BDh; void *
0x18003d62a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d62f  mov     rcx, [rsp+290h+var_250]
0x18003d634  mov     [rsp+290h+var_250], r14
0x18003d639  test    rcx, rcx
0x18003d63c  jz      loc_18003D597
0x18003d642  call    cs:__imp_SRCache_Free
0x18003d649  nop     dword ptr [rax+rax+00h]
0x18003d64e  jmp     loc_18003D597
0x18003d653  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x18003d65a  lea     r9, [rsp+290h+var_270]; bool *
0x18003d65f  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003d664  mov     [rsp+290h+var_260], r14
0x18003d669  lea     rcx, [rsp+290h+var_260]; this
0x18003d66e  mov     [rsp+290h+var_270], r14b; int
0x18003d673  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003d678  mov     ebx, eax
0x18003d67a  test    eax, eax
0x18003d67c  jns     short loc_18003D6B9
0x18003d67e  mov     edx, 0C1h; void *
0x18003d683  mov     rcx, [rbp+198h]; this
0x18003d68a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d691  mov     r9d, ebx; char *
0x18003d694  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d699  mov     rcx, [rsp+290h+var_260]
0x18003d69e  mov     [rsp+290h+var_260], r14
0x18003d6a3  test    rcx, rcx
0x18003d6a6  jz      short loc_18003D62F
0x18003d6a8  call    cs:__imp_SRCacheContext_Close
0x18003d6af  nop     dword ptr [rax+rax+00h]
0x18003d6b4  jmp     loc_18003D62F
0x18003d6b9  cmp     [rsp+290h+var_270], r14b
0x18003d6be  jz      short loc_18003D6FE
0x18003d6c0  mov     rcx, [rsp+290h+var_260]
0x18003d6c5  mov     r8, rdi
0x18003d6c8  xor     edx, edx
0x18003d6ca  call    cs:__imp_SRCacheContext_EnumerateData
0x18003d6d1  nop     dword ptr [rax+rax+00h]
0x18003d6d6  mov     ebx, eax
0x18003d6d8  test    eax, eax
0x18003d6da  jns     short loc_18003D6FE
0x18003d6dc  mov     rcx, [rbp+198h]; this
0x18003d6e3  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d6ea  mov     r9d, eax; char *
0x18003d6ed  mov     edx, 2A6h; void *
0x18003d6f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d6f7  mov     edx, 0C4h
0x18003d6fc  jmp     short loc_18003D683
0x18003d6fe  mov     rcx, [rsp+290h+var_268]
0x18003d703  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18003d70a  call    cs:__imp_SRCacheContext_AddToCache
0x18003d711  nop     dword ptr [rax+rax+00h]
0x18003d716  mov     ebx, eax
0x18003d718  test    eax, eax
0x18003d71a  jns     short loc_18003D741
0x18003d71c  mov     rcx, [rbp+198h]; this
0x18003d723  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d72a  mov     r9d, eax; char *
0x18003d72d  mov     edx, 1A6h; void *
0x18003d732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d737  mov     edx, 0C7h
0x18003d73c  jmp     loc_18003D683
0x18003d741  mov     rcx, [rsp+290h+var_260]
0x18003d746  mov     [rsp+290h+var_260], r14
0x18003d74b  test    rcx, rcx
0x18003d74e  jz      short loc_18003D75C
0x18003d750  call    cs:__imp_SRCacheContext_Close
0x18003d757  nop     dword ptr [rax+rax+00h]
0x18003d75c  mov     rcx, [rsp+290h+var_250]
0x18003d761  mov     [rsp+290h+var_250], r14
0x18003d766  test    rcx, rcx
0x18003d769  jz      short loc_18003D777
0x18003d76b  call    cs:__imp_SRCache_Free
0x18003d772  nop     dword ptr [rax+rax+00h]
0x18003d777  mov     rcx, [rsp+290h+var_268]
0x18003d77c  mov     [rsp+290h+var_268], r14
0x18003d781  test    rcx, rcx
0x18003d784  jz      short loc_18003D792
0x18003d786  call    cs:__imp_SRCacheContext_Close
0x18003d78d  nop     dword ptr [rax+rax+00h]
0x18003d792  xor     eax, eax
0x18003d794  mov     rcx, [rbp+190h+var_30]
0x18003d79b  xor     rcx, rsp; StackCookie
0x18003d79e  call    __security_check_cookie
0x18003d7a3  add     rsp, 270h
0x18003d7aa  pop     r14
0x18003d7ac  pop     rdi
0x18003d7ad  pop     rsi
0x18003d7ae  pop     rbx
0x18003d7af  pop     rbp
0x18003d7b0  retn
```
