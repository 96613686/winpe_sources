# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180002e78`
- end: `0x180002f2c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003598`
- `0x180003a3c`
- `0x1800082ac`

## callees

- `0x180002e78`
- `0x180019010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180002eca`
- `KERNEL32!LoadLibraryExW` at `0x180002eca`
- `KERNEL32!GetModuleHandleW` at `0x180002e9d`
- `KERNEL32!GetModuleHandleW` at `0x180002e9d`
- `KERNEL32!GetProcAddress` at `0x180002eb2`
- `KERNEL32!GetProcAddress` at `0x180002edf`
- `KERNEL32!GetProcAddress` at `0x180002eb2`
- `KERNEL32!GetProcAddress` at `0x180002edf`
- `KERNEL32!GetLastError` at `0x180002f1b`
- `KERNEL32!GetLastError` at `0x180002f1b`

## string_xrefs

- `0x180002e96`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180002ea8`: `RegDeleteKeyExW`
- `0x180002ec1`: `advapi32.dll`
- `0x180002ed5`: `RegDeleteKeyW`

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
0x180002e78  mov     [rsp+arg_0], rbx
0x180002e7d  push    rdi
0x180002e7e  sub     rsp, 30h
0x180002e82  cmp     qword ptr [rcx+8], 0
0x180002e87  mov     rdi, rdx
0x180002e8a  mov     rbx, rcx
0x180002e8d  jnz     short loc_180002EE9
0x180002e8f  cmp     qword ptr [rcx+10h], 0
0x180002e94  jnz     short loc_180002EE9
0x180002e96  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180002e9d  call    cs:__imp_GetModuleHandleW
0x180002ea3  test    rax, rax
0x180002ea6  jz      short loc_180002EBE
0x180002ea8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180002eaf  mov     rcx, rax; hModule
0x180002eb2  call    cs:__imp_GetProcAddress
0x180002eb8  mov     [rbx+8], rax
0x180002ebc  jmp     short loc_180002EE9
0x180002ebe  xor     r8d, r8d; dwFlags
0x180002ec1  lea     rcx, LibFileName; "advapi32.dll"
0x180002ec8  xor     edx, edx; hFile
0x180002eca  call    cs:__imp_LoadLibraryExW
0x180002ed0  test    rax, rax
0x180002ed3  jz      short loc_180002EE9
0x180002ed5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180002edc  mov     rcx, rax; hModule
0x180002edf  call    cs:__imp_GetProcAddress
0x180002ee5  mov     [rbx+10h], rax
0x180002ee9  mov     rax, [rbx+8]
0x180002eed  test    rax, rax
0x180002ef0  jz      short loc_180002F05
0x180002ef2  mov     rcx, [rbx]
0x180002ef5  xor     r9d, r9d
0x180002ef8  xor     r8d, r8d
0x180002efb  mov     rdx, rdi
0x180002efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f03  jmp     short loc_180002F21
0x180002f05  mov     rax, [rbx+10h]
0x180002f09  test    rax, rax
0x180002f0c  jz      short loc_180002F1B
0x180002f0e  mov     rcx, [rbx]
0x180002f11  mov     rdx, rdi
0x180002f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f19  jmp     short loc_180002F21
0x180002f1b  call    cs:__imp_GetLastError
0x180002f21  mov     rbx, [rsp+38h+arg_0]
0x180002f26  add     rsp, 30h
0x180002f2a  pop     rdi
0x180002f2b  retn
```
