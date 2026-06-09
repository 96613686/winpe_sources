# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800bbed0`
- end: `0x1800bc0c4`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b563c`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bbed0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bbf58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc096`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bbf58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc096`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bbff4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc07b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bbff4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc07b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc035`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc035`

## string_xrefs

- `0x1800bc04e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bbf3a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800bbfd2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
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
         L"Activation\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
    v8 = 392;
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
    v11 = 395;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 396;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Activation\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 398;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
0x1800bbed0  push    rbp
0x1800bbed2  push    rbx
0x1800bbed3  push    rsi
0x1800bbed4  push    rdi
0x1800bbed5  push    r14
0x1800bbed7  push    r15
0x1800bbed9  lea     rbp, [rsp-168h]
0x1800bbee1  sub     rsp, 268h
0x1800bbee8  mov     rax, cs:__security_cookie
0x1800bbeef  xor     rax, rsp
0x1800bbef2  mov     [rbp+190h+var_40], rax
0x1800bbef9  mov     r14, rdx
0x1800bbefc  mov     rsi, r9
0x1800bbeff  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800bbf02  lea     r9, [rsp+290h+var_270]; bool *
0x1800bbf07  mov     rdi, r8
0x1800bbf0a  lea     rcx, [rsp+290h+var_268]; this
0x1800bbf0f  xor     r15d, r15d
0x1800bbf12  lea     r8, aActivationData; "Activation\\Data"
0x1800bbf19  mov     [rsp+290h+var_268], r15
0x1800bbf1e  mov     [rsp+290h+var_270], r15b; int
0x1800bbf23  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bbf28  mov     ebx, eax
0x1800bbf2a  test    eax, eax
0x1800bbf2c  jns     short loc_1800BBF6B
0x1800bbf2e  mov     edx, 187h; void *
0x1800bbf33  mov     rcx, [rbp+198h]; this
0x1800bbf3a  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bbf41  mov     r9d, ebx; char *
0x1800bbf44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbf49  mov     rcx, [rsp+290h+var_268]
0x1800bbf4e  mov     [rsp+290h+var_268], r15
0x1800bbf53  test    rcx, rcx
0x1800bbf56  jz      short loc_1800BBF64
0x1800bbf58  call    cs:__imp_SRCacheContext_Close
0x1800bbf5f  nop     dword ptr [rax+rax+00h]
0x1800bbf64  mov     eax, ebx
0x1800bbf66  jmp     loc_1800BC0A4
0x1800bbf6b  cmp     [rsp+290h+var_270], r15b
0x1800bbf70  jnz     short loc_1800BBF7E
0x1800bbf72  mov     ebx, 80670012h
0x1800bbf77  mov     edx, 188h
0x1800bbf7c  jmp     short loc_1800BBF33
0x1800bbf7e  xor     edx, edx; Val
0x1800bbf80  mov     [rsp+290h+var_260], r15
0x1800bbf85  mov     r8d, 200h; Size
0x1800bbf8b  lea     rcx, [rsp+290h+var_258]; void *
0x1800bbf90  call    memset_0
0x1800bbf95  lea     rax, [rsp+290h+var_258]
0x1800bbf9a  mov     [rbp+190h+var_58], r15
0x1800bbfa1  mov     rdx, r14; __int64
0x1800bbfa4  mov     [rbp+190h+var_48], rax
0x1800bbfab  lea     rcx, [rsp+290h+var_260]; this
0x1800bbfb0  mov     [rbp+190h+var_50], 100h
0x1800bbfbb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bbfc0  mov     ebx, eax
0x1800bbfc2  test    eax, eax
0x1800bbfc4  jns     short loc_1800BC005
0x1800bbfc6  mov     edx, 18Bh; void *
0x1800bbfcb  mov     rcx, [rbp+198h]; this
0x1800bbfd2  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bbfd9  mov     r9d, ebx; char *
0x1800bbfdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbfe1  mov     rcx, [rsp+290h+var_260]
0x1800bbfe6  mov     [rsp+290h+var_260], r15
0x1800bbfeb  test    rcx, rcx
0x1800bbfee  jz      loc_1800BBF49
0x1800bbff4  call    cs:__imp_SRCache_Free
0x1800bbffb  nop     dword ptr [rax+rax+00h]
0x1800bc000  jmp     loc_1800BBF49
0x1800bc005  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bc00c  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bc011  mov     r9, rsi; bool *
0x1800bc014  mov     rcx, rdi; this
0x1800bc017  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bc01c  mov     ebx, eax
0x1800bc01e  test    eax, eax
0x1800bc020  jns     short loc_1800BC029
0x1800bc022  mov     edx, 18Ch
0x1800bc027  jmp     short loc_1800BBFCB
0x1800bc029  mov     rcx, [rsp+290h+var_268]
0x1800bc02e  lea     rdx, aActivationData; "Activation\\Data"
0x1800bc035  call    cs:__imp_SRCacheContext_AddToCache
0x1800bc03c  nop     dword ptr [rax+rax+00h]
0x1800bc041  mov     ebx, eax
0x1800bc043  test    eax, eax
0x1800bc045  jns     short loc_1800BC06C
0x1800bc047  mov     rcx, [rbp+198h]; this
0x1800bc04e  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc055  mov     r9d, eax; char *
0x1800bc058  mov     edx, 1A6h; void *
0x1800bc05d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc062  mov     edx, 18Eh
0x1800bc067  jmp     loc_1800BBFCB
0x1800bc06c  mov     rcx, [rsp+290h+var_260]
0x1800bc071  mov     [rsp+290h+var_260], r15
0x1800bc076  test    rcx, rcx
0x1800bc079  jz      short loc_1800BC087
0x1800bc07b  call    cs:__imp_SRCache_Free
0x1800bc082  nop     dword ptr [rax+rax+00h]
0x1800bc087  mov     rcx, [rsp+290h+var_268]
0x1800bc08c  mov     [rsp+290h+var_268], r15
0x1800bc091  test    rcx, rcx
0x1800bc094  jz      short loc_1800BC0A2
0x1800bc096  call    cs:__imp_SRCacheContext_Close
0x1800bc09d  nop     dword ptr [rax+rax+00h]
0x1800bc0a2  xor     eax, eax
0x1800bc0a4  mov     rcx, [rbp+190h+var_40]
0x1800bc0ab  xor     rcx, rsp; StackCookie
0x1800bc0ae  call    __security_check_cookie
0x1800bc0b3  add     rsp, 268h
0x1800bc0ba  pop     r15
0x1800bc0bc  pop     r14
0x1800bc0be  pop     rdi
0x1800bc0bf  pop     rsi
0x1800bc0c0  pop     rbx
0x1800bc0c1  pop     rbp
0x1800bc0c2  retn
```
