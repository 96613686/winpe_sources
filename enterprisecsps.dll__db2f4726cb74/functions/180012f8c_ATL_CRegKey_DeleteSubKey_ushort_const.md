# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180012f8c`
- end: `0x180013060`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800142fc`
- `0x180014770`

## callees

- `0x180012f8c`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012fb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012fb1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013005`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013047`

## string_xrefs

- `0x180012faa`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180012fc2`: `RegDeleteKeyExW`
- `0x180012fe3`: `advapi32.dll`
- `0x180012ffb`: `RegDeleteKeyW`

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
0x180012f8c  mov     [rsp+arg_0], rbx
0x180012f91  push    rdi
0x180012f92  sub     rsp, 30h
0x180012f96  mov     rdi, rdx
0x180012f99  mov     rbx, rcx
0x180012f9c  cmp     qword ptr [rcx+8], 0
0x180012fa1  jnz     short loc_180013015
0x180012fa3  cmp     qword ptr [rcx+10h], 0
0x180012fa8  jnz     short loc_180013015
0x180012faa  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180012fb1  call    cs:__imp_GetModuleHandleW
0x180012fb8  nop     dword ptr [rax+rax+00h]
0x180012fbd  test    rax, rax
0x180012fc0  jz      short loc_180012FDE
0x180012fc2  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180012fc9  mov     rcx, rax; hModule
0x180012fcc  call    cs:__imp_GetProcAddress
0x180012fd3  nop     dword ptr [rax+rax+00h]
0x180012fd8  mov     [rbx+8], rax
0x180012fdc  jmp     short loc_180013015
0x180012fde  xor     r8d, r8d; dwFlags
0x180012fe1  xor     edx, edx; hFile
0x180012fe3  lea     rcx, LibFileName; "advapi32.dll"
0x180012fea  call    cs:__imp_LoadLibraryExW
0x180012ff1  nop     dword ptr [rax+rax+00h]
0x180012ff6  test    rax, rax
0x180012ff9  jz      short loc_180013015
0x180012ffb  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180013002  mov     rcx, rax; hModule
0x180013005  call    cs:__imp_GetProcAddress
0x18001300c  nop     dword ptr [rax+rax+00h]
0x180013011  mov     [rbx+10h], rax
0x180013015  mov     rax, [rbx+8]
0x180013019  test    rax, rax
0x18001301c  jz      short loc_180013031
0x18001301e  xor     r9d, r9d
0x180013021  xor     r8d, r8d
0x180013024  mov     rdx, rdi
0x180013027  mov     rcx, [rbx]
0x18001302a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302f  jmp     short loc_180013054
0x180013031  mov     rax, [rbx+10h]
0x180013035  test    rax, rax
0x180013038  jz      short loc_180013047
0x18001303a  mov     rdx, rdi
0x18001303d  mov     rcx, [rbx]
0x180013040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013045  jmp     short loc_180013054
0x180013047  call    cs:__imp_GetLastError
0x18001304e  nop     dword ptr [rax+rax+00h]
0x180013053  nop
0x180013054  mov     rbx, [rsp+38h+arg_0]
0x180013059  add     rsp, 30h
0x18001305d  pop     rdi
0x18001305e  retn
```
