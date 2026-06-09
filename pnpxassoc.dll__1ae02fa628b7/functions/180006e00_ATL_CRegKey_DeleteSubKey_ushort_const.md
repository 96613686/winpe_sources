# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006e00`
- end: `0x180006eb4`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800062a8`
- `0x1800077a8`
- `0x180007c4c`

## callees

- `0x180006e00`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006ea3`
- `KERNEL32!GetLastError` at `0x180006ea3`
- `KERNEL32!GetProcAddress` at `0x180006e3a`
- `KERNEL32!GetProcAddress` at `0x180006e67`
- `KERNEL32!GetProcAddress` at `0x180006e3a`
- `KERNEL32!GetProcAddress` at `0x180006e67`
- `KERNEL32!GetModuleHandleW` at `0x180006e25`
- `KERNEL32!GetModuleHandleW` at `0x180006e25`
- `KERNEL32!LoadLibraryExW` at `0x180006e52`
- `KERNEL32!LoadLibraryExW` at `0x180006e52`

## string_xrefs

- `0x180006e1e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006e30`: `RegDeleteKeyExW`
- `0x180006e49`: `advapi32.dll`
- `0x180006e5d`: `RegDeleteKeyW`

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
0x180006e00  mov     [rsp+arg_0], rbx
0x180006e05  push    rdi
0x180006e06  sub     rsp, 30h
0x180006e0a  cmp     qword ptr [rcx+8], 0
0x180006e0f  mov     rdi, rdx
0x180006e12  mov     rbx, rcx
0x180006e15  jnz     short loc_180006E71
0x180006e17  cmp     qword ptr [rcx+10h], 0
0x180006e1c  jnz     short loc_180006E71
0x180006e1e  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006e25  call    cs:__imp_GetModuleHandleW
0x180006e2b  test    rax, rax
0x180006e2e  jz      short loc_180006E46
0x180006e30  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180006e37  mov     rcx, rax; hModule
0x180006e3a  call    cs:__imp_GetProcAddress
0x180006e40  mov     [rbx+8], rax
0x180006e44  jmp     short loc_180006E71
0x180006e46  xor     r8d, r8d; dwFlags
0x180006e49  lea     rcx, LibFileName; "advapi32.dll"
0x180006e50  xor     edx, edx; hFile
0x180006e52  call    cs:__imp_LoadLibraryExW
0x180006e58  test    rax, rax
0x180006e5b  jz      short loc_180006E71
0x180006e5d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006e64  mov     rcx, rax; hModule
0x180006e67  call    cs:__imp_GetProcAddress
0x180006e6d  mov     [rbx+10h], rax
0x180006e71  mov     rax, [rbx+8]
0x180006e75  test    rax, rax
0x180006e78  jz      short loc_180006E8D
0x180006e7a  mov     rcx, [rbx]
0x180006e7d  xor     r9d, r9d
0x180006e80  xor     r8d, r8d
0x180006e83  mov     rdx, rdi
0x180006e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8b  jmp     short loc_180006EA9
0x180006e8d  mov     rax, [rbx+10h]
0x180006e91  test    rax, rax
0x180006e94  jz      short loc_180006EA3
0x180006e96  mov     rcx, [rbx]
0x180006e99  mov     rdx, rdi
0x180006e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea1  jmp     short loc_180006EA9
0x180006ea3  call    cs:__imp_GetLastError
0x180006ea9  mov     rbx, [rsp+38h+arg_0]
0x180006eae  add     rsp, 30h
0x180006eb2  pop     rdi
0x180006eb3  retn
```
