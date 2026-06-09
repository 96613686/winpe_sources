# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180108a44`
- end: `0x180108cfa`
- name: `?OpenByApplication@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `694`
- prototype: `int(StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18012a29c`

## callees

- `0x18002f340`
- `0x180058768`
- `0x1800caf60`
- `0x1800e15d8`
- `0x180108a44`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180108ac9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180108ac9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108a90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108aed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108b96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108bf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108c91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108a90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108aed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108b96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108bf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180108c91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180108b81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180108c62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180108c7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180108b81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180108c62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180108c7c`

## string_xrefs

- `0x180108b63`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180108bcb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180108c1f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180108c3f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180108ca5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180108c04`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180108aab`: `ApplicationExtension\Index\Application`
- `0x1801962e9`: `ApplicationExtension\Index\Application`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(
        StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  int *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  char v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+268h] [rbp+168h]
  __int64 v30; // [rsp+270h] [rbp+170h]
  _BYTE *v31; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a3 )
  {
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      (int)v20);
    return v14;
  }
  v6 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v6 )
    SRCacheContext_Close(v6);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v24 = &v23;
  v23 = 0;
  v25 = 0;
  v26 = 1;
  v8 = SRCacheContext_Open(v7, L"ApplicationExtension\\Index\\Application", 0, &v25);
  if ( v26 )
  {
    v9 = *v24;
    *v24 = v25;
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
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v21);
LABEL_13:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v8;
  }
  if ( !v23 )
  {
    v14 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80670012LL,
      (int)v20);
LABEL_17:
    v15 = v23;
    v23 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    return v14;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( v8 < 0 )
  {
    v10 = 731;
    goto LABEL_11;
  }
  v20 = &v22;
  LOBYTE(v22) = 0;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(this, &v23, v31);
  if ( v8 < 0 )
  {
    v10 = 734;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    v11 = v27;
    v27 = 0;
    if ( v11 )
      SRCache_Free(v11);
    goto LABEL_13;
  }
  if ( (_BYTE)v22 )
    *((_QWORD *)this + 2) = a2;
  v19 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)&v23,
          L"ApplicationExtension\\Index\\Application");
  v14 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v19,
      (int)&v22);
    v16 = v27;
    v27 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_17;
  }
  v17 = v27;
  v27 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = v23;
  v23 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x180108a44  mov     [rsp-8+arg_18], rbx
