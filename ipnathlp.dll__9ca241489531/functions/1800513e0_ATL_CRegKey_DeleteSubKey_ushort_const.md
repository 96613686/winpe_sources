# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800513e0`
- end: `0x180051495`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18005358c`
- `0x180053e48`

## callees

- `0x1800513e0`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051432`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051432`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005141a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051447`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005141a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051447`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051405`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051483`

## string_xrefs

- `0x1800513fe`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180051410`: `RegDeleteKeyExW`
- `0x18005142b`: `advapi32.dll`
- `0x18005143d`: `RegDeleteKeyW`

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
0x1800513e0  mov     [rsp+arg_0], rbx
0x1800513e5  push    rdi
0x1800513e6  sub     rsp, 30h
0x1800513ea  mov     rdi, rdx
0x1800513ed  mov     rbx, rcx
0x1800513f0  cmp     qword ptr [rcx+8], 0
0x1800513f5  jnz     short loc_180051451
0x1800513f7  cmp     qword ptr [rcx+10h], 0
0x1800513fc  jnz     short loc_180051451
0x1800513fe  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180051405  call    cs:__imp_GetModuleHandleW
0x18005140b  test    rax, rax
0x18005140e  jz      short loc_180051426
0x180051410  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180051417  mov     rcx, rax; hModule
0x18005141a  call    cs:__imp_GetProcAddress
0x180051420  mov     [rbx+8], rax
0x180051424  jmp     short loc_180051451
0x180051426  xor     r8d, r8d; dwFlags
0x180051429  xor     edx, edx; hFile
0x18005142b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180051432  call    cs:__imp_LoadLibraryExW
0x180051438  test    rax, rax
0x18005143b  jz      short loc_180051451
0x18005143d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180051444  mov     rcx, rax; hModule
0x180051447  call    cs:__imp_GetProcAddress
0x18005144d  mov     [rbx+10h], rax
0x180051451  mov     rax, [rbx+8]
0x180051455  test    rax, rax
0x180051458  jz      short loc_18005146D
0x18005145a  xor     r9d, r9d
0x18005145d  xor     r8d, r8d
0x180051460  mov     rdx, rdi
0x180051463  mov     rcx, [rbx]
0x180051466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005146b  jmp     short loc_18005148A
0x18005146d  mov     rax, [rbx+10h]
0x180051471  test    rax, rax
0x180051474  jz      short loc_180051483
0x180051476  mov     rdx, rdi
0x180051479  mov     rcx, [rbx]
0x18005147c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051481  jmp     short loc_18005148A
0x180051483  call    cs:__imp_GetLastError
0x180051489  nop
0x18005148a  mov     rbx, [rsp+38h+arg_0]
0x18005148f  add     rsp, 30h
0x180051493  pop     rdi
0x180051494  retn
```
