# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800100a8`
- end: `0x18001015c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010ae8`
- `0x180011038`

## callees

- `0x1800100a8`
- `0x180014010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800100fa`
- `KERNEL32!LoadLibraryExW` at `0x1800100fa`
- `KERNEL32!GetModuleHandleW` at `0x1800100cd`
- `KERNEL32!GetModuleHandleW` at `0x1800100cd`
- `KERNEL32!GetProcAddress` at `0x1800100e2`
- `KERNEL32!GetProcAddress` at `0x18001010f`
- `KERNEL32!GetProcAddress` at `0x1800100e2`
- `KERNEL32!GetProcAddress` at `0x18001010f`
- `KERNEL32!GetLastError` at `0x18001014b`
- `KERNEL32!GetLastError` at `0x18001014b`

## string_xrefs

- `0x1800100c6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800100d8`: `RegDeleteKeyExW`
- `0x1800100f1`: `advapi32.dll`
- `0x180010105`: `RegDeleteKeyW`

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
0x1800100a8  mov     [rsp+arg_0], rbx
0x1800100ad  push    rdi
0x1800100ae  sub     rsp, 30h
0x1800100b2  cmp     qword ptr [rcx+8], 0
0x1800100b7  mov     rdi, rdx
0x1800100ba  mov     rbx, rcx
0x1800100bd  jnz     short loc_180010119
0x1800100bf  cmp     qword ptr [rcx+10h], 0
0x1800100c4  jnz     short loc_180010119
0x1800100c6  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800100cd  call    cs:__imp_GetModuleHandleW
0x1800100d3  test    rax, rax
0x1800100d6  jz      short loc_1800100EE
0x1800100d8  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800100df  mov     rcx, rax; hModule
0x1800100e2  call    cs:__imp_GetProcAddress
0x1800100e8  mov     [rbx+8], rax
0x1800100ec  jmp     short loc_180010119
0x1800100ee  xor     r8d, r8d; dwFlags
0x1800100f1  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800100f8  xor     edx, edx; hFile
0x1800100fa  call    cs:__imp_LoadLibraryExW
0x180010100  test    rax, rax
0x180010103  jz      short loc_180010119
0x180010105  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001010c  mov     rcx, rax; hModule
0x18001010f  call    cs:__imp_GetProcAddress
0x180010115  mov     [rbx+10h], rax
0x180010119  mov     rax, [rbx+8]
0x18001011d  test    rax, rax
0x180010120  jz      short loc_180010135
0x180010122  mov     rcx, [rbx]
0x180010125  xor     r9d, r9d
0x180010128  xor     r8d, r8d
0x18001012b  mov     rdx, rdi
0x18001012e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010133  jmp     short loc_180010151
0x180010135  mov     rax, [rbx+10h]
0x180010139  test    rax, rax
0x18001013c  jz      short loc_18001014B
0x18001013e  mov     rcx, [rbx]
0x180010141  mov     rdx, rdi
0x180010144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010149  jmp     short loc_180010151
0x18001014b  call    cs:__imp_GetLastError
0x180010151  mov     rbx, [rsp+38h+arg_0]
0x180010156  add     rsp, 30h
0x18001015a  pop     rdi
0x18001015b  retn
```
