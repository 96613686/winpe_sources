# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003eba4`
- end: `0x18003ed98`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003cccc`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003eba4`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ec2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ed6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ec2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ed6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ecc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ed4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ecc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ed4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003ed09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003ed09`

## string_xrefs

- `0x18003ed22`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003ec0e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003eca6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *this,
        bool *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  bool v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+238h] [rbp+138h]
  __int64 v21; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v22; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v17 = 0;
  v16[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         a1,
         L"ApplicationUser\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 505;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v16);
LABEL_4:
    v9 = v17;
    v17 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v7;
  }
  if ( !v16[0] )
  {
    v7 = -2140733422;
    v8 = 506;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v22 = (unsigned __int16 *)v19;
  v21 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, a2);
  if ( v7 < 0 )
  {
    v11 = 509;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 510;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"ApplicationUser\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 512;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v16);
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v18;
  v18 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = v17;
  v17 = 0;
  if ( v15 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18003eba4  push    rbp
0x18003eba6  push    rbx
0x18003eba7  push    rsi
0x18003eba8  push    rdi
0x18003eba9  push    r14
0x18003ebab  push    r15
0x18003ebad  lea     rbp, [rsp-168h]
0x18003ebb5  sub     rsp, 268h
0x18003ebbc  mov     rax, cs:__security_cookie
0x18003ebc3  xor     rax, rsp
0x18003ebc6  mov     [rbp+190h+var_40], rax
0x18003ebcd  mov     r14, rdx
0x18003ebd0  mov     rsi, r9
0x18003ebd3  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003ebd6  lea     r9, [rsp+290h+var_270]; bool *
0x18003ebdb  mov     rdi, r8
0x18003ebde  lea     rcx, [rsp+290h+var_268]; this
0x18003ebe3  xor     r15d, r15d
0x18003ebe6  lea     r8, aApplicationuse; "ApplicationUser\\Data"
0x18003ebed  mov     [rsp+290h+var_268], r15
0x18003ebf2  mov     [rsp+290h+var_270], r15b; int
0x18003ebf7  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003ebfc  mov     ebx, eax
0x18003ebfe  test    eax, eax
0x18003ec00  jns     short loc_18003EC3F
0x18003ec02  mov     edx, 1F9h; void *
0x18003ec07  mov     rcx, [rbp+198h]; this
0x18003ec0e  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ec15  mov     r9d, ebx; char *
0x18003ec18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ec1d  mov     rcx, [rsp+290h+var_268]
0x18003ec22  mov     [rsp+290h+var_268], r15
0x18003ec27  test    rcx, rcx
0x18003ec2a  jz      short loc_18003EC38
0x18003ec2c  call    cs:__imp_SRCacheContext_Close
0x18003ec33  nop     dword ptr [rax+rax+00h]
0x18003ec38  mov     eax, ebx
0x18003ec3a  jmp     loc_18003ED78
0x18003ec3f  cmp     [rsp+290h+var_270], r15b
0x18003ec44  jnz     short loc_18003EC52
0x18003ec46  mov     ebx, 80670012h
0x18003ec4b  mov     edx, 1FAh
0x18003ec50  jmp     short loc_18003EC07
0x18003ec52  xor     edx, edx; Val
0x18003ec54  mov     [rsp+290h+var_260], r15
0x18003ec59  mov     r8d, 200h; Size
0x18003ec5f  lea     rcx, [rsp+290h+var_258]; void *
0x18003ec64  call    memset_0
0x18003ec69  lea     rax, [rsp+290h+var_258]
0x18003ec6e  mov     [rbp+190h+var_58], r15
0x18003ec75  mov     rdx, r14; __int64
0x18003ec78  mov     [rbp+190h+var_48], rax
0x18003ec7f  lea     rcx, [rsp+290h+var_260]; this
0x18003ec84  mov     [rbp+190h+var_50], 100h
0x18003ec8f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003ec94  mov     ebx, eax
0x18003ec96  test    eax, eax
0x18003ec98  jns     short loc_18003ECD9
0x18003ec9a  mov     edx, 1FDh; void *
0x18003ec9f  mov     rcx, [rbp+198h]; this
0x18003eca6  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ecad  mov     r9d, ebx; char *
0x18003ecb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ecb5  mov     rcx, [rsp+290h+var_260]
0x18003ecba  mov     [rsp+290h+var_260], r15
0x18003ecbf  test    rcx, rcx
0x18003ecc2  jz      loc_18003EC1D
0x18003ecc8  call    cs:__imp_SRCache_Free
0x18003eccf  nop     dword ptr [rax+rax+00h]
0x18003ecd4  jmp     loc_18003EC1D
0x18003ecd9  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003ece0  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003ece5  mov     r9, rsi; bool *
0x18003ece8  mov     rcx, rdi; this
0x18003eceb  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003ecf0  mov     ebx, eax
0x18003ecf2  test    eax, eax
0x18003ecf4  jns     short loc_18003ECFD
0x18003ecf6  mov     edx, 1FEh
0x18003ecfb  jmp     short loc_18003EC9F
0x18003ecfd  mov     rcx, [rsp+290h+var_268]
0x18003ed02  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x18003ed09  call    cs:__imp_SRCacheContext_AddToCache
0x18003ed10  nop     dword ptr [rax+rax+00h]
0x18003ed15  mov     ebx, eax
0x18003ed17  test    eax, eax
0x18003ed19  jns     short loc_18003ED40
0x18003ed1b  mov     rcx, [rbp+198h]; this
0x18003ed22  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ed29  mov     r9d, eax; char *
0x18003ed2c  mov     edx, 1A6h; void *
0x18003ed31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ed36  mov     edx, 200h
0x18003ed3b  jmp     loc_18003EC9F
0x18003ed40  mov     rcx, [rsp+290h+var_260]
0x18003ed45  mov     [rsp+290h+var_260], r15
0x18003ed4a  test    rcx, rcx
0x18003ed4d  jz      short loc_18003ED5B
0x18003ed4f  call    cs:__imp_SRCache_Free
0x18003ed56  nop     dword ptr [rax+rax+00h]
0x18003ed5b  mov     rcx, [rsp+290h+var_268]
0x18003ed60  mov     [rsp+290h+var_268], r15
0x18003ed65  test    rcx, rcx
0x18003ed68  jz      short loc_18003ED76
0x18003ed6a  call    cs:__imp_SRCacheContext_Close
0x18003ed71  nop     dword ptr [rax+rax+00h]
0x18003ed76  xor     eax, eax
0x18003ed78  mov     rcx, [rbp+190h+var_40]
0x18003ed7f  xor     rcx, rsp; StackCookie
0x18003ed82  call    __security_check_cookie
0x18003ed87  add     rsp, 268h
0x18003ed8e  pop     r15
0x18003ed90  pop     r14
0x18003ed92  pop     rdi
0x18003ed93  pop     rsi
0x18003ed94  pop     rbx
0x18003ed95  pop     rbp
0x18003ed96  retn
```
