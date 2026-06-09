# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000a394`
- end: `0x18000a449`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800099a8`
- `0x18000af48`
- `0x18000b44c`

## callees

- `0x18000a394`
- `0x18001c010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000a3e6`
- `KERNEL32!LoadLibraryExW` at `0x18000a3e6`
- `KERNEL32!GetLastError` at `0x18000a437`
- `KERNEL32!GetLastError` at `0x18000a437`
- `KERNEL32!GetModuleHandleW` at `0x18000a3b9`
- `KERNEL32!GetModuleHandleW` at `0x18000a3b9`
- `KERNEL32!GetProcAddress` at `0x18000a3ce`
- `KERNEL32!GetProcAddress` at `0x18000a3fb`
- `KERNEL32!GetProcAddress` at `0x18000a3ce`
- `KERNEL32!GetProcAddress` at `0x18000a3fb`

## string_xrefs

- `0x18000a3b2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000a3c4`: `RegDeleteKeyExW`
- `0x18000a3df`: `advapi32.dll`
- `0x18000a3f1`: `RegDeleteKeyW`

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
0x18000a394  mov     [rsp+arg_0], rbx
0x18000a399  push    rdi
0x18000a39a  sub     rsp, 30h
0x18000a39e  mov     rdi, rdx
0x18000a3a1  mov     rbx, rcx
0x18000a3a4  cmp     qword ptr [rcx+8], 0
0x18000a3a9  jnz     short loc_18000A405
0x18000a3ab  cmp     qword ptr [rcx+10h], 0
0x18000a3b0  jnz     short loc_18000A405
0x18000a3b2  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000a3b9  call    cs:__imp_GetModuleHandleW
0x18000a3bf  test    rax, rax
0x18000a3c2  jz      short loc_18000A3DA
0x18000a3c4  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000a3cb  mov     rcx, rax; hModule
0x18000a3ce  call    cs:__imp_GetProcAddress
0x18000a3d4  mov     [rbx+8], rax
0x18000a3d8  jmp     short loc_18000A405
0x18000a3da  xor     r8d, r8d; dwFlags
0x18000a3dd  xor     edx, edx; hFile
0x18000a3df  lea     rcx, LibFileName; "advapi32.dll"
0x18000a3e6  call    cs:__imp_LoadLibraryExW
0x18000a3ec  test    rax, rax
0x18000a3ef  jz      short loc_18000A405
0x18000a3f1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000a3f8  mov     rcx, rax; hModule
0x18000a3fb  call    cs:__imp_GetProcAddress
0x18000a401  mov     [rbx+10h], rax
0x18000a405  mov     rax, [rbx+8]
0x18000a409  test    rax, rax
0x18000a40c  jz      short loc_18000A421
0x18000a40e  xor     r9d, r9d
0x18000a411  xor     r8d, r8d
0x18000a414  mov     rdx, rdi
0x18000a417  mov     rcx, [rbx]
0x18000a41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41f  jmp     short loc_18000A43E
0x18000a421  mov     rax, [rbx+10h]
0x18000a425  test    rax, rax
0x18000a428  jz      short loc_18000A437
0x18000a42a  mov     rdx, rdi
0x18000a42d  mov     rcx, [rbx]
0x18000a430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a435  jmp     short loc_18000A43E
0x18000a437  call    cs:__imp_GetLastError
0x18000a43d  nop
0x18000a43e  mov     rbx, [rsp+38h+arg_0]
0x18000a443  add     rsp, 30h
0x18000a447  pop     rdi
0x18000a448  retn
```
