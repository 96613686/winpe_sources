# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180055354`
- end: `0x180055428`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800576c4`
- `0x180057fd0`

## callees

- `0x180055354`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800553b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800553b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055394`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800553cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055394`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800553cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180055379`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180055379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005540f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005540f`

## string_xrefs

- `0x180055372`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18005538a`: `RegDeleteKeyExW`
- `0x1800553ab`: `advapi32.dll`
- `0x1800553c3`: `RegDeleteKeyW`

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
0x180055354  mov     [rsp+arg_0], rbx
0x180055359  push    rdi
0x18005535a  sub     rsp, 30h
0x18005535e  mov     rdi, rdx
0x180055361  mov     rbx, rcx
0x180055364  cmp     qword ptr [rcx+8], 0
0x180055369  jnz     short loc_1800553DD
0x18005536b  cmp     qword ptr [rcx+10h], 0
0x180055370  jnz     short loc_1800553DD
0x180055372  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180055379  call    cs:__imp_GetModuleHandleW
0x180055380  nop     dword ptr [rax+rax+00h]
0x180055385  test    rax, rax
0x180055388  jz      short loc_1800553A6
0x18005538a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180055391  mov     rcx, rax; hModule
0x180055394  call    cs:__imp_GetProcAddress
0x18005539b  nop     dword ptr [rax+rax+00h]
0x1800553a0  mov     [rbx+8], rax
0x1800553a4  jmp     short loc_1800553DD
0x1800553a6  xor     r8d, r8d; dwFlags
0x1800553a9  xor     edx, edx; hFile
0x1800553ab  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800553b2  call    cs:__imp_LoadLibraryExW
0x1800553b9  nop     dword ptr [rax+rax+00h]
0x1800553be  test    rax, rax
0x1800553c1  jz      short loc_1800553DD
0x1800553c3  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800553ca  mov     rcx, rax; hModule
0x1800553cd  call    cs:__imp_GetProcAddress
0x1800553d4  nop     dword ptr [rax+rax+00h]
0x1800553d9  mov     [rbx+10h], rax
0x1800553dd  mov     rax, [rbx+8]
0x1800553e1  test    rax, rax
0x1800553e4  jz      short loc_1800553F9
0x1800553e6  xor     r9d, r9d
0x1800553e9  xor     r8d, r8d
0x1800553ec  mov     rdx, rdi
0x1800553ef  mov     rcx, [rbx]
0x1800553f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553f7  jmp     short loc_18005541C
0x1800553f9  mov     rax, [rbx+10h]
0x1800553fd  test    rax, rax
0x180055400  jz      short loc_18005540F
0x180055402  mov     rdx, rdi
0x180055405  mov     rcx, [rbx]
0x180055408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005540d  jmp     short loc_18005541C
0x18005540f  call    cs:__imp_GetLastError
0x180055416  nop     dword ptr [rax+rax+00h]
0x18005541b  nop
0x18005541c  mov     rbx, [rsp+38h+arg_0]
0x180055421  add     rsp, 30h
0x180055425  pop     rdi
0x180055426  retn
```
