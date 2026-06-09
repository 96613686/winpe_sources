# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800279cc`
- end: `0x180027a81`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180028c78`
- `0x1800290b0`

## callees

- `0x1800279cc`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027a33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027a33`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027a1e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027a1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800279f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800279f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a6f`

## string_xrefs

- `0x1800279ea`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800279fc`: `RegDeleteKeyExW`
- `0x180027a17`: `advapi32.dll`
- `0x180027a29`: `RegDeleteKeyW`

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
0x1800279cc  mov     [rsp+arg_0], rbx
0x1800279d1  push    rdi
0x1800279d2  sub     rsp, 30h
0x1800279d6  mov     rdi, rdx
0x1800279d9  mov     rbx, rcx
0x1800279dc  cmp     qword ptr [rcx+8], 0
0x1800279e1  jnz     short loc_180027A3D
0x1800279e3  cmp     qword ptr [rcx+10h], 0
0x1800279e8  jnz     short loc_180027A3D
0x1800279ea  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800279f1  call    cs:__imp_GetModuleHandleW
0x1800279f7  test    rax, rax
0x1800279fa  jz      short loc_180027A12
0x1800279fc  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180027a03  mov     rcx, rax; hModule
0x180027a06  call    cs:__imp_GetProcAddress
0x180027a0c  mov     [rbx+8], rax
0x180027a10  jmp     short loc_180027A3D
0x180027a12  xor     r8d, r8d; dwFlags
0x180027a15  xor     edx, edx; hFile
0x180027a17  lea     rcx, LibFileName; "advapi32.dll"
0x180027a1e  call    cs:__imp_LoadLibraryExW
0x180027a24  test    rax, rax
0x180027a27  jz      short loc_180027A3D
0x180027a29  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180027a30  mov     rcx, rax; hModule
0x180027a33  call    cs:__imp_GetProcAddress
0x180027a39  mov     [rbx+10h], rax
0x180027a3d  mov     rax, [rbx+8]
0x180027a41  test    rax, rax
0x180027a44  jz      short loc_180027A59
0x180027a46  xor     r9d, r9d
0x180027a49  xor     r8d, r8d
0x180027a4c  mov     rdx, rdi
0x180027a4f  mov     rcx, [rbx]
0x180027a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a57  jmp     short loc_180027A76
0x180027a59  mov     rax, [rbx+10h]
0x180027a5d  test    rax, rax
0x180027a60  jz      short loc_180027A6F
0x180027a62  mov     rdx, rdi
0x180027a65  mov     rcx, [rbx]
0x180027a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a6d  jmp     short loc_180027A76
0x180027a6f  call    cs:__imp_GetLastError
0x180027a75  nop
0x180027a76  mov     rbx, [rsp+38h+arg_0]
0x180027a7b  add     rsp, 30h
0x180027a7f  pop     rdi
0x180027a80  retn
```
