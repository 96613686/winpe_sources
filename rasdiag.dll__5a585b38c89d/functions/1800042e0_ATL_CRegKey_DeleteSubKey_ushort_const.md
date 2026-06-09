# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800042e0`
- end: `0x1800043b4`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003a50`
- `0x1800049dc`
- `0x180004ef8`

## callees

- `0x1800042e0`
- `0x18000f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000439b`
- `KERNEL32!GetLastError` at `0x18000439b`
- `KERNEL32!GetProcAddress` at `0x180004320`
- `KERNEL32!GetProcAddress` at `0x180004359`
- `KERNEL32!GetProcAddress` at `0x180004320`
- `KERNEL32!GetProcAddress` at `0x180004359`
- `KERNEL32!LoadLibraryExW` at `0x18000433e`
- `KERNEL32!LoadLibraryExW` at `0x18000433e`
- `KERNEL32!GetModuleHandleW` at `0x180004305`
- `KERNEL32!GetModuleHandleW` at `0x180004305`

## string_xrefs

- `0x1800042fe`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004316`: `RegDeleteKeyExW`
- `0x180004337`: `advapi32.dll`
- `0x18000434f`: `RegDeleteKeyW`

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
0x1800042e0  mov     [rsp+arg_0], rbx
0x1800042e5  push    rdi
0x1800042e6  sub     rsp, 30h
0x1800042ea  mov     rdi, rdx
0x1800042ed  mov     rbx, rcx
0x1800042f0  cmp     qword ptr [rcx+8], 0
0x1800042f5  jnz     short loc_180004369
0x1800042f7  cmp     qword ptr [rcx+10h], 0
0x1800042fc  jnz     short loc_180004369
0x1800042fe  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004305  call    cs:__imp_GetModuleHandleW
0x18000430c  nop     dword ptr [rax+rax+00h]
0x180004311  test    rax, rax
0x180004314  jz      short loc_180004332
0x180004316  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000431d  mov     rcx, rax; hModule
0x180004320  call    cs:__imp_GetProcAddress
0x180004327  nop     dword ptr [rax+rax+00h]
0x18000432c  mov     [rbx+8], rax
0x180004330  jmp     short loc_180004369
0x180004332  xor     r8d, r8d; dwFlags
0x180004335  xor     edx, edx; hFile
0x180004337  lea     rcx, LibFileName; "advapi32.dll"
0x18000433e  call    cs:__imp_LoadLibraryExW
0x180004345  nop     dword ptr [rax+rax+00h]
0x18000434a  test    rax, rax
0x18000434d  jz      short loc_180004369
0x18000434f  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004356  mov     rcx, rax; hModule
0x180004359  call    cs:__imp_GetProcAddress
0x180004360  nop     dword ptr [rax+rax+00h]
0x180004365  mov     [rbx+10h], rax
0x180004369  mov     rax, [rbx+8]
0x18000436d  test    rax, rax
0x180004370  jz      short loc_180004385
0x180004372  xor     r9d, r9d
0x180004375  xor     r8d, r8d
0x180004378  mov     rdx, rdi
0x18000437b  mov     rcx, [rbx]
0x18000437e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004383  jmp     short loc_1800043A8
0x180004385  mov     rax, [rbx+10h]
0x180004389  test    rax, rax
0x18000438c  jz      short loc_18000439B
0x18000438e  mov     rdx, rdi
0x180004391  mov     rcx, [rbx]
0x180004394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004399  jmp     short loc_1800043A8
0x18000439b  call    cs:__imp_GetLastError
0x1800043a2  nop     dword ptr [rax+rax+00h]
0x1800043a7  nop
0x1800043a8  mov     rbx, [rsp+38h+arg_0]
0x1800043ad  add     rsp, 30h
0x1800043b1  pop     rdi
0x1800043b2  retn
```
