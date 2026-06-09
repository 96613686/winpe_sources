# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180016000`
- end: `0x1800160b4`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f2b4`
- `0x180016e48`

## callees

- `0x180016000`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016025`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016025`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001603a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016067`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001603a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016067`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016052`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160a3`

## string_xrefs

- `0x18001601e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180016030`: `RegDeleteKeyExW`
- `0x180016049`: `advapi32.dll`
- `0x18001605d`: `RegDeleteKeyW`

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
0x180016000  mov     [rsp+arg_0], rbx
0x180016005  push    rdi
0x180016006  sub     rsp, 30h
0x18001600a  cmp     qword ptr [rcx+8], 0
0x18001600f  mov     rdi, rdx
0x180016012  mov     rbx, rcx
0x180016015  jnz     short loc_180016071
0x180016017  cmp     qword ptr [rcx+10h], 0
0x18001601c  jnz     short loc_180016071
0x18001601e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180016025  call    cs:__imp_GetModuleHandleW
0x18001602b  test    rax, rax
0x18001602e  jz      short loc_180016046
0x180016030  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180016037  mov     rcx, rax; hModule
0x18001603a  call    cs:__imp_GetProcAddress
0x180016040  mov     [rbx+8], rax
0x180016044  jmp     short loc_180016071
0x180016046  xor     r8d, r8d; dwFlags
0x180016049  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180016050  xor     edx, edx; hFile
0x180016052  call    cs:__imp_LoadLibraryExW
0x180016058  test    rax, rax
0x18001605b  jz      short loc_180016071
0x18001605d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180016064  mov     rcx, rax; hModule
0x180016067  call    cs:__imp_GetProcAddress
0x18001606d  mov     [rbx+10h], rax
0x180016071  mov     rax, [rbx+8]
0x180016075  test    rax, rax
0x180016078  jz      short loc_18001608D
0x18001607a  mov     rcx, [rbx]
0x18001607d  xor     r9d, r9d
0x180016080  xor     r8d, r8d
0x180016083  mov     rdx, rdi
0x180016086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001608b  jmp     short loc_1800160A9
0x18001608d  mov     rax, [rbx+10h]
0x180016091  test    rax, rax
0x180016094  jz      short loc_1800160A3
0x180016096  mov     rcx, [rbx]
0x180016099  mov     rdx, rdi
0x18001609c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160a1  jmp     short loc_1800160A9
0x1800160a3  call    cs:__imp_GetLastError
0x1800160a9  mov     rbx, [rsp+38h+arg_0]
0x1800160ae  add     rsp, 30h
0x1800160b2  pop     rdi
0x1800160b3  retn
```
