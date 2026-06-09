# StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByFileType(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800bcbbc`
- end: `0x1800bce56`
- name: `?OpenByFileType@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `666`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b7104`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x18003b060`
- `0x18003ef9c`
- `0x18003f4d4`
- `0x1800bcbbc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcbff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcc66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bccaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bce21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcbff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bcc66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bccaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800bce21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcd38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcde6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bce06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcd38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bcde6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800bce06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bcd8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800bcd8b`

## string_xrefs

- `0x1800bcda4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800bcc43`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800bcc87`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800bcd16`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800bcdbf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

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
0x1800bcbbc  mov     [rsp-8+arg_18], rbx
0x1800bcbc1  push    rbp
0x1800bcbc2  push    rsi
0x1800bcbc3  push    rdi
0x1800bcbc4  push    r14
0x1800bcbc6  push    r15
0x1800bcbc8  lea     rbp, [rsp-160h]
0x1800bcbd0  sub     rsp, 260h
0x1800bcbd7  mov     rax, cs:__security_cookie
0x1800bcbde  xor     rax, rsp
0x1800bcbe1  mov     [rbp+180h+var_30], rax
0x1800bcbe8  mov     rbx, rcx
0x1800bcbeb  xor     r15d, r15d
0x1800bcbee  mov     rcx, [rcx]
0x1800bcbf1  mov     r14, r8
0x1800bcbf4  mov     rsi, rdx
0x1800bcbf7  mov     [rbx], r15
0x1800bcbfa  test    rcx, rcx
0x1800bcbfd  jz      short loc_1800BCC0B
0x1800bcbff  call    cs:__imp_SRCacheContext_Close
0x1800bcc06  nop     dword ptr [rax+rax+00h]
0x1800bcc0b  lea     r9, [rsp+280h+var_260]; bool *
0x1800bcc10  mov     [rbx+8], r15d
0x1800bcc14  lea     r8, aFiletypeassoci_1; "FileTypeAssociation\\Index\\FileType"
0x1800bcc1b  mov     [rbx+10h], r15
0x1800bcc1f  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800bcc22  mov     [rsp+280h+var_258], r15
0x1800bcc27  lea     rcx, [rsp+280h+var_258]; this
0x1800bcc2c  mov     [rsp+280h+var_260], r15b; int
0x1800bcc31  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800bcc36  mov     edi, eax
0x1800bcc38  test    eax, eax
0x1800bcc3a  jns     short loc_1800BCC79
0x1800bcc3c  mov     rcx, [rbp+188h]; this
0x1800bcc43  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcc4a  mov     r9d, eax; char *
0x1800bcc4d  mov     edx, 261h; void *
0x1800bcc52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcc57  mov     rcx, [rsp+280h+var_258]
0x1800bcc5c  mov     [rsp+280h+var_258], r15
0x1800bcc61  test    rcx, rcx
0x1800bcc64  jz      short loc_1800BCC72
0x1800bcc66  call    cs:__imp_SRCacheContext_Close
0x1800bcc6d  nop     dword ptr [rax+rax+00h]
0x1800bcc72  mov     eax, edi
0x1800bcc74  jmp     loc_1800BCE2F
0x1800bcc79  cmp     [rsp+280h+var_260], r15b
0x1800bcc7e  jnz     short loc_1800BCCC2
0x1800bcc80  mov     rcx, [rbp+188h]; this
0x1800bcc87  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcc8e  mov     ebx, 80670012h
0x1800bcc93  mov     edx, 262h; void *
0x1800bcc98  mov     r9d, ebx; char *
0x1800bcc9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcca0  mov     rcx, [rsp+280h+var_258]
0x1800bcca5  mov     [rsp+280h+var_258], r15
0x1800bccaa  test    rcx, rcx
0x1800bccad  jz      short loc_1800BCCBB
0x1800bccaf  call    cs:__imp_SRCacheContext_Close
0x1800bccb6  nop     dword ptr [rax+rax+00h]
0x1800bccbb  mov     eax, ebx
0x1800bccbd  jmp     loc_1800BCE2F
0x1800bccc2  xor     edx, edx; Val
0x1800bccc4  mov     [rsp+280h+var_250], r15
0x1800bccc9  mov     r8d, 200h; Size
0x1800bcccf  lea     rcx, [rsp+280h+var_248]; void *
0x1800bccd4  call    memset_0
0x1800bccd9  lea     rax, [rsp+280h+var_248]
0x1800bccde  mov     [rbp+180h+var_48], r15
0x1800bcce5  mov     rdx, r14; unsigned __int16 *
0x1800bcce8  mov     [rbp+180h+var_38], rax
0x1800bccef  lea     rcx, [rsp+280h+var_250]; this
0x1800bccf4  mov     [rbp+180h+var_40], 100h
0x1800bccff  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800bcd04  mov     edi, eax
0x1800bcd06  test    eax, eax
0x1800bcd08  jns     short loc_1800BCD49
0x1800bcd0a  mov     edx, 265h; void *
0x1800bcd0f  mov     rcx, [rbp+188h]; this
0x1800bcd16  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcd1d  mov     r9d, edi; char *
0x1800bcd20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcd25  mov     rcx, [rsp+280h+var_250]
0x1800bcd2a  mov     [rsp+280h+var_250], r15
0x1800bcd2f  test    rcx, rcx
0x1800bcd32  jz      loc_1800BCC57
0x1800bcd38  call    cs:__imp_SRCache_Free
0x1800bcd3f  nop     dword ptr [rax+rax+00h]
0x1800bcd44  jmp     loc_1800BCC57
0x1800bcd49  mov     r8, [rbp+180h+var_38]; unsigned __int16 *
0x1800bcd50  lea     r9, [rsp+280h+var_260]; bool *
0x1800bcd55  lea     rdx, [rsp+280h+var_258]; struct StateRepository::Cache::Context_NoThrow *
0x1800bcd5a  mov     [rsp+280h+var_260], r15b; int
0x1800bcd5f  mov     rcx, rbx; this
0x1800bcd62  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x1800bcd67  mov     edi, eax
0x1800bcd69  test    eax, eax
0x1800bcd6b  jns     short loc_1800BCD74
0x1800bcd6d  mov     edx, 268h
0x1800bcd72  jmp     short loc_1800BCD0F
0x1800bcd74  cmp     [rsp+280h+var_260], r15b
0x1800bcd79  jz      short loc_1800BCD7F
0x1800bcd7b  mov     [rbx+10h], rsi
0x1800bcd7f  mov     rcx, [rsp+280h+var_258]
0x1800bcd84  lea     rdx, aFiletypeassoci_1; "FileTypeAssociation\\Index\\FileType"
0x1800bcd8b  call    cs:__imp_SRCacheContext_AddToCache
0x1800bcd92  nop     dword ptr [rax+rax+00h]
0x1800bcd97  mov     ebx, eax
0x1800bcd99  test    eax, eax
0x1800bcd9b  jns     short loc_1800BCDF7
0x1800bcd9d  mov     rcx, [rbp+188h]; this
0x1800bcda4  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcdab  mov     r9d, eax; char *
0x1800bcdae  mov     edx, 1A6h; void *
0x1800bcdb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcdb8  mov     rcx, [rbp+188h]; this
0x1800bcdbf  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800bcdc6  mov     r9d, ebx; char *
0x1800bcdc9  mov     edx, 26Eh; void *
0x1800bcdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcdd3  mov     rcx, [rsp+280h+var_250]
0x1800bcdd8  mov     [rsp+280h+var_250], r15
0x1800bcddd  test    rcx, rcx
0x1800bcde0  jz      loc_1800BCCA0
0x1800bcde6  call    cs:__imp_SRCache_Free
0x1800bcded  nop     dword ptr [rax+rax+00h]
0x1800bcdf2  jmp     loc_1800BCCA0
0x1800bcdf7  mov     rcx, [rsp+280h+var_250]
0x1800bcdfc  mov     [rsp+280h+var_250], r15
0x1800bce01  test    rcx, rcx
0x1800bce04  jz      short loc_1800BCE12
0x1800bce06  call    cs:__imp_SRCache_Free
0x1800bce0d  nop     dword ptr [rax+rax+00h]
0x1800bce12  mov     rcx, [rsp+280h+var_258]
0x1800bce17  mov     [rsp+280h+var_258], r15
0x1800bce1c  test    rcx, rcx
0x1800bce1f  jz      short loc_1800BCE2D
0x1800bce21  call    cs:__imp_SRCacheContext_Close
0x1800bce28  nop     dword ptr [rax+rax+00h]
0x1800bce2d  xor     eax, eax
0x1800bce2f  mov     rcx, [rbp+180h+var_30]
0x1800bce36  xor     rcx, rsp; StackCookie
0x1800bce39  call    __security_check_cookie
0x1800bce3e  mov     rbx, [rsp+280h+arg_18]
0x1800bce46  add     rsp, 260h
0x1800bce4d  pop     r15
0x1800bce4f  pop     r14
0x1800bce51  pop     rdi
0x1800bce52  pop     rsi
0x1800bce53  pop     rbp
0x1800bce54  retn
```
