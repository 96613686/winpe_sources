# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000fd78`
- end: `0x18000fe2d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000eb5c`
- `0x180010dc8`
- `0x180011384`

## callees

- `0x18000fd78`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fe1b`
- `KERNEL32!GetLastError` at `0x18000fe1b`
- `KERNEL32!GetProcAddress` at `0x18000fdb2`
- `KERNEL32!GetProcAddress` at `0x18000fddf`
- `KERNEL32!GetProcAddress` at `0x18000fdb2`
- `KERNEL32!GetProcAddress` at `0x18000fddf`
- `KERNEL32!GetModuleHandleW` at `0x18000fd9d`
- `KERNEL32!GetModuleHandleW` at `0x18000fd9d`
- `KERNEL32!LoadLibraryExW` at `0x18000fdca`
- `KERNEL32!LoadLibraryExW` at `0x18000fdca`

## string_xrefs

- `0x18000fd96`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000fda8`: `RegDeleteKeyExW`
- `0x18000fdc3`: `advapi32.dll`
- `0x18000fdd5`: `RegDeleteKeyW`

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
0x18000fd78  mov     [rsp+arg_0], rbx
0x18000fd7d  push    rdi
0x18000fd7e  sub     rsp, 30h
0x18000fd82  mov     rdi, rdx
0x18000fd85  mov     rbx, rcx
0x18000fd88  cmp     qword ptr [rcx+8], 0
0x18000fd8d  jnz     short loc_18000FDE9
0x18000fd8f  cmp     qword ptr [rcx+10h], 0
0x18000fd94  jnz     short loc_18000FDE9
0x18000fd96  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000fd9d  call    cs:__imp_GetModuleHandleW
0x18000fda3  test    rax, rax
0x18000fda6  jz      short loc_18000FDBE
0x18000fda8  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000fdaf  mov     rcx, rax; hModule
0x18000fdb2  call    cs:__imp_GetProcAddress
0x18000fdb8  mov     [rbx+8], rax
0x18000fdbc  jmp     short loc_18000FDE9
0x18000fdbe  xor     r8d, r8d; dwFlags
0x18000fdc1  xor     edx, edx; hFile
0x18000fdc3  lea     rcx, LibFileName; "advapi32.dll"
0x18000fdca  call    cs:__imp_LoadLibraryExW
0x18000fdd0  test    rax, rax
0x18000fdd3  jz      short loc_18000FDE9
0x18000fdd5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000fddc  mov     rcx, rax; hModule
0x18000fddf  call    cs:__imp_GetProcAddress
0x18000fde5  mov     [rbx+10h], rax
0x18000fde9  mov     rax, [rbx+8]
0x18000fded  test    rax, rax
0x18000fdf0  jz      short loc_18000FE05
0x18000fdf2  xor     r9d, r9d
0x18000fdf5  xor     r8d, r8d
0x18000fdf8  mov     rdx, rdi
0x18000fdfb  mov     rcx, [rbx]
0x18000fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe03  jmp     short loc_18000FE22
0x18000fe05  mov     rax, [rbx+10h]
0x18000fe09  test    rax, rax
0x18000fe0c  jz      short loc_18000FE1B
0x18000fe0e  mov     rdx, rdi
0x18000fe11  mov     rcx, [rbx]
0x18000fe14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe19  jmp     short loc_18000FE22
0x18000fe1b  call    cs:__imp_GetLastError
0x18000fe21  nop
0x18000fe22  mov     rbx, [rsp+38h+arg_0]
0x18000fe27  add     rsp, 30h
0x18000fe2b  pop     rdi
0x18000fe2c  retn
```
