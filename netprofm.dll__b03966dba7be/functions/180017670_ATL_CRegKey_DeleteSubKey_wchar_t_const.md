# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x180017670`
- end: `0x180017725`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001690c`

## callees

- `0x180017670`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800176c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800176c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017695`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017695`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800176aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800176d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800176aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800176d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017713`

## string_xrefs

- `0x18001768e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800176a0`: `RegDeleteKeyExW`
- `0x1800176bb`: `advapi32.dll`
- `0x1800176cd`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
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
0x180017670  mov     [rsp+arg_0], rbx
0x180017675  push    rdi
0x180017676  sub     rsp, 30h
0x18001767a  mov     rdi, rdx
0x18001767d  mov     rbx, rcx
0x180017680  cmp     qword ptr [rcx+8], 0
0x180017685  jnz     short loc_1800176E1
0x180017687  cmp     qword ptr [rcx+10h], 0
0x18001768c  jnz     short loc_1800176E1
0x18001768e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180017695  call    cs:__imp_GetModuleHandleW
0x18001769b  test    rax, rax
0x18001769e  jz      short loc_1800176B6
0x1800176a0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800176a7  mov     rcx, rax; hModule
0x1800176aa  call    cs:__imp_GetProcAddress
0x1800176b0  mov     [rbx+8], rax
0x1800176b4  jmp     short loc_1800176E1
0x1800176b6  xor     r8d, r8d; dwFlags
0x1800176b9  xor     edx, edx; hFile
0x1800176bb  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800176c2  call    cs:__imp_LoadLibraryExW
0x1800176c8  test    rax, rax
0x1800176cb  jz      short loc_1800176E1
0x1800176cd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800176d4  mov     rcx, rax; hModule
0x1800176d7  call    cs:__imp_GetProcAddress
0x1800176dd  mov     [rbx+10h], rax
0x1800176e1  mov     rax, [rbx+8]
0x1800176e5  test    rax, rax
0x1800176e8  jz      short loc_1800176FD
0x1800176ea  xor     r9d, r9d
0x1800176ed  xor     r8d, r8d
0x1800176f0  mov     rdx, rdi
0x1800176f3  mov     rcx, [rbx]
0x1800176f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176fb  jmp     short loc_18001771A
0x1800176fd  mov     rax, [rbx+10h]
0x180017701  test    rax, rax
0x180017704  jz      short loc_180017713
0x180017706  mov     rdx, rdi
0x180017709  mov     rcx, [rbx]
0x18001770c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017711  jmp     short loc_18001771A
0x180017713  call    cs:__imp_GetLastError
0x180017719  nop
0x18001771a  mov     rbx, [rsp+38h+arg_0]
0x18001771f  add     rsp, 30h
0x180017723  pop     rdi
0x180017724  retn
```
