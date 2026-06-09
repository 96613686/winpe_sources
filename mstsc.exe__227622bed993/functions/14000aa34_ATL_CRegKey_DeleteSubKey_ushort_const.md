# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x14000aa34`
- end: `0x14000aae8`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a198`
- `0x14000b86c`
- `0x14000bf0c`

## callees

- `0x14000aa34`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000aa86`
- `KERNEL32!LoadLibraryExW` at `0x14000aa86`
- `KERNEL32!GetModuleHandleW` at `0x14000aa59`
- `KERNEL32!GetModuleHandleW` at `0x14000aa59`
- `KERNEL32!GetProcAddress` at `0x14000aa6e`
- `KERNEL32!GetProcAddress` at `0x14000aa9b`
- `KERNEL32!GetProcAddress` at `0x14000aa6e`
- `KERNEL32!GetProcAddress` at `0x14000aa9b`
- `KERNEL32!GetLastError` at `0x14000aad7`
- `KERNEL32!GetLastError` at `0x14000aad7`

## string_xrefs

- `0x14000aa52`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14000aa64`: `RegDeleteKeyExW`
- `0x14000aa7d`: `advapi32.dll`
- `0x14000aa91`: `RegDeleteKeyW`

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
0x14000aa34  mov     [rsp+arg_0], rbx
0x14000aa39  push    rdi
0x14000aa3a  sub     rsp, 30h
0x14000aa3e  cmp     qword ptr [rcx+8], 0
0x14000aa43  mov     rdi, rdx
0x14000aa46  mov     rbx, rcx
0x14000aa49  jnz     short loc_14000AAA5
0x14000aa4b  cmp     qword ptr [rcx+10h], 0
0x14000aa50  jnz     short loc_14000AAA5
0x14000aa52  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14000aa59  call    cs:__imp_GetModuleHandleW
0x14000aa5f  test    rax, rax
0x14000aa62  jz      short loc_14000AA7A
0x14000aa64  lea     rdx, ProcName; "RegDeleteKeyExW"
0x14000aa6b  mov     rcx, rax; hModule
0x14000aa6e  call    cs:__imp_GetProcAddress
0x14000aa74  mov     [rbx+8], rax
0x14000aa78  jmp     short loc_14000AAA5
0x14000aa7a  xor     r8d, r8d; dwFlags
0x14000aa7d  lea     rcx, LibFileName; "advapi32.dll"
0x14000aa84  xor     edx, edx; hFile
0x14000aa86  call    cs:__imp_LoadLibraryExW
0x14000aa8c  test    rax, rax
0x14000aa8f  jz      short loc_14000AAA5
0x14000aa91  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14000aa98  mov     rcx, rax; hModule
0x14000aa9b  call    cs:__imp_GetProcAddress
0x14000aaa1  mov     [rbx+10h], rax
0x14000aaa5  mov     rax, [rbx+8]
0x14000aaa9  test    rax, rax
0x14000aaac  jz      short loc_14000AAC1
0x14000aaae  mov     rcx, [rbx]
0x14000aab1  xor     r9d, r9d
0x14000aab4  xor     r8d, r8d
0x14000aab7  mov     rdx, rdi
0x14000aaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aabf  jmp     short loc_14000AADD
0x14000aac1  mov     rax, [rbx+10h]
0x14000aac5  test    rax, rax
0x14000aac8  jz      short loc_14000AAD7
0x14000aaca  mov     rcx, [rbx]
0x14000aacd  mov     rdx, rdi
0x14000aad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aad5  jmp     short loc_14000AADD
0x14000aad7  call    cs:__imp_GetLastError
0x14000aadd  mov     rbx, [rsp+38h+arg_0]
0x14000aae2  add     rsp, 30h
0x14000aae6  pop     rdi
0x14000aae7  retn
```
