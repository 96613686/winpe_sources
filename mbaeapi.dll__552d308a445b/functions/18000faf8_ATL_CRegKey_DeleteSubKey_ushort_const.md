# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000faf8`
- end: `0x18000fbad`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e5a0`
- `0x180011608`
- `0x180011ac8`

## callees

- `0x18000faf8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fb4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fb4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fb1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fb1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb9b`

## string_xrefs

- `0x18000fb16`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000fb28`: `RegDeleteKeyExW`
- `0x18000fb43`: `advapi32.dll`
- `0x18000fb55`: `RegDeleteKeyW`

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
0x18000faf8  mov     [rsp+arg_0], rbx
0x18000fafd  push    rdi
0x18000fafe  sub     rsp, 30h
0x18000fb02  mov     rdi, rdx
0x18000fb05  mov     rbx, rcx
0x18000fb08  cmp     qword ptr [rcx+8], 0
0x18000fb0d  jnz     short loc_18000FB69
0x18000fb0f  cmp     qword ptr [rcx+10h], 0
0x18000fb14  jnz     short loc_18000FB69
0x18000fb16  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000fb1d  call    cs:__imp_GetModuleHandleW
0x18000fb23  test    rax, rax
0x18000fb26  jz      short loc_18000FB3E
0x18000fb28  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000fb2f  mov     rcx, rax; hModule
0x18000fb32  call    cs:__imp_GetProcAddress
0x18000fb38  mov     [rbx+8], rax
0x18000fb3c  jmp     short loc_18000FB69
0x18000fb3e  xor     r8d, r8d; dwFlags
0x18000fb41  xor     edx, edx; hFile
0x18000fb43  lea     rcx, LibFileName; "advapi32.dll"
0x18000fb4a  call    cs:__imp_LoadLibraryExW
0x18000fb50  test    rax, rax
0x18000fb53  jz      short loc_18000FB69
0x18000fb55  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000fb5c  mov     rcx, rax; hModule
0x18000fb5f  call    cs:__imp_GetProcAddress
0x18000fb65  mov     [rbx+10h], rax
0x18000fb69  mov     rax, [rbx+8]
0x18000fb6d  test    rax, rax
0x18000fb70  jz      short loc_18000FB85
0x18000fb72  xor     r9d, r9d
0x18000fb75  xor     r8d, r8d
0x18000fb78  mov     rdx, rdi
0x18000fb7b  mov     rcx, [rbx]
0x18000fb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb83  jmp     short loc_18000FBA2
0x18000fb85  mov     rax, [rbx+10h]
0x18000fb89  test    rax, rax
0x18000fb8c  jz      short loc_18000FB9B
0x18000fb8e  mov     rdx, rdi
0x18000fb91  mov     rcx, [rbx]
0x18000fb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb99  jmp     short loc_18000FBA2
0x18000fb9b  call    cs:__imp_GetLastError
0x18000fba1  nop
0x18000fba2  mov     rbx, [rsp+38h+arg_0]
0x18000fba7  add     rsp, 30h
0x18000fbab  pop     rdi
0x18000fbac  retn
```
