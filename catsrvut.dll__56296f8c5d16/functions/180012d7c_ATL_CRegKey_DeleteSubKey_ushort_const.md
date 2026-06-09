# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180012d7c`
- end: `0x180012e30`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a980`
- `0x18001405c`

## callees

- `0x180012d7c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012da1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012da1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012dce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012dce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012db6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012de3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012db6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e1f`

## string_xrefs

- `0x180012d9a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180012dac`: `RegDeleteKeyExW`
- `0x180012dc5`: `advapi32.dll`
- `0x180012dd9`: `RegDeleteKeyW`

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
0x180012d7c  mov     [rsp+arg_0], rbx
0x180012d81  push    rdi
0x180012d82  sub     rsp, 30h
0x180012d86  cmp     qword ptr [rcx+8], 0
0x180012d8b  mov     rdi, rdx
0x180012d8e  mov     rbx, rcx
0x180012d91  jnz     short loc_180012DED
0x180012d93  cmp     qword ptr [rcx+10h], 0
0x180012d98  jnz     short loc_180012DED
0x180012d9a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180012da1  call    cs:__imp_GetModuleHandleW
0x180012da7  test    rax, rax
0x180012daa  jz      short loc_180012DC2
0x180012dac  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180012db3  mov     rcx, rax; hModule
0x180012db6  call    cs:__imp_GetProcAddress
0x180012dbc  mov     [rbx+8], rax
0x180012dc0  jmp     short loc_180012DED
0x180012dc2  xor     r8d, r8d; dwFlags
0x180012dc5  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180012dcc  xor     edx, edx; hFile
0x180012dce  call    cs:__imp_LoadLibraryExW
0x180012dd4  test    rax, rax
0x180012dd7  jz      short loc_180012DED
0x180012dd9  lea     rdx, aRegdeletekeyw_0; "RegDeleteKeyW"
0x180012de0  mov     rcx, rax; hModule
0x180012de3  call    cs:__imp_GetProcAddress
0x180012de9  mov     [rbx+10h], rax
0x180012ded  mov     rax, [rbx+8]
0x180012df1  test    rax, rax
0x180012df4  jz      short loc_180012E09
0x180012df6  mov     rcx, [rbx]
0x180012df9  xor     r9d, r9d
0x180012dfc  xor     r8d, r8d
0x180012dff  mov     rdx, rdi
0x180012e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e07  jmp     short loc_180012E25
0x180012e09  mov     rax, [rbx+10h]
0x180012e0d  test    rax, rax
0x180012e10  jz      short loc_180012E1F
0x180012e12  mov     rcx, [rbx]
0x180012e15  mov     rdx, rdi
0x180012e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e1d  jmp     short loc_180012E25
0x180012e1f  call    cs:__imp_GetLastError
0x180012e25  mov     rbx, [rsp+38h+arg_0]
0x180012e2a  add     rsp, 30h
0x180012e2e  pop     rdi
0x180012e2f  retn
```
