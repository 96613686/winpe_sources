# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180007910`
- end: `0x180007c8e`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `894`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000669c`
- `0x1800078c4`
- `0x1800082a0`

## callees

- `0x180007910`
- `0x18000a690`
- `0x18005b2c4`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180007a58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180007a58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000799b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000799b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000795c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800079c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007a82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007ae7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007bf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000795c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800079c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007a82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007ae7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007bf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007acc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007b61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007bdb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007acc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007b61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180007bdb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180007aab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180007aab`

## string_xrefs

- `0x180007b3e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180007b76`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180007bbd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180007c10`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180007c75`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180007b23`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007c35`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007c5a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v12;
  }
  v6 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v6 )
    SRCacheContext_Close(v6);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_Open(v7, L"Package\\Index\\PackageFamily", 0, &v23);
  if ( v24 )
  {
    v9 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
  }
  else
  {
    if ( !*(_QWORD *)v21 )
    {
      v12 = -2140733422;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x799,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)0x80670012LL,
        0);
LABEL_25:
      v17 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
      if ( v17 )
        SRCacheContext_Close(v17);
      return v12;
    }
    v25 = 0;
    memset_0(v26, 0, sizeof(v26));
    v27 = 0;
    v29 = v26;
    v28 = 256;
    v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
    if ( v8 < 0 )
    {
      v18 = 1948;
    }
    else
    {
      v22 = (int *)this;
      v23 = 0;
      v24 = 1;
      v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
      if ( v24 )
      {
        v10 = *(_QWORD *)v22;
        *(_QWORD *)v22 = v23;
        if ( v10 )
          SRCacheContext_Close(v10);
      }
      if ( v8 >= 0 )
      {
        if ( *(_QWORD *)this )
          *((_QWORD *)this + 2) = a2;
        v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Package\\Index\\PackageFamily");
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = v25;
          v25 = 0;
          if ( v13 )
            SRCache_Free(v13);
          v14 = *(_QWORD *)v21;
          *(_QWORD *)v21 = 0;
          if ( v14 )
            SRCacheContext_Close(v14);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v11,
          v21[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A5,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
          (const char *)v12,
          v21[0]);
        v16 = v25;
        v25 = 0;
        if ( v16 )
          SRCache_Free(v16);
        goto LABEL_25;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v21[0]);
      v18 = 1951;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    v19 = v25;
    v25 = 0;
    if ( v19 )
      SRCache_Free(v19);
  }
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007910  mov     [rsp-8+arg_18], rbx
0x180007915  push    rbp
0x180007916  push    rsi
0x180007917  push    rdi
0x180007918  push    r14
0x18000791a  push    r15
0x18000791c  lea     rbp, [rsp-170h]
0x180007924  sub     rsp, 270h
0x18000792b  mov     rax, cs:__security_cookie
0x180007932  xor     rax, rsp
0x180007935  mov     [rbp+190h+var_30], rax
0x18000793c  xor     r15d, r15d
0x18000793f  mov     r14, r8
0x180007942  mov     rsi, rdx
0x180007945  mov     rbx, rcx
0x180007948  test    r8, r8
0x18000794b  jz      loc_180007C09
0x180007951  mov     rcx, [rcx]
0x180007954  mov     [rbx], r15
0x180007957  test    rcx, rcx
0x18000795a  jz      short loc_180007968
0x18000795c  call    cs:__imp_SRCacheContext_Close
0x180007963  nop     dword ptr [rax+rax+00h]
0x180007968  mov     [rbx+8], r15d
0x18000796c  lea     rax, [rsp+290h+var_270]
0x180007971  mov     [rbx+10h], r15
0x180007975  lea     r9, [rsp+290h+var_260]
0x18000797a  mov     rcx, [rsi]
0x18000797d  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x180007984  xor     r8d, r8d
0x180007987  mov     [rsp+290h+var_268], rax
0x18000798c  mov     qword ptr [rsp+290h+var_270], r15; int
0x180007991  mov     [rsp+290h+var_260], r15
0x180007996  mov     [rsp+290h+var_258], 1
0x18000799b  call    cs:__imp_SRCacheContext_Open
0x1800079a2  nop     dword ptr [rax+rax+00h]
0x1800079a7  mov     edi, eax
0x1800079a9  cmp     [rsp+290h+var_258], r15b
0x1800079ae  jz      short loc_1800079D1
0x1800079b0  mov     r8, [rsp+290h+var_268]
0x1800079b5  mov     rdx, [rsp+290h+var_260]
0x1800079ba  mov     rcx, [r8]
0x1800079bd  mov     [r8], rdx
0x1800079c0  test    rcx, rcx
0x1800079c3  jz      short loc_1800079D1
0x1800079c5  call    cs:__imp_SRCacheContext_Close
0x1800079cc  nop     dword ptr [rax+rax+00h]
0x1800079d1  test    edi, edi
0x1800079d3  js      loc_180007C53
0x1800079d9  cmp     qword ptr [rsp+290h+var_270], r15
0x1800079de  setnz   al
0x1800079e1  test    al, al
0x1800079e3  jz      loc_180007B6F
0x1800079e9  xor     edx, edx; Val
0x1800079eb  mov     [rsp+290h+var_250], r15
0x1800079f0  mov     r8d, 200h; Size
0x1800079f6  lea     rcx, [rsp+290h+var_248]; void *
0x1800079fb  call    memset_0
0x180007a00  lea     rax, [rsp+290h+var_248]
0x180007a05  mov     [rbp+190h+var_48], r15
0x180007a0c  mov     rdx, r14; unsigned __int64
0x180007a0f  mov     [rbp+190h+var_38], rax
0x180007a16  lea     rcx, [rsp+290h+var_250]; this
0x180007a1b  mov     [rbp+190h+var_40], 100h
0x180007a26  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180007a2b  mov     edi, eax
0x180007a2d  test    eax, eax
0x180007a2f  js      loc_180007BB1
0x180007a35  mov     rdx, [rbp+190h+var_38]
0x180007a3c  lea     r9, [rsp+290h+var_260]
0x180007a41  mov     rcx, qword ptr [rsp+290h+var_270]
0x180007a46  xor     r8d, r8d
0x180007a49  mov     [rsp+290h+var_268], rbx
0x180007a4e  mov     [rsp+290h+var_260], r15
0x180007a53  mov     [rsp+290h+var_258], 1
0x180007a58  call    cs:__imp_SRCacheContext_OpenSubContext
0x180007a5f  nop     dword ptr [rax+rax+00h]
0x180007a64  mov     edi, eax
0x180007a66  cmp     [rsp+290h+var_258], r15b
0x180007a6b  jz      short loc_180007A8E
0x180007a6d  mov     r8, [rsp+290h+var_268]
0x180007a72  mov     rdx, [rsp+290h+var_260]
0x180007a77  mov     rcx, [r8]
0x180007a7a  mov     [r8], rdx
0x180007a7d  test    rcx, rcx
0x180007a80  jz      short loc_180007A8E
0x180007a82  call    cs:__imp_SRCacheContext_Close
0x180007a89  nop     dword ptr [rax+rax+00h]
0x180007a8e  test    edi, edi
0x180007a90  js      loc_180007C2E
0x180007a96  cmp     [rbx], r15
0x180007a99  jz      short loc_180007A9F
0x180007a9b  mov     [rbx+10h], rsi
0x180007a9f  mov     rcx, qword ptr [rsp+290h+var_270]
0x180007aa4  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x180007aab  call    cs:__imp_SRCacheContext_AddToCache
0x180007ab2  nop     dword ptr [rax+rax+00h]
0x180007ab7  mov     ebx, eax
0x180007ab9  test    eax, eax
0x180007abb  js      short loc_180007B1C
0x180007abd  mov     rcx, [rsp+290h+var_250]
0x180007ac2  mov     [rsp+290h+var_250], r15
0x180007ac7  test    rcx, rcx
0x180007aca  jz      short loc_180007AD8
0x180007acc  call    cs:__imp_SRCache_Free
0x180007ad3  nop     dword ptr [rax+rax+00h]
0x180007ad8  mov     rcx, qword ptr [rsp+290h+var_270]
0x180007add  mov     qword ptr [rsp+290h+var_270], r15
0x180007ae2  test    rcx, rcx
0x180007ae5  jz      short loc_180007AF3
0x180007ae7  call    cs:__imp_SRCacheContext_Close
0x180007aee  nop     dword ptr [rax+rax+00h]
0x180007af3  xor     eax, eax
0x180007af5  mov     rcx, [rbp+190h+var_30]
0x180007afc  xor     rcx, rsp; StackCookie
0x180007aff  call    __security_check_cookie
0x180007b04  mov     rbx, [rsp+290h+arg_18]
0x180007b0c  add     rsp, 270h
0x180007b13  pop     r15
0x180007b15  pop     r14
0x180007b17  pop     rdi
0x180007b18  pop     rsi
0x180007b19  pop     rbp
0x180007b1a  retn
0x180007b1c  mov     rcx, [rbp+198h]; this
0x180007b23  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007b2a  mov     r9d, ebx; char *
0x180007b2d  mov     edx, 1A6h; void *
0x180007b32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b37  mov     rcx, [rbp+198h]; this
0x180007b3e  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007b45  mov     r9d, ebx; char *
0x180007b48  mov     edx, 7A5h; void *
0x180007b4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b52  mov     rcx, [rsp+290h+var_250]
0x180007b57  mov     [rsp+290h+var_250], r15
0x180007b5c  test    rcx, rcx
0x180007b5f  jz      short loc_180007B8F
0x180007b61  call    cs:__imp_SRCache_Free
0x180007b68  nop     dword ptr [rax+rax+00h]
0x180007b6d  jmp     short loc_180007B8F
0x180007b6f  mov     rcx, [rbp+198h]; this
0x180007b76  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007b7d  mov     ebx, 80670012h
0x180007b82  mov     edx, 799h; void *
0x180007b87  mov     r9d, ebx; char *
0x180007b8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b8f  mov     rcx, qword ptr [rsp+290h+var_270]
0x180007b94  mov     qword ptr [rsp+290h+var_270], r15
0x180007b99  test    rcx, rcx
0x180007b9c  jz      short loc_180007BAA
0x180007b9e  call    cs:__imp_SRCacheContext_Close
0x180007ba5  nop     dword ptr [rax+rax+00h]
0x180007baa  mov     eax, ebx
0x180007bac  jmp     loc_180007AF5
0x180007bb1  mov     edx, 79Ch; void *
0x180007bb6  mov     rcx, [rbp+198h]; this
0x180007bbd  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007bc4  mov     r9d, edi; char *
0x180007bc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bcc  mov     rcx, [rsp+290h+var_250]
0x180007bd1  mov     [rsp+290h+var_250], r15
0x180007bd6  test    rcx, rcx
0x180007bd9  jz      short loc_180007BE7
0x180007bdb  call    cs:__imp_SRCache_Free
0x180007be2  nop     dword ptr [rax+rax+00h]
0x180007be7  mov     rcx, qword ptr [rsp+290h+var_270]
0x180007bec  mov     qword ptr [rsp+290h+var_270], r15
0x180007bf1  test    rcx, rcx
0x180007bf4  jz      short loc_180007C02
0x180007bf6  call    cs:__imp_SRCacheContext_Close
0x180007bfd  nop     dword ptr [rax+rax+00h]
0x180007c02  mov     eax, edi
0x180007c04  jmp     loc_180007AF5
0x180007c09  mov     rcx, [rbp+198h]; this
0x180007c10  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007c17  mov     ebx, 80070057h
0x180007c1c  mov     edx, 792h; void *
0x180007c21  mov     r9d, ebx; char *
0x180007c24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c29  jmp     loc_180007BAA
0x180007c2e  mov     rcx, [rbp+198h]; this
0x180007c35  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007c3c  mov     r9d, edi; char *
0x180007c3f  mov     edx, 1B0h; void *
0x180007c44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c49  mov     edx, 79Fh
0x180007c4e  jmp     loc_180007BB6
0x180007c53  mov     rcx, [rbp+198h]; this
0x180007c5a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007c61  mov     r9d, edi; char *
0x180007c64  mov     edx, 18Ch; void *
0x180007c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c6e  mov     rcx, [rbp+198h]; this
0x180007c75  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007c7c  mov     r9d, edi; char *
0x180007c7f  mov     edx, 798h; void *
0x180007c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c89  jmp     loc_180007BE7
```
