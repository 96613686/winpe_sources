# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800052a0`
- end: `0x180005354`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000892c`
- `0x180008dd0`

## callees

- `0x1800052a0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005343`
- `KERNEL32!GetLastError` at `0x180005343`
- `KERNEL32!GetProcAddress` at `0x1800052da`
- `KERNEL32!GetProcAddress` at `0x180005307`
- `KERNEL32!GetProcAddress` at `0x1800052da`
- `KERNEL32!GetProcAddress` at `0x180005307`
- `KERNEL32!GetModuleHandleW` at `0x1800052c5`
- `KERNEL32!GetModuleHandleW` at `0x1800052c5`
- `KERNEL32!LoadLibraryExW` at `0x1800052f2`
- `KERNEL32!LoadLibraryExW` at `0x1800052f2`

## string_xrefs

- `0x1800052be`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800052d0`: `RegDeleteKeyExW`
- `0x1800052e9`: `advapi32.dll`
- `0x1800052fd`: `RegDeleteKeyW`

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
0x1800052a0  mov     [rsp+arg_0], rbx
0x1800052a5  push    rdi
0x1800052a6  sub     rsp, 30h
0x1800052aa  cmp     qword ptr [rcx+8], 0
0x1800052af  mov     rdi, rdx
0x1800052b2  mov     rbx, rcx
0x1800052b5  jnz     short loc_180005311
0x1800052b7  cmp     qword ptr [rcx+10h], 0
0x1800052bc  jnz     short loc_180005311
0x1800052be  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800052c5  call    cs:__imp_GetModuleHandleW
0x1800052cb  test    rax, rax
0x1800052ce  jz      short loc_1800052E6
0x1800052d0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800052d7  mov     rcx, rax; hModule
0x1800052da  call    cs:__imp_GetProcAddress
0x1800052e0  mov     [rbx+8], rax
0x1800052e4  jmp     short loc_180005311
0x1800052e6  xor     r8d, r8d; dwFlags
0x1800052e9  lea     rcx, LibFileName; "advapi32.dll"
0x1800052f0  xor     edx, edx; hFile
0x1800052f2  call    cs:__imp_LoadLibraryExW
0x1800052f8  test    rax, rax
0x1800052fb  jz      short loc_180005311
0x1800052fd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180005304  mov     rcx, rax; hModule
0x180005307  call    cs:__imp_GetProcAddress
0x18000530d  mov     [rbx+10h], rax
0x180005311  mov     rax, [rbx+8]
0x180005315  test    rax, rax
0x180005318  jz      short loc_18000532D
0x18000531a  mov     rcx, [rbx]
0x18000531d  xor     r9d, r9d
0x180005320  xor     r8d, r8d
0x180005323  mov     rdx, rdi
0x180005326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000532b  jmp     short loc_180005349
0x18000532d  mov     rax, [rbx+10h]
0x180005331  test    rax, rax
0x180005334  jz      short loc_180005343
0x180005336  mov     rcx, [rbx]
0x180005339  mov     rdx, rdi
0x18000533c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005341  jmp     short loc_180005349
0x180005343  call    cs:__imp_GetLastError
0x180005349  mov     rbx, [rsp+38h+arg_0]
0x18000534e  add     rsp, 30h
0x180005352  pop     rdi
0x180005353  retn
```
