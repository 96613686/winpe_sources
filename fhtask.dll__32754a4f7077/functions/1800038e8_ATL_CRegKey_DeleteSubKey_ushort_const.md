# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800038e8`
- end: `0x18000399d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004148`
- `0x18000460c`
- `0x1800054a0`

## callees

- `0x1800038e8`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000398b`
- `KERNEL32!GetLastError` at `0x18000398b`
- `KERNEL32!GetProcAddress` at `0x180003922`
- `KERNEL32!GetProcAddress` at `0x18000394f`
- `KERNEL32!GetProcAddress` at `0x180003922`
- `KERNEL32!GetProcAddress` at `0x18000394f`
- `KERNEL32!GetModuleHandleW` at `0x18000390d`
- `KERNEL32!GetModuleHandleW` at `0x18000390d`
- `KERNEL32!LoadLibraryExW` at `0x18000393a`
- `KERNEL32!LoadLibraryExW` at `0x18000393a`

## string_xrefs

- `0x180003906`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003918`: `RegDeleteKeyExW`
- `0x180003933`: `advapi32.dll`
- `0x180003945`: `RegDeleteKeyW`

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
0x1800038e8  mov     [rsp+arg_0], rbx
0x1800038ed  push    rdi
0x1800038ee  sub     rsp, 30h
0x1800038f2  mov     rdi, rdx
0x1800038f5  mov     rbx, rcx
0x1800038f8  cmp     qword ptr [rcx+8], 0
0x1800038fd  jnz     short loc_180003959
0x1800038ff  cmp     qword ptr [rcx+10h], 0
0x180003904  jnz     short loc_180003959
0x180003906  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000390d  call    cs:__imp_GetModuleHandleW
0x180003913  test    rax, rax
0x180003916  jz      short loc_18000392E
0x180003918  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000391f  mov     rcx, rax; hModule
0x180003922  call    cs:__imp_GetProcAddress
0x180003928  mov     [rbx+8], rax
0x18000392c  jmp     short loc_180003959
0x18000392e  xor     r8d, r8d; dwFlags
0x180003931  xor     edx, edx; hFile
0x180003933  lea     rcx, LibFileName; "advapi32.dll"
0x18000393a  call    cs:__imp_LoadLibraryExW
0x180003940  test    rax, rax
0x180003943  jz      short loc_180003959
0x180003945  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000394c  mov     rcx, rax; hModule
0x18000394f  call    cs:__imp_GetProcAddress
0x180003955  mov     [rbx+10h], rax
0x180003959  mov     rax, [rbx+8]
0x18000395d  test    rax, rax
0x180003960  jz      short loc_180003975
0x180003962  xor     r9d, r9d
0x180003965  xor     r8d, r8d
0x180003968  mov     rdx, rdi
0x18000396b  mov     rcx, [rbx]
0x18000396e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003973  jmp     short loc_180003992
0x180003975  mov     rax, [rbx+10h]
0x180003979  test    rax, rax
0x18000397c  jz      short loc_18000398B
0x18000397e  mov     rdx, rdi
0x180003981  mov     rcx, [rbx]
0x180003984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003989  jmp     short loc_180003992
0x18000398b  call    cs:__imp_GetLastError
0x180003991  nop
0x180003992  mov     rbx, [rsp+38h+arg_0]
0x180003997  add     rsp, 30h
0x18000399b  pop     rdi
0x18000399c  retn
```
