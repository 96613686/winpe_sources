# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ba6c8`
- end: `0x1800ba8bc`
- name: `?Open@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b3e08`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180039534`
- `0x18003d264`
- `0x18003d794`
- `0x1800ba6c8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba750`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba88e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba750`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ba88e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba7ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba873`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba7ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba873`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba82d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ba82d`

## string_xrefs

- `0x1800ba846`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ba732`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800ba7ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

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
0x1800ba6c8  push    rbp
0x1800ba6ca  push    rbx
0x1800ba6cb  push    rsi
0x1800ba6cc  push    rdi
0x1800ba6cd  push    r14
0x1800ba6cf  push    r15
0x1800ba6d1  lea     rbp, [rsp-168h]
0x1800ba6d9  sub     rsp, 268h
0x1800ba6e0  mov     rax, cs:__security_cookie
0x1800ba6e7  xor     rax, rsp
0x1800ba6ea  mov     [rbp+190h+var_40], rax
0x1800ba6f1  mov     r14, rdx
0x1800ba6f4  mov     rsi, r9
0x1800ba6f7  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba6fa  lea     r9, [rsp+290h+var_270]; bool *
0x1800ba6ff  mov     rdi, r8
0x1800ba702  lea     rcx, [rsp+290h+var_268]; this
0x1800ba707  xor     r15d, r15d
0x1800ba70a  lea     r8, aFiletypeassoci_0; "FileTypeAssociation\\Data"
0x1800ba711  mov     [rsp+290h+var_268], r15
0x1800ba716  mov     [rsp+290h+var_270], r15b; int
0x1800ba71b  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800ba720  mov     ebx, eax
0x1800ba722  test    eax, eax
0x1800ba724  jns     short loc_1800BA763
0x1800ba726  mov     edx, 115h; void *
0x1800ba72b  mov     rcx, [rbp+198h]; this
0x1800ba732  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba739  mov     r9d, ebx; char *
0x1800ba73c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba741  mov     rcx, [rsp+290h+var_268]
0x1800ba746  mov     [rsp+290h+var_268], r15
0x1800ba74b  test    rcx, rcx
0x1800ba74e  jz      short loc_1800BA75C
0x1800ba750  call    cs:__imp_SRCacheContext_Close
0x1800ba757  nop     dword ptr [rax+rax+00h]
0x1800ba75c  mov     eax, ebx
0x1800ba75e  jmp     loc_1800BA89C
0x1800ba763  cmp     [rsp+290h+var_270], r15b
0x1800ba768  jnz     short loc_1800BA776
0x1800ba76a  mov     ebx, 80670012h
0x1800ba76f  mov     edx, 116h
0x1800ba774  jmp     short loc_1800BA72B
0x1800ba776  xor     edx, edx; Val
0x1800ba778  mov     [rsp+290h+var_260], r15
0x1800ba77d  mov     r8d, 200h; Size
0x1800ba783  lea     rcx, [rsp+290h+var_258]; void *
0x1800ba788  call    memset_0
0x1800ba78d  lea     rax, [rsp+290h+var_258]
0x1800ba792  mov     [rbp+190h+var_58], r15
0x1800ba799  mov     rdx, r14; __int64
0x1800ba79c  mov     [rbp+190h+var_48], rax
0x1800ba7a3  lea     rcx, [rsp+290h+var_260]; this
0x1800ba7a8  mov     [rbp+190h+var_50], 100h
0x1800ba7b3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x1800ba7b8  mov     ebx, eax
0x1800ba7ba  test    eax, eax
0x1800ba7bc  jns     short loc_1800BA7FD
0x1800ba7be  mov     edx, 119h; void *
0x1800ba7c3  mov     rcx, [rbp+198h]; this
0x1800ba7ca  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba7d1  mov     r9d, ebx; char *
0x1800ba7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba7d9  mov     rcx, [rsp+290h+var_260]
0x1800ba7de  mov     [rsp+290h+var_260], r15
0x1800ba7e3  test    rcx, rcx
0x1800ba7e6  jz      loc_1800BA741
0x1800ba7ec  call    cs:__imp_SRCache_Free
0x1800ba7f3  nop     dword ptr [rax+rax+00h]
0x1800ba7f8  jmp     loc_1800BA741
0x1800ba7fd  mov     r8, [rbp+190h+var_48]; unsigned __int16 *
0x1800ba804  lea     rdx, [rsp+290h+var_268]; struct StateRepository::Cache::Context_NoThrow *
0x1800ba809  mov     r9, rsi; bool *
0x1800ba80c  mov     rcx, rdi; this
0x1800ba80f  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800ba814  mov     ebx, eax
0x1800ba816  test    eax, eax
0x1800ba818  jns     short loc_1800BA821
0x1800ba81a  mov     edx, 11Ah
0x1800ba81f  jmp     short loc_1800BA7C3
0x1800ba821  mov     rcx, [rsp+290h+var_268]
0x1800ba826  lea     rdx, aFiletypeassoci_0; "FileTypeAssociation\\Data"
0x1800ba82d  call    cs:__imp_SRCacheContext_AddToCache
0x1800ba834  nop     dword ptr [rax+rax+00h]
0x1800ba839  mov     ebx, eax
0x1800ba83b  test    eax, eax
0x1800ba83d  jns     short loc_1800BA864
0x1800ba83f  mov     rcx, [rbp+198h]; this
0x1800ba846  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba84d  mov     r9d, eax; char *
0x1800ba850  mov     edx, 1A6h; void *
0x1800ba855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba85a  mov     edx, 11Ch
0x1800ba85f  jmp     loc_1800BA7C3
0x1800ba864  mov     rcx, [rsp+290h+var_260]
0x1800ba869  mov     [rsp+290h+var_260], r15
0x1800ba86e  test    rcx, rcx
0x1800ba871  jz      short loc_1800BA87F
0x1800ba873  call    cs:__imp_SRCache_Free
0x1800ba87a  nop     dword ptr [rax+rax+00h]
0x1800ba87f  mov     rcx, [rsp+290h+var_268]
0x1800ba884  mov     [rsp+290h+var_268], r15
0x1800ba889  test    rcx, rcx
0x1800ba88c  jz      short loc_1800BA89A
0x1800ba88e  call    cs:__imp_SRCacheContext_Close
0x1800ba895  nop     dword ptr [rax+rax+00h]
0x1800ba89a  xor     eax, eax
0x1800ba89c  mov     rcx, [rbp+190h+var_40]
0x1800ba8a3  xor     rcx, rsp; StackCookie
0x1800ba8a6  call    __security_check_cookie
0x1800ba8ab  add     rsp, 268h
0x1800ba8b2  pop     r15
0x1800ba8b4  pop     r14
0x1800ba8b6  pop     rdi
0x1800ba8b7  pop     rsi
0x1800ba8b8  pop     rbx
0x1800ba8b9  pop     rbp
0x1800ba8ba  retn
```
