# StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800bc0cc`
- end: `0x1800bc2c0`
- name: `?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b9520`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bc0cc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc154`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc292`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc154`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc292`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc1f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc277`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc1f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc277`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc231`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc231`

## string_xrefs

- `0x1800bc24a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bc136`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800bc1ce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800bc10e`: `AppExtension\Data`
- `0x1800bc22a`: `AppExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::Open(
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
         L"AppExtension\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
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
    v8 = 312;
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
    v11 = 315;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 316;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"AppExtension\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 318;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
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
0x1800bc0cc  push    rbp
0x1800bc0ce  push    rbx
0x1800bc0cf  push    rsi
0x1800bc0d0  push    rdi
0x1800bc0d1  push    r14
0x1800bc0d3  push    r15
0x1800bc0d5  lea     rbp, [rsp-168h]
0x1800bc0dd  sub     rsp, 268h
0x1800bc0e4  mov     rax, cs:__security_cookie
0x1800bc0eb  xor     rax, rsp
0x1800bc0ee  mov     [rbp+190h+var_40], rax
0x1800bc0f5  mov     r14, rdx
0x1800bc0f8  mov     rsi, r9
0x1800bc0fb  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800bc0fe  lea     r9, [rsp+290h+var_270]; bool *
0x1800bc103  mov     rdi, r8
0x1800bc106  lea     rcx, [rsp+290h+var_268]; this
0x1800bc10b  xor     r15d, r15d
0x1800bc10e  lea     r8, aAppextensionDa; "AppExtension\\Data"
0x1800bc115  mov     [rsp+290h+var_268], r15
0x1800bc11a  mov     [rsp+290h+var_270], r15b; int
0x1800bc11f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bc124  mov     ebx, eax
0x1800bc126  test    eax, eax
0x1800bc128  jns     short loc_1800BC167
0x1800bc12a  mov     edx, 137h; void *
0x1800bc12f  mov     rcx, [rbp+198h]; this
0x1800bc136  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc13d  mov     r9d, ebx; char *
0x1800bc140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc145  mov     rcx, [rsp+290h+var_268]
0x1800bc14a  mov     [rsp+290h+var_268], r15
0x1800bc14f  test    rcx, rcx
0x1800bc152  jz      short loc_1800BC160
0x1800bc154  call    cs:__imp_SRCacheContext_Close
0x1800bc15b  nop     dword ptr [rax+rax+00h]
0x1800bc160  mov     eax, ebx
0x1800bc162  jmp     loc_1800BC2A0
0x1800bc167  cmp     [rsp+290h+var_270], r15b
0x1800bc16c  jnz     short loc_1800BC17A
0x1800bc16e  mov     ebx, 80670012h
0x1800bc173  mov     edx, 138h
0x1800bc178  jmp     short loc_1800BC12F
0x1800bc17a  xor     edx, edx; Val
0x1800bc17c  mov     [rsp+290h+var_260], r15
0x1800bc181  mov     r8d, 200h; Size
0x1800bc187  lea     rcx, [rsp+290h+var_258]; void *
0x1800bc18c  call    memset_0
0x1800bc191  lea     rax, [rsp+290h+var_258]
0x1800bc196  mov     [rbp+190h+var_58], r15
0x1800bc19d  mov     rdx, r14; __int64
0x1800bc1a0  mov     [rbp+190h+var_48], rax
0x1800bc1a7  lea     rcx, [rsp+290h+var_260]; this
0x1800bc1ac  mov     [rbp+190h+var_50], 100h
0x1800bc1b7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bc1bc  mov     ebx, eax
0x1800bc1be  test    eax, eax
0x1800bc1c0  jns     short loc_1800BC201
0x1800bc1c2  mov     edx, 13Bh; void *
0x1800bc1c7  mov     rcx, [rbp+198h]; this
0x1800bc1ce  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc1d5  mov     r9d, ebx; char *
0x1800bc1d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc1dd  mov     rcx, [rsp+290h+var_260]
0x1800bc1e2  mov     [rsp+290h+var_260], r15
0x1800bc1e7  test    rcx, rcx
0x1800bc1ea  jz      loc_1800BC145
0x1800bc1f0  call    cs:__imp_SRCache_Free
0x1800bc1f7  nop     dword ptr [rax+rax+00h]
0x1800bc1fc  jmp     loc_1800BC145
0x1800bc201  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bc208  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bc20d  mov     r9, rsi; bool *
0x1800bc210  mov     rcx, rdi; this
0x1800bc213  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bc218  mov     ebx, eax
0x1800bc21a  test    eax, eax
0x1800bc21c  jns     short loc_1800BC225
0x1800bc21e  mov     edx, 13Ch
0x1800bc223  jmp     short loc_1800BC1C7
0x1800bc225  mov     rcx, [rsp+290h+var_268]
0x1800bc22a  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x1800bc231  call    cs:__imp_SRCacheContext_AddToCache
0x1800bc238  nop     dword ptr [rax+rax+00h]
0x1800bc23d  mov     ebx, eax
0x1800bc23f  test    eax, eax
0x1800bc241  jns     short loc_1800BC268
0x1800bc243  mov     rcx, [rbp+198h]; this
0x1800bc24a  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc251  mov     r9d, eax; char *
0x1800bc254  mov     edx, 1A6h; void *
0x1800bc259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc25e  mov     edx, 13Eh
0x1800bc263  jmp     loc_1800BC1C7
0x1800bc268  mov     rcx, [rsp+290h+var_260]
0x1800bc26d  mov     [rsp+290h+var_260], r15
0x1800bc272  test    rcx, rcx
0x1800bc275  jz      short loc_1800BC283
0x1800bc277  call    cs:__imp_SRCache_Free
0x1800bc27e  nop     dword ptr [rax+rax+00h]
0x1800bc283  mov     rcx, [rsp+290h+var_268]
0x1800bc288  mov     [rsp+290h+var_268], r15
0x1800bc28d  test    rcx, rcx
0x1800bc290  jz      short loc_1800BC29E
0x1800bc292  call    cs:__imp_SRCacheContext_Close
0x1800bc299  nop     dword ptr [rax+rax+00h]
0x1800bc29e  xor     eax, eax
0x1800bc2a0  mov     rcx, [rbp+190h+var_40]
0x1800bc2a7  xor     rcx, rsp; StackCookie
0x1800bc2aa  call    __security_check_cookie
0x1800bc2af  add     rsp, 268h
0x1800bc2b6  pop     r15
0x1800bc2b8  pop     r14
0x1800bc2ba  pop     rdi
0x1800bc2bb  pop     rsi
0x1800bc2bc  pop     rbx
0x1800bc2bd  pop     rbp
0x1800bc2be  retn
```
