# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180002e08`
- end: `0x180002ebc`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800034a8`
- `0x1800039f4`

## callees

- `0x180002e08`
- `0x180017010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180002e5a`
- `KERNEL32!LoadLibraryExW` at `0x180002e5a`
- `KERNEL32!GetModuleHandleW` at `0x180002e2d`
- `KERNEL32!GetModuleHandleW` at `0x180002e2d`
- `KERNEL32!GetProcAddress` at `0x180002e42`
- `KERNEL32!GetProcAddress` at `0x180002e6f`
- `KERNEL32!GetProcAddress` at `0x180002e42`
- `KERNEL32!GetProcAddress` at `0x180002e6f`
- `KERNEL32!GetLastError` at `0x180002eab`
- `KERNEL32!GetLastError` at `0x180002eab`

## string_xrefs

- `0x180002e26`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180002e38`: `RegDeleteKeyExW`
- `0x180002e51`: `advapi32.dll`
- `0x180002e65`: `RegDeleteKeyW`

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
0x180002e08  mov     [rsp+arg_0], rbx
0x180002e0d  push    rdi
0x180002e0e  sub     rsp, 30h
0x180002e12  cmp     qword ptr [rcx+8], 0
0x180002e17  mov     rdi, rdx
0x180002e1a  mov     rbx, rcx
0x180002e1d  jnz     short loc_180002E79
0x180002e1f  cmp     qword ptr [rcx+10h], 0
0x180002e24  jnz     short loc_180002E79
0x180002e26  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180002e2d  call    cs:__imp_GetModuleHandleW
0x180002e33  test    rax, rax
0x180002e36  jz      short loc_180002E4E
0x180002e38  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180002e3f  mov     rcx, rax; hModule
0x180002e42  call    cs:__imp_GetProcAddress
0x180002e48  mov     [rbx+8], rax
0x180002e4c  jmp     short loc_180002E79
0x180002e4e  xor     r8d, r8d; dwFlags
0x180002e51  lea     rcx, LibFileName; "advapi32.dll"
0x180002e58  xor     edx, edx; hFile
0x180002e5a  call    cs:__imp_LoadLibraryExW
0x180002e60  test    rax, rax
0x180002e63  jz      short loc_180002E79
0x180002e65  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180002e6c  mov     rcx, rax; hModule
0x180002e6f  call    cs:__imp_GetProcAddress
0x180002e75  mov     [rbx+10h], rax
0x180002e79  mov     rax, [rbx+8]
0x180002e7d  test    rax, rax
0x180002e80  jz      short loc_180002E95
0x180002e82  mov     rcx, [rbx]
0x180002e85  xor     r9d, r9d
0x180002e88  xor     r8d, r8d
0x180002e8b  mov     rdx, rdi
0x180002e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e93  jmp     short loc_180002EB1
0x180002e95  mov     rax, [rbx+10h]
0x180002e99  test    rax, rax
0x180002e9c  jz      short loc_180002EAB
0x180002e9e  mov     rcx, [rbx]
0x180002ea1  mov     rdx, rdi
0x180002ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea9  jmp     short loc_180002EB1
0x180002eab  call    cs:__imp_GetLastError
0x180002eb1  mov     rbx, [rsp+38h+arg_0]
0x180002eb6  add     rsp, 30h
0x180002eba  pop     rdi
0x180002ebb  retn
```
