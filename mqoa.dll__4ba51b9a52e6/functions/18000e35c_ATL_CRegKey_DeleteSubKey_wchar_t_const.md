# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000e35c`
- end: `0x18000e410`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180011038`
- `0x180011504`

## callees

- `0x18000e35c`
- `0x180029010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e3ff`
- `KERNEL32!GetLastError` at `0x18000e3ff`
- `KERNEL32!GetModuleHandleW` at `0x18000e381`
- `KERNEL32!GetModuleHandleW` at `0x18000e381`
- `KERNEL32!GetProcAddress` at `0x18000e396`
- `KERNEL32!GetProcAddress` at `0x18000e3c3`
- `KERNEL32!GetProcAddress` at `0x18000e396`
- `KERNEL32!GetProcAddress` at `0x18000e3c3`
- `KERNEL32!LoadLibraryExW` at `0x18000e3ae`
- `KERNEL32!LoadLibraryExW` at `0x18000e3ae`

## string_xrefs

- `0x18000e37a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000e38c`: `RegDeleteKeyExW`
- `0x18000e3a5`: `advapi32.dll`
- `0x18000e3b9`: `RegDeleteKeyW`

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
0x18000e35c  mov     [rsp+arg_0], rbx
0x18000e361  push    rdi
0x18000e362  sub     rsp, 30h
0x18000e366  cmp     qword ptr [rcx+8], 0
0x18000e36b  mov     rdi, rdx
0x18000e36e  mov     rbx, rcx
0x18000e371  jnz     short loc_18000E3CD
0x18000e373  cmp     qword ptr [rcx+10h], 0
0x18000e378  jnz     short loc_18000E3CD
0x18000e37a  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000e381  call    cs:__imp_GetModuleHandleW
0x18000e387  test    rax, rax
0x18000e38a  jz      short loc_18000E3A2
0x18000e38c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000e393  mov     rcx, rax; hModule
0x18000e396  call    cs:__imp_GetProcAddress
0x18000e39c  mov     [rbx+8], rax
0x18000e3a0  jmp     short loc_18000E3CD
0x18000e3a2  xor     r8d, r8d; dwFlags
0x18000e3a5  lea     rcx, LibFileName; "advapi32.dll"
0x18000e3ac  xor     edx, edx; hFile
0x18000e3ae  call    cs:__imp_LoadLibraryExW
0x18000e3b4  test    rax, rax
0x18000e3b7  jz      short loc_18000E3CD
0x18000e3b9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000e3c0  mov     rcx, rax; hModule
0x18000e3c3  call    cs:__imp_GetProcAddress
0x18000e3c9  mov     [rbx+10h], rax
0x18000e3cd  mov     rax, [rbx+8]
0x18000e3d1  test    rax, rax
0x18000e3d4  jz      short loc_18000E3E9
0x18000e3d6  mov     rcx, [rbx]
0x18000e3d9  xor     r9d, r9d
0x18000e3dc  xor     r8d, r8d
0x18000e3df  mov     rdx, rdi
0x18000e3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e7  jmp     short loc_18000E405
0x18000e3e9  mov     rax, [rbx+10h]
0x18000e3ed  test    rax, rax
0x18000e3f0  jz      short loc_18000E3FF
0x18000e3f2  mov     rcx, [rbx]
0x18000e3f5  mov     rdx, rdi
0x18000e3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3fd  jmp     short loc_18000E405
0x18000e3ff  call    cs:__imp_GetLastError
0x18000e405  mov     rbx, [rsp+38h+arg_0]
0x18000e40a  add     rsp, 30h
0x18000e40e  pop     rdi
0x18000e40f  retn
```
