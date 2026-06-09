# CLCIDToLocaleNameConverter::Initialize(void)

- ea: `0x18000d274`
- end: `0x18000d2e8`
- name: `?Initialize@CLCIDToLocaleNameConverter@@QEAAJXZ`
- size: `116`
- prototype: `__int64 __fastcall(CLCIDToLocaleNameConverter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b68c`

## callees

- `0x18000d274`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d29d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d29d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d2dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d2dc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d284`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d284`

## string_xrefs

- `0x18000d27d`: `kernelbase.dll`

## pseudocode

```c
HRESULT __fastcall CLCIDToLocaleNameConverter::Initialize(CLCIDToLocaleNameConverter *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx

  LibraryW = LoadLibraryW(L"kernelbase.dll");
  *((_QWORD *)this + 3) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "LocaleNameToLCID");
    v4 = (HMODULE)*((_QWORD *)this + 3);
    *(_QWORD *)this = ProcAddress;
    *((_QWORD *)this + 1) = GetProcAddress(v4, "LCIDToLocaleName");
  }
  *((_BYTE *)this + 32) = 1;
  return CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a, (LPVOID *)this + 2);
}

```

## disassembly

```asm
0x18000d274  push    rbx
0x18000d276  sub     rsp, 30h
0x18000d27a  mov     rbx, rcx
0x18000d27d  lea     rcx, LibFileName; "kernelbase.dll"
0x18000d284  call    cs:__imp_LoadLibraryW
0x18000d28a  mov     [rbx+18h], rax
0x18000d28e  test    rax, rax
0x18000d291  jz      short loc_18000D2BB
0x18000d293  lea     rdx, ProcName; "LocaleNameToLCID"
0x18000d29a  mov     rcx, rax; hModule
0x18000d29d  call    cs:__imp_GetProcAddress
0x18000d2a3  mov     rcx, [rbx+18h]; hModule
0x18000d2a7  lea     rdx, aLcidtolocalena; "LCIDToLocaleName"
0x18000d2ae  mov     [rbx], rax
0x18000d2b1  call    cs:__imp_GetProcAddress
0x18000d2b7  mov     [rbx+8], rax
0x18000d2bb  xor     edx, edx; pUnkOuter
0x18000d2bd  mov     byte ptr [rbx+20h], 1
0x18000d2c1  lea     rax, [rbx+10h]
0x18000d2c5  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x18000d2cc  mov     [rsp+38h+ppv], rax; ppv
0x18000d2d1  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000d2d8  lea     r8d, [rdx+1]; dwClsContext
0x18000d2dc  call    cs:__imp_CoCreateInstance
0x18000d2e2  add     rsp, 30h
0x18000d2e6  pop     rbx
0x18000d2e7  retn
```
