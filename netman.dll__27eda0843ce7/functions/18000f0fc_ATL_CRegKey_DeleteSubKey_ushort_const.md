# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000f0fc`
- end: `0x18000f1b1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180014780`
- `0x180014d38`

## callees

- `0x18000f0fc`
- `0x180036010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000f14e`
- `KERNEL32!LoadLibraryExW` at `0x18000f14e`
- `KERNEL32!GetLastError` at `0x18000f19f`
- `KERNEL32!GetLastError` at `0x18000f19f`
- `KERNEL32!GetModuleHandleW` at `0x18000f121`
- `KERNEL32!GetModuleHandleW` at `0x18000f121`
- `KERNEL32!GetProcAddress` at `0x18000f136`
- `KERNEL32!GetProcAddress` at `0x18000f163`
- `KERNEL32!GetProcAddress` at `0x18000f136`
- `KERNEL32!GetProcAddress` at `0x18000f163`

## string_xrefs

- `0x18000f11a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000f12c`: `RegDeleteKeyExW`
- `0x18000f147`: `advapi32.dll`
- `0x18000f159`: `RegDeleteKeyW`

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
0x18000f0fc  mov     [rsp+arg_0], rbx
0x18000f101  push    rdi
0x18000f102  sub     rsp, 30h
0x18000f106  mov     rdi, rdx
0x18000f109  mov     rbx, rcx
0x18000f10c  cmp     qword ptr [rcx+8], 0
0x18000f111  jnz     short loc_18000F16D
0x18000f113  cmp     qword ptr [rcx+10h], 0
0x18000f118  jnz     short loc_18000F16D
0x18000f11a  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000f121  call    cs:__imp_GetModuleHandleW
0x18000f127  test    rax, rax
0x18000f12a  jz      short loc_18000F142
0x18000f12c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000f133  mov     rcx, rax; hModule
0x18000f136  call    cs:__imp_GetProcAddress
0x18000f13c  mov     [rbx+8], rax
0x18000f140  jmp     short loc_18000F16D
0x18000f142  xor     r8d, r8d; dwFlags
0x18000f145  xor     edx, edx; hFile
0x18000f147  lea     rcx, LibFileName; "advapi32.dll"
0x18000f14e  call    cs:__imp_LoadLibraryExW
0x18000f154  test    rax, rax
0x18000f157  jz      short loc_18000F16D
0x18000f159  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000f160  mov     rcx, rax; hModule
0x18000f163  call    cs:__imp_GetProcAddress
0x18000f169  mov     [rbx+10h], rax
0x18000f16d  mov     rax, [rbx+8]
0x18000f171  test    rax, rax
0x18000f174  jz      short loc_18000F189
0x18000f176  xor     r9d, r9d
0x18000f179  xor     r8d, r8d
0x18000f17c  mov     rdx, rdi
0x18000f17f  mov     rcx, [rbx]
0x18000f182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f187  jmp     short loc_18000F1A6
0x18000f189  mov     rax, [rbx+10h]
0x18000f18d  test    rax, rax
0x18000f190  jz      short loc_18000F19F
0x18000f192  mov     rdx, rdi
0x18000f195  mov     rcx, [rbx]
0x18000f198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f19d  jmp     short loc_18000F1A6
0x18000f19f  call    cs:__imp_GetLastError
0x18000f1a5  nop
0x18000f1a6  mov     rbx, [rsp+38h+arg_0]
0x18000f1ab  add     rsp, 30h
0x18000f1af  pop     rdi
0x18000f1b0  retn
```
