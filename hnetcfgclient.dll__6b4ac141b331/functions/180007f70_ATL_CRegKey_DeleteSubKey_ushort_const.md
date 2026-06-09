# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180007f70`
- end: `0x180008025`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800076f8`
- `0x180008998`
- `0x180008e68`

## callees

- `0x180007f70`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f95`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007fc2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007fc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007fd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008013`

## string_xrefs

- `0x180007f8e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180007fa0`: `RegDeleteKeyExW`
- `0x180007fbb`: `advapi32.dll`
- `0x180007fcd`: `RegDeleteKeyW`

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
0x180007f70  mov     [rsp+arg_0], rbx
0x180007f75  push    rdi
0x180007f76  sub     rsp, 30h
0x180007f7a  mov     rdi, rdx
0x180007f7d  mov     rbx, rcx
0x180007f80  cmp     qword ptr [rcx+8], 0
0x180007f85  jnz     short loc_180007FE1
0x180007f87  cmp     qword ptr [rcx+10h], 0
0x180007f8c  jnz     short loc_180007FE1
0x180007f8e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180007f95  call    cs:__imp_GetModuleHandleW
0x180007f9b  test    rax, rax
0x180007f9e  jz      short loc_180007FB6
0x180007fa0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180007fa7  mov     rcx, rax; hModule
0x180007faa  call    cs:__imp_GetProcAddress
0x180007fb0  mov     [rbx+8], rax
0x180007fb4  jmp     short loc_180007FE1
0x180007fb6  xor     r8d, r8d; dwFlags
0x180007fb9  xor     edx, edx; hFile
0x180007fbb  lea     rcx, LibFileName; "advapi32.dll"
0x180007fc2  call    cs:__imp_LoadLibraryExW
0x180007fc8  test    rax, rax
0x180007fcb  jz      short loc_180007FE1
0x180007fcd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180007fd4  mov     rcx, rax; hModule
0x180007fd7  call    cs:__imp_GetProcAddress
0x180007fdd  mov     [rbx+10h], rax
0x180007fe1  mov     rax, [rbx+8]
0x180007fe5  test    rax, rax
0x180007fe8  jz      short loc_180007FFD
0x180007fea  xor     r9d, r9d
0x180007fed  xor     r8d, r8d
0x180007ff0  mov     rdx, rdi
0x180007ff3  mov     rcx, [rbx]
0x180007ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ffb  jmp     short loc_18000801A
0x180007ffd  mov     rax, [rbx+10h]
0x180008001  test    rax, rax
0x180008004  jz      short loc_180008013
0x180008006  mov     rdx, rdi
0x180008009  mov     rcx, [rbx]
0x18000800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008011  jmp     short loc_18000801A
0x180008013  call    cs:__imp_GetLastError
0x180008019  nop
0x18000801a  mov     rbx, [rsp+38h+arg_0]
0x18000801f  add     rsp, 30h
0x180008023  pop     rdi
0x180008024  retn
```
