# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800027b4`
- end: `0x180002869`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800022c4`
- `0x1800051a8`
- `0x18000566c`

## callees

- `0x1800027b4`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002857`
- `KERNEL32!GetLastError` at `0x180002857`
- `KERNEL32!GetProcAddress` at `0x1800027ee`
- `KERNEL32!GetProcAddress` at `0x18000281b`
- `KERNEL32!GetProcAddress` at `0x1800027ee`
- `KERNEL32!GetProcAddress` at `0x18000281b`
- `KERNEL32!LoadLibraryExW` at `0x180002806`
- `KERNEL32!LoadLibraryExW` at `0x180002806`
- `KERNEL32!GetModuleHandleW` at `0x1800027d9`
- `KERNEL32!GetModuleHandleW` at `0x1800027d9`

## string_xrefs

- `0x1800027d2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800027e4`: `RegDeleteKeyExW`
- `0x1800027ff`: `advapi32.dll`
- `0x180002811`: `RegDeleteKeyW`

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
0x1800027b4  mov     [rsp+arg_0], rbx
0x1800027b9  push    rdi
0x1800027ba  sub     rsp, 30h
0x1800027be  mov     rdi, rdx
0x1800027c1  mov     rbx, rcx
0x1800027c4  cmp     qword ptr [rcx+8], 0
0x1800027c9  jnz     short loc_180002825
0x1800027cb  cmp     qword ptr [rcx+10h], 0
0x1800027d0  jnz     short loc_180002825
0x1800027d2  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800027d9  call    cs:__imp_GetModuleHandleW
0x1800027df  test    rax, rax
0x1800027e2  jz      short loc_1800027FA
0x1800027e4  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800027eb  mov     rcx, rax; hModule
0x1800027ee  call    cs:__imp_GetProcAddress
0x1800027f4  mov     [rbx+8], rax
0x1800027f8  jmp     short loc_180002825
0x1800027fa  xor     r8d, r8d; dwFlags
0x1800027fd  xor     edx, edx; hFile
0x1800027ff  lea     rcx, LibFileName; "advapi32.dll"
0x180002806  call    cs:__imp_LoadLibraryExW
0x18000280c  test    rax, rax
0x18000280f  jz      short loc_180002825
0x180002811  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180002818  mov     rcx, rax; hModule
0x18000281b  call    cs:__imp_GetProcAddress
0x180002821  mov     [rbx+10h], rax
0x180002825  mov     rax, [rbx+8]
0x180002829  test    rax, rax
0x18000282c  jz      short loc_180002841
0x18000282e  xor     r9d, r9d
0x180002831  xor     r8d, r8d
0x180002834  mov     rdx, rdi
0x180002837  mov     rcx, [rbx]
0x18000283a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283f  jmp     short loc_18000285E
0x180002841  mov     rax, [rbx+10h]
0x180002845  test    rax, rax
0x180002848  jz      short loc_180002857
0x18000284a  mov     rdx, rdi
0x18000284d  mov     rcx, [rbx]
0x180002850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002855  jmp     short loc_18000285E
0x180002857  call    cs:__imp_GetLastError
0x18000285d  nop
0x18000285e  mov     rbx, [rsp+38h+arg_0]
0x180002863  add     rsp, 30h
0x180002867  pop     rdi
0x180002868  retn
```
