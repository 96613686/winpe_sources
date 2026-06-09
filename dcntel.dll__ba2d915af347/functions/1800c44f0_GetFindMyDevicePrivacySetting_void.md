# GetFindMyDevicePrivacySetting(void)

- ea: `0x1800c44f0`
- end: `0x1800c45c9`
- name: `?GetFindMyDevicePrivacySetting@@YA?AVPrivacySettingConsentState@@XZ`
- size: `217`
- prototype: `struct PrivacySettingConsentState __high(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066f40`
- `0x1800c2e60`
- `0x1800d02d0`

## callees

- `0x180011ce4`
- `0x1800c44f0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c4519`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c4519`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c4580`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c45a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c4580`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c45a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c4538`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c4538`

## string_xrefs

- `0x1800c4512`: `mdmcommon.dll`
- `0x1800c456b`: `onecore\base\appcompat\programs\devicecensus\dlls\privacysettingspriv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BYTE *__fastcall GetFindMyDevicePrivacySetting(_BYTE *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax
  __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  bool v8; // di
  bool v9; // si
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v13; // [rsp+48h] [rbp+10h] BYREF
  int v14; // [rsp+50h] [rbp+18h] BYREF
  HMODULE v15; // [rsp+58h] [rbp+20h]

  v13 = 0;
  v14 = 0;
  Library = LoadLibraryExW(L"mdmcommon.dll", 0, 0x800u);
  v3 = Library;
  v15 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MdmIsFindMyDeviceEnabled");
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(int *, int *))ProcAddress)(&v13, &v14);
      if ( v7 >= 0 )
      {
        v8 = v13 != 0;
        v9 = v14 != 0;
        FreeLibrary(v3);
        *a1 = !v8 + 1;
        a1[1] = 2 * v9;
        return a1;
      }
      v5 = (unsigned int)v7;
      v6 = 1825;
    }
    else
    {
      v5 = 2147500037LL;
      v6 = 1823;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\privacysettingspriv.cpp",
      (const char *)v5,
      v11);
    FreeLibrary(v3);
  }
  *(_WORD *)a1 = -1;
  return a1;
}

```

## disassembly

```asm
0x1800c44f0  mov     [rsp+arg_0], rbx
0x1800c44f5  push    rsi
0x1800c44f6  push    rdi
0x1800c44f7  push    r14; int
0x1800c44f9  sub     rsp, 20h
0x1800c44fd  mov     r14, rcx
0x1800c4500  xor     esi, esi
0x1800c4502  mov     [rsp+38h+arg_8], esi
0x1800c4506  mov     [rsp+38h+arg_10], esi
0x1800c450a  xor     edx, edx; hFile
0x1800c450c  mov     r8d, 800h; dwFlags
0x1800c4512  lea     rcx, aMdmcommonDll; "mdmcommon.dll"
0x1800c4519  call    cs:__imp_LoadLibraryExW
0x1800c451f  mov     rbx, rax
0x1800c4522  mov     [rsp+38h+arg_18], rax
0x1800c4527  test    rax, rax
0x1800c452a  jnz     short loc_1800C452E
0x1800c452c  jmp     short loc_1800C4586
0x1800c452e  lea     rdx, aMdmisfindmydev; "MdmIsFindMyDeviceEnabled"
0x1800c4535  mov     rcx, rbx; hModule
0x1800c4538  call    cs:__imp_GetProcAddress
0x1800c453e  test    rax, rax
0x1800c4541  jnz     short loc_1800C4550
0x1800c4543  mov     r9d, 80004005h
0x1800c4549  mov     edx, 71Fh
0x1800c454e  jmp     short loc_1800C456B
0x1800c4550  lea     rdx, [rsp+38h+arg_10]
0x1800c4555  lea     rcx, [rsp+38h+arg_8]
0x1800c455a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c455f  test    eax, eax
0x1800c4561  jns     short loc_1800C458E
0x1800c4563  mov     r9d, eax; char *
0x1800c4566  mov     edx, 721h; void *
0x1800c456b  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appcompat\\programs\\dev"...
0x1800c4572  mov     rcx, [rsp+38h]; this
0x1800c4577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c457c  nop
0x1800c457d  mov     rcx, rbx; hLibModule
0x1800c4580  call    cs:__imp_FreeLibrary
0x1800c4586  mov     word ptr [r14], 0FFFFh
0x1800c458c  jmp     short loc_1800C45B8
0x1800c458e  cmp     [rsp+38h+arg_8], esi
0x1800c4592  setnz   dil
0x1800c4596  cmp     [rsp+38h+arg_10], esi
0x1800c459a  setnz   sil
0x1800c459e  mov     rcx, rbx; hLibModule
0x1800c45a1  call    cs:__imp_FreeLibrary
0x1800c45a7  xor     dil, 1
0x1800c45ab  inc     dil
0x1800c45ae  mov     [r14], dil
0x1800c45b1  add     sil, sil
0x1800c45b4  mov     [r14+1], sil
0x1800c45b8  mov     rax, r14
0x1800c45bb  mov     rbx, [rsp+38h+arg_0]
0x1800c45c0  add     rsp, 20h
0x1800c45c4  pop     r14
0x1800c45c6  pop     rdi
0x1800c45c7  pop     rsi
0x1800c45c8  retn
```
