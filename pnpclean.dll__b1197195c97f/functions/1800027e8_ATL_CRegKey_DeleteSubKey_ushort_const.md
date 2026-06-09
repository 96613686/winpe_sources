# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800027e8`
- end: `0x18000289c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002304`

## callees

- `0x1800027e8`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000288b`
- `KERNEL32!GetLastError` at `0x18000288b`
- `KERNEL32!GetProcAddress` at `0x180002822`
- `KERNEL32!GetProcAddress` at `0x18000284f`
- `KERNEL32!GetProcAddress` at `0x180002822`
- `KERNEL32!GetProcAddress` at `0x18000284f`
- `KERNEL32!GetModuleHandleW` at `0x18000280d`
- `KERNEL32!GetModuleHandleW` at `0x18000280d`
- `KERNEL32!LoadLibraryExW` at `0x18000283a`
- `KERNEL32!LoadLibraryExW` at `0x18000283a`

## string_xrefs

- `0x180002806`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180002818`: `RegDeleteKeyExW`
- `0x180002831`: `advapi32.dll`
- `0x180002845`: `RegDeleteKeyW`

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
0x1800027e8  mov     [rsp+arg_0], rbx
0x1800027ed  push    rdi
0x1800027ee  sub     rsp, 30h
0x1800027f2  cmp     qword ptr [rcx+8], 0
0x1800027f7  mov     rdi, rdx
0x1800027fa  mov     rbx, rcx
0x1800027fd  jnz     short loc_180002859
0x1800027ff  cmp     qword ptr [rcx+10h], 0
0x180002804  jnz     short loc_180002859
0x180002806  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000280d  call    cs:__imp_GetModuleHandleW
0x180002813  test    rax, rax
0x180002816  jz      short loc_18000282E
0x180002818  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000281f  mov     rcx, rax; hModule
0x180002822  call    cs:__imp_GetProcAddress
0x180002828  mov     [rbx+8], rax
0x18000282c  jmp     short loc_180002859
0x18000282e  xor     r8d, r8d; dwFlags
0x180002831  lea     rcx, LibFileName; "advapi32.dll"
0x180002838  xor     edx, edx; hFile
0x18000283a  call    cs:__imp_LoadLibraryExW
0x180002840  test    rax, rax
0x180002843  jz      short loc_180002859
0x180002845  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000284c  mov     rcx, rax; hModule
0x18000284f  call    cs:__imp_GetProcAddress
0x180002855  mov     [rbx+10h], rax
0x180002859  mov     rax, [rbx+8]
0x18000285d  test    rax, rax
0x180002860  jz      short loc_180002875
0x180002862  mov     rcx, [rbx]
0x180002865  xor     r9d, r9d
0x180002868  xor     r8d, r8d
0x18000286b  mov     rdx, rdi
0x18000286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002873  jmp     short loc_180002891
0x180002875  mov     rax, [rbx+10h]
0x180002879  test    rax, rax
0x18000287c  jz      short loc_18000288B
0x18000287e  mov     rcx, [rbx]
0x180002881  mov     rdx, rdi
0x180002884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002889  jmp     short loc_180002891
0x18000288b  call    cs:__imp_GetLastError
0x180002891  mov     rbx, [rsp+38h+arg_0]
0x180002896  add     rsp, 30h
0x18000289a  pop     rdi
0x18000289b  retn
```
