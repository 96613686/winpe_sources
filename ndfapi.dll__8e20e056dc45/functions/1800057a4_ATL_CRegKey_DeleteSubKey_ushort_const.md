# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800057a4`
- end: `0x180005859`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004fdc`
- `0x180005de8`
- `0x1800062ac`

## callees

- `0x1800057a4`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800057de`
- `KERNEL32!GetProcAddress` at `0x18000580b`
- `KERNEL32!GetProcAddress` at `0x1800057de`
- `KERNEL32!GetProcAddress` at `0x18000580b`
- `KERNEL32!GetModuleHandleW` at `0x1800057c9`
- `KERNEL32!GetModuleHandleW` at `0x1800057c9`
- `KERNEL32!GetLastError` at `0x180005847`
- `KERNEL32!GetLastError` at `0x180005847`
- `KERNEL32!LoadLibraryExW` at `0x1800057f6`
- `KERNEL32!LoadLibraryExW` at `0x1800057f6`

## string_xrefs

- `0x1800057c2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800057d4`: `RegDeleteKeyExW`
- `0x1800057ef`: `advapi32.dll`
- `0x180005801`: `RegDeleteKeyW`

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
0x1800057a4  mov     [rsp+arg_0], rbx
0x1800057a9  push    rdi
0x1800057aa  sub     rsp, 30h
0x1800057ae  mov     rdi, rdx
0x1800057b1  mov     rbx, rcx
0x1800057b4  cmp     qword ptr [rcx+8], 0
0x1800057b9  jnz     short loc_180005815
0x1800057bb  cmp     qword ptr [rcx+10h], 0
0x1800057c0  jnz     short loc_180005815
0x1800057c2  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800057c9  call    cs:__imp_GetModuleHandleW
0x1800057cf  test    rax, rax
0x1800057d2  jz      short loc_1800057EA
0x1800057d4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800057db  mov     rcx, rax; hModule
0x1800057de  call    cs:__imp_GetProcAddress
0x1800057e4  mov     [rbx+8], rax
0x1800057e8  jmp     short loc_180005815
0x1800057ea  xor     r8d, r8d; dwFlags
0x1800057ed  xor     edx, edx; hFile
0x1800057ef  lea     rcx, LibFileName; "advapi32.dll"
0x1800057f6  call    cs:__imp_LoadLibraryExW
0x1800057fc  test    rax, rax
0x1800057ff  jz      short loc_180005815
0x180005801  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180005808  mov     rcx, rax; hModule
0x18000580b  call    cs:__imp_GetProcAddress
0x180005811  mov     [rbx+10h], rax
0x180005815  mov     rax, [rbx+8]
0x180005819  test    rax, rax
0x18000581c  jz      short loc_180005831
0x18000581e  xor     r9d, r9d
0x180005821  xor     r8d, r8d
0x180005824  mov     rdx, rdi
0x180005827  mov     rcx, [rbx]
0x18000582a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582f  jmp     short loc_18000584E
0x180005831  mov     rax, [rbx+10h]
0x180005835  test    rax, rax
0x180005838  jz      short loc_180005847
0x18000583a  mov     rdx, rdi
0x18000583d  mov     rcx, [rbx]
0x180005840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005845  jmp     short loc_18000584E
0x180005847  call    cs:__imp_GetLastError
0x18000584d  nop
0x18000584e  mov     rbx, [rsp+38h+arg_0]
0x180005853  add     rsp, 30h
0x180005857  pop     rdi
0x180005858  retn
```
