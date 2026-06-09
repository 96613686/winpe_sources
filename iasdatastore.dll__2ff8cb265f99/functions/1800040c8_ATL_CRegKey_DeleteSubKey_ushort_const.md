# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800040c8`
- end: `0x18000417d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800032f8`
- `0x180004a38`
- `0x180004efc`

## callees

- `0x1800040c8`
- `0x180010010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000416b`
- `KERNEL32!GetLastError` at `0x18000416b`
- `KERNEL32!GetProcAddress` at `0x180004102`
- `KERNEL32!GetProcAddress` at `0x18000412f`
- `KERNEL32!GetProcAddress` at `0x180004102`
- `KERNEL32!GetProcAddress` at `0x18000412f`
- `KERNEL32!LoadLibraryExW` at `0x18000411a`
- `KERNEL32!LoadLibraryExW` at `0x18000411a`
- `KERNEL32!GetModuleHandleW` at `0x1800040ed`
- `KERNEL32!GetModuleHandleW` at `0x1800040ed`

## string_xrefs

- `0x1800040e6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800040f8`: `RegDeleteKeyExW`
- `0x180004113`: `advapi32.dll`
- `0x180004125`: `RegDeleteKeyW`

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
0x1800040c8  mov     [rsp+arg_0], rbx
0x1800040cd  push    rdi
0x1800040ce  sub     rsp, 30h
0x1800040d2  mov     rdi, rdx
0x1800040d5  mov     rbx, rcx
0x1800040d8  cmp     qword ptr [rcx+8], 0
0x1800040dd  jnz     short loc_180004139
0x1800040df  cmp     qword ptr [rcx+10h], 0
0x1800040e4  jnz     short loc_180004139
0x1800040e6  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800040ed  call    cs:__imp_GetModuleHandleW
0x1800040f3  test    rax, rax
0x1800040f6  jz      short loc_18000410E
0x1800040f8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800040ff  mov     rcx, rax; hModule
0x180004102  call    cs:__imp_GetProcAddress
0x180004108  mov     [rbx+8], rax
0x18000410c  jmp     short loc_180004139
0x18000410e  xor     r8d, r8d; dwFlags
0x180004111  xor     edx, edx; hFile
0x180004113  lea     rcx, LibFileName; "advapi32.dll"
0x18000411a  call    cs:__imp_LoadLibraryExW
0x180004120  test    rax, rax
0x180004123  jz      short loc_180004139
0x180004125  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000412c  mov     rcx, rax; hModule
0x18000412f  call    cs:__imp_GetProcAddress
0x180004135  mov     [rbx+10h], rax
0x180004139  mov     rax, [rbx+8]
0x18000413d  test    rax, rax
0x180004140  jz      short loc_180004155
0x180004142  xor     r9d, r9d
0x180004145  xor     r8d, r8d
0x180004148  mov     rdx, rdi
0x18000414b  mov     rcx, [rbx]
0x18000414e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004153  jmp     short loc_180004172
0x180004155  mov     rax, [rbx+10h]
0x180004159  test    rax, rax
0x18000415c  jz      short loc_18000416B
0x18000415e  mov     rdx, rdi
0x180004161  mov     rcx, [rbx]
0x180004164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004169  jmp     short loc_180004172
0x18000416b  call    cs:__imp_GetLastError
0x180004171  nop
0x180004172  mov     rbx, [rsp+38h+arg_0]
0x180004177  add     rsp, 30h
0x18000417b  pop     rdi
0x18000417c  retn
```
