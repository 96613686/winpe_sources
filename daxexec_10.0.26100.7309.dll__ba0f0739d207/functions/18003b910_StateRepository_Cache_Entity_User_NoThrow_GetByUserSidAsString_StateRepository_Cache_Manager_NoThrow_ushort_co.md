# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18003b910`
- end: `0x18003bba2`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18003b850`
- `0x18009f27c`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x18003b910`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b996`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ba98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003bb40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003bb76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b996`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ba98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003bb40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003bb76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003baba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18003baba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ba32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003bb5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ba32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003bb5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003bafa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003bafa`

## string_xrefs

- `0x18003bad3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003bb13`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003b978`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18003ba0b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18003ba7a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18003b955`: `User\Index\UserSid`
- `0x18003baf3`: `User\Index\UserSid`

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
0x18003b910  push    rbp
0x18003b912  push    rbx
0x18003b913  push    rsi
0x18003b914  push    rdi
0x18003b915  push    r14
0x18003b917  lea     rbp, [rsp-170h]
0x18003b91f  sub     rsp, 270h
0x18003b926  mov     rax, cs:__security_cookie
0x18003b92d  xor     rax, rsp
0x18003b930  mov     [rbp+190h+var_30], rax
0x18003b937  xor     r14d, r14d
0x18003b93a  lea     r9, [rsp+290h+var_270]; bool *
0x18003b93f  mov     rsi, rdx
0x18003b942  mov     [r8], r14
0x18003b945  mov     rdi, r8
0x18003b948  mov     [rsp+290h+var_270], r14b; int
0x18003b94d  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003b950  mov     [rsp+290h+var_268], r14
0x18003b955  lea     r8, aUserIndexUsers; "User\\Index\\UserSid"
0x18003b95c  lea     rcx, [rsp+290h+var_268]; this
0x18003b961  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003b966  mov     ebx, eax
0x18003b968  test    eax, eax
0x18003b96a  jns     short loc_18003B9A9
0x18003b96c  mov     edx, 0B9h; void *
0x18003b971  mov     rcx, [rbp+198h]; this
0x18003b978  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b97f  mov     r9d, ebx; char *
0x18003b982  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b987  mov     rcx, [rsp+290h+var_268]
0x18003b98c  mov     [rsp+290h+var_268], r14
0x18003b991  test    rcx, rcx
0x18003b994  jz      short loc_18003B9A2
0x18003b996  call    cs:__imp_SRCacheContext_Close
0x18003b99d  nop     dword ptr [rax+rax+00h]
0x18003b9a2  mov     eax, ebx
0x18003b9a4  jmp     loc_18003BB84
0x18003b9a9  cmp     [rsp+290h+var_270], r14b
0x18003b9ae  jnz     short loc_18003B9BC
0x18003b9b0  mov     ebx, 80670012h
0x18003b9b5  mov     edx, 0BAh
0x18003b9ba  jmp     short loc_18003B971
0x18003b9bc  xor     edx, edx; Val
0x18003b9be  mov     [rsp+290h+var_250], r14
0x18003b9c3  mov     r8d, 200h; Size
0x18003b9c9  lea     rcx, [rsp+290h+var_248]; void *
0x18003b9ce  call    memset_0
0x18003b9d3  lea     rax, [rsp+290h+var_248]
0x18003b9d8  mov     [rbp+190h+var_48], r14
0x18003b9df  mov     rdx, rsi; unsigned __int16 *
0x18003b9e2  mov     [rbp+190h+var_38], rax
0x18003b9e9  lea     rcx, [rsp+290h+var_250]; this
0x18003b9ee  mov     [rbp+190h+var_40], 100h
0x18003b9f9  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18003b9fe  mov     ebx, eax
0x18003ba00  test    eax, eax
0x18003ba02  jns     short loc_18003BA43
0x18003ba04  mov     rcx, [rbp+198h]; this
0x18003ba0b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ba12  mov     r9d, eax; char *
0x18003ba15  mov     edx, 0BDh; void *
0x18003ba1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba1f  mov     rcx, [rsp+290h+var_250]
0x18003ba24  mov     [rsp+290h+var_250], r14
0x18003ba29  test    rcx, rcx
0x18003ba2c  jz      loc_18003B987
0x18003ba32  call    cs:__imp_SRCache_Free
0x18003ba39  nop     dword ptr [rax+rax+00h]
0x18003ba3e  jmp     loc_18003B987
0x18003ba43  mov     r8, [rbp+190h+var_38]; unsigned __int16 *
0x18003ba4a  lea     r9, [rsp+290h+var_270]; bool *
0x18003ba4f  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003ba54  mov     [rsp+290h+var_260], r14
0x18003ba59  lea     rcx, [rsp+290h+var_260]; this
0x18003ba5e  mov     [rsp+290h+var_270], r14b; int
0x18003ba63  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003ba68  mov     ebx, eax
0x18003ba6a  test    eax, eax
0x18003ba6c  jns     short loc_18003BAA9
0x18003ba6e  mov     edx, 0C1h; void *
0x18003ba73  mov     rcx, [rbp+198h]; this
0x18003ba7a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ba81  mov     r9d, ebx; char *
0x18003ba84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba89  mov     rcx, [rsp+290h+var_260]
0x18003ba8e  mov     [rsp+290h+var_260], r14
0x18003ba93  test    rcx, rcx
0x18003ba96  jz      short loc_18003BA1F
0x18003ba98  call    cs:__imp_SRCacheContext_Close
0x18003ba9f  nop     dword ptr [rax+rax+00h]
0x18003baa4  jmp     loc_18003BA1F
0x18003baa9  cmp     [rsp+290h+var_270], r14b
0x18003baae  jz      short loc_18003BAEE
0x18003bab0  mov     rcx, [rsp+290h+var_260]
0x18003bab5  mov     r8, rdi
0x18003bab8  xor     edx, edx
0x18003baba  call    cs:__imp_SRCacheContext_EnumerateData
0x18003bac1  nop     dword ptr [rax+rax+00h]
0x18003bac6  mov     ebx, eax
0x18003bac8  test    eax, eax
0x18003baca  jns     short loc_18003BAEE
0x18003bacc  mov     rcx, [rbp+198h]; this
0x18003bad3  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003bada  mov     r9d, eax; char *
0x18003badd  mov     edx, 2A6h; void *
0x18003bae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bae7  mov     edx, 0C4h
0x18003baec  jmp     short loc_18003BA73
0x18003baee  mov     rcx, [rsp+290h+var_268]
0x18003baf3  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18003bafa  call    cs:__imp_SRCacheContext_AddToCache
0x18003bb01  nop     dword ptr [rax+rax+00h]
0x18003bb06  mov     ebx, eax
0x18003bb08  test    eax, eax
0x18003bb0a  jns     short loc_18003BB31
0x18003bb0c  mov     rcx, [rbp+198h]; this
0x18003bb13  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003bb1a  mov     r9d, eax; char *
0x18003bb1d  mov     edx, 1A6h; void *
0x18003bb22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb27  mov     edx, 0C7h
0x18003bb2c  jmp     loc_18003BA73
0x18003bb31  mov     rcx, [rsp+290h+var_260]
0x18003bb36  mov     [rsp+290h+var_260], r14
0x18003bb3b  test    rcx, rcx
0x18003bb3e  jz      short loc_18003BB4C
0x18003bb40  call    cs:__imp_SRCacheContext_Close
0x18003bb47  nop     dword ptr [rax+rax+00h]
0x18003bb4c  mov     rcx, [rsp+290h+var_250]
0x18003bb51  mov     [rsp+290h+var_250], r14
0x18003bb56  test    rcx, rcx
0x18003bb59  jz      short loc_18003BB67
0x18003bb5b  call    cs:__imp_SRCache_Free
0x18003bb62  nop     dword ptr [rax+rax+00h]
0x18003bb67  mov     rcx, [rsp+290h+var_268]
0x18003bb6c  mov     [rsp+290h+var_268], r14
0x18003bb71  test    rcx, rcx
0x18003bb74  jz      short loc_18003BB82
0x18003bb76  call    cs:__imp_SRCacheContext_Close
0x18003bb7d  nop     dword ptr [rax+rax+00h]
0x18003bb82  xor     eax, eax
0x18003bb84  mov     rcx, [rbp+190h+var_30]
0x18003bb8b  xor     rcx, rsp; StackCookie
0x18003bb8e  call    __security_check_cookie
0x18003bb93  add     rsp, 270h
0x18003bb9a  pop     r14
0x18003bb9c  pop     rdi
0x18003bb9d  pop     rsi
0x18003bb9e  pop     rbx
0x18003bb9f  pop     rbp
0x18003bba0  retn
```
