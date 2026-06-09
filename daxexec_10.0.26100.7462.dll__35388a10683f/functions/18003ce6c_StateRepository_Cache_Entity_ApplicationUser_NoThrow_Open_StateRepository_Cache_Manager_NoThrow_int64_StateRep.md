# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003ce6c`
- end: `0x18003d060`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003b0d4`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003ce6c`
- `0x18003d264`
- `0x18003d794`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cef4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d032`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003cef4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d032`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003cf90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d017`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003cf90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d017`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003cfd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003cfd1`

## string_xrefs

- `0x18003cfea`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003ced6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18003cf6e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

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
0x18003ce6c  push    rbp
0x18003ce6e  push    rbx
0x18003ce6f  push    rsi
0x18003ce70  push    rdi
0x18003ce71  push    r14
0x18003ce73  push    r15
0x18003ce75  lea     rbp, [rsp-168h]
0x18003ce7d  sub     rsp, 268h
0x18003ce84  mov     rax, cs:__security_cookie
0x18003ce8b  xor     rax, rsp
0x18003ce8e  mov     [rbp+190h+var_40], rax
0x18003ce95  mov     r14, rdx
0x18003ce98  mov     rsi, r9
0x18003ce9b  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18003ce9e  lea     r9, [rsp+290h+var_270]; bool *
0x18003cea3  mov     rdi, r8
0x18003cea6  lea     rcx, [rsp+290h+var_268]; this
0x18003ceab  xor     r15d, r15d
0x18003ceae  lea     r8, aApplicationuse; "ApplicationUser\\Data"
0x18003ceb5  mov     [rsp+290h+var_268], r15
0x18003ceba  mov     [rsp+290h+var_270], r15b; int
0x18003cebf  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003cec4  mov     ebx, eax
0x18003cec6  test    eax, eax
0x18003cec8  jns     short loc_18003CF07
0x18003ceca  mov     edx, 1F9h; void *
0x18003cecf  mov     rcx, [rbp+198h]; this
0x18003ced6  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cedd  mov     r9d, ebx; char *
0x18003cee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cee5  mov     rcx, [rsp+290h+var_268]
0x18003ceea  mov     [rsp+290h+var_268], r15
0x18003ceef  test    rcx, rcx
0x18003cef2  jz      short loc_18003CF00
0x18003cef4  call    cs:__imp_SRCacheContext_Close
0x18003cefb  nop     dword ptr [rax+rax+00h]
0x18003cf00  mov     eax, ebx
0x18003cf02  jmp     loc_18003D040
0x18003cf07  cmp     [rsp+290h+var_270], r15b
0x18003cf0c  jnz     short loc_18003CF1A
0x18003cf0e  mov     ebx, 80670012h
0x18003cf13  mov     edx, 1FAh
0x18003cf18  jmp     short loc_18003CECF
0x18003cf1a  xor     edx, edx; Val
0x18003cf1c  mov     [rsp+290h+var_260], r15
0x18003cf21  mov     r8d, 200h; Size
0x18003cf27  lea     rcx, [rsp+290h+var_258]; void *
0x18003cf2c  call    memset_0
0x18003cf31  lea     rax, [rsp+290h+var_258]
0x18003cf36  mov     [rbp+190h+var_58], r15
0x18003cf3d  mov     rdx, r14; __int64
0x18003cf40  mov     [rbp+190h+var_48], rax
0x18003cf47  lea     rcx, [rsp+290h+var_260]; this
0x18003cf4c  mov     [rbp+190h+var_50], 100h
0x18003cf57  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18003cf5c  mov     ebx, eax
0x18003cf5e  test    eax, eax
0x18003cf60  jns     short loc_18003CFA1
0x18003cf62  mov     edx, 1FDh; void *
0x18003cf67  mov     rcx, [rbp+198h]; this
0x18003cf6e  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cf75  mov     r9d, ebx; char *
0x18003cf78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf7d  mov     rcx, [rsp+290h+var_260]
0x18003cf82  mov     [rsp+290h+var_260], r15
0x18003cf87  test    rcx, rcx
0x18003cf8a  jz      loc_18003CEE5
0x18003cf90  call    cs:__imp_SRCache_Free
0x18003cf97  nop     dword ptr [rax+rax+00h]
0x18003cf9c  jmp     loc_18003CEE5
0x18003cfa1  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x18003cfa8  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x18003cfad  mov     r9, rsi; bool *
0x18003cfb0  mov     rcx, rdi; this
0x18003cfb3  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18003cfb8  mov     ebx, eax
0x18003cfba  test    eax, eax
0x18003cfbc  jns     short loc_18003CFC5
0x18003cfbe  mov     edx, 1FEh
0x18003cfc3  jmp     short loc_18003CF67
0x18003cfc5  mov     rcx, [rsp+290h+var_268]
0x18003cfca  lea     rdx, aApplicationuse; "ApplicationUser\\Data"
0x18003cfd1  call    cs:__imp_SRCacheContext_AddToCache
0x18003cfd8  nop     dword ptr [rax+rax+00h]
0x18003cfdd  mov     ebx, eax
0x18003cfdf  test    eax, eax
0x18003cfe1  jns     short loc_18003D008
0x18003cfe3  mov     rcx, [rbp+198h]; this
0x18003cfea  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003cff1  mov     r9d, eax; char *
0x18003cff4  mov     edx, 1A6h; void *
0x18003cff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cffe  mov     edx, 200h
0x18003d003  jmp     loc_18003CF67
0x18003d008  mov     rcx, [rsp+290h+var_260]
0x18003d00d  mov     [rsp+290h+var_260], r15
0x18003d012  test    rcx, rcx
0x18003d015  jz      short loc_18003D023
0x18003d017  call    cs:__imp_SRCache_Free
0x18003d01e  nop     dword ptr [rax+rax+00h]
0x18003d023  mov     rcx, [rsp+290h+var_268]
0x18003d028  mov     [rsp+290h+var_268], r15
0x18003d02d  test    rcx, rcx
0x18003d030  jz      short loc_18003D03E
0x18003d032  call    cs:__imp_SRCacheContext_Close
0x18003d039  nop     dword ptr [rax+rax+00h]
0x18003d03e  xor     eax, eax
0x18003d040  mov     rcx, [rbp+190h+var_40]
0x18003d047  xor     rcx, rsp; StackCookie
0x18003d04a  call    __security_check_cookie
0x18003d04f  add     rsp, 268h
0x18003d056  pop     r15
0x18003d058  pop     r14
0x18003d05a  pop     rdi
0x18003d05b  pop     rsi
0x18003d05c  pop     rbx
0x18003d05d  pop     rbp
0x18003d05e  retn
```
