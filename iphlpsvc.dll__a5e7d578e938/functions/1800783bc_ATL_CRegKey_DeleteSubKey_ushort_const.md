# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800783bc`
- end: `0x180078490`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180078b3c`
- `0x180078fb0`

## callees

- `0x1800783bc`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078477`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800783fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078435`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800783fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078435`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800783e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800783e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007841a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007841a`

## string_xrefs

- `0x1800783da`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800783f2`: `RegDeleteKeyExW`
- `0x180078413`: `advapi32.dll`
- `0x18007842b`: `RegDeleteKeyW`

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
0x1800783bc  mov     [rsp+arg_0], rbx
0x1800783c1  push    rdi
0x1800783c2  sub     rsp, 30h
0x1800783c6  mov     rdi, rdx
0x1800783c9  mov     rbx, rcx
0x1800783cc  cmp     qword ptr [rcx+8], 0
0x1800783d1  jnz     short loc_180078445
0x1800783d3  cmp     qword ptr [rcx+10h], 0
0x1800783d8  jnz     short loc_180078445
0x1800783da  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800783e1  call    cs:__imp_GetModuleHandleW
0x1800783e8  nop     dword ptr [rax+rax+00h]
0x1800783ed  test    rax, rax
0x1800783f0  jz      short loc_18007840E
0x1800783f2  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800783f9  mov     rcx, rax; hModule
0x1800783fc  call    cs:__imp_GetProcAddress
0x180078403  nop     dword ptr [rax+rax+00h]
0x180078408  mov     [rbx+8], rax
0x18007840c  jmp     short loc_180078445
0x18007840e  xor     r8d, r8d; dwFlags
0x180078411  xor     edx, edx; hFile
0x180078413  lea     rcx, LibFileName; "advapi32.dll"
0x18007841a  call    cs:__imp_LoadLibraryExW
0x180078421  nop     dword ptr [rax+rax+00h]
0x180078426  test    rax, rax
0x180078429  jz      short loc_180078445
0x18007842b  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180078432  mov     rcx, rax; hModule
0x180078435  call    cs:__imp_GetProcAddress
0x18007843c  nop     dword ptr [rax+rax+00h]
0x180078441  mov     [rbx+10h], rax
0x180078445  mov     rax, [rbx+8]
0x180078449  test    rax, rax
0x18007844c  jz      short loc_180078461
0x18007844e  xor     r9d, r9d
0x180078451  xor     r8d, r8d
0x180078454  mov     rdx, rdi
0x180078457  mov     rcx, [rbx]
0x18007845a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007845f  jmp     short loc_180078484
0x180078461  mov     rax, [rbx+10h]
0x180078465  test    rax, rax
0x180078468  jz      short loc_180078477
0x18007846a  mov     rdx, rdi
0x18007846d  mov     rcx, [rbx]
0x180078470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078475  jmp     short loc_180078484
0x180078477  call    cs:__imp_GetLastError
0x18007847e  nop     dword ptr [rax+rax+00h]
0x180078483  nop
0x180078484  mov     rbx, [rsp+38h+arg_0]
0x180078489  add     rsp, 30h
0x18007848d  pop     rdi
0x18007848e  retn
```
