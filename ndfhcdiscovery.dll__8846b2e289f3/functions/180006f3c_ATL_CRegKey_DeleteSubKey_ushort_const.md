# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006f3c`
- end: `0x180007010`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180008b8c`
- `0x180009108`
- `0x180012560`

## callees

- `0x180006f3c`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006f7c`
- `KERNEL32!GetProcAddress` at `0x180006fb5`
- `KERNEL32!GetProcAddress` at `0x180006f7c`
- `KERNEL32!GetProcAddress` at `0x180006fb5`
- `KERNEL32!GetModuleHandleW` at `0x180006f61`
- `KERNEL32!GetModuleHandleW` at `0x180006f61`
- `KERNEL32!GetLastError` at `0x180006ff7`
- `KERNEL32!GetLastError` at `0x180006ff7`
- `KERNEL32!LoadLibraryExW` at `0x180006f9a`
- `KERNEL32!LoadLibraryExW` at `0x180006f9a`

## string_xrefs

- `0x180006f5a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006f72`: `RegDeleteKeyExW`
- `0x180006f93`: `advapi32.dll`
- `0x180006fab`: `RegDeleteKeyW`

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
0x180006f3c  mov     [rsp+arg_0], rbx
0x180006f41  push    rdi
0x180006f42  sub     rsp, 30h
0x180006f46  mov     rdi, rdx
0x180006f49  mov     rbx, rcx
0x180006f4c  cmp     qword ptr [rcx+8], 0
0x180006f51  jnz     short loc_180006FC5
0x180006f53  cmp     qword ptr [rcx+10h], 0
0x180006f58  jnz     short loc_180006FC5
0x180006f5a  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006f61  call    cs:__imp_GetModuleHandleW
0x180006f68  nop     dword ptr [rax+rax+00h]
0x180006f6d  test    rax, rax
0x180006f70  jz      short loc_180006F8E
0x180006f72  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180006f79  mov     rcx, rax; hModule
0x180006f7c  call    cs:__imp_GetProcAddress
0x180006f83  nop     dword ptr [rax+rax+00h]
0x180006f88  mov     [rbx+8], rax
0x180006f8c  jmp     short loc_180006FC5
0x180006f8e  xor     r8d, r8d; dwFlags
0x180006f91  xor     edx, edx; hFile
0x180006f93  lea     rcx, LibFileName; "advapi32.dll"
0x180006f9a  call    cs:__imp_LoadLibraryExW
0x180006fa1  nop     dword ptr [rax+rax+00h]
0x180006fa6  test    rax, rax
0x180006fa9  jz      short loc_180006FC5
0x180006fab  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006fb2  mov     rcx, rax; hModule
0x180006fb5  call    cs:__imp_GetProcAddress
0x180006fbc  nop     dword ptr [rax+rax+00h]
0x180006fc1  mov     [rbx+10h], rax
0x180006fc5  mov     rax, [rbx+8]
0x180006fc9  test    rax, rax
0x180006fcc  jz      short loc_180006FE1
0x180006fce  xor     r9d, r9d
0x180006fd1  xor     r8d, r8d
0x180006fd4  mov     rdx, rdi
0x180006fd7  mov     rcx, [rbx]
0x180006fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fdf  jmp     short loc_180007004
0x180006fe1  mov     rax, [rbx+10h]
0x180006fe5  test    rax, rax
0x180006fe8  jz      short loc_180006FF7
0x180006fea  mov     rdx, rdi
0x180006fed  mov     rcx, [rbx]
0x180006ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff5  jmp     short loc_180007004
0x180006ff7  call    cs:__imp_GetLastError
0x180006ffe  nop     dword ptr [rax+rax+00h]
0x180007003  nop
0x180007004  mov     rbx, [rsp+38h+arg_0]
0x180007009  add     rsp, 30h
0x18000700d  pop     rdi
0x18000700e  retn
```
