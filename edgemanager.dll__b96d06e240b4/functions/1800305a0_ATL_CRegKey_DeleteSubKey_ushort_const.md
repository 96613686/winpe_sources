# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800305a0`
- end: `0x180030655`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f8e0`
- `0x180031db8`
- `0x180032298`

## callees

- `0x1800305a0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800305f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800305f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800305c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800305c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800305da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030607`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800305da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030643`

## string_xrefs

- `0x1800305be`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800305d0`: `RegDeleteKeyExW`
- `0x1800305eb`: `advapi32.dll`
- `0x1800305fd`: `RegDeleteKeyW`

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
0x1800305a0  mov     [rsp+arg_0], rbx
0x1800305a5  push    rdi
0x1800305a6  sub     rsp, 30h
0x1800305aa  mov     rdi, rdx
0x1800305ad  mov     rbx, rcx
0x1800305b0  cmp     qword ptr [rcx+8], 0
0x1800305b5  jnz     short loc_180030611
0x1800305b7  cmp     qword ptr [rcx+10h], 0
0x1800305bc  jnz     short loc_180030611
0x1800305be  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800305c5  call    cs:__imp_GetModuleHandleW
0x1800305cb  test    rax, rax
0x1800305ce  jz      short loc_1800305E6
0x1800305d0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800305d7  mov     rcx, rax; hModule
0x1800305da  call    cs:__imp_GetProcAddress
0x1800305e0  mov     [rbx+8], rax
0x1800305e4  jmp     short loc_180030611
0x1800305e6  xor     r8d, r8d; dwFlags
0x1800305e9  xor     edx, edx; hFile
0x1800305eb  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800305f2  call    cs:__imp_LoadLibraryExW
0x1800305f8  test    rax, rax
0x1800305fb  jz      short loc_180030611
0x1800305fd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180030604  mov     rcx, rax; hModule
0x180030607  call    cs:__imp_GetProcAddress
0x18003060d  mov     [rbx+10h], rax
0x180030611  mov     rax, [rbx+8]
0x180030615  test    rax, rax
0x180030618  jz      short loc_18003062D
0x18003061a  xor     r9d, r9d
0x18003061d  xor     r8d, r8d
0x180030620  mov     rdx, rdi
0x180030623  mov     rcx, [rbx]
0x180030626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003062b  jmp     short loc_18003064A
0x18003062d  mov     rax, [rbx+10h]
0x180030631  test    rax, rax
0x180030634  jz      short loc_180030643
0x180030636  mov     rdx, rdi
0x180030639  mov     rcx, [rbx]
0x18003063c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030641  jmp     short loc_18003064A
0x180030643  call    cs:__imp_GetLastError
0x180030649  nop
0x18003064a  mov     rbx, [rsp+38h+arg_0]
0x18003064f  add     rsp, 30h
0x180030653  pop     rdi
0x180030654  retn
```
