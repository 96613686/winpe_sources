# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800bc4c4`
- end: `0x1800bc6b8`
- name: `?Open@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b5a10`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b19c`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bc4c4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc54c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc68a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc54c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bc68a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc5e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc66f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc5e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bc66f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bc629`

## string_xrefs

- `0x1800bc642`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bc52e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800bc5c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(
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
         L"FileTypeAssociation\\Data",
         v16);
  if ( v7 < 0 )
  {
    v8 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
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
  v13 = SRCacheContext_AddToCache(v17, L"FileTypeAssociation\\Data");
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
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
0x1800bc4c4  push    rbp
0x1800bc4c6  push    rbx
0x1800bc4c7  push    rsi
0x1800bc4c8  push    rdi
0x1800bc4c9  push    r14
0x1800bc4cb  push    r15
0x1800bc4cd  lea     rbp, [rsp-168h]
0x1800bc4d5  sub     rsp, 268h
0x1800bc4dc  mov     rax, cs:__security_cookie
0x1800bc4e3  xor     rax, rsp
0x1800bc4e6  mov     [rbp+190h+var_40], rax
0x1800bc4ed  mov     r14, rdx
0x1800bc4f0  mov     rsi, r9
0x1800bc4f3  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800bc4f6  lea     r9, [rsp+290h+var_270]; bool *
0x1800bc4fb  mov     rdi, r8
0x1800bc4fe  lea     rcx, [rsp+290h+var_268]; this
0x1800bc503  xor     r15d, r15d
0x1800bc506  lea     r8, aFiletypeassoci_0; "FileTypeAssociation\\Data"
0x1800bc50d  mov     [rsp+290h+var_268], r15
0x1800bc512  mov     [rsp+290h+var_270], r15b; int
0x1800bc517  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bc51c  mov     ebx, eax
0x1800bc51e  test    eax, eax
0x1800bc520  jns     short loc_1800BC55F
0x1800bc522  mov     edx, 115h; void *
0x1800bc527  mov     rcx, [rbp+198h]; this
0x1800bc52e  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc535  mov     r9d, ebx; char *
0x1800bc538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc53d  mov     rcx, [rsp+290h+var_268]
0x1800bc542  mov     [rsp+290h+var_268], r15
0x1800bc547  test    rcx, rcx
0x1800bc54a  jz      short loc_1800BC558
0x1800bc54c  call    cs:__imp_SRCacheContext_Close
0x1800bc553  nop     dword ptr [rax+rax+00h]
0x1800bc558  mov     eax, ebx
0x1800bc55a  jmp     loc_1800BC698
0x1800bc55f  cmp     [rsp+290h+var_270], r15b
0x1800bc564  jnz     short loc_1800BC572
0x1800bc566  mov     ebx, 80670012h
0x1800bc56b  mov     edx, 116h
0x1800bc570  jmp     short loc_1800BC527
0x1800bc572  xor     edx, edx; Val
0x1800bc574  mov     [rsp+290h+var_260], r15
0x1800bc579  mov     r8d, 200h; Size
0x1800bc57f  lea     rcx, [rsp+290h+var_258]; void *
0x1800bc584  call    memset_0
0x1800bc589  lea     rax, [rsp+290h+var_258]
0x1800bc58e  mov     [rbp+190h+var_58], r15
0x1800bc595  mov     rdx, r14; __int64
0x1800bc598  mov     [rbp+190h+var_48], rax
0x1800bc59f  lea     rcx, [rsp+290h+var_260]; this
0x1800bc5a4  mov     [rbp+190h+var_50], 100h
0x1800bc5af  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800bc5b4  mov     ebx, eax
0x1800bc5b6  test    eax, eax
0x1800bc5b8  jns     short loc_1800BC5F9
0x1800bc5ba  mov     edx, 119h; void *
0x1800bc5bf  mov     rcx, [rbp+198h]; this
0x1800bc5c6  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc5cd  mov     r9d, ebx; char *
0x1800bc5d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc5d5  mov     rcx, [rsp+290h+var_260]
0x1800bc5da  mov     [rsp+290h+var_260], r15
0x1800bc5df  test    rcx, rcx
0x1800bc5e2  jz      loc_1800BC53D
0x1800bc5e8  call    cs:__imp_SRCache_Free
0x1800bc5ef  nop     dword ptr [rax+rax+00h]
0x1800bc5f4  jmp     loc_1800BC53D
0x1800bc5f9  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800bc600  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800bc605  mov     r9, rsi; bool *
0x1800bc608  mov     rcx, rdi; this
0x1800bc60b  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bc610  mov     ebx, eax
0x1800bc612  test    eax, eax
0x1800bc614  jns     short loc_1800BC61D
0x1800bc616  mov     edx, 11Ah
0x1800bc61b  jmp     short loc_1800BC5BF
0x1800bc61d  mov     rcx, [rsp+290h+var_268]
0x1800bc622  lea     rdx, aFiletypeassoci_0; "FileTypeAssociation\\Data"
0x1800bc629  call    cs:__imp_SRCacheContext_AddToCache
0x1800bc630  nop     dword ptr [rax+rax+00h]
0x1800bc635  mov     ebx, eax
0x1800bc637  test    eax, eax
0x1800bc639  jns     short loc_1800BC660
0x1800bc63b  mov     rcx, [rbp+198h]; this
0x1800bc642  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bc649  mov     r9d, eax; char *
0x1800bc64c  mov     edx, 1A6h; void *
0x1800bc651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc656  mov     edx, 11Ch
0x1800bc65b  jmp     loc_1800BC5BF
0x1800bc660  mov     rcx, [rsp+290h+var_260]
0x1800bc665  mov     [rsp+290h+var_260], r15
0x1800bc66a  test    rcx, rcx
0x1800bc66d  jz      short loc_1800BC67B
0x1800bc66f  call    cs:__imp_SRCache_Free
0x1800bc676  nop     dword ptr [rax+rax+00h]
0x1800bc67b  mov     rcx, [rsp+290h+var_268]
0x1800bc680  mov     [rsp+290h+var_268], r15
0x1800bc685  test    rcx, rcx
0x1800bc688  jz      short loc_1800BC696
0x1800bc68a  call    cs:__imp_SRCacheContext_Close
0x1800bc691  nop     dword ptr [rax+rax+00h]
0x1800bc696  xor     eax, eax
0x1800bc698  mov     rcx, [rbp+190h+var_40]
0x1800bc69f  xor     rcx, rsp; StackCookie
0x1800bc6a2  call    __security_check_cookie
0x1800bc6a7  add     rsp, 268h
0x1800bc6ae  pop     r15
0x1800bc6b0  pop     r14
0x1800bc6b2  pop     rdi
0x1800bc6b3  pop     rsi
0x1800bc6b4  pop     rbx
0x1800bc6b5  pop     rbp
0x1800bc6b6  retn
```
