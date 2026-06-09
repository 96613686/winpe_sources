# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18006877c`
- end: `0x180068830`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180067e08`
- `0x180069438`
- `0x180069900`

## callees

- `0x18006877c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800687ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800687ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800687a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800687a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800687b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800687e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800687b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800687e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006881f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006881f`

## string_xrefs

- `0x18006879a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800687ac`: `RegDeleteKeyExW`
- `0x1800687c5`: `advapi32.dll`
- `0x1800687d9`: `RegDeleteKeyW`

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
0x18006877c  mov     [rsp+arg_0], rbx
0x180068781  push    rdi
0x180068782  sub     rsp, 30h
0x180068786  cmp     qword ptr [rcx+8], 0
0x18006878b  mov     rdi, rdx
0x18006878e  mov     rbx, rcx
0x180068791  jnz     short loc_1800687ED
0x180068793  cmp     qword ptr [rcx+10h], 0
0x180068798  jnz     short loc_1800687ED
0x18006879a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800687a1  call    cs:__imp_GetModuleHandleW
0x1800687a7  test    rax, rax
0x1800687aa  jz      short loc_1800687C2
0x1800687ac  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800687b3  mov     rcx, rax; hModule
0x1800687b6  call    cs:__imp_GetProcAddress
0x1800687bc  mov     [rbx+8], rax
0x1800687c0  jmp     short loc_1800687ED
0x1800687c2  xor     r8d, r8d; dwFlags
0x1800687c5  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800687cc  xor     edx, edx; hFile
0x1800687ce  call    cs:__imp_LoadLibraryExW
0x1800687d4  test    rax, rax
0x1800687d7  jz      short loc_1800687ED
0x1800687d9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800687e0  mov     rcx, rax; hModule
0x1800687e3  call    cs:__imp_GetProcAddress
0x1800687e9  mov     [rbx+10h], rax
0x1800687ed  mov     rax, [rbx+8]
0x1800687f1  test    rax, rax
0x1800687f4  jz      short loc_180068809
0x1800687f6  mov     rcx, [rbx]
0x1800687f9  xor     r9d, r9d
0x1800687fc  xor     r8d, r8d
0x1800687ff  mov     rdx, rdi
0x180068802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068807  jmp     short loc_180068825
0x180068809  mov     rax, [rbx+10h]
0x18006880d  test    rax, rax
0x180068810  jz      short loc_18006881F
0x180068812  mov     rcx, [rbx]
0x180068815  mov     rdx, rdi
0x180068818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006881d  jmp     short loc_180068825
0x18006881f  call    cs:__imp_GetLastError
0x180068825  mov     rbx, [rsp+38h+arg_0]
0x18006882a  add     rsp, 30h
0x18006882e  pop     rdi
0x18006882f  retn
```
