# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000a0ec`
- end: `0x18000a1a1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a9f8`
- `0x18000ae30`

## callees

- `0x18000a0ec`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000a126`
- `KERNEL32!GetProcAddress` at `0x18000a153`
- `KERNEL32!GetProcAddress` at `0x18000a126`
- `KERNEL32!GetProcAddress` at `0x18000a153`
- `KERNEL32!GetLastError` at `0x18000a18f`
- `KERNEL32!GetLastError` at `0x18000a18f`
- `KERNEL32!LoadLibraryExW` at `0x18000a13e`
- `KERNEL32!LoadLibraryExW` at `0x18000a13e`
- `KERNEL32!GetModuleHandleW` at `0x18000a111`
- `KERNEL32!GetModuleHandleW` at `0x18000a111`

## string_xrefs

- `0x18000a10a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000a11c`: `RegDeleteKeyExW`
- `0x18000a137`: `advapi32.dll`
- `0x18000a149`: `RegDeleteKeyW`

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
0x18000a0ec  mov     [rsp+arg_0], rbx
0x18000a0f1  push    rdi
0x18000a0f2  sub     rsp, 30h
0x18000a0f6  mov     rdi, rdx
0x18000a0f9  mov     rbx, rcx
0x18000a0fc  cmp     qword ptr [rcx+8], 0
0x18000a101  jnz     short loc_18000A15D
0x18000a103  cmp     qword ptr [rcx+10h], 0
0x18000a108  jnz     short loc_18000A15D
0x18000a10a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000a111  call    cs:__imp_GetModuleHandleW
0x18000a117  test    rax, rax
0x18000a11a  jz      short loc_18000A132
0x18000a11c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000a123  mov     rcx, rax; hModule
0x18000a126  call    cs:__imp_GetProcAddress
0x18000a12c  mov     [rbx+8], rax
0x18000a130  jmp     short loc_18000A15D
0x18000a132  xor     r8d, r8d; dwFlags
0x18000a135  xor     edx, edx; hFile
0x18000a137  lea     rcx, LibFileName; "advapi32.dll"
0x18000a13e  call    cs:__imp_LoadLibraryExW
0x18000a144  test    rax, rax
0x18000a147  jz      short loc_18000A15D
0x18000a149  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000a150  mov     rcx, rax; hModule
0x18000a153  call    cs:__imp_GetProcAddress
0x18000a159  mov     [rbx+10h], rax
0x18000a15d  mov     rax, [rbx+8]
0x18000a161  test    rax, rax
0x18000a164  jz      short loc_18000A179
0x18000a166  xor     r9d, r9d
0x18000a169  xor     r8d, r8d
0x18000a16c  mov     rdx, rdi
0x18000a16f  mov     rcx, [rbx]
0x18000a172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a177  jmp     short loc_18000A196
0x18000a179  mov     rax, [rbx+10h]
0x18000a17d  test    rax, rax
0x18000a180  jz      short loc_18000A18F
0x18000a182  mov     rdx, rdi
0x18000a185  mov     rcx, [rbx]
0x18000a188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18d  jmp     short loc_18000A196
0x18000a18f  call    cs:__imp_GetLastError
0x18000a195  nop
0x18000a196  mov     rbx, [rsp+38h+arg_0]
0x18000a19b  add     rsp, 30h
0x18000a19f  pop     rdi
0x18000a1a0  retn
```
