# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180026cbc`
- end: `0x180026d71`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180026628`
- `0x180027338`
- `0x180027800`

## callees

- `0x180026cbc`
- `0x180088010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180026d0e`
- `KERNEL32!LoadLibraryExW` at `0x180026d0e`
- `KERNEL32!GetModuleHandleW` at `0x180026ce1`
- `KERNEL32!GetModuleHandleW` at `0x180026ce1`
- `KERNEL32!GetProcAddress` at `0x180026cf6`
- `KERNEL32!GetProcAddress` at `0x180026d23`
- `KERNEL32!GetProcAddress` at `0x180026cf6`
- `KERNEL32!GetProcAddress` at `0x180026d23`
- `KERNEL32!GetLastError` at `0x180026d5f`
- `KERNEL32!GetLastError` at `0x180026d5f`

## string_xrefs

- `0x180026cda`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180026cec`: `RegDeleteKeyExW`
- `0x180026d07`: `advapi32.dll`
- `0x180026d19`: `RegDeleteKeyW`

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
0x180026cbc  mov     [rsp+arg_0], rbx
0x180026cc1  push    rdi
0x180026cc2  sub     rsp, 30h
0x180026cc6  mov     rdi, rdx
0x180026cc9  mov     rbx, rcx
0x180026ccc  cmp     qword ptr [rcx+8], 0
0x180026cd1  jnz     short loc_180026D2D
0x180026cd3  cmp     qword ptr [rcx+10h], 0
0x180026cd8  jnz     short loc_180026D2D
0x180026cda  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180026ce1  call    cs:__imp_GetModuleHandleW
0x180026ce7  test    rax, rax
0x180026cea  jz      short loc_180026D02
0x180026cec  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180026cf3  mov     rcx, rax; hModule
0x180026cf6  call    cs:__imp_GetProcAddress
0x180026cfc  mov     [rbx+8], rax
0x180026d00  jmp     short loc_180026D2D
0x180026d02  xor     r8d, r8d; dwFlags
0x180026d05  xor     edx, edx; hFile
0x180026d07  lea     rcx, LibFileName; "advapi32.dll"
0x180026d0e  call    cs:__imp_LoadLibraryExW
0x180026d14  test    rax, rax
0x180026d17  jz      short loc_180026D2D
0x180026d19  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180026d20  mov     rcx, rax; hModule
0x180026d23  call    cs:__imp_GetProcAddress
0x180026d29  mov     [rbx+10h], rax
0x180026d2d  mov     rax, [rbx+8]
0x180026d31  test    rax, rax
0x180026d34  jz      short loc_180026D49
0x180026d36  xor     r9d, r9d
0x180026d39  xor     r8d, r8d
0x180026d3c  mov     rdx, rdi
0x180026d3f  mov     rcx, [rbx]
0x180026d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d47  jmp     short loc_180026D66
0x180026d49  mov     rax, [rbx+10h]
0x180026d4d  test    rax, rax
0x180026d50  jz      short loc_180026D5F
0x180026d52  mov     rdx, rdi
0x180026d55  mov     rcx, [rbx]
0x180026d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d5d  jmp     short loc_180026D66
0x180026d5f  call    cs:__imp_GetLastError
0x180026d65  nop
0x180026d66  mov     rbx, [rsp+38h+arg_0]
0x180026d6b  add     rsp, 30h
0x180026d6f  pop     rdi
0x180026d70  retn
```
