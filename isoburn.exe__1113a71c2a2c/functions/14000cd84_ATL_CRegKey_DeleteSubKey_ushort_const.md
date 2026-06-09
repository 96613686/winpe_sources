# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x14000cd84`
- end: `0x14000ce38`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d428`
- `0x14000d8cc`

## callees

- `0x14000cd84`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000ce27`
- `KERNEL32!GetLastError` at `0x14000ce27`
- `KERNEL32!GetProcAddress` at `0x14000cdbe`
- `KERNEL32!GetProcAddress` at `0x14000cdeb`
- `KERNEL32!GetProcAddress` at `0x14000cdbe`
- `KERNEL32!GetProcAddress` at `0x14000cdeb`
- `KERNEL32!LoadLibraryExW` at `0x14000cdd6`
- `KERNEL32!LoadLibraryExW` at `0x14000cdd6`
- `KERNEL32!GetModuleHandleW` at `0x14000cda9`
- `KERNEL32!GetModuleHandleW` at `0x14000cda9`

## string_xrefs

- `0x14000cda2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14000cdb4`: `RegDeleteKeyExW`
- `0x14000cdcd`: `advapi32.dll`
- `0x14000cde1`: `RegDeleteKeyW`

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
0x14000cd84  mov     [rsp+arg_0], rbx
0x14000cd89  push    rdi
0x14000cd8a  sub     rsp, 30h
0x14000cd8e  cmp     qword ptr [rcx+8], 0
0x14000cd93  mov     rdi, rdx
0x14000cd96  mov     rbx, rcx
0x14000cd99  jnz     short loc_14000CDF5
0x14000cd9b  cmp     qword ptr [rcx+10h], 0
0x14000cda0  jnz     short loc_14000CDF5
0x14000cda2  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14000cda9  call    cs:__imp_GetModuleHandleW
0x14000cdaf  test    rax, rax
0x14000cdb2  jz      short loc_14000CDCA
0x14000cdb4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x14000cdbb  mov     rcx, rax; hModule
0x14000cdbe  call    cs:__imp_GetProcAddress
0x14000cdc4  mov     [rbx+8], rax
0x14000cdc8  jmp     short loc_14000CDF5
0x14000cdca  xor     r8d, r8d; dwFlags
0x14000cdcd  lea     rcx, LibFileName; "advapi32.dll"
0x14000cdd4  xor     edx, edx; hFile
0x14000cdd6  call    cs:__imp_LoadLibraryExW
0x14000cddc  test    rax, rax
0x14000cddf  jz      short loc_14000CDF5
0x14000cde1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14000cde8  mov     rcx, rax; hModule
0x14000cdeb  call    cs:__imp_GetProcAddress
0x14000cdf1  mov     [rbx+10h], rax
0x14000cdf5  mov     rax, [rbx+8]
0x14000cdf9  test    rax, rax
0x14000cdfc  jz      short loc_14000CE11
0x14000cdfe  mov     rcx, [rbx]
0x14000ce01  xor     r9d, r9d
0x14000ce04  xor     r8d, r8d
0x14000ce07  mov     rdx, rdi
0x14000ce0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce0f  jmp     short loc_14000CE2D
0x14000ce11  mov     rax, [rbx+10h]
0x14000ce15  test    rax, rax
0x14000ce18  jz      short loc_14000CE27
0x14000ce1a  mov     rcx, [rbx]
0x14000ce1d  mov     rdx, rdi
0x14000ce20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce25  jmp     short loc_14000CE2D
0x14000ce27  call    cs:__imp_GetLastError
0x14000ce2d  mov     rbx, [rsp+38h+arg_0]
0x14000ce32  add     rsp, 30h
0x14000ce36  pop     rdi
0x14000ce37  retn
```
