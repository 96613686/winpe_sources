# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x180017dac`
- end: `0x180017e61`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180017670`
- `0x18001a304`
- `0x18001a7d4`

## callees

- `0x180017dac`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017de6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017de6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017dd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017dd1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017dfe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e4f`

## string_xrefs

- `0x180017dca`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180017ddc`: `RegDeleteKeyExW`
- `0x180017df7`: `advapi32.dll`
- `0x180017e09`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const wchar_t *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const wchar_t *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const wchar_t *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180017dac  mov     [rsp+arg_0], rbx
0x180017db1  push    rdi
0x180017db2  sub     rsp, 30h
0x180017db6  mov     rdi, rdx
0x180017db9  mov     rbx, rcx
0x180017dbc  cmp     qword ptr [rcx+8], 0
0x180017dc1  jnz     short loc_180017E1D
0x180017dc3  cmp     qword ptr [rcx+10h], 0
0x180017dc8  jnz     short loc_180017E1D
0x180017dca  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180017dd1  call    cs:__imp_GetModuleHandleW
0x180017dd7  test    rax, rax
0x180017dda  jz      short loc_180017DF2
0x180017ddc  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180017de3  mov     rcx, rax; hModule
0x180017de6  call    cs:__imp_GetProcAddress
0x180017dec  mov     [rbx+8], rax
0x180017df0  jmp     short loc_180017E1D
0x180017df2  xor     r8d, r8d; dwFlags
0x180017df5  xor     edx, edx; hFile
0x180017df7  lea     rcx, LibFileName; "advapi32.dll"
0x180017dfe  call    cs:__imp_LoadLibraryExW
0x180017e04  test    rax, rax
0x180017e07  jz      short loc_180017E1D
0x180017e09  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180017e10  mov     rcx, rax; hModule
0x180017e13  call    cs:__imp_GetProcAddress
0x180017e19  mov     [rbx+10h], rax
0x180017e1d  mov     rax, [rbx+8]
0x180017e21  test    rax, rax
0x180017e24  jz      short loc_180017E39
0x180017e26  xor     r9d, r9d
0x180017e29  xor     r8d, r8d
0x180017e2c  mov     rdx, rdi
0x180017e2f  mov     rcx, [rbx]
0x180017e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e37  jmp     short loc_180017E56
0x180017e39  mov     rax, [rbx+10h]
0x180017e3d  test    rax, rax
0x180017e40  jz      short loc_180017E4F
0x180017e42  mov     rdx, rdi
0x180017e45  mov     rcx, [rbx]
0x180017e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e4d  jmp     short loc_180017E56
0x180017e4f  call    cs:__imp_GetLastError
0x180017e55  nop
0x180017e56  mov     rbx, [rsp+38h+arg_0]
0x180017e5b  add     rsp, 30h
0x180017e5f  pop     rdi
0x180017e60  retn
```
