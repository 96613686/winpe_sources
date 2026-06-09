# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003eda0`
- end: `0x18003ef94`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003c294`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003eda0`
- `0x18003ef9c`
- `0x18003f4d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ee28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ef66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ee28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003ef66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003eec4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ef4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003eec4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ef4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003ef05`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003ef05`

## string_xrefs

- `0x18003ef1e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003ee0a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18003eea2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
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
         L"Application\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 433;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
    v8 = 434;
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
    v11 = 437;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 438;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Application\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 440;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
0x18003eda0  push    rbp
0x18003eda2  push    rbx
0x18003eda3  push    rsi
0x18003eda4  push    rdi
0x18003eda5  push    r14
0x18003eda7  push    r15
0x18003eda9  lea     rbp, [rsp-168h]
0x18003edb1  sub     rsp, 268h
0x18003edb8  mov     rax, cs:__security_cookie
0x18003edbf  xor     rax, rsp
0x18003edc2  mov     [rbp+190h+var_40], rax
0x18003edc9  mov     r14, rdx
0x18003edcc  mov     rsi, r9
0x18003edcf  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003edd2  lea     r9, [rsp+290h+var_270]; bool *
0x18003edd7  mov     rdi, r8
0x18003edda  lea     rcx, [rsp+290h+var_268]; this
0x18003eddf  xor     r15d, r15d
0x18003ede2  lea     r8, aApplicationDat; "Application\\Data"
0x18003ede9  mov     [rsp+290h+var_268], r15
0x18003edee  mov     [rsp+290h+var_270], r15b; int
0x18003edf3  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003edf8  mov     ebx, eax
0x18003edfa  test    eax, eax
0x18003edfc  jns     short loc_18003EE3B
0x18003edfe  mov     edx, 1B1h; void *
0x18003ee03  mov     rcx, [rbp+198h]; this
0x18003ee0a  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ee11  mov     r9d, ebx; char *
0x18003ee14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee19  mov     rcx, [rsp+290h+var_268]
0x18003ee1e  mov     [rsp+290h+var_268], r15
0x18003ee23  test    rcx, rcx
0x18003ee26  jz      short loc_18003EE34
0x18003ee28  call    cs:__imp_SRCacheContext_Close
0x18003ee2f  nop     dword ptr [rax+rax+00h]
0x18003ee34  mov     eax, ebx
0x18003ee36  jmp     loc_18003EF74
0x18003ee3b  cmp     [rsp+290h+var_270], r15b
0x18003ee40  jnz     short loc_18003EE4E
0x18003ee42  mov     ebx, 80670012h
0x18003ee47  mov     edx, 1B2h
0x18003ee4c  jmp     short loc_18003EE03
0x18003ee4e  xor     edx, edx; Val
0x18003ee50  mov     [rsp+290h+var_260], r15
0x18003ee55  mov     r8d, 200h; Size
0x18003ee5b  lea     rcx, [rsp+290h+var_258]; void *
0x18003ee60  call    memset_0
0x18003ee65  lea     rax, [rsp+290h+var_258]
0x18003ee6a  mov     [rbp+190h+var_58], r15
0x18003ee71  mov     rdx, r14; __int64
0x18003ee74  mov     [rbp+190h+var_48], rax
0x18003ee7b  lea     rcx, [rsp+290h+var_260]; this
0x18003ee80  mov     [rbp+190h+var_50], 100h
0x18003ee8b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003ee90  mov     ebx, eax
0x18003ee92  test    eax, eax
0x18003ee94  jns     short loc_18003EED5
0x18003ee96  mov     edx, 1B5h; void *
0x18003ee9b  mov     rcx, [rbp+198h]; this
0x18003eea2  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003eea9  mov     r9d, ebx; char *
0x18003eeac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eeb1  mov     rcx, [rsp+290h+var_260]
0x18003eeb6  mov     [rsp+290h+var_260], r15
0x18003eebb  test    rcx, rcx
0x18003eebe  jz      loc_18003EE19
0x18003eec4  call    cs:__imp_SRCache_Free
0x18003eecb  nop     dword ptr [rax+rax+00h]
0x18003eed0  jmp     loc_18003EE19
0x18003eed5  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003eedc  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003eee1  mov     r9, rsi; bool *
0x18003eee4  mov     rcx, rdi; this
0x18003eee7  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003eeec  mov     ebx, eax
0x18003eeee  test    eax, eax
0x18003eef0  jns     short loc_18003EEF9
0x18003eef2  mov     edx, 1B6h
0x18003eef7  jmp     short loc_18003EE9B
0x18003eef9  mov     rcx, [rsp+290h+var_268]
0x18003eefe  lea     rdx, aApplicationDat; "Application\\Data"
0x18003ef05  call    cs:__imp_SRCacheContext_AddToCache
0x18003ef0c  nop     dword ptr [rax+rax+00h]
0x18003ef11  mov     ebx, eax
0x18003ef13  test    eax, eax
0x18003ef15  jns     short loc_18003EF3C
0x18003ef17  mov     rcx, [rbp+198h]; this
0x18003ef1e  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003ef25  mov     r9d, eax; char *
0x18003ef28  mov     edx, 1A6h; void *
0x18003ef2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef32  mov     edx, 1B8h
0x18003ef37  jmp     loc_18003EE9B
0x18003ef3c  mov     rcx, [rsp+290h+var_260]
0x18003ef41  mov     [rsp+290h+var_260], r15
0x18003ef46  test    rcx, rcx
0x18003ef49  jz      short loc_18003EF57
0x18003ef4b  call    cs:__imp_SRCache_Free
0x18003ef52  nop     dword ptr [rax+rax+00h]
0x18003ef57  mov     rcx, [rsp+290h+var_268]
0x18003ef5c  mov     [rsp+290h+var_268], r15
0x18003ef61  test    rcx, rcx
0x18003ef64  jz      short loc_18003EF72
0x18003ef66  call    cs:__imp_SRCacheContext_Close
0x18003ef6d  nop     dword ptr [rax+rax+00h]
0x18003ef72  xor     eax, eax
0x18003ef74  mov     rcx, [rbp+190h+var_40]
0x18003ef7b  xor     rcx, rsp; StackCookie
0x18003ef7e  call    __security_check_cookie
0x18003ef83  add     rsp, 268h
0x18003ef8a  pop     r15
0x18003ef8c  pop     r14
0x18003ef8e  pop     rdi
0x18003ef8f  pop     rsi
0x18003ef90  pop     rbx
0x18003ef91  pop     rbp
0x18003ef92  retn
```
