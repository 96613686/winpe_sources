# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000d3dc`
- end: `0x18000d491`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bee8`
- `0x180010154`
- `0x180010624`

## callees

- `0x18000d3dc`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d42e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d42e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d416`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d443`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d416`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d443`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d401`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d47f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d47f`

## string_xrefs

- `0x18000d3fa`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000d40c`: `RegDeleteKeyExW`
- `0x18000d427`: `advapi32.dll`
- `0x18000d439`: `RegDeleteKeyW`

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
0x18000d3dc  mov     [rsp+arg_0], rbx
0x18000d3e1  push    rdi
0x18000d3e2  sub     rsp, 30h
0x18000d3e6  mov     rdi, rdx
0x18000d3e9  mov     rbx, rcx
0x18000d3ec  cmp     qword ptr [rcx+8], 0
0x18000d3f1  jnz     short loc_18000D44D
0x18000d3f3  cmp     qword ptr [rcx+10h], 0
0x18000d3f8  jnz     short loc_18000D44D
0x18000d3fa  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000d401  call    cs:__imp_GetModuleHandleW
0x18000d407  test    rax, rax
0x18000d40a  jz      short loc_18000D422
0x18000d40c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000d413  mov     rcx, rax; hModule
0x18000d416  call    cs:__imp_GetProcAddress
0x18000d41c  mov     [rbx+8], rax
0x18000d420  jmp     short loc_18000D44D
0x18000d422  xor     r8d, r8d; dwFlags
0x18000d425  xor     edx, edx; hFile
0x18000d427  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18000d42e  call    cs:__imp_LoadLibraryExW
0x18000d434  test    rax, rax
0x18000d437  jz      short loc_18000D44D
0x18000d439  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000d440  mov     rcx, rax; hModule
0x18000d443  call    cs:__imp_GetProcAddress
0x18000d449  mov     [rbx+10h], rax
0x18000d44d  mov     rax, [rbx+8]
0x18000d451  test    rax, rax
0x18000d454  jz      short loc_18000D469
0x18000d456  xor     r9d, r9d
0x18000d459  xor     r8d, r8d
0x18000d45c  mov     rdx, rdi
0x18000d45f  mov     rcx, [rbx]
0x18000d462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d467  jmp     short loc_18000D486
0x18000d469  mov     rax, [rbx+10h]
0x18000d46d  test    rax, rax
0x18000d470  jz      short loc_18000D47F
0x18000d472  mov     rdx, rdi
0x18000d475  mov     rcx, [rbx]
0x18000d478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d47d  jmp     short loc_18000D486
0x18000d47f  call    cs:__imp_GetLastError
0x18000d485  nop
0x18000d486  mov     rbx, [rsp+38h+arg_0]
0x18000d48b  add     rsp, 30h
0x18000d48f  pop     rdi
0x18000d490  retn
```
