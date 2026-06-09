# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180015a44`
- end: `0x180015af8`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180008670`
- `0x180016738`

## callees

- `0x180015a44`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015aab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015aab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015a69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015a69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015a96`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015a96`

## string_xrefs

- `0x180015a62`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180015a74`: `RegDeleteKeyExW`
- `0x180015a8d`: `advapi32.dll`
- `0x180015aa1`: `RegDeleteKeyW`

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
0x180015a44  mov     [rsp+arg_0], rbx
0x180015a49  push    rdi
0x180015a4a  sub     rsp, 30h
0x180015a4e  cmp     qword ptr [rcx+8], 0
0x180015a53  mov     rdi, rdx
0x180015a56  mov     rbx, rcx
0x180015a59  jnz     short loc_180015AB5
0x180015a5b  cmp     qword ptr [rcx+10h], 0
0x180015a60  jnz     short loc_180015AB5
0x180015a62  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180015a69  call    cs:__imp_GetModuleHandleW
0x180015a6f  test    rax, rax
0x180015a72  jz      short loc_180015A8A
0x180015a74  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180015a7b  mov     rcx, rax; hModule
0x180015a7e  call    cs:__imp_GetProcAddress
0x180015a84  mov     [rbx+8], rax
0x180015a88  jmp     short loc_180015AB5
0x180015a8a  xor     r8d, r8d; dwFlags
0x180015a8d  lea     rcx, LibFileName; "advapi32.dll"
0x180015a94  xor     edx, edx; hFile
0x180015a96  call    cs:__imp_LoadLibraryExW
0x180015a9c  test    rax, rax
0x180015a9f  jz      short loc_180015AB5
0x180015aa1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180015aa8  mov     rcx, rax; hModule
0x180015aab  call    cs:__imp_GetProcAddress
0x180015ab1  mov     [rbx+10h], rax
0x180015ab5  mov     rax, [rbx+8]
0x180015ab9  test    rax, rax
0x180015abc  jz      short loc_180015AD1
0x180015abe  mov     rcx, [rbx]
0x180015ac1  xor     r9d, r9d
0x180015ac4  xor     r8d, r8d
0x180015ac7  mov     rdx, rdi
0x180015aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015acf  jmp     short loc_180015AED
0x180015ad1  mov     rax, [rbx+10h]
0x180015ad5  test    rax, rax
0x180015ad8  jz      short loc_180015AE7
0x180015ada  mov     rcx, [rbx]
0x180015add  mov     rdx, rdi
0x180015ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae5  jmp     short loc_180015AED
0x180015ae7  call    cs:__imp_GetLastError
0x180015aed  mov     rbx, [rsp+38h+arg_0]
0x180015af2  add     rsp, 30h
0x180015af6  pop     rdi
0x180015af7  retn
```
