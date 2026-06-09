# StateRepository::Cache::Entity::Protocol_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800bc6c0`
- end: `0x1800bc8b4`
- name: `?Open@Protocol_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b5d58`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bc6c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc748`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc886`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc748`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc886`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc7e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc86b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc7e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc86b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc825`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc825`

## string_xrefs

- `0x1800bc83e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bc72a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bc7c2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800bc702`: `Protocol\Data`
- `0x1800bc81e`: `Protocol\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::Open(
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
         L"Protocol\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
    v8 = 278;
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
    v11 = 281;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         v22,
         a4);
  if ( v7 < 0 )
  {
    v11 = 282;
    goto LABEL_11;
  }
  v13 = SRCacheContext_AddToCache(v17, L"Protocol\\Data");
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      *(int *)v16);
    v11 = 284;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
0x1800bc6c0  push    rbp
0x1800bc6c2  push    rbx
0x1800bc6c3  push    rsi
0x1800bc6c4  push    rdi
0x1800bc6c5  push    r14
0x1800bc6c7  push    r15
0x1800bc6c9  lea     rbp, [rsp-168h]
0x1800bc6d1  sub     rsp, 268h
0x1800bc6d8  mov     rax, cs:__security_cookie
0x1800bc6df  xor     rax, rsp
0x1800bc6e2  mov     [rbp+190h+var_40], rax
0x1800bc6e9  mov     r14, rdx
0x1800bc6ec  mov     rsi, r9
0x1800bc6ef  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800bc6f2  lea     r9, [rsp+290h+var_270]; bool *
0x1800bc6f7  mov     rdi, r8
0x1800bc6fa  lea     rcx, [rsp+290h+var_268]; this
0x1800bc6ff  xor     r15d, r15d
0x1800bc702  lea     r8, aProtocolData; "Protocol\\Data"
0x1800bc709  mov     [rsp+290h+var_268], r15
0x1800bc70e  mov     [rsp+290h+var_270], r15b; int
0x1800bc713  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bc718  mov     ebx, eax
0x1800bc71a  test    eax, eax
0x1800bc71c  jns     short loc_1800BC75B
0x1800bc71e  mov     edx, 115h; void *
0x1800bc723  mov     rcx, [rbp+198h]; this
0x1800bc72a  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc731  mov     r9d, ebx; char *
0x1800bc734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc739  mov     rcx, [rsp+290h+var_268]
0x1800bc73e  mov     [rsp+290h+var_268], r15
0x1800bc743  test    rcx, rcx
0x1800bc746  jz      short loc_1800BC754
0x1800bc748  call    cs:__imp_SRCacheContext_Close
0x1800bc74f  nop     dword ptr [rax+rax+00h]
0x1800bc754  mov     eax, ebx
0x1800bc756  jmp     loc_1800BC894
0x1800bc75b  cmp     [rsp+290h+var_270], r15b
0x1800bc760  jnz     short loc_1800BC76E
0x1800bc762  mov     ebx, 80670012h
0x1800bc767  mov     edx, 116h
0x1800bc76c  jmp     short loc_1800BC723
0x1800bc76e  xor     edx, edx; Val
0x1800bc770  mov     [rsp+290h+var_260], r15
0x1800bc775  mov     r8d, 200h; Size
0x1800bc77b  lea     rcx, [rsp+290h+var_258]; void *
0x1800bc780  call    memset_0
0x1800bc785  lea     rax, [rsp+290h+var_258]
0x1800bc78a  mov     [rbp+190h+var_58], r15
0x1800bc791  mov     rdx, r14; __int64
0x1800bc794  mov     [rbp+190h+var_48], rax
0x1800bc79b  lea     rcx, [rsp+290h+var_260]; this
0x1800bc7a0  mov     [rbp+190h+var_50], 100h
0x1800bc7ab  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bc7b0  mov     ebx, eax
0x1800bc7b2  test    eax, eax
0x1800bc7b4  jns     short loc_1800BC7F5
0x1800bc7b6  mov     edx, 119h; void *
0x1800bc7bb  mov     rcx, [rbp+198h]; this
0x1800bc7c2  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc7c9  mov     r9d, ebx; char *
0x1800bc7cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc7d1  mov     rcx, [rsp+290h+var_260]
0x1800bc7d6  mov     [rsp+290h+var_260], r15
0x1800bc7db  test    rcx, rcx
0x1800bc7de  jz      loc_1800BC739
0x1800bc7e4  call    cs:__imp_SRCache_Free
0x1800bc7eb  nop     dword ptr [rax+rax+00h]
0x1800bc7f0  jmp     loc_1800BC739
0x1800bc7f5  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bc7fc  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bc801  mov     r9, rsi; bool *
0x1800bc804  mov     rcx, rdi; this
0x1800bc807  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bc80c  mov     ebx, eax
0x1800bc80e  test    eax, eax
0x1800bc810  jns     short loc_1800BC819
0x1800bc812  mov     edx, 11Ah
0x1800bc817  jmp     short loc_1800BC7BB
0x1800bc819  mov     rcx, [rsp+290h+var_268]
0x1800bc81e  lea     rdx, aProtocolData; "Protocol\\Data"
0x1800bc825  call    cs:__imp_SRCacheContext_AddToCache
0x1800bc82c  nop     dword ptr [rax+rax+00h]
0x1800bc831  mov     ebx, eax
0x1800bc833  test    eax, eax
0x1800bc835  jns     short loc_1800BC85C
0x1800bc837  mov     rcx, [rbp+198h]; this
0x1800bc83e  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc845  mov     r9d, eax; char *
0x1800bc848  mov     edx, 1A6h; void *
0x1800bc84d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc852  mov     edx, 11Ch
0x1800bc857  jmp     loc_1800BC7BB
0x1800bc85c  mov     rcx, [rsp+290h+var_260]
0x1800bc861  mov     [rsp+290h+var_260], r15
0x1800bc866  test    rcx, rcx
0x1800bc869  jz      short loc_1800BC877
0x1800bc86b  call    cs:__imp_SRCache_Free
0x1800bc872  nop     dword ptr [rax+rax+00h]
0x1800bc877  mov     rcx, [rsp+290h+var_268]
0x1800bc87c  mov     [rsp+290h+var_268], r15
0x1800bc881  test    rcx, rcx
0x1800bc884  jz      short loc_1800BC892
0x1800bc886  call    cs:__imp_SRCacheContext_Close
0x1800bc88d  nop     dword ptr [rax+rax+00h]
0x1800bc892  xor     eax, eax
0x1800bc894  mov     rcx, [rbp+190h+var_40]
0x1800bc89b  xor     rcx, rsp; StackCookie
0x1800bc89e  call    __security_check_cookie
0x1800bc8a3  add     rsp, 268h
0x1800bc8aa  pop     r15
0x1800bc8ac  pop     r14
0x1800bc8ae  pop     rdi
0x1800bc8af  pop     rsi
0x1800bc8b0  pop     rbx
0x1800bc8b1  pop     rbp
0x1800bc8b2  retn
```
