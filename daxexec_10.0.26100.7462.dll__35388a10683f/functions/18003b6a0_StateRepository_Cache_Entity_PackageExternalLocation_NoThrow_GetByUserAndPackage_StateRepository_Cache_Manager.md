# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x18003b6a0`
- end: `0x18003b84a`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `426`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18003bf38`
- `0x1800b5cac`
- `0x1800b9e20`
- `0x1800bb760`

## callees

- `0x18000e234`
- `0x18003b3a4`
- `0x18003b6a0`
- `0x18003d39c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18003b76c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18003b76c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b801`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b828`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b801`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003b828`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b7b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003b7b3`

## string_xrefs

- `0x18003b782`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003b6d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003b7c7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18003b7e7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

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
0x18003b6a0  mov     [rsp-18h+arg_0], rbx
0x18003b6a5  mov     [rsp-18h+arg_8], rsi
0x18003b6aa  mov     [rsp-18h+arg_18], r9
0x18003b6af  push    rbp
0x18003b6b0  push    rdi
0x18003b6b1  push    r14
0x18003b6b3  mov     rbp, rsp
0x18003b6b6  sub     rsp, 40h
0x18003b6ba  mov     rsi, [rbp+arg_28]
0x18003b6be  mov     r14, rcx
0x18003b6c1  mov     byte ptr [rsi], 0
0x18003b6c4  test    r8, r8
0x18003b6c7  jnz     short loc_18003B6ED
0x18003b6c9  mov     ebx, 80070057h
0x18003b6ce  mov     edx, 0E1h; void *
0x18003b6d3  mov     rcx, [rbp+18h]; this
0x18003b6d7  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b6de  mov     r9d, ebx; char *
0x18003b6e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b6e6  mov     eax, ebx
0x18003b6e8  jmp     loc_18003B836
0x18003b6ed  and     [rbp+arg_28], 0
0x18003b6f2  lea     r9, [rbp+arg_28]; __int64 *
0x18003b6f6  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)
0x18003b6fb  mov     ebx, eax
0x18003b6fd  test    eax, eax
0x18003b6ff  jns     short loc_18003B708
0x18003b701  mov     edx, 0E4h
0x18003b706  jmp     short loc_18003B6D3
0x18003b708  mov     rdi, [rbp+arg_28]
0x18003b70c  test    rdi, rdi
0x18003b70f  jz      loc_18003B834
0x18003b715  and     [rbp+arg_18], 0
0x18003b71a  lea     r8, [rbp+arg_18]; this
0x18003b71e  mov     r9, rsi; bool *
0x18003b721  mov     rdx, rdi; __int64
0x18003b724  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18003b727  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18003b72c  mov     ebx, eax
0x18003b72e  test    eax, eax
0x18003b730  jns     short loc_18003B73F
0x18003b732  mov     r9d, eax
0x18003b735  mov     edx, 0A4h
0x18003b73a  jmp     loc_18003B7E3
0x18003b73f  cmp     byte ptr [rsi], 0
0x18003b742  mov     rcx, [rbp+arg_18]
0x18003b746  jz      loc_18003B81E
0x18003b74c  mov     rsi, [rbp+arg_20]
0x18003b750  lea     r8, [rbp+var_18]
0x18003b754  and     [rbp+var_18], 0
0x18003b759  lea     rdx, aPath; "Path"
0x18003b760  mov     [rbp+var_10], 1
0x18003b764  lea     rax, [rsi+18h]
0x18003b768  mov     [rbp+var_20], rax
0x18003b76c  call    cs:__imp_SRCacheContext_GetField_String
0x18003b773  nop     dword ptr [rax+rax+00h]
0x18003b778  mov     ebx, eax
0x18003b77a  test    eax, eax
0x18003b77c  jns     short loc_18003B798
0x18003b77e  mov     rcx, [rbp+18h]; this
0x18003b782  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b789  mov     r9d, eax; char *
0x18003b78c  mov     edx, 246h; void *
0x18003b791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b796  jmp     short loc_18003B79A
0x18003b798  xor     ebx, ebx
0x18003b79a  cmp     [rbp+var_10], 0
0x18003b79e  jz      short loc_18003B7BF
0x18003b7a0  mov     rdx, [rbp+var_20]
0x18003b7a4  mov     rax, [rbp+var_18]
0x18003b7a8  mov     rcx, [rdx]
0x18003b7ab  mov     [rdx], rax
0x18003b7ae  test    rcx, rcx
0x18003b7b1  jz      short loc_18003B7BF
0x18003b7b3  call    cs:__imp_SRCache_Free
0x18003b7ba  nop     dword ptr [rax+rax+00h]
0x18003b7bf  test    ebx, ebx
0x18003b7c1  jns     short loc_18003B817
0x18003b7c3  mov     rcx, [rbp+18h]; this
0x18003b7c7  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b7ce  mov     r9d, ebx; char *
0x18003b7d1  mov     edx, 269h; void *
0x18003b7d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b7db  mov     r9d, ebx; char *
0x18003b7de  mov     edx, 0A9h; void *
0x18003b7e3  mov     rcx, [rbp+18h]; this
0x18003b7e7  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003b7ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b7f3  mov     rcx, [rbp+arg_18]
0x18003b7f7  and     [rbp+arg_18], 0
0x18003b7fc  test    rcx, rcx
0x18003b7ff  jz      short loc_18003B80D
0x18003b801  call    cs:__imp_SRCacheContext_Close
0x18003b808  nop     dword ptr [rax+rax+00h]
0x18003b80d  mov     edx, 0E7h
0x18003b812  jmp     loc_18003B6D3
0x18003b817  mov     rcx, [rbp+arg_18]
0x18003b81b  mov     [rsi], rdi
0x18003b81e  and     [rbp+arg_18], 0
0x18003b823  test    rcx, rcx
0x18003b826  jz      short loc_18003B834
0x18003b828  call    cs:__imp_SRCacheContext_Close
0x18003b82f  nop     dword ptr [rax+rax+00h]
0x18003b834  xor     eax, eax
0x18003b836  mov     rbx, [rsp+40h+arg_0]
0x18003b83b  mov     rsi, [rsp+40h+arg_8]
0x18003b840  add     rsp, 40h
0x18003b844  pop     r14
0x18003b846  pop     rdi
0x18003b847  pop     rbp
0x18003b848  retn
```
