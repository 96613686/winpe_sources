# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x1400058ec`
- end: `0x1400059a1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400066b8`
- `0x140006af0`

## callees

- `0x1400058ec`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000598f`
- `KERNEL32!GetLastError` at `0x14000598f`
- `KERNEL32!GetProcAddress` at `0x140005926`
- `KERNEL32!GetProcAddress` at `0x140005953`
- `KERNEL32!GetProcAddress` at `0x140005926`
- `KERNEL32!GetProcAddress` at `0x140005953`
- `KERNEL32!LoadLibraryExW` at `0x14000593e`
- `KERNEL32!LoadLibraryExW` at `0x14000593e`
- `KERNEL32!GetModuleHandleW` at `0x140005911`
- `KERNEL32!GetModuleHandleW` at `0x140005911`

## string_xrefs

- `0x14000590a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14000591c`: `RegDeleteKeyExW`
- `0x140005937`: `advapi32.dll`
- `0x140005949`: `RegDeleteKeyW`

## pseudocode

```c
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
0x1400058ec  mov     [rsp+arg_0], rbx
0x1400058f1  push    rdi
0x1400058f2  sub     rsp, 30h
0x1400058f6  mov     rdi, rdx
0x1400058f9  mov     rbx, rcx
0x1400058fc  cmp     qword ptr [rcx+8], 0
0x140005901  jnz     short loc_14000595D
0x140005903  cmp     qword ptr [rcx+10h], 0
0x140005908  jnz     short loc_14000595D
0x14000590a  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140005911  call    cs:__imp_GetModuleHandleW
0x140005917  test    rax, rax
0x14000591a  jz      short loc_140005932
0x14000591c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x140005923  mov     rcx, rax; hModule
0x140005926  call    cs:__imp_GetProcAddress
0x14000592c  mov     [rbx+8], rax
0x140005930  jmp     short loc_14000595D
0x140005932  xor     r8d, r8d; dwFlags
0x140005935  xor     edx, edx; hFile
0x140005937  lea     rcx, LibFileName; "advapi32.dll"
0x14000593e  call    cs:__imp_LoadLibraryExW
0x140005944  test    rax, rax
0x140005947  jz      short loc_14000595D
0x140005949  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140005950  mov     rcx, rax; hModule
0x140005953  call    cs:__imp_GetProcAddress
0x140005959  mov     [rbx+10h], rax
0x14000595d  mov     rax, [rbx+8]
0x140005961  test    rax, rax
0x140005964  jz      short loc_140005979
0x140005966  xor     r9d, r9d
0x140005969  xor     r8d, r8d
0x14000596c  mov     rdx, rdi
0x14000596f  mov     rcx, [rbx]
0x140005972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005977  jmp     short loc_140005996
0x140005979  mov     rax, [rbx+10h]
0x14000597d  test    rax, rax
0x140005980  jz      short loc_14000598F
0x140005982  mov     rdx, rdi
0x140005985  mov     rcx, [rbx]
0x140005988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000598d  jmp     short loc_140005996
0x14000598f  call    cs:__imp_GetLastError
0x140005995  nop
0x140005996  mov     rbx, [rsp+38h+arg_0]
0x14000599b  add     rsp, 30h
0x14000599f  pop     rdi
0x1400059a0  retn
```
