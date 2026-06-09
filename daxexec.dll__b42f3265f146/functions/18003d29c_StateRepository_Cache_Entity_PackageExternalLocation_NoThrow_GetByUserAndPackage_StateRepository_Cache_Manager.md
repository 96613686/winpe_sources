# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x18003d29c`
- end: `0x18003d455`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `441`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18003db44`
- `0x1800b7a8c`
- `0x1800bbc00`
- `0x1800bd570`

## callees

- `0x18000ff24`
- `0x18003cfa0`
- `0x18003d29c`
- `0x18003f0dc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d409`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d433`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d409`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003d433`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18003d371`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18003d371`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d3b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003d3b8`

## string_xrefs

- `0x18003d387`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003d2d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003d3cc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003d3ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        ...)
{
  bool *v3; // rsi
  int v5; // ebx
  __int64 v6; // rdx
  bool *v8; // rdi
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool **v13; // rsi
  int Field_String; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-20h]
  __int64 *v18; // [rsp+20h] [rbp-20h]
  __int64 v19; // [rsp+28h] [rbp-18h] BYREF
  char v20; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v22; // [rsp+78h] [rbp+38h] BYREF
  va_list va; // [rsp+78h] [rbp+38h]
  _QWORD *v24; // [rsp+80h] [rbp+40h]
  bool *v25; // [rsp+88h] [rbp+48h] BYREF
  va_list va1; // [rsp+88h] [rbp+48h]
  va_list va2; // [rsp+90h] [rbp+50h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v22 = va_arg(va1, _QWORD);
  v24 = va_arg(va1, _QWORD *);
  va_copy(va2, va1);
  v25 = va_arg(va2, bool *);
  v3 = v25;
  *v25 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 225;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v5,
      v17);
    return (unsigned int)v5;
  }
  v25 = 0;
  v5 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(a1, a2, a3, (__int64 *)va1);
  if ( v5 < 0 )
  {
    v6 = 228;
    goto LABEL_3;
  }
  v8 = v25;
  if ( v25 )
  {
    v22 = 0;
    v9 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
           a1,
           (__int64)v25,
           (struct StateRepository::Cache::Context_NoThrow *)va,
           v3);
    v5 = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v11 = 164;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
        (const char *)v10,
        v17);
      v16 = v22;
      v22 = 0;
      if ( v16 )
        SRCacheContext_Close();
      v6 = 231;
      goto LABEL_3;
    }
    v12 = v22;
    if ( *v3 )
    {
      v13 = (bool **)v24;
      v19 = 0;
      v20 = 1;
      v18 = v24 + 3;
      Field_String = SRCacheContext_GetField_String(v22, L"Path", &v19);
      v5 = Field_String;
      if ( Field_String >= 0 )
        v5 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_String,
          (int)v18);
      if ( v20 )
      {
        v15 = *v18;
        *v18 = v19;
        if ( v15 )
          SRCache_Free();
      }
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v5,
          (int)v18);
        v10 = (unsigned int)v5;
        v11 = 169;
        goto LABEL_18;
      }
      v12 = v22;
      *v13 = v8;
    }
    v22 = 0;
    if ( v12 )
      SRCacheContext_Close();
  }
  return 0;
}

```

## disassembly

