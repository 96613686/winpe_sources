# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006b9c`
- end: `0x180006c51`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180008198`
- `0x18000893c`

## callees

- `0x180006b9c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006bc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006bc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006bee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006bee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c03`

## string_xrefs

- `0x180006bba`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006bcc`: `RegDeleteKeyExW`
- `0x180006be7`: `advapi32.dll`
- `0x180006bf9`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
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
0x180006b9c  mov     [rsp+arg_0], rbx
0x180006ba1  push    rdi
0x180006ba2  sub     rsp, 30h
0x180006ba6  mov     rdi, rdx
0x180006ba9  mov     rbx, rcx
0x180006bac  cmp     qword ptr [rcx+8], 0
0x180006bb1  jnz     short loc_180006C0D
0x180006bb3  cmp     qword ptr [rcx+10h], 0
0x180006bb8  jnz     short loc_180006C0D
0x180006bba  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006bc1  call    cs:__imp_GetModuleHandleW
0x180006bc7  test    rax, rax
0x180006bca  jz      short loc_180006BE2
0x180006bcc  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180006bd3  mov     rcx, rax; hModule
0x180006bd6  call    cs:__imp_GetProcAddress
0x180006bdc  mov     [rbx+8], rax
0x180006be0  jmp     short loc_180006C0D
0x180006be2  xor     r8d, r8d; dwFlags
0x180006be5  xor     edx, edx; hFile
0x180006be7  lea     rcx, LibFileName; "advapi32.dll"
0x180006bee  call    cs:__imp_LoadLibraryExW
0x180006bf4  test    rax, rax
0x180006bf7  jz      short loc_180006C0D
0x180006bf9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006c00  mov     rcx, rax; hModule
0x180006c03  call    cs:__imp_GetProcAddress
0x180006c09  mov     [rbx+10h], rax
0x180006c0d  mov     rax, [rbx+8]
0x180006c11  test    rax, rax
0x180006c14  jz      short loc_180006C29
0x180006c16  xor     r9d, r9d
0x180006c19  xor     r8d, r8d
0x180006c1c  mov     rdx, rdi
0x180006c1f  mov     rcx, [rbx]
0x180006c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c27  jmp     short loc_180006C46
0x180006c29  mov     rax, [rbx+10h]
0x180006c2d  test    rax, rax
0x180006c30  jz      short loc_180006C3F
0x180006c32  mov     rdx, rdi
0x180006c35  mov     rcx, [rbx]
0x180006c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c3d  jmp     short loc_180006C46
0x180006c3f  call    cs:__imp_GetLastError
0x180006c45  nop
0x180006c46  mov     rbx, [rsp+38h+arg_0]
0x180006c4b  add     rsp, 30h
0x180006c4f  pop     rdi
0x180006c50  retn
```
