# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000c05c`
- end: `0x18000c111`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180007214`
- `0x18000dcc8`
- `0x18000e1a8`

## callees

- `0x18000c05c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c0c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c0c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c081`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c081`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c0ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c0ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0ff`

## string_xrefs

- `0x18000c07a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000c08c`: `RegDeleteKeyExW`
- `0x18000c0a7`: `advapi32.dll`
- `0x18000c0b9`: `RegDeleteKeyW`

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
0x18000c05c  mov     [rsp+arg_0], rbx
0x18000c061  push    rdi
0x18000c062  sub     rsp, 30h
0x18000c066  mov     rdi, rdx
0x18000c069  mov     rbx, rcx
0x18000c06c  cmp     qword ptr [rcx+8], 0
0x18000c071  jnz     short loc_18000C0CD
0x18000c073  cmp     qword ptr [rcx+10h], 0
0x18000c078  jnz     short loc_18000C0CD
0x18000c07a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000c081  call    cs:__imp_GetModuleHandleW
0x18000c087  test    rax, rax
0x18000c08a  jz      short loc_18000C0A2
0x18000c08c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000c093  mov     rcx, rax; hModule
0x18000c096  call    cs:__imp_GetProcAddress
0x18000c09c  mov     [rbx+8], rax
0x18000c0a0  jmp     short loc_18000C0CD
0x18000c0a2  xor     r8d, r8d; dwFlags
0x18000c0a5  xor     edx, edx; hFile
0x18000c0a7  lea     rcx, LibFileName; "advapi32.dll"
0x18000c0ae  call    cs:__imp_LoadLibraryExW
0x18000c0b4  test    rax, rax
0x18000c0b7  jz      short loc_18000C0CD
0x18000c0b9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000c0c0  mov     rcx, rax; hModule
0x18000c0c3  call    cs:__imp_GetProcAddress
0x18000c0c9  mov     [rbx+10h], rax
0x18000c0cd  mov     rax, [rbx+8]
0x18000c0d1  test    rax, rax
0x18000c0d4  jz      short loc_18000C0E9
0x18000c0d6  xor     r9d, r9d
0x18000c0d9  xor     r8d, r8d
0x18000c0dc  mov     rdx, rdi
0x18000c0df  mov     rcx, [rbx]
0x18000c0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0e7  jmp     short loc_18000C106
0x18000c0e9  mov     rax, [rbx+10h]
0x18000c0ed  test    rax, rax
0x18000c0f0  jz      short loc_18000C0FF
0x18000c0f2  mov     rdx, rdi
0x18000c0f5  mov     rcx, [rbx]
0x18000c0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0fd  jmp     short loc_18000C106
0x18000c0ff  call    cs:__imp_GetLastError
0x18000c105  nop
0x18000c106  mov     rbx, [rsp+38h+arg_0]
0x18000c10b  add     rsp, 30h
0x18000c10f  pop     rdi
0x18000c110  retn
```
