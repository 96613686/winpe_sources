# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ba4cc`
- end: `0x1800ba6c0`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b3c14`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x1800ba4cc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba554`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba692`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba554`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba692`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba5f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba677`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba5f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba677`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba631`

## string_xrefs

- `0x1800ba64a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ba536`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800ba5ce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800ba50e`: `ApplicationExtension\Data`
- `0x1800ba62a`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
         L"ApplicationExtension\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v8 = 365;
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
    v11 = 368;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 369;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"ApplicationExtension\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 371;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x1800ba4cc  push    rbp
0x1800ba4ce  push    rbx
0x1800ba4cf  push    rsi
0x1800ba4d0  push    rdi
0x1800ba4d1  push    r14
0x1800ba4d3  push    r15
0x1800ba4d5  lea     rbp, [rsp-168h]
0x1800ba4dd  sub     rsp, 268h
0x1800ba4e4  mov     rax, cs:__security_cookie
0x1800ba4eb  xor     rax, rsp
0x1800ba4ee  mov     [rbp+190h+var_40], rax
0x1800ba4f5  mov     r14, rdx
0x1800ba4f8  mov     rsi, r9
0x1800ba4fb  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba4fe  lea     r9, [rsp+290h+var_270]; bool *
0x1800ba503  mov     rdi, r8
0x1800ba506  lea     rcx, [rsp+290h+var_268]; this
0x1800ba50b  xor     r15d, r15d
0x1800ba50e  lea     r8, aApplicationext_0; "ApplicationExtension\\Data"
0x1800ba515  mov     [rsp+290h+var_268], r15
0x1800ba51a  mov     [rsp+290h+var_270], r15b; int
0x1800ba51f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800ba524  mov     ebx, eax
0x1800ba526  test    eax, eax
0x1800ba528  jns     short loc_1800BA567
0x1800ba52a  mov     edx, 16Ch; void *
0x1800ba52f  mov     rcx, [rbp+198h]; this
0x1800ba536  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba53d  mov     r9d, ebx; char *
0x1800ba540  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba545  mov     rcx, [rsp+290h+var_268]
0x1800ba54a  mov     [rsp+290h+var_268], r15
0x1800ba54f  test    rcx, rcx
0x1800ba552  jz      short loc_1800BA560
0x1800ba554  call    cs:__imp_SRCacheContext_Close
0x1800ba55b  nop     dword ptr [rax+rax+00h]
0x1800ba560  mov     eax, ebx
0x1800ba562  jmp     loc_1800BA6A0
0x1800ba567  cmp     [rsp+290h+var_270], r15b
0x1800ba56c  jnz     short loc_1800BA57A
0x1800ba56e  mov     ebx, 80670012h
0x1800ba573  mov     edx, 16Dh
0x1800ba578  jmp     short loc_1800BA52F
0x1800ba57a  xor     edx, edx; Val
0x1800ba57c  mov     [rsp+290h+var_260], r15
0x1800ba581  mov     r8d, 200h; Size
0x1800ba587  lea     rcx, [rsp+290h+var_258]; void *
0x1800ba58c  call    memset_0
0x1800ba591  lea     rax, [rsp+290h+var_258]
0x1800ba596  mov     [rbp+190h+var_58], r15
0x1800ba59d  mov     rdx, r14; __int64
0x1800ba5a0  mov     [rbp+190h+var_48], rax
0x1800ba5a7  lea     rcx, [rsp+290h+var_260]; this
0x1800ba5ac  mov     [rbp+190h+var_50], 100h
0x1800ba5b7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800ba5bc  mov     ebx, eax
0x1800ba5be  test    eax, eax
0x1800ba5c0  jns     short loc_1800BA601
0x1800ba5c2  mov     edx, 170h; void *
0x1800ba5c7  mov     rcx, [rbp+198h]; this
0x1800ba5ce  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba5d5  mov     r9d, ebx; char *
0x1800ba5d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba5dd  mov     rcx, [rsp+290h+var_260]
0x1800ba5e2  mov     [rsp+290h+var_260], r15
0x1800ba5e7  test    rcx, rcx
0x1800ba5ea  jz      loc_1800BA545
0x1800ba5f0  call    cs:__imp_SRCache_Free
0x1800ba5f7  nop     dword ptr [rax+rax+00h]
0x1800ba5fc  jmp     loc_1800BA545
0x1800ba601  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800ba608  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800ba60d  mov     r9, rsi; bool *
0x1800ba610  mov     rcx, rdi; this
0x1800ba613  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800ba618  mov     ebx, eax
0x1800ba61a  test    eax, eax
0x1800ba61c  jns     short loc_1800BA625
0x1800ba61e  mov     edx, 171h
0x1800ba623  jmp     short loc_1800BA5C7
0x1800ba625  mov     rcx, [rsp+290h+var_268]
0x1800ba62a  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800ba631  call    cs:__imp_SRCacheContext_AddToCache
0x1800ba638  nop     dword ptr [rax+rax+00h]
0x1800ba63d  mov     ebx, eax
0x1800ba63f  test    eax, eax
0x1800ba641  jns     short loc_1800BA668
0x1800ba643  mov     rcx, [rbp+198h]; this
0x1800ba64a  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba651  mov     r9d, eax; char *
0x1800ba654  mov     edx, 1A6h; void *
0x1800ba659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba65e  mov     edx, 173h
0x1800ba663  jmp     loc_1800BA5C7
0x1800ba668  mov     rcx, [rsp+290h+var_260]
0x1800ba66d  mov     [rsp+290h+var_260], r15
0x1800ba672  test    rcx, rcx
0x1800ba675  jz      short loc_1800BA683
0x1800ba677  call    cs:__imp_SRCache_Free
0x1800ba67e  nop     dword ptr [rax+rax+00h]
0x1800ba683  mov     rcx, [rsp+290h+var_268]
0x1800ba688  mov     [rsp+290h+var_268], r15
0x1800ba68d  test    rcx, rcx
0x1800ba690  jz      short loc_1800BA69E
0x1800ba692  call    cs:__imp_SRCacheContext_Close
0x1800ba699  nop     dword ptr [rax+rax+00h]
0x1800ba69e  xor     eax, eax
0x1800ba6a0  mov     rcx, [rbp+190h+var_40]
0x1800ba6a7  xor     rcx, rsp; StackCookie
0x1800ba6aa  call    __security_check_cookie
0x1800ba6af  add     rsp, 268h
0x1800ba6b6  pop     r15
0x1800ba6b8  pop     r14
0x1800ba6ba  pop     rdi
0x1800ba6bb  pop     rsi
0x1800ba6bc  pop     rbx
0x1800ba6bd  pop     rbp
0x1800ba6be  retn
```
