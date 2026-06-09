# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180021784`
- end: `0x180021839`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180022698`
- `0x180022ad0`

## callees

- `0x180021784`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800217d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800217d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800217be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800217eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800217be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800217eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800217a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800217a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021827`

## string_xrefs

- `0x1800217cf`: `advapi32.dll`
- `0x1800217a2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800217b4`: `RegDeleteKeyExW`
- `0x1800217e1`: `RegDeleteKeyW`

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
0x180021784  mov     [rsp+arg_0], rbx
0x180021789  push    rdi
0x18002178a  sub     rsp, 30h
0x18002178e  mov     rdi, rdx
0x180021791  mov     rbx, rcx
0x180021794  cmp     qword ptr [rcx+8], 0
0x180021799  jnz     short loc_1800217F5
0x18002179b  cmp     qword ptr [rcx+10h], 0
0x1800217a0  jnz     short loc_1800217F5
0x1800217a2  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800217a9  call    cs:__imp_GetModuleHandleW
0x1800217af  test    rax, rax
0x1800217b2  jz      short loc_1800217CA
0x1800217b4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800217bb  mov     rcx, rax; hModule
0x1800217be  call    cs:__imp_GetProcAddress
0x1800217c4  mov     [rbx+8], rax
0x1800217c8  jmp     short loc_1800217F5
0x1800217ca  xor     r8d, r8d; dwFlags
0x1800217cd  xor     edx, edx; hFile
0x1800217cf  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800217d6  call    cs:__imp_LoadLibraryExW
0x1800217dc  test    rax, rax
0x1800217df  jz      short loc_1800217F5
0x1800217e1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800217e8  mov     rcx, rax; hModule
0x1800217eb  call    cs:__imp_GetProcAddress
0x1800217f1  mov     [rbx+10h], rax
0x1800217f5  mov     rax, [rbx+8]
0x1800217f9  test    rax, rax
0x1800217fc  jz      short loc_180021811
0x1800217fe  xor     r9d, r9d
0x180021801  xor     r8d, r8d
0x180021804  mov     rdx, rdi
0x180021807  mov     rcx, [rbx]
0x18002180a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002180f  jmp     short loc_18002182E
0x180021811  mov     rax, [rbx+10h]
0x180021815  test    rax, rax
0x180021818  jz      short loc_180021827
0x18002181a  mov     rdx, rdi
0x18002181d  mov     rcx, [rbx]
0x180021820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021825  jmp     short loc_18002182E
0x180021827  call    cs:__imp_GetLastError
0x18002182d  nop
0x18002182e  mov     rbx, [rsp+38h+arg_0]
0x180021833  add     rsp, 30h
0x180021837  pop     rdi
0x180021838  retn
```
