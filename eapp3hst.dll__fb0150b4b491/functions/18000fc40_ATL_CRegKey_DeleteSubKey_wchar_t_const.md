# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000fc40`
- end: `0x18000fcf5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010328`
- `0x18001075c`

## callees

- `0x18000fc40`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fca7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fc92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fc92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fc65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fce3`

## string_xrefs

- `0x18000fc5e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000fc70`: `RegDeleteKeyExW`
- `0x18000fc8b`: `advapi32.dll`
- `0x18000fc9d`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const wchar_t *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const wchar_t *); // rax

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
  v6 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const wchar_t *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18000fc40  mov     [rsp+arg_0], rbx
0x18000fc45  push    rdi
0x18000fc46  sub     rsp, 30h
0x18000fc4a  mov     rdi, rdx
0x18000fc4d  mov     rbx, rcx
0x18000fc50  cmp     qword ptr [rcx+8], 0
0x18000fc55  jnz     short loc_18000FCB1
0x18000fc57  cmp     qword ptr [rcx+10h], 0
0x18000fc5c  jnz     short loc_18000FCB1
0x18000fc5e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000fc65  call    cs:__imp_GetModuleHandleW
0x18000fc6b  test    rax, rax
0x18000fc6e  jz      short loc_18000FC86
0x18000fc70  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000fc77  mov     rcx, rax; hModule
0x18000fc7a  call    cs:__imp_GetProcAddress
0x18000fc80  mov     [rbx+8], rax
0x18000fc84  jmp     short loc_18000FCB1
0x18000fc86  xor     r8d, r8d; dwFlags
0x18000fc89  xor     edx, edx; hFile
0x18000fc8b  lea     rcx, LibFileName; "advapi32.dll"
0x18000fc92  call    cs:__imp_LoadLibraryExW
0x18000fc98  test    rax, rax
0x18000fc9b  jz      short loc_18000FCB1
0x18000fc9d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000fca4  mov     rcx, rax; hModule
0x18000fca7  call    cs:__imp_GetProcAddress
0x18000fcad  mov     [rbx+10h], rax
0x18000fcb1  mov     rax, [rbx+8]
0x18000fcb5  test    rax, rax
0x18000fcb8  jz      short loc_18000FCCD
0x18000fcba  xor     r9d, r9d
0x18000fcbd  xor     r8d, r8d
0x18000fcc0  mov     rdx, rdi
0x18000fcc3  mov     rcx, [rbx]
0x18000fcc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fccb  jmp     short loc_18000FCEA
0x18000fccd  mov     rax, [rbx+10h]
0x18000fcd1  test    rax, rax
0x18000fcd4  jz      short loc_18000FCE3
0x18000fcd6  mov     rdx, rdi
0x18000fcd9  mov     rcx, [rbx]
0x18000fcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fce1  jmp     short loc_18000FCEA
0x18000fce3  call    cs:__imp_GetLastError
0x18000fce9  nop
0x18000fcea  mov     rbx, [rsp+38h+arg_0]
0x18000fcef  add     rsp, 30h
0x18000fcf3  pop     rdi
0x18000fcf4  retn
```
