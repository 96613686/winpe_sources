# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800063fc`
- end: `0x1800064b1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004860`
- `0x1800078c8`
- `0x180007e04`

## callees

- `0x1800063fc`
- `0x18002e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000649f`
- `KERNEL32!GetLastError` at `0x18000649f`
- `KERNEL32!GetProcAddress` at `0x180006436`
- `KERNEL32!GetProcAddress` at `0x180006463`
- `KERNEL32!GetProcAddress` at `0x180006436`
- `KERNEL32!GetProcAddress` at `0x180006463`
- `KERNEL32!LoadLibraryExW` at `0x18000644e`
- `KERNEL32!LoadLibraryExW` at `0x18000644e`
- `KERNEL32!GetModuleHandleW` at `0x180006421`
- `KERNEL32!GetModuleHandleW` at `0x180006421`

## string_xrefs

- `0x18000641a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000642c`: `RegDeleteKeyExW`
- `0x180006447`: `advapi32.dll`
- `0x180006459`: `RegDeleteKeyW`

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
0x1800063fc  mov     [rsp+arg_0], rbx
0x180006401  push    rdi
0x180006402  sub     rsp, 30h
0x180006406  mov     rdi, rdx
0x180006409  mov     rbx, rcx
0x18000640c  cmp     qword ptr [rcx+8], 0
0x180006411  jnz     short loc_18000646D
0x180006413  cmp     qword ptr [rcx+10h], 0
0x180006418  jnz     short loc_18000646D
0x18000641a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006421  call    cs:__imp_GetModuleHandleW
0x180006427  test    rax, rax
0x18000642a  jz      short loc_180006442
0x18000642c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180006433  mov     rcx, rax; hModule
0x180006436  call    cs:__imp_GetProcAddress
0x18000643c  mov     [rbx+8], rax
0x180006440  jmp     short loc_18000646D
0x180006442  xor     r8d, r8d; dwFlags
0x180006445  xor     edx, edx; hFile
0x180006447  lea     rcx, LibFileName; "advapi32.dll"
0x18000644e  call    cs:__imp_LoadLibraryExW
0x180006454  test    rax, rax
0x180006457  jz      short loc_18000646D
0x180006459  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006460  mov     rcx, rax; hModule
0x180006463  call    cs:__imp_GetProcAddress
0x180006469  mov     [rbx+10h], rax
0x18000646d  mov     rax, [rbx+8]
0x180006471  test    rax, rax
0x180006474  jz      short loc_180006489
0x180006476  xor     r9d, r9d
0x180006479  xor     r8d, r8d
0x18000647c  mov     rdx, rdi
0x18000647f  mov     rcx, [rbx]
0x180006482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006487  jmp     short loc_1800064A6
0x180006489  mov     rax, [rbx+10h]
0x18000648d  test    rax, rax
0x180006490  jz      short loc_18000649F
0x180006492  mov     rdx, rdi
0x180006495  mov     rcx, [rbx]
0x180006498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649d  jmp     short loc_1800064A6
0x18000649f  call    cs:__imp_GetLastError
0x1800064a5  nop
0x1800064a6  mov     rbx, [rsp+38h+arg_0]
0x1800064ab  add     rsp, 30h
0x1800064af  pop     rdi
0x1800064b0  retn
```
