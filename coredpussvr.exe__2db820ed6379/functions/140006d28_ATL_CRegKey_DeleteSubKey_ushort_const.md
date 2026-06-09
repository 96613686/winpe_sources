# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140006d28`
- end: `0x140006dfc`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000756c`
- `0x140007a88`

## callees

- `0x140006d28`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006da1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006da1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006d86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006de3`

## string_xrefs

- `0x140006d46`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140006d5e`: `RegDeleteKeyExW`
- `0x140006d7f`: `advapi32.dll`
- `0x140006d97`: `RegDeleteKeyW`

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
0x140006d28  mov     [rsp+arg_0], rbx
0x140006d2d  push    rdi
0x140006d2e  sub     rsp, 30h
0x140006d32  mov     rdi, rdx
0x140006d35  mov     rbx, rcx
0x140006d38  cmp     qword ptr [rcx+8], 0
0x140006d3d  jnz     short loc_140006DB1
0x140006d3f  cmp     qword ptr [rcx+10h], 0
0x140006d44  jnz     short loc_140006DB1
0x140006d46  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140006d4d  call    cs:__imp_GetModuleHandleW
0x140006d54  nop     dword ptr [rax+rax+00h]
0x140006d59  test    rax, rax
0x140006d5c  jz      short loc_140006D7A
0x140006d5e  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x140006d65  mov     rcx, rax; hModule
0x140006d68  call    cs:__imp_GetProcAddress
0x140006d6f  nop     dword ptr [rax+rax+00h]
0x140006d74  mov     [rbx+8], rax
0x140006d78  jmp     short loc_140006DB1
0x140006d7a  xor     r8d, r8d; dwFlags
0x140006d7d  xor     edx, edx; hFile
0x140006d7f  lea     rcx, LibFileName; "advapi32.dll"
0x140006d86  call    cs:__imp_LoadLibraryExW
0x140006d8d  nop     dword ptr [rax+rax+00h]
0x140006d92  test    rax, rax
0x140006d95  jz      short loc_140006DB1
0x140006d97  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140006d9e  mov     rcx, rax; hModule
0x140006da1  call    cs:__imp_GetProcAddress
0x140006da8  nop     dword ptr [rax+rax+00h]
0x140006dad  mov     [rbx+10h], rax
0x140006db1  mov     rax, [rbx+8]
0x140006db5  test    rax, rax
0x140006db8  jz      short loc_140006DCD
0x140006dba  xor     r9d, r9d
0x140006dbd  xor     r8d, r8d
0x140006dc0  mov     rdx, rdi
0x140006dc3  mov     rcx, [rbx]
0x140006dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006dcb  jmp     short loc_140006DF0
0x140006dcd  mov     rax, [rbx+10h]
0x140006dd1  test    rax, rax
0x140006dd4  jz      short loc_140006DE3
0x140006dd6  mov     rdx, rdi
0x140006dd9  mov     rcx, [rbx]
0x140006ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006de1  jmp     short loc_140006DF0
0x140006de3  call    cs:__imp_GetLastError
0x140006dea  nop     dword ptr [rax+rax+00h]
0x140006def  nop
0x140006df0  mov     rbx, [rsp+38h+arg_0]
0x140006df5  add     rsp, 30h
0x140006df9  pop     rdi
0x140006dfa  retn
```
