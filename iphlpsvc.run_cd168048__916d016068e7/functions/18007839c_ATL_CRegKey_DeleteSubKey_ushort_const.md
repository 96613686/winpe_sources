# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18007839c`
- end: `0x180078470`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180078b1c`
- `0x180078f90`

## callees

- `0x18007839c`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078457`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800783dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078415`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800783dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078415`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800783c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800783c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800783fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800783fa`

## string_xrefs

- `0x1800783ba`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800783d2`: `RegDeleteKeyExW`
- `0x1800783f3`: `advapi32.dll`
- `0x18007840b`: `RegDeleteKeyW`

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
0x18007839c  mov     [rsp+arg_0], rbx
0x1800783a1  push    rdi
0x1800783a2  sub     rsp, 30h
0x1800783a6  mov     rdi, rdx
0x1800783a9  mov     rbx, rcx
0x1800783ac  cmp     qword ptr [rcx+8], 0
0x1800783b1  jnz     short loc_180078425
0x1800783b3  cmp     qword ptr [rcx+10h], 0
0x1800783b8  jnz     short loc_180078425
0x1800783ba  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800783c1  call    cs:__imp_GetModuleHandleW
0x1800783c8  nop     dword ptr [rax+rax+00h]
0x1800783cd  test    rax, rax
0x1800783d0  jz      short loc_1800783EE
0x1800783d2  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800783d9  mov     rcx, rax; hModule
0x1800783dc  call    cs:__imp_GetProcAddress
0x1800783e3  nop     dword ptr [rax+rax+00h]
0x1800783e8  mov     [rbx+8], rax
0x1800783ec  jmp     short loc_180078425
0x1800783ee  xor     r8d, r8d; dwFlags
0x1800783f1  xor     edx, edx; hFile
0x1800783f3  lea     rcx, LibFileName; "advapi32.dll"
0x1800783fa  call    cs:__imp_LoadLibraryExW
0x180078401  nop     dword ptr [rax+rax+00h]
0x180078406  test    rax, rax
0x180078409  jz      short loc_180078425
0x18007840b  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180078412  mov     rcx, rax; hModule
0x180078415  call    cs:__imp_GetProcAddress
0x18007841c  nop     dword ptr [rax+rax+00h]
0x180078421  mov     [rbx+10h], rax
0x180078425  mov     rax, [rbx+8]
0x180078429  test    rax, rax
0x18007842c  jz      short loc_180078441
0x18007842e  xor     r9d, r9d
0x180078431  xor     r8d, r8d
0x180078434  mov     rdx, rdi
0x180078437  mov     rcx, [rbx]
0x18007843a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007843f  jmp     short loc_180078464
0x180078441  mov     rax, [rbx+10h]
0x180078445  test    rax, rax
0x180078448  jz      short loc_180078457
0x18007844a  mov     rdx, rdi
0x18007844d  mov     rcx, [rbx]
0x180078450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078455  jmp     short loc_180078464
0x180078457  call    cs:__imp_GetLastError
0x18007845e  nop     dword ptr [rax+rax+00h]
0x180078463  nop
0x180078464  mov     rbx, [rsp+38h+arg_0]
0x180078469  add     rsp, 30h
0x18007846d  pop     rdi
0x18007846e  retn
```
