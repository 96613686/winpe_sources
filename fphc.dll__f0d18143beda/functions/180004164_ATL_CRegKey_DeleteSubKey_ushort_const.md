# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004164`
- end: `0x180004219`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000399c`
- `0x1800047a8`
- `0x180004c68`

## callees

- `0x180004164`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800041b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800041b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000419e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000419e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004189`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004207`

## string_xrefs

- `0x180004182`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004194`: `RegDeleteKeyExW`
- `0x1800041af`: `advapi32.dll`
- `0x1800041c1`: `RegDeleteKeyW`

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
0x180004164  mov     [rsp+arg_0], rbx
0x180004169  push    rdi
0x18000416a  sub     rsp, 30h
0x18000416e  mov     rdi, rdx
0x180004171  mov     rbx, rcx
0x180004174  cmp     qword ptr [rcx+8], 0
0x180004179  jnz     short loc_1800041D5
0x18000417b  cmp     qword ptr [rcx+10h], 0
0x180004180  jnz     short loc_1800041D5
0x180004182  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004189  call    cs:__imp_GetModuleHandleW
0x18000418f  test    rax, rax
0x180004192  jz      short loc_1800041AA
0x180004194  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000419b  mov     rcx, rax; hModule
0x18000419e  call    cs:__imp_GetProcAddress
0x1800041a4  mov     [rbx+8], rax
0x1800041a8  jmp     short loc_1800041D5
0x1800041aa  xor     r8d, r8d; dwFlags
0x1800041ad  xor     edx, edx; hFile
0x1800041af  lea     rcx, LibFileName; "advapi32.dll"
0x1800041b6  call    cs:__imp_LoadLibraryExW
0x1800041bc  test    rax, rax
0x1800041bf  jz      short loc_1800041D5
0x1800041c1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800041c8  mov     rcx, rax; hModule
0x1800041cb  call    cs:__imp_GetProcAddress
0x1800041d1  mov     [rbx+10h], rax
0x1800041d5  mov     rax, [rbx+8]
0x1800041d9  test    rax, rax
0x1800041dc  jz      short loc_1800041F1
0x1800041de  xor     r9d, r9d
0x1800041e1  xor     r8d, r8d
0x1800041e4  mov     rdx, rdi
0x1800041e7  mov     rcx, [rbx]
0x1800041ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ef  jmp     short loc_18000420E
0x1800041f1  mov     rax, [rbx+10h]
0x1800041f5  test    rax, rax
0x1800041f8  jz      short loc_180004207
0x1800041fa  mov     rdx, rdi
0x1800041fd  mov     rcx, [rbx]
0x180004200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004205  jmp     short loc_18000420E
0x180004207  call    cs:__imp_GetLastError
0x18000420d  nop
0x18000420e  mov     rbx, [rsp+38h+arg_0]
0x180004213  add     rsp, 30h
0x180004217  pop     rdi
0x180004218  retn
```
