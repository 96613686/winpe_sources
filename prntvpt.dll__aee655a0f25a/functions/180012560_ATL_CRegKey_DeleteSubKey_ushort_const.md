# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180012560`
- end: `0x180012614`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800151dc`
- `0x1800155fc`
- `0x1800180bc`

## callees

- `0x180012560`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012603`
- `KERNEL32!GetLastError` at `0x180012603`
- `KERNEL32!GetModuleHandleW` at `0x180012585`
- `KERNEL32!GetModuleHandleW` at `0x180012585`
- `KERNEL32!GetProcAddress` at `0x18001259a`
- `KERNEL32!GetProcAddress` at `0x1800125c7`
- `KERNEL32!GetProcAddress` at `0x18001259a`
- `KERNEL32!GetProcAddress` at `0x1800125c7`
- `KERNEL32!LoadLibraryExW` at `0x1800125b2`
- `KERNEL32!LoadLibraryExW` at `0x1800125b2`

## string_xrefs

- `0x18001257e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180012590`: `RegDeleteKeyExW`
- `0x1800125a9`: `advapi32.dll`
- `0x1800125bd`: `RegDeleteKeyW`

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
0x180012560  mov     [rsp+arg_0], rbx
0x180012565  push    rdi
0x180012566  sub     rsp, 30h
0x18001256a  cmp     qword ptr [rcx+8], 0
0x18001256f  mov     rdi, rdx
0x180012572  mov     rbx, rcx
0x180012575  jnz     short loc_1800125D1
0x180012577  cmp     qword ptr [rcx+10h], 0
0x18001257c  jnz     short loc_1800125D1
0x18001257e  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180012585  call    cs:__imp_GetModuleHandleW
0x18001258b  test    rax, rax
0x18001258e  jz      short loc_1800125A6
0x180012590  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180012597  mov     rcx, rax; hModule
0x18001259a  call    cs:__imp_GetProcAddress
0x1800125a0  mov     [rbx+8], rax
0x1800125a4  jmp     short loc_1800125D1
0x1800125a6  xor     r8d, r8d; dwFlags
0x1800125a9  lea     rcx, LibFileName; "advapi32.dll"
0x1800125b0  xor     edx, edx; hFile
0x1800125b2  call    cs:__imp_LoadLibraryExW
0x1800125b8  test    rax, rax
0x1800125bb  jz      short loc_1800125D1
0x1800125bd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800125c4  mov     rcx, rax; hModule
0x1800125c7  call    cs:__imp_GetProcAddress
0x1800125cd  mov     [rbx+10h], rax
0x1800125d1  mov     rax, [rbx+8]
0x1800125d5  test    rax, rax
0x1800125d8  jz      short loc_1800125ED
0x1800125da  mov     rcx, [rbx]
0x1800125dd  xor     r9d, r9d
0x1800125e0  xor     r8d, r8d
0x1800125e3  mov     rdx, rdi
0x1800125e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125eb  jmp     short loc_180012609
0x1800125ed  mov     rax, [rbx+10h]
0x1800125f1  test    rax, rax
0x1800125f4  jz      short loc_180012603
0x1800125f6  mov     rcx, [rbx]
0x1800125f9  mov     rdx, rdi
0x1800125fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012601  jmp     short loc_180012609
0x180012603  call    cs:__imp_GetLastError
0x180012609  mov     rbx, [rsp+38h+arg_0]
0x18001260e  add     rsp, 30h
0x180012612  pop     rdi
0x180012613  retn
```
