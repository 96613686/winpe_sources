# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000f8e4`
- end: `0x18000f9b8`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001012c`
- `0x1800105a0`

## callees

- `0x18000f8e4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f909`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f909`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f942`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f942`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f924`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f95d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f924`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f99f`

## string_xrefs

- `0x18000f902`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000f91a`: `RegDeleteKeyExW`
- `0x18000f93b`: `advapi32.dll`
- `0x18000f953`: `RegDeleteKeyW`

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
0x18000f8e4  mov     [rsp+arg_0], rbx
0x18000f8e9  push    rdi
0x18000f8ea  sub     rsp, 30h
0x18000f8ee  mov     rdi, rdx
0x18000f8f1  mov     rbx, rcx
0x18000f8f4  cmp     qword ptr [rcx+8], 0
0x18000f8f9  jnz     short loc_18000F96D
0x18000f8fb  cmp     qword ptr [rcx+10h], 0
0x18000f900  jnz     short loc_18000F96D
0x18000f902  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000f909  call    cs:__imp_GetModuleHandleW
0x18000f910  nop     dword ptr [rax+rax+00h]
0x18000f915  test    rax, rax
0x18000f918  jz      short loc_18000F936
0x18000f91a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000f921  mov     rcx, rax; hModule
0x18000f924  call    cs:__imp_GetProcAddress
0x18000f92b  nop     dword ptr [rax+rax+00h]
0x18000f930  mov     [rbx+8], rax
0x18000f934  jmp     short loc_18000F96D
0x18000f936  xor     r8d, r8d; dwFlags
0x18000f939  xor     edx, edx; hFile
0x18000f93b  lea     rcx, LibFileName; "advapi32.dll"
0x18000f942  call    cs:__imp_LoadLibraryExW
0x18000f949  nop     dword ptr [rax+rax+00h]
0x18000f94e  test    rax, rax
0x18000f951  jz      short loc_18000F96D
0x18000f953  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000f95a  mov     rcx, rax; hModule
0x18000f95d  call    cs:__imp_GetProcAddress
0x18000f964  nop     dword ptr [rax+rax+00h]
0x18000f969  mov     [rbx+10h], rax
0x18000f96d  mov     rax, [rbx+8]
0x18000f971  test    rax, rax
0x18000f974  jz      short loc_18000F989
0x18000f976  xor     r9d, r9d
0x18000f979  xor     r8d, r8d
0x18000f97c  mov     rdx, rdi
0x18000f97f  mov     rcx, [rbx]
0x18000f982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f987  jmp     short loc_18000F9AC
0x18000f989  mov     rax, [rbx+10h]
0x18000f98d  test    rax, rax
0x18000f990  jz      short loc_18000F99F
0x18000f992  mov     rdx, rdi
0x18000f995  mov     rcx, [rbx]
0x18000f998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f99d  jmp     short loc_18000F9AC
0x18000f99f  call    cs:__imp_GetLastError
0x18000f9a6  nop     dword ptr [rax+rax+00h]
0x18000f9ab  nop
0x18000f9ac  mov     rbx, [rsp+38h+arg_0]
0x18000f9b1  add     rsp, 30h
0x18000f9b5  pop     rdi
0x18000f9b6  retn
```
