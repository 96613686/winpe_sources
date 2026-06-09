# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180003874`
- end: `0x180003929`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003284`
- `0x180003fc8`
- `0x18000448c`

## callees

- `0x180003874`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003917`
- `KERNEL32!GetLastError` at `0x180003917`
- `KERNEL32!GetProcAddress` at `0x1800038ae`
- `KERNEL32!GetProcAddress` at `0x1800038db`
- `KERNEL32!GetProcAddress` at `0x1800038ae`
- `KERNEL32!GetProcAddress` at `0x1800038db`
- `KERNEL32!GetModuleHandleW` at `0x180003899`
- `KERNEL32!GetModuleHandleW` at `0x180003899`
- `KERNEL32!LoadLibraryExW` at `0x1800038c6`
- `KERNEL32!LoadLibraryExW` at `0x1800038c6`

## string_xrefs

- `0x180003892`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800038a4`: `RegDeleteKeyExW`
- `0x1800038bf`: `advapi32.dll`
- `0x1800038d1`: `RegDeleteKeyW`

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
0x180003874  mov     [rsp+arg_0], rbx
0x180003879  push    rdi
0x18000387a  sub     rsp, 30h
0x18000387e  mov     rdi, rdx
0x180003881  mov     rbx, rcx
0x180003884  cmp     qword ptr [rcx+8], 0
0x180003889  jnz     short loc_1800038E5
0x18000388b  cmp     qword ptr [rcx+10h], 0
0x180003890  jnz     short loc_1800038E5
0x180003892  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003899  call    cs:__imp_GetModuleHandleW
0x18000389f  test    rax, rax
0x1800038a2  jz      short loc_1800038BA
0x1800038a4  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800038ab  mov     rcx, rax; hModule
0x1800038ae  call    cs:__imp_GetProcAddress
0x1800038b4  mov     [rbx+8], rax
0x1800038b8  jmp     short loc_1800038E5
0x1800038ba  xor     r8d, r8d; dwFlags
0x1800038bd  xor     edx, edx; hFile
0x1800038bf  lea     rcx, LibFileName; "advapi32.dll"
0x1800038c6  call    cs:__imp_LoadLibraryExW
0x1800038cc  test    rax, rax
0x1800038cf  jz      short loc_1800038E5
0x1800038d1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800038d8  mov     rcx, rax; hModule
0x1800038db  call    cs:__imp_GetProcAddress
0x1800038e1  mov     [rbx+10h], rax
0x1800038e5  mov     rax, [rbx+8]
0x1800038e9  test    rax, rax
0x1800038ec  jz      short loc_180003901
0x1800038ee  xor     r9d, r9d
0x1800038f1  xor     r8d, r8d
0x1800038f4  mov     rdx, rdi
0x1800038f7  mov     rcx, [rbx]
0x1800038fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ff  jmp     short loc_18000391E
0x180003901  mov     rax, [rbx+10h]
0x180003905  test    rax, rax
0x180003908  jz      short loc_180003917
0x18000390a  mov     rdx, rdi
0x18000390d  mov     rcx, [rbx]
0x180003910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003915  jmp     short loc_18000391E
0x180003917  call    cs:__imp_GetLastError
0x18000391d  nop
0x18000391e  mov     rbx, [rsp+38h+arg_0]
0x180003923  add     rsp, 30h
0x180003927  pop     rdi
0x180003928  retn
```
