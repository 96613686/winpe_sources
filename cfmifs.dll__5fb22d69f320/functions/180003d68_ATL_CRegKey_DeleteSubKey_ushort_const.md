# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180003d68`
- end: `0x180003e1c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800034c0`
- `0x180004538`
- `0x1800049dc`

## callees

- `0x180003d68`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003da2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003dcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003da2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003dcf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003dba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003dba`

## string_xrefs

- `0x180003d86`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003d98`: `RegDeleteKeyExW`
- `0x180003db1`: `advapi32.dll`
- `0x180003dc5`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

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
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180003d68  mov     [rsp+arg_0], rbx
0x180003d6d  push    rdi
0x180003d6e  sub     rsp, 30h
0x180003d72  cmp     qword ptr [rcx+8], 0
0x180003d77  mov     rdi, rdx
0x180003d7a  mov     rbx, rcx
0x180003d7d  jnz     short loc_180003DD9
0x180003d7f  cmp     qword ptr [rcx+10h], 0
0x180003d84  jnz     short loc_180003DD9
0x180003d86  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003d8d  call    cs:__imp_GetModuleHandleW
0x180003d93  test    rax, rax
0x180003d96  jz      short loc_180003DAE
0x180003d98  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180003d9f  mov     rcx, rax; hModule
0x180003da2  call    cs:__imp_GetProcAddress
0x180003da8  mov     [rbx+8], rax
0x180003dac  jmp     short loc_180003DD9
0x180003dae  xor     r8d, r8d; dwFlags
0x180003db1  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180003db8  xor     edx, edx; hFile
0x180003dba  call    cs:__imp_LoadLibraryExW
0x180003dc0  test    rax, rax
0x180003dc3  jz      short loc_180003DD9
0x180003dc5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180003dcc  mov     rcx, rax; hModule
0x180003dcf  call    cs:__imp_GetProcAddress
0x180003dd5  mov     [rbx+10h], rax
0x180003dd9  mov     rax, [rbx+8]
0x180003ddd  test    rax, rax
0x180003de0  jz      short loc_180003DF5
0x180003de2  mov     rcx, [rbx]
0x180003de5  xor     r9d, r9d
0x180003de8  xor     r8d, r8d
0x180003deb  mov     rdx, rdi
0x180003dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df3  jmp     short loc_180003E11
0x180003df5  mov     rax, [rbx+10h]
0x180003df9  test    rax, rax
0x180003dfc  jz      short loc_180003E0B
0x180003dfe  mov     rcx, [rbx]
0x180003e01  mov     rdx, rdi
0x180003e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e09  jmp     short loc_180003E11
0x180003e0b  call    cs:__imp_GetLastError
0x180003e11  mov     rbx, [rsp+38h+arg_0]
0x180003e16  add     rsp, 30h
0x180003e1a  pop     rdi
0x180003e1b  retn
```
