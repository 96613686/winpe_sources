# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000c790`
- end: `0x18000c845`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000eae8`
- `0x18000efac`

## callees

- `0x18000c790`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c7e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c833`

## string_xrefs

- `0x18000c7ae`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000c7c0`: `RegDeleteKeyExW`
- `0x18000c7db`: `advapi32.dll`
- `0x18000c7ed`: `RegDeleteKeyW`

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
0x18000c790  mov     [rsp+arg_0], rbx
0x18000c795  push    rdi
0x18000c796  sub     rsp, 30h
0x18000c79a  mov     rdi, rdx
0x18000c79d  mov     rbx, rcx
0x18000c7a0  cmp     qword ptr [rcx+8], 0
0x18000c7a5  jnz     short loc_18000C801
0x18000c7a7  cmp     qword ptr [rcx+10h], 0
0x18000c7ac  jnz     short loc_18000C801
0x18000c7ae  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000c7b5  call    cs:__imp_GetModuleHandleW
0x18000c7bb  test    rax, rax
0x18000c7be  jz      short loc_18000C7D6
0x18000c7c0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000c7c7  mov     rcx, rax; hModule
0x18000c7ca  call    cs:__imp_GetProcAddress
0x18000c7d0  mov     [rbx+8], rax
0x18000c7d4  jmp     short loc_18000C801
0x18000c7d6  xor     r8d, r8d; dwFlags
0x18000c7d9  xor     edx, edx; hFile
0x18000c7db  lea     rcx, LibFileName; "advapi32.dll"
0x18000c7e2  call    cs:__imp_LoadLibraryExW
0x18000c7e8  test    rax, rax
0x18000c7eb  jz      short loc_18000C801
0x18000c7ed  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000c7f4  mov     rcx, rax; hModule
0x18000c7f7  call    cs:__imp_GetProcAddress
0x18000c7fd  mov     [rbx+10h], rax
0x18000c801  mov     rax, [rbx+8]
0x18000c805  test    rax, rax
0x18000c808  jz      short loc_18000C81D
0x18000c80a  xor     r9d, r9d
0x18000c80d  xor     r8d, r8d
0x18000c810  mov     rdx, rdi
0x18000c813  mov     rcx, [rbx]
0x18000c816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c81b  jmp     short loc_18000C83A
0x18000c81d  mov     rax, [rbx+10h]
0x18000c821  test    rax, rax
0x18000c824  jz      short loc_18000C833
0x18000c826  mov     rdx, rdi
0x18000c829  mov     rcx, [rbx]
0x18000c82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c831  jmp     short loc_18000C83A
0x18000c833  call    cs:__imp_GetLastError
0x18000c839  nop
0x18000c83a  mov     rbx, [rsp+38h+arg_0]
0x18000c83f  add     rsp, 30h
0x18000c843  pop     rdi
0x18000c844  retn
```
