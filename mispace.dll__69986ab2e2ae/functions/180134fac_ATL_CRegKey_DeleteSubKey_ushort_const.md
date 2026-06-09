# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180134fac`
- end: `0x180135080`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1801362ec`
- `0x18013674c`

## callees

- `0x180134fac`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135067`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18013500a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18013500a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180134fd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180134fd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180134fec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180135025`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180134fec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180135025`

## string_xrefs

- `0x180135003`: `advapi32.dll`
- `0x18013501b`: `RegDeleteKeyW`
- `0x180134fca`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180134fe2`: `RegDeleteKeyExW`

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
0x180134fac  mov     [rsp+arg_0], rbx
0x180134fb1  push    rdi
0x180134fb2  sub     rsp, 30h
0x180134fb6  mov     rdi, rdx
0x180134fb9  mov     rbx, rcx
0x180134fbc  cmp     qword ptr [rcx+8], 0
0x180134fc1  jnz     short loc_180135035
0x180134fc3  cmp     qword ptr [rcx+10h], 0
0x180134fc8  jnz     short loc_180135035
0x180134fca  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180134fd1  call    cs:__imp_GetModuleHandleW
0x180134fd8  nop     dword ptr [rax+rax+00h]
0x180134fdd  test    rax, rax
0x180134fe0  jz      short loc_180134FFE
0x180134fe2  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180134fe9  mov     rcx, rax; hModule
0x180134fec  call    cs:__imp_GetProcAddress
0x180134ff3  nop     dword ptr [rax+rax+00h]
0x180134ff8  mov     [rbx+8], rax
0x180134ffc  jmp     short loc_180135035
0x180134ffe  xor     r8d, r8d; dwFlags
0x180135001  xor     edx, edx; hFile
0x180135003  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18013500a  call    cs:__imp_LoadLibraryExW
0x180135011  nop     dword ptr [rax+rax+00h]
0x180135016  test    rax, rax
0x180135019  jz      short loc_180135035
0x18013501b  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180135022  mov     rcx, rax; hModule
0x180135025  call    cs:__imp_GetProcAddress
0x18013502c  nop     dword ptr [rax+rax+00h]
0x180135031  mov     [rbx+10h], rax
0x180135035  mov     rax, [rbx+8]
0x180135039  test    rax, rax
0x18013503c  jz      short loc_180135051
0x18013503e  xor     r9d, r9d
0x180135041  xor     r8d, r8d
0x180135044  mov     rdx, rdi
0x180135047  mov     rcx, [rbx]
0x18013504a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013504f  jmp     short loc_180135074
0x180135051  mov     rax, [rbx+10h]
0x180135055  test    rax, rax
0x180135058  jz      short loc_180135067
0x18013505a  mov     rdx, rdi
0x18013505d  mov     rcx, [rbx]
0x180135060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135065  jmp     short loc_180135074
0x180135067  call    cs:__imp_GetLastError
0x18013506e  nop     dword ptr [rax+rax+00h]
0x180135073  nop
0x180135074  mov     rbx, [rsp+38h+arg_0]
0x180135079  add     rsp, 30h
0x18013507d  pop     rdi
0x18013507e  retn
```
