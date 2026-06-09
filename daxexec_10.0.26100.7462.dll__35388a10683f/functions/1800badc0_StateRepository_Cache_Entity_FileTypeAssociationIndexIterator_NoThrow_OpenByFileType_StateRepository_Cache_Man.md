# StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByFileType(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800badc0`
- end: `0x1800bb05a`
- name: `?OpenByFileType@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `666`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b52fc`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x1800393c0`
- `0x18003d264`
- `0x18003d794`
- `0x1800badc0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bae03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bae6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800baeb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb025`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bae03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bae6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800baeb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bb025`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800baf3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bafea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb00a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800baf3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bafea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bb00a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800baf8f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800baf8f`

## string_xrefs

- `0x1800bafa8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bae47`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800bae8b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800baf1a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800bafc3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByFileType(
        StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  int v7; // eax
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  bool v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+238h] [rbp+138h]
  __int64 v24; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v25; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v20 = 0;
  v19[0] = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v20,
         a2,
         L"FileTypeAssociation\\Index\\FileType",
         v19);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v7,
      *(int *)v19);
LABEL_5:
    v9 = v20;
    v20 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v8;
  }
  if ( !v19[0] )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)0x80670012LL,
      *(int *)v19);
LABEL_10:
    v12 = v20;
    v20 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return v11;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = (unsigned __int16 *)v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a3);
  if ( v8 < 0 )
  {
    v13 = 613;
    goto LABEL_15;
  }
  v19[0] = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         this,
         (struct StateRepository::Cache::Context_NoThrow *)&v20,
         v25,
         v19);
  if ( v8 < 0 )
  {
    v13 = 616;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v8,
      *(int *)v19);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_5;
  }
  if ( v19[0] )
    *((_QWORD *)this + 2) = a2;
  v15 = SRCacheContext_AddToCache(v20, L"FileTypeAssociation\\Index\\FileType");
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      *(int *)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)v11,
      *(int *)v19);
    v16 = v21;
    v21 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_10;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = v20;
  v20 = 0;
  if ( v18 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1800badc0  mov     [rsp-8+arg_18], rbx
0x1800badc5  push    rbp
0x1800badc6  push    rsi
0x1800badc7  push    rdi
0x1800badc8  push    r14
0x1800badca  push    r15
0x1800badcc  lea     rbp, [rsp-160h]
0x1800badd4  sub     rsp, 260h
0x1800baddb  mov     rax, cs:__security_cookie
0x1800bade2  xor     rax, rsp
0x1800bade5  mov     [rbp+180h+var_30], rax
0x1800badec  mov     rbx, rcx
0x1800badef  xor     r15d, r15d
0x1800badf2  mov     rcx, [rcx]
0x1800badf5  mov     r14, r8
0x1800badf8  mov     rsi, rdx
0x1800badfb  mov     [rbx], r15
0x1800badfe  test    rcx, rcx
0x1800bae01  jz      short loc_1800BAE0F
0x1800bae03  call    cs:__imp_SRCacheContext_Close
0x1800bae0a  nop     dword ptr [rax+rax+00h]
0x1800bae0f  lea     r9, [rsp+280h+var_260]; bool *
0x1800bae14  mov     [rbx+8], r15d
0x1800bae18  lea     r8, aFiletypeassoci_1; "FileTypeAssociation\\Index\\FileType"
0x1800bae1f  mov     [rbx+10h], r15
0x1800bae23  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800bae26  mov     [rsp+280h+var_258], r15
0x1800bae2b  lea     rcx, [rsp+280h+var_258]; this
0x1800bae30  mov     [rsp+280h+var_260], r15b; int
0x1800bae35  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bae3a  mov     edi, eax
0x1800bae3c  test    eax, eax
0x1800bae3e  jns     short loc_1800BAE7D
0x1800bae40  mov     rcx, [rbp+188h]; this
0x1800bae47  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bae4e  mov     r9d, eax; char *
0x1800bae51  mov     edx, 261h; void *
0x1800bae56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bae5b  mov     rcx, [rsp+280h+var_258]
0x1800bae60  mov     [rsp+280h+var_258], r15
0x1800bae65  test    rcx, rcx
0x1800bae68  jz      short loc_1800BAE76
0x1800bae6a  call    cs:__imp_SRCacheContext_Close
0x1800bae71  nop     dword ptr [rax+rax+00h]
0x1800bae76  mov     eax, edi
0x1800bae78  jmp     loc_1800BB033
0x1800bae7d  cmp     [rsp+280h+var_260], r15b
0x1800bae82  jnz     short loc_1800BAEC6
0x1800bae84  mov     rcx, [rbp+188h]; this
0x1800bae8b  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bae92  mov     ebx, 80670012h
0x1800bae97  mov     edx, 262h; void *
0x1800bae9c  mov     r9d, ebx; char *
0x1800bae9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baea4  mov     rcx, [rsp+280h+var_258]
0x1800baea9  mov     [rsp+280h+var_258], r15
0x1800baeae  test    rcx, rcx
0x1800baeb1  jz      short loc_1800BAEBF
0x1800baeb3  call    cs:__imp_SRCacheContext_Close
0x1800baeba  nop     dword ptr [rax+rax+00h]
0x1800baebf  mov     eax, ebx
0x1800baec1  jmp     loc_1800BB033
0x1800baec6  xor     edx, edx; Val
0x1800baec8  mov     [rsp+280h+var_250], r15
0x1800baecd  mov     r8d, 200h; Size
0x1800baed3  lea     rcx, [rsp+280h+var_248]; void *
0x1800baed8  call    memset_0
0x1800baedd  lea     rax, [rsp+280h+var_248]
0x1800baee2  mov     [rbp+180h+var_48], r15
0x1800baee9  mov     rdx, r14; unsigned __int16 *
0x1800baeec  mov     [rbp+180h+var_38], rax
0x1800baef3  lea     rcx, [rsp+280h+var_250]; this
0x1800baef8  mov     [rbp+180h+var_40], 100h
0x1800baf03  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800baf08  mov     edi, eax
0x1800baf0a  test    eax, eax
0x1800baf0c  jns     short loc_1800BAF4D
0x1800baf0e  mov     edx, 265h; void *
0x1800baf13  mov     rcx, [rbp+188h]; this
0x1800baf1a  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800baf21  mov     r9d, edi; char *
0x1800baf24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baf29  mov     rcx, [rsp+280h+var_250]
0x1800baf2e  mov     [rsp+280h+var_250], r15
0x1800baf33  test    rcx, rcx
0x1800baf36  jz      loc_1800BAE5B
0x1800baf3c  call    cs:__imp_SRCache_Free
0x1800baf43  nop     dword ptr [rax+rax+00h]
0x1800baf48  jmp     loc_1800BAE5B
0x1800baf4d  mov     r8, [rbp+180h+var_38]; unsigned __int16 *
0x1800baf54  lea     r9, [rsp+280h+var_260]; bool *
0x1800baf59  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x1800baf5e  mov     [rsp+280h+var_260], r15b; int
0x1800baf63  mov     rcx, rbx; this
0x1800baf66  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800baf6b  mov     edi, eax
0x1800baf6d  test    eax, eax
0x1800baf6f  jns     short loc_1800BAF78
0x1800baf71  mov     edx, 268h
0x1800baf76  jmp     short loc_1800BAF13
0x1800baf78  cmp     [rsp+280h+var_260], r15b
0x1800baf7d  jz      short loc_1800BAF83
0x1800baf7f  mov     [rbx+10h], rsi
0x1800baf83  mov     rcx, [rsp+280h+var_258]
0x1800baf88  lea     rdx, aFiletypeassoci_1; "FileTypeAssociation\\Index\\FileType"
0x1800baf8f  call    cs:__imp_SRCacheContext_AddToCache
0x1800baf96  nop     dword ptr [rax+rax+00h]
0x1800baf9b  mov     ebx, eax
0x1800baf9d  test    eax, eax
0x1800baf9f  jns     short loc_1800BAFFB
0x1800bafa1  mov     rcx, [rbp+188h]; this
0x1800bafa8  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bafaf  mov     r9d, eax; char *
0x1800bafb2  mov     edx, 1A6h; void *
0x1800bafb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bafbc  mov     rcx, [rbp+188h]; this
0x1800bafc3  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bafca  mov     r9d, ebx; char *
0x1800bafcd  mov     edx, 26Eh; void *
0x1800bafd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bafd7  mov     rcx, [rsp+280h+var_250]
0x1800bafdc  mov     [rsp+280h+var_250], r15
0x1800bafe1  test    rcx, rcx
0x1800bafe4  jz      loc_1800BAEA4
0x1800bafea  call    cs:__imp_SRCache_Free
0x1800baff1  nop     dword ptr [rax+rax+00h]
0x1800baff6  jmp     loc_1800BAEA4
0x1800baffb  mov     rcx, [rsp+280h+var_250]
0x1800bb000  mov     [rsp+280h+var_250], r15
0x1800bb005  test    rcx, rcx
0x1800bb008  jz      short loc_1800BB016
0x1800bb00a  call    cs:__imp_SRCache_Free
0x1800bb011  nop     dword ptr [rax+rax+00h]
0x1800bb016  mov     rcx, [rsp+280h+var_258]
0x1800bb01b  mov     [rsp+280h+var_258], r15
0x1800bb020  test    rcx, rcx
0x1800bb023  jz      short loc_1800BB031
0x1800bb025  call    cs:__imp_SRCacheContext_Close
0x1800bb02c  nop     dword ptr [rax+rax+00h]
0x1800bb031  xor     eax, eax
0x1800bb033  mov     rcx, [rbp+180h+var_30]
0x1800bb03a  xor     rcx, rsp; StackCookie
0x1800bb03d  call    __security_check_cookie
0x1800bb042  mov     rbx, [rsp+280h+arg_18]
0x1800bb04a  add     rsp, 260h
0x1800bb051  pop     r15
0x1800bb053  pop     r14
0x1800bb055  pop     rdi
0x1800bb056  pop     rsi
0x1800bb057  pop     rbp
0x1800bb058  retn
```
