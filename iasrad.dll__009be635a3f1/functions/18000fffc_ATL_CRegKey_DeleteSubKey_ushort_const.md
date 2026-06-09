# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000fffc`
- end: `0x1800100b1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f430`
- `0x180010bb8`
- `0x1800110f4`

## callees

- `0x18000fffc`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001009f`
- `KERNEL32!GetLastError` at `0x18001009f`
- `KERNEL32!GetModuleHandleW` at `0x180010021`
- `KERNEL32!GetModuleHandleW` at `0x180010021`
- `KERNEL32!GetProcAddress` at `0x180010036`
- `KERNEL32!GetProcAddress` at `0x180010063`
- `KERNEL32!GetProcAddress` at `0x180010036`
- `KERNEL32!GetProcAddress` at `0x180010063`
- `KERNEL32!LoadLibraryExW` at `0x18001004e`
- `KERNEL32!LoadLibraryExW` at `0x18001004e`

## string_xrefs

- `0x18001001a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001002c`: `RegDeleteKeyExW`
- `0x180010047`: `advapi32.dll`
- `0x180010059`: `RegDeleteKeyW`

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
0x18000fffc  mov     [rsp+arg_0], rbx
0x180010001  push    rdi
0x180010002  sub     rsp, 30h
0x180010006  mov     rdi, rdx
0x180010009  mov     rbx, rcx
0x18001000c  cmp     qword ptr [rcx+8], 0
0x180010011  jnz     short loc_18001006D
0x180010013  cmp     qword ptr [rcx+10h], 0
0x180010018  jnz     short loc_18001006D
0x18001001a  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180010021  call    cs:__imp_GetModuleHandleW
0x180010027  test    rax, rax
0x18001002a  jz      short loc_180010042
0x18001002c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180010033  mov     rcx, rax; hModule
0x180010036  call    cs:__imp_GetProcAddress
0x18001003c  mov     [rbx+8], rax
0x180010040  jmp     short loc_18001006D
0x180010042  xor     r8d, r8d; dwFlags
0x180010045  xor     edx, edx; hFile
0x180010047  lea     rcx, LibFileName; "advapi32.dll"
0x18001004e  call    cs:__imp_LoadLibraryExW
0x180010054  test    rax, rax
0x180010057  jz      short loc_18001006D
0x180010059  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180010060  mov     rcx, rax; hModule
0x180010063  call    cs:__imp_GetProcAddress
0x180010069  mov     [rbx+10h], rax
0x18001006d  mov     rax, [rbx+8]
0x180010071  test    rax, rax
0x180010074  jz      short loc_180010089
0x180010076  xor     r9d, r9d
0x180010079  xor     r8d, r8d
0x18001007c  mov     rdx, rdi
0x18001007f  mov     rcx, [rbx]
0x180010082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010087  jmp     short loc_1800100A6
0x180010089  mov     rax, [rbx+10h]
0x18001008d  test    rax, rax
0x180010090  jz      short loc_18001009F
0x180010092  mov     rdx, rdi
0x180010095  mov     rcx, [rbx]
0x180010098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009d  jmp     short loc_1800100A6
0x18001009f  call    cs:__imp_GetLastError
0x1800100a5  nop
0x1800100a6  mov     rbx, [rsp+38h+arg_0]
0x1800100ab  add     rsp, 30h
0x1800100af  pop     rdi
0x1800100b0  retn
```
