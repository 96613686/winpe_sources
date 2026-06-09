# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000c980`
- end: `0x18000ca31`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d348`
- `0x18000d764`

## callees

- `0x18000c980`
- `0x18000e738`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca20`

## string_xrefs

- `0x18000c99e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000c9b0`: `RegDeleteKeyExW`
- `0x18000c9c9`: `advapi32.dll`
- `0x18000c9da`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rdx
  HMODULE Library; // rax
  __int64 (__fastcall *v7)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v9)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = IsolationAwareLoadLibraryExW(L"advapi32.dll", v5, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v7 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v7 )
    return v7(*(_QWORD *)this, a2, 0, 0);
  v9 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v9 )
    return v9(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18000c980  mov     [rsp+arg_0], rbx
0x18000c985  push    rdi
0x18000c986  sub     rsp, 30h
0x18000c98a  cmp     qword ptr [rcx+8], 0
0x18000c98f  mov     rdi, rdx
0x18000c992  mov     rbx, rcx
0x18000c995  jnz     short loc_18000C9EE
0x18000c997  cmp     qword ptr [rcx+10h], 0
0x18000c99c  jnz     short loc_18000C9EE
0x18000c99e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000c9a5  call    cs:__imp_GetModuleHandleW
0x18000c9ab  test    rax, rax
0x18000c9ae  jz      short loc_18000C9C6
0x18000c9b0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000c9b7  mov     rcx, rax; hModule
0x18000c9ba  call    cs:__imp_GetProcAddress
0x18000c9c0  mov     [rbx+8], rax
0x18000c9c4  jmp     short loc_18000C9EE
0x18000c9c6  xor     r8d, r8d
0x18000c9c9  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18000c9d0  call    IsolationAwareLoadLibraryExW
0x18000c9d5  test    rax, rax
0x18000c9d8  jz      short loc_18000C9EE
0x18000c9da  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000c9e1  mov     rcx, rax; hModule
0x18000c9e4  call    cs:__imp_GetProcAddress
0x18000c9ea  mov     [rbx+10h], rax
0x18000c9ee  mov     rax, [rbx+8]
0x18000c9f2  test    rax, rax
0x18000c9f5  jz      short loc_18000CA0A
0x18000c9f7  mov     rcx, [rbx]
0x18000c9fa  xor     r9d, r9d
0x18000c9fd  xor     r8d, r8d
0x18000ca00  mov     rdx, rdi
0x18000ca03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca08  jmp     short loc_18000CA26
0x18000ca0a  mov     rax, [rbx+10h]
0x18000ca0e  test    rax, rax
0x18000ca11  jz      short loc_18000CA20
0x18000ca13  mov     rcx, [rbx]
0x18000ca16  mov     rdx, rdi
0x18000ca19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca1e  jmp     short loc_18000CA26
0x18000ca20  call    cs:__imp_GetLastError
0x18000ca26  mov     rbx, [rsp+38h+arg_0]
0x18000ca2b  add     rsp, 30h
0x18000ca2f  pop     rdi
0x18000ca30  retn
```
