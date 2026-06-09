# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004d4c`
- end: `0x180004e01`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005658`
- `0x180005a90`
- `0x180006b44`

## callees

- `0x180004d4c`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004def`
- `KERNEL32!GetLastError` at `0x180004def`
- `KERNEL32!GetProcAddress` at `0x180004d86`
- `KERNEL32!GetProcAddress` at `0x180004db3`
- `KERNEL32!GetProcAddress` at `0x180004d86`
- `KERNEL32!GetProcAddress` at `0x180004db3`
- `KERNEL32!GetModuleHandleW` at `0x180004d71`
- `KERNEL32!GetModuleHandleW` at `0x180004d71`
- `KERNEL32!LoadLibraryExW` at `0x180004d9e`
- `KERNEL32!LoadLibraryExW` at `0x180004d9e`

## string_xrefs

- `0x180004d6a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004d7c`: `RegDeleteKeyExW`
- `0x180004d97`: `advapi32.dll`
- `0x180004da9`: `RegDeleteKeyW`

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
0x180004d4c  mov     [rsp+arg_0], rbx
0x180004d51  push    rdi
0x180004d52  sub     rsp, 30h
0x180004d56  mov     rdi, rdx
0x180004d59  mov     rbx, rcx
0x180004d5c  cmp     qword ptr [rcx+8], 0
0x180004d61  jnz     short loc_180004DBD
0x180004d63  cmp     qword ptr [rcx+10h], 0
0x180004d68  jnz     short loc_180004DBD
0x180004d6a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004d71  call    cs:__imp_GetModuleHandleW
0x180004d77  test    rax, rax
0x180004d7a  jz      short loc_180004D92
0x180004d7c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004d83  mov     rcx, rax; hModule
0x180004d86  call    cs:__imp_GetProcAddress
0x180004d8c  mov     [rbx+8], rax
0x180004d90  jmp     short loc_180004DBD
0x180004d92  xor     r8d, r8d; dwFlags
0x180004d95  xor     edx, edx; hFile
0x180004d97  lea     rcx, LibFileName; "advapi32.dll"
0x180004d9e  call    cs:__imp_LoadLibraryExW
0x180004da4  test    rax, rax
0x180004da7  jz      short loc_180004DBD
0x180004da9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004db0  mov     rcx, rax; hModule
0x180004db3  call    cs:__imp_GetProcAddress
0x180004db9  mov     [rbx+10h], rax
0x180004dbd  mov     rax, [rbx+8]
0x180004dc1  test    rax, rax
0x180004dc4  jz      short loc_180004DD9
0x180004dc6  xor     r9d, r9d
0x180004dc9  xor     r8d, r8d
0x180004dcc  mov     rdx, rdi
0x180004dcf  mov     rcx, [rbx]
0x180004dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd7  jmp     short loc_180004DF6
0x180004dd9  mov     rax, [rbx+10h]
0x180004ddd  test    rax, rax
0x180004de0  jz      short loc_180004DEF
0x180004de2  mov     rdx, rdi
0x180004de5  mov     rcx, [rbx]
0x180004de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ded  jmp     short loc_180004DF6
0x180004def  call    cs:__imp_GetLastError
0x180004df5  nop
0x180004df6  mov     rbx, [rsp+38h+arg_0]
0x180004dfb  add     rsp, 30h
0x180004dff  pop     rdi
0x180004e00  retn
```
