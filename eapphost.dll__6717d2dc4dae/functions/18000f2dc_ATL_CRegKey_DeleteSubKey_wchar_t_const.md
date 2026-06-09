# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000f2dc`
- end: `0x18000f391`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000fa68`
- `0x18000fea0`

## callees

- `0x18000f2dc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f301`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f301`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f32e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f32e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f316`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f316`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f37f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f37f`

## string_xrefs

- `0x18000f2fa`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000f30c`: `RegDeleteKeyExW`
- `0x18000f327`: `advapi32.dll`
- `0x18000f339`: `RegDeleteKeyW`

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
0x18000f2dc  mov     [rsp+arg_0], rbx
0x18000f2e1  push    rdi
0x18000f2e2  sub     rsp, 30h
0x18000f2e6  mov     rdi, rdx
0x18000f2e9  mov     rbx, rcx
0x18000f2ec  cmp     qword ptr [rcx+8], 0
0x18000f2f1  jnz     short loc_18000F34D
0x18000f2f3  cmp     qword ptr [rcx+10h], 0
0x18000f2f8  jnz     short loc_18000F34D
0x18000f2fa  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000f301  call    cs:__imp_GetModuleHandleW
0x18000f307  test    rax, rax
0x18000f30a  jz      short loc_18000F322
0x18000f30c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000f313  mov     rcx, rax; hModule
0x18000f316  call    cs:__imp_GetProcAddress
0x18000f31c  mov     [rbx+8], rax
0x18000f320  jmp     short loc_18000F34D
0x18000f322  xor     r8d, r8d; dwFlags
0x18000f325  xor     edx, edx; hFile
0x18000f327  lea     rcx, LibFileName; "advapi32.dll"
0x18000f32e  call    cs:__imp_LoadLibraryExW
0x18000f334  test    rax, rax
0x18000f337  jz      short loc_18000F34D
0x18000f339  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000f340  mov     rcx, rax; hModule
0x18000f343  call    cs:__imp_GetProcAddress
0x18000f349  mov     [rbx+10h], rax
0x18000f34d  mov     rax, [rbx+8]
0x18000f351  test    rax, rax
0x18000f354  jz      short loc_18000F369
0x18000f356  xor     r9d, r9d
0x18000f359  xor     r8d, r8d
0x18000f35c  mov     rdx, rdi
0x18000f35f  mov     rcx, [rbx]
0x18000f362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f367  jmp     short loc_18000F386
0x18000f369  mov     rax, [rbx+10h]
0x18000f36d  test    rax, rax
0x18000f370  jz      short loc_18000F37F
0x18000f372  mov     rdx, rdi
0x18000f375  mov     rcx, [rbx]
0x18000f378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f37d  jmp     short loc_18000F386
0x18000f37f  call    cs:__imp_GetLastError
0x18000f385  nop
0x18000f386  mov     rbx, [rsp+38h+arg_0]
0x18000f38b  add     rsp, 30h
0x18000f38f  pop     rdi
0x18000f390  retn
```
