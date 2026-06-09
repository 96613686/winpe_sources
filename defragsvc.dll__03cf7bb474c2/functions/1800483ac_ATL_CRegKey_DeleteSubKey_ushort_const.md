# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800483ac`
- end: `0x180048461`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180047d5c`
- `0x180048d88`
- `0x1800493b8`

## callees

- `0x1800483ac`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004844f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004844f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800483d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800483d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800483fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800483fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800483e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048413`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800483e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048413`

## string_xrefs

- `0x1800483ca`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800483dc`: `RegDeleteKeyExW`
- `0x1800483f7`: `advapi32.dll`
- `0x180048409`: `RegDeleteKeyW`

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
0x1800483ac  mov     [rsp+arg_0], rbx
0x1800483b1  push    rdi
0x1800483b2  sub     rsp, 30h
0x1800483b6  mov     rdi, rdx
0x1800483b9  mov     rbx, rcx
0x1800483bc  cmp     qword ptr [rcx+8], 0
0x1800483c1  jnz     short loc_18004841D
0x1800483c3  cmp     qword ptr [rcx+10h], 0
0x1800483c8  jnz     short loc_18004841D
0x1800483ca  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800483d1  call    cs:__imp_GetModuleHandleW
0x1800483d7  test    rax, rax
0x1800483da  jz      short loc_1800483F2
0x1800483dc  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800483e3  mov     rcx, rax; hModule
0x1800483e6  call    cs:__imp_GetProcAddress
0x1800483ec  mov     [rbx+8], rax
0x1800483f0  jmp     short loc_18004841D
0x1800483f2  xor     r8d, r8d; dwFlags
0x1800483f5  xor     edx, edx; hFile
0x1800483f7  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800483fe  call    cs:__imp_LoadLibraryExW
0x180048404  test    rax, rax
0x180048407  jz      short loc_18004841D
0x180048409  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180048410  mov     rcx, rax; hModule
0x180048413  call    cs:__imp_GetProcAddress
0x180048419  mov     [rbx+10h], rax
0x18004841d  mov     rax, [rbx+8]
0x180048421  test    rax, rax
0x180048424  jz      short loc_180048439
0x180048426  xor     r9d, r9d
0x180048429  xor     r8d, r8d
0x18004842c  mov     rdx, rdi
0x18004842f  mov     rcx, [rbx]
0x180048432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048437  jmp     short loc_180048456
0x180048439  mov     rax, [rbx+10h]
0x18004843d  test    rax, rax
0x180048440  jz      short loc_18004844F
0x180048442  mov     rdx, rdi
0x180048445  mov     rcx, [rbx]
0x180048448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004844d  jmp     short loc_180048456
0x18004844f  call    cs:__imp_GetLastError
0x180048455  nop
0x180048456  mov     rbx, [rsp+38h+arg_0]
0x18004845b  add     rsp, 30h
0x18004845f  pop     rdi
0x180048460  retn
```
