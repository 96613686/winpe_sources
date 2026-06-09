# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800114a0`
- end: `0x180011554`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180012218`
- `0x180012874`

## callees

- `0x1800114a0`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800114f2`
- `KERNEL32!LoadLibraryExW` at `0x1800114f2`
- `KERNEL32!GetProcAddress` at `0x1800114da`
- `KERNEL32!GetProcAddress` at `0x180011507`
- `KERNEL32!GetProcAddress` at `0x1800114da`
- `KERNEL32!GetProcAddress` at `0x180011507`
- `KERNEL32!GetLastError` at `0x180011543`
- `KERNEL32!GetLastError` at `0x180011543`
- `KERNEL32!GetModuleHandleW` at `0x1800114c5`
- `KERNEL32!GetModuleHandleW` at `0x1800114c5`

## string_xrefs

- `0x1800114be`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800114d0`: `RegDeleteKeyExW`
- `0x1800114e9`: `advapi32.dll`
- `0x1800114fd`: `RegDeleteKeyW`

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
0x1800114a0  mov     [rsp+arg_0], rbx
0x1800114a5  push    rdi
0x1800114a6  sub     rsp, 30h
0x1800114aa  cmp     qword ptr [rcx+8], 0
0x1800114af  mov     rdi, rdx
0x1800114b2  mov     rbx, rcx
0x1800114b5  jnz     short loc_180011511
0x1800114b7  cmp     qword ptr [rcx+10h], 0
0x1800114bc  jnz     short loc_180011511
0x1800114be  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800114c5  call    cs:__imp_GetModuleHandleW
0x1800114cb  test    rax, rax
0x1800114ce  jz      short loc_1800114E6
0x1800114d0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800114d7  mov     rcx, rax; hModule
0x1800114da  call    cs:__imp_GetProcAddress
0x1800114e0  mov     [rbx+8], rax
0x1800114e4  jmp     short loc_180011511
0x1800114e6  xor     r8d, r8d; dwFlags
0x1800114e9  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800114f0  xor     edx, edx; hFile
0x1800114f2  call    cs:__imp_LoadLibraryExW
0x1800114f8  test    rax, rax
0x1800114fb  jz      short loc_180011511
0x1800114fd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180011504  mov     rcx, rax; hModule
0x180011507  call    cs:__imp_GetProcAddress
0x18001150d  mov     [rbx+10h], rax
0x180011511  mov     rax, [rbx+8]
0x180011515  test    rax, rax
0x180011518  jz      short loc_18001152D
0x18001151a  mov     rcx, [rbx]
0x18001151d  xor     r9d, r9d
0x180011520  xor     r8d, r8d
0x180011523  mov     rdx, rdi
0x180011526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001152b  jmp     short loc_180011549
0x18001152d  mov     rax, [rbx+10h]
0x180011531  test    rax, rax
0x180011534  jz      short loc_180011543
0x180011536  mov     rcx, [rbx]
0x180011539  mov     rdx, rdi
0x18001153c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011541  jmp     short loc_180011549
0x180011543  call    cs:__imp_GetLastError
0x180011549  mov     rbx, [rsp+38h+arg_0]
0x18001154e  add     rsp, 30h
0x180011552  pop     rdi
0x180011553  retn
```
