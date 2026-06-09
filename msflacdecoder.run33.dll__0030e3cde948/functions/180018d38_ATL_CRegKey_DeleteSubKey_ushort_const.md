# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180018d38`
- end: `0x180018ded`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180018020`
- `0x18001a2b8`
- `0x18001a8b0`

## callees

- `0x180018d38`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018d5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018d5d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018d8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018d8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018d72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018d9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018d72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ddb`

## string_xrefs

- `0x180018d56`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180018d68`: `RegDeleteKeyExW`
- `0x180018d83`: `advapi32.dll`
- `0x180018d95`: `RegDeleteKeyW`

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
0x180018d38  mov     [rsp+arg_0], rbx
0x180018d3d  push    rdi
0x180018d3e  sub     rsp, 30h
0x180018d42  mov     rdi, rdx
0x180018d45  mov     rbx, rcx
0x180018d48  cmp     qword ptr [rcx+8], 0
0x180018d4d  jnz     short loc_180018DA9
0x180018d4f  cmp     qword ptr [rcx+10h], 0
0x180018d54  jnz     short loc_180018DA9
0x180018d56  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180018d5d  call    cs:__imp_GetModuleHandleW
0x180018d63  test    rax, rax
0x180018d66  jz      short loc_180018D7E
0x180018d68  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180018d6f  mov     rcx, rax; hModule
0x180018d72  call    cs:__imp_GetProcAddress
0x180018d78  mov     [rbx+8], rax
0x180018d7c  jmp     short loc_180018DA9
0x180018d7e  xor     r8d, r8d; dwFlags
0x180018d81  xor     edx, edx; hFile
0x180018d83  lea     rcx, LibFileName; "advapi32.dll"
0x180018d8a  call    cs:__imp_LoadLibraryExW
0x180018d90  test    rax, rax
0x180018d93  jz      short loc_180018DA9
0x180018d95  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180018d9c  mov     rcx, rax; hModule
0x180018d9f  call    cs:__imp_GetProcAddress
0x180018da5  mov     [rbx+10h], rax
0x180018da9  mov     rax, [rbx+8]
0x180018dad  test    rax, rax
0x180018db0  jz      short loc_180018DC5
0x180018db2  xor     r9d, r9d
0x180018db5  xor     r8d, r8d
0x180018db8  mov     rdx, rdi
0x180018dbb  mov     rcx, [rbx]
0x180018dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dc3  jmp     short loc_180018DE2
0x180018dc5  mov     rax, [rbx+10h]
0x180018dc9  test    rax, rax
0x180018dcc  jz      short loc_180018DDB
0x180018dce  mov     rdx, rdi
0x180018dd1  mov     rcx, [rbx]
0x180018dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dd9  jmp     short loc_180018DE2
0x180018ddb  call    cs:__imp_GetLastError
0x180018de1  nop
0x180018de2  mov     rbx, [rsp+38h+arg_0]
0x180018de7  add     rsp, 30h
0x180018deb  pop     rdi
0x180018dec  retn
```