```asm
0x18003d29c  mov     [rsp-18h+arg_0], rbx
0x18003d2a1  mov     [rsp-18h+arg_8], rsi
0x18003d2a6  mov     [rsp-18h+arg_18], r9
0x18003d2ab  push    rbp
0x18003d2ac  push    rdi
0x18003d2ad  push    r14
0x18003d2af  mov     rbp, rsp
0x18003d2b2  sub     rsp, 40h
0x18003d2b6  mov     rsi, [rbp+arg_28]
0x18003d2ba  mov     r14, rcx
0x18003d2bd  mov     byte ptr [rsi], 0
0x18003d2c0  test    r8, r8
0x18003d2c3  jnz     short loc_18003D2E9
0x18003d2c5  mov     ebx, 80070057h
0x18003d2ca  mov     edx, 0E1h; void *
0x18003d2cf  mov     rcx, [rbp+18h]; this
0x18003d2d3  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d2da  mov     r9d, ebx; char *
0x18003d2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d2e2  mov     eax, ebx
0x18003d2e4  jmp     loc_18003D441
0x18003d2e9  lea     r9, [rbp+arg_28]; __int64 *
0x18003d2ed  mov     [rbp+arg_28], 0
0x18003d2f5  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)
0x18003d2fa  mov     ebx, eax
0x18003d2fc  test    eax, eax
0x18003d2fe  jns     short loc_18003D307
0x18003d300  mov     edx, 0E4h
0x18003d305  jmp     short loc_18003D2CF
0x18003d307  mov     rdi, [rbp+arg_28]
0x18003d30b  test    rdi, rdi
0x18003d30e  jz      loc_18003D43F
0x18003d314  mov     r9, rsi; bool *
0x18003d317  mov     [rbp+arg_18], 0
0x18003d31f  lea     r8, [rbp+arg_18]; this
0x18003d323  mov     rdx, rdi; __int64
0x18003d326  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18003d329  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18003d32e  mov     ebx, eax
0x18003d330  test    eax, eax
0x18003d332  jns     short loc_18003D341
0x18003d334  mov     r9d, eax
0x18003d337  mov     edx, 0A4h
0x18003d33c  jmp     loc_18003D3E8
0x18003d341  cmp     byte ptr [rsi], 0
0x18003d344  mov     rcx, [rbp+arg_18]
0x18003d348  jz      loc_18003D426
0x18003d34e  mov     rsi, [rbp+arg_20]
0x18003d352  lea     r8, [rbp+var_18]
0x18003d356  lea     rdx, aPath; "Path"
0x18003d35d  mov     [rbp+var_18], 0
0x18003d365  mov     [rbp+var_10], 1
0x18003d369  lea     rax, [rsi+18h]
0x18003d36d  mov     [rbp+var_20], rax
0x18003d371  call    cs:__imp_SRCacheContext_GetField_String
0x18003d378  nop     dword ptr [rax+rax+00h]
0x18003d37d  mov     ebx, eax
0x18003d37f  test    eax, eax
0x18003d381  jns     short loc_18003D39D
0x18003d383  mov     rcx, [rbp+18h]; this
0x18003d387  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d38e  mov     r9d, eax; char *
0x18003d391  mov     edx, 246h; void *
0x18003d396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d39b  jmp     short loc_18003D39F
0x18003d39d  xor     ebx, ebx
0x18003d39f  cmp     [rbp+var_10], 0
0x18003d3a3  jz      short loc_18003D3C4
0x18003d3a5  mov     rdx, [rbp+var_20]
0x18003d3a9  mov     rax, [rbp+var_18]
0x18003d3ad  mov     rcx, [rdx]
0x18003d3b0  mov     [rdx], rax
0x18003d3b3  test    rcx, rcx
0x18003d3b6  jz      short loc_18003D3C4
0x18003d3b8  call    cs:__imp_SRCache_Free
0x18003d3bf  nop     dword ptr [rax+rax+00h]
0x18003d3c4  test    ebx, ebx
0x18003d3c6  jns     short loc_18003D41F
0x18003d3c8  mov     rcx, [rbp+18h]; this
0x18003d3cc  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d3d3  mov     r9d, ebx; char *
0x18003d3d6  mov     edx, 269h; void *
0x18003d3db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d3e0  mov     r9d, ebx; char *
0x18003d3e3  mov     edx, 0A9h; void *
0x18003d3e8  mov     rcx, [rbp+18h]; this
0x18003d3ec  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003d3f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d3f8  mov     rcx, [rbp+arg_18]
0x18003d3fc  mov     [rbp+arg_18], 0
0x18003d404  test    rcx, rcx
0x18003d407  jz      short loc_18003D415
0x18003d409  call    cs:__imp_SRCacheContext_Close
0x18003d410  nop     dword ptr [rax+rax+00h]
0x18003d415  mov     edx, 0E7h
0x18003d41a  jmp     loc_18003D2CF
0x18003d41f  mov     rcx, [rbp+arg_18]
0x18003d423  mov     [rsi], rdi
0x18003d426  mov     [rbp+arg_18], 0
0x18003d42e  test    rcx, rcx
0x18003d431  jz      short loc_18003D43F
0x18003d433  call    cs:__imp_SRCacheContext_Close
0x18003d43a  nop     dword ptr [rax+rax+00h]
0x18003d43f  xor     eax, eax
0x18003d441  mov     rbx, [rsp+40h+arg_0]
0x18003d446  mov     rsi, [rsp+40h+arg_8]
0x18003d44b  add     rsp, 40h
0x18003d44f  pop     r14
0x18003d451  pop     rdi
0x18003d452  pop     rbp
0x18003d453  retn
```