0x180108a49  push    rbp
0x180108a4a  push    rsi
0x180108a4b  push    rdi
0x180108a4c  push    r14
0x180108a4e  push    r15
0x180108a50  lea     rbp, [rsp-190h]
0x180108a58  sub     rsp, 290h
0x180108a5f  mov     rax, cs:__security_cookie
0x180108a66  xor     rax, rsp
0x180108a69  mov     [rbp+1B0h+var_30], rax
0x180108a70  xor     r15d, r15d
0x180108a73  mov     r14, r8
0x180108a76  mov     rsi, rdx
0x180108a79  mov     rbx, rcx
0x180108a7c  test    r8, r8
0x180108a7f  jz      loc_180108C9E
0x180108a85  mov     rcx, [rcx]
0x180108a88  mov     [rbx], r15
0x180108a8b  test    rcx, rcx
0x180108a8e  jz      short loc_180108A96
0x180108a90  call    cs:__imp_SRCacheContext_Close
0x180108a96  mov     [rbx+8], r15d
0x180108a9a  lea     rax, [rsp+2B0h+var_278]
0x180108a9f  mov     [rbx+10h], r15
0x180108aa3  lea     r9, [rsp+2B0h+var_268]
0x180108aa8  mov     rcx, [rsi]
0x180108aab  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x180108ab2  xor     r8d, r8d
0x180108ab5  mov     [rsp+2B0h+var_270], rax
0x180108aba  mov     [rsp+2B0h+var_278], r15
0x180108abf  mov     [rsp+2B0h+var_268], r15
0x180108ac4  mov     [rsp+2B0h+var_260], 1
0x180108ac9  call    cs:__imp_SRCacheContext_Open
0x180108acf  mov     edi, eax
0x180108ad1  cmp     [rsp+2B0h+var_260], r15b
0x180108ad6  jz      short loc_180108AF3
0x180108ad8  mov     r8, [rsp+2B0h+var_270]
0x180108add  mov     rdx, [rsp+2B0h+var_268]
0x180108ae2  mov     rcx, [r8]
0x180108ae5  mov     [r8], rdx
0x180108ae8  test    rcx, rcx
0x180108aeb  jz      short loc_180108AF3
0x180108aed  call    cs:__imp_SRCacheContext_Close
0x180108af3  test    edi, edi
0x180108af5  js      loc_180108BFD
0x180108afb  cmp     [rsp+2B0h+var_278], r15
0x180108b00  setnz   al
0x180108b03  test    al, al
0x180108b05  jz      loc_180108BC4
0x180108b0b  xor     edx, edx; Val
0x180108b0d  mov     [rsp+2B0h+var_250], r15
0x180108b12  mov     r8d, 200h; Size
0x180108b18  lea     rcx, [rsp+2B0h+var_248]; void *
0x180108b1d  call    memset_0
0x180108b22  lea     rax, [rsp+2B0h+var_248]
0x180108b27  mov     [rbp+1B0h+var_48], r15
0x180108b2e  mov     rdx, r14; unsigned __int64
0x180108b31  mov     [rbp+1B0h+var_38], rax
0x180108b38  lea     rcx, [rsp+2B0h+var_250]; this
0x180108b3d  mov     [rbp+1B0h+var_40], 100h
0x180108b48  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180108b4d  mov     edi, eax
0x180108b4f  test    eax, eax
0x180108b51  jns     loc_180108CC3
0x180108b57  mov     edx, 2DBh; void *
0x180108b5c  mov     rcx, [rbp+1B8h]; this
0x180108b63  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180108b6a  mov     r9d, edi; char *
0x180108b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108b72  mov     rcx, [rsp+2B0h+var_250]
0x180108b77  mov     [rsp+2B0h+var_250], r15
0x180108b7c  test    rcx, rcx
0x180108b7f  jz      short loc_180108B87
0x180108b81  call    cs:__imp_SRCache_Free
0x180108b87  mov     rcx, [rsp+2B0h+var_278]
0x180108b8c  mov     [rsp+2B0h+var_278], r15
0x180108b91  test    rcx, rcx
0x180108b94  jz      short loc_180108B9C
0x180108b96  call    cs:__imp_SRCacheContext_Close
0x180108b9c  mov     eax, edi
0x180108b9e  mov     rcx, [rbp+1B0h+var_30]
0x180108ba5  xor     rcx, rsp; StackCookie
0x180108ba8  call    __security_check_cookie
0x180108bad  mov     rbx, [rsp+2B0h+arg_18]
0x180108bb5  add     rsp, 290h
0x180108bbc  pop     r15
0x180108bbe  pop     r14
0x180108bc0  pop     rdi
0x180108bc1  pop     rsi
0x180108bc2  pop     rbp
0x180108bc3  retn
0x180108bc4  mov     rcx, [rbp+1B8h]; this
0x180108bcb  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180108bd2  mov     ebx, 80670012h
0x180108bd7  mov     edx, 2D8h; void *
0x180108bdc  mov     r9d, ebx; char *
0x180108bdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108be4  mov     rcx, [rsp+2B0h+var_278]
0x180108be9  mov     [rsp+2B0h+var_278], r15
0x180108bee  test    rcx, rcx
0x180108bf1  jz      short loc_180108BF9
0x180108bf3  call    cs:__imp_SRCacheContext_Close
0x180108bf9  mov     eax, ebx
0x180108bfb  jmp     short loc_180108B9E
0x180108bfd  mov     rcx, [rbp+1B8h]; this
0x180108c04  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180108c0b  mov     r9d, edi; char *
0x180108c0e  mov     edx, 18Ch; void *
0x180108c13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108c18  mov     rcx, [rbp+1B8h]; this
0x180108c1f  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180108c26  mov     r9d, edi; char *
0x180108c29  mov     edx, 2D7h; void *
0x180108c2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108c33  jmp     loc_180108B87
0x180108c38  mov     rcx, [rbp+1B8h]; this
0x180108c3f  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180108c46  mov     r9d, ebx; char *
0x180108c49  mov     edx, 2E4h; void *
0x180108c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108c53  mov     rcx, [rsp+2B0h+var_250]
0x180108c58  mov     [rsp+2B0h+var_250], r15
0x180108c5d  test    rcx, rcx
0x180108c60  jz      short loc_180108BE4
0x180108c62  call    cs:__imp_SRCache_Free
0x180108c68  jmp     loc_180108BE4
0x180108c6d  mov     rcx, [rsp+2B0h+var_250]
0x180108c72  mov     [rsp+2B0h+var_250], r15
0x180108c77  test    rcx, rcx
0x180108c7a  jz      short loc_180108C82
0x180108c7c  call    cs:__imp_SRCache_Free
0x180108c82  mov     rcx, [rsp+2B0h+var_278]
0x180108c87  mov     [rsp+2B0h+var_278], r15
0x180108c8c  test    rcx, rcx
0x180108c8f  jz      short loc_180108C97
0x180108c91  call    cs:__imp_SRCacheContext_Close
0x180108c97  xor     eax, eax
0x180108c99  jmp     loc_180108B9E
0x180108c9e  mov     rcx, [rbp+1B8h]; this
0x180108ca5  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180108cac  mov     ebx, 80070057h
0x180108cb1  mov     edx, 2D1h; void *
0x180108cb6  mov     r9d, ebx; char *
0x180108cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108cbe  jmp     loc_180108BF9
0x180108cc3  mov     r8, [rbp+1B0h+var_38]
0x180108cca  lea     rax, [rsp+2B0h+var_280]
0x180108ccf  lea     rdx, [rsp+2B0h+var_278]
0x180108cd4  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x180108cd9  mov     rcx, rbx
0x180108cdc  mov     byte ptr [rsp+2B0h+var_280], r15b
0x180108ce1  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180108ce6  mov     edi, eax
0x180108ce8  test    eax, eax
0x180108cea  jns     loc_1801962DE
0x180108cf0  mov     edx, 2DEh
0x180108cf5  jmp     loc_180108B5C
0x1801962de  cmp     byte ptr [rsp+2B0h+var_280], r15b
0x1801962e3  jz      short loc_1801962E9
0x1801962e5  mov     [rbx+10h], rsi
0x1801962e9  lea     rdx, aApplicationext; "ApplicationExtension\\Index\\Applicatio"...
0x1801962f0  lea     rcx, [rsp+2B0h+var_278]; this
0x1801962f5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801962fa  mov     ebx, eax
0x1801962fc  test    eax, eax
0x1801962fe  jns     loc_180108C6D
0x180196304  jmp     loc_180108C38
```
