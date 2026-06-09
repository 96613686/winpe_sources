# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180014aac`
- end: `0x180014b61`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016038`
- `0x18001646c`

## callees

- `0x180014aac`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014ae6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014b13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014ae6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014b13`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014afe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014ad1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b4f`

## string_xrefs

- `0x180014aca`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180014adc`: `RegDeleteKeyExW`
- `0x180014af7`: `advapi32.dll`
- `0x180014b09`: `RegDeleteKeyW`

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
0x180014aac  mov     [rsp+arg_0], rbx
0x180014ab1  push    rdi
0x180014ab2  sub     rsp, 30h
0x180014ab6  mov     rdi, rdx
0x180014ab9  mov     rbx, rcx
0x180014abc  cmp     qword ptr [rcx+8], 0
0x180014ac1  jnz     short loc_180014B1D
0x180014ac3  cmp     qword ptr [rcx+10h], 0
0x180014ac8  jnz     short loc_180014B1D
0x180014aca  lea     rcx, aApiMsWinCoreLo_3; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180014ad1  call    cs:__imp_GetModuleHandleW
0x180014ad7  test    rax, rax
0x180014ada  jz      short loc_180014AF2
0x180014adc  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180014ae3  mov     rcx, rax; hModule
0x180014ae6  call    cs:__imp_GetProcAddress
0x180014aec  mov     [rbx+8], rax
0x180014af0  jmp     short loc_180014B1D
0x180014af2  xor     r8d, r8d; dwFlags
0x180014af5  xor     edx, edx; hFile
0x180014af7  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180014afe  call    cs:__imp_LoadLibraryExW
0x180014b04  test    rax, rax
0x180014b07  jz      short loc_180014B1D
0x180014b09  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180014b10  mov     rcx, rax; hModule
0x180014b13  call    cs:__imp_GetProcAddress
0x180014b19  mov     [rbx+10h], rax
0x180014b1d  mov     rax, [rbx+8]
0x180014b21  test    rax, rax
0x180014b24  jz      short loc_180014B39
0x180014b26  xor     r9d, r9d
0x180014b29  xor     r8d, r8d
0x180014b2c  mov     rdx, rdi
0x180014b2f  mov     rcx, [rbx]
0x180014b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b37  jmp     short loc_180014B56
0x180014b39  mov     rax, [rbx+10h]
0x180014b3d  test    rax, rax
0x180014b40  jz      short loc_180014B4F
0x180014b42  mov     rdx, rdi
0x180014b45  mov     rcx, [rbx]
0x180014b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b4d  jmp     short loc_180014B56
0x180014b4f  call    cs:__imp_GetLastError
0x180014b55  nop
0x180014b56  mov     rbx, [rsp+38h+arg_0]
0x180014b5b  add     rsp, 30h
0x180014b5f  pop     rdi
0x180014b60  retn
```
