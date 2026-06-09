# IasLoadParamInfo

- ea: `0x180029e90`
- end: `0x180029f40`
- name: `IasLoadParamInfo`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002a310`
- `0x18002b0c8`

## callees

- `0x180029e90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029ef7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029f0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029ef7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029f0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029f2f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029f2f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029ebf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029ebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ed2`

## string_xrefs

- `0x180029eb8`: `iassam.dll`

## pseudocode

```c
DWORD __fastcall IasLoadParamInfo(__int64 a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  FARPROC v8; // rax
  bool v9; // zf

  if ( !a1 )
    return 87;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  Library = LoadLibraryExW(L"iassam.dll", 0, 0x800u);
  *(_QWORD *)a1 = Library;
  if ( !Library )
    return GetLastError();
  ProcAddress = GetProcAddress(Library, "IASParmsSetUserProperty");
  v5 = *(HMODULE *)a1;
  *(_QWORD *)(a1 + 8) = ProcAddress;
  v6 = GetProcAddress(v5, "IASParmsQueryUserProperty");
  v7 = *(HMODULE *)a1;
  *(_QWORD *)(a1 + 16) = v6;
  v8 = GetProcAddress(v7, "IASParmsFreeUserParms");
  v9 = *(_QWORD *)(a1 + 8) == 0;
  *(_QWORD *)(a1 + 24) = v8;
  if ( !v9 && *(_QWORD *)(a1 + 16) && v8 )
    return 0;
  FreeLibrary(*(HMODULE *)a1);
  return 1003;
}

```

## disassembly

```asm
0x180029e90  push    rbx
0x180029e92  sub     rsp, 20h
0x180029e96  mov     rbx, rcx
0x180029e99  test    rcx, rcx
0x180029e9c  jnz     short loc_180029EA6
0x180029e9e  lea     eax, [rcx+57h]
0x180029ea1  jmp     loc_180029F3A
0x180029ea6  xorps   xmm0, xmm0
0x180029ea9  xor     edx, edx; hFile
0x180029eab  movups  xmmword ptr [rcx], xmm0
0x180029eae  mov     r8d, 800h; dwFlags
0x180029eb4  movups  xmmword ptr [rcx+10h], xmm0
0x180029eb8  lea     rcx, pszIasLibrary; "iassam.dll"
0x180029ebf  call    cs:__imp_LoadLibraryExW
0x180029ec5  mov     [rbx], rax
0x180029ec8  test    rax, rax
0x180029ecb  jnz     short loc_180029ED9
0x180029ecd  add     rsp, 20h
0x180029ed1  pop     rbx
0x180029ed2  jmp     cs:__imp_GetLastError
0x180029ed9  lea     rdx, pszIasSetUserPropFunc; "IASParmsSetUserProperty"
0x180029ee0  mov     rcx, rax; hModule
0x180029ee3  call    cs:__imp_GetProcAddress
0x180029ee9  mov     rcx, [rbx]; hModule
0x180029eec  lea     rdx, pszIasQueryUserPropFunc; "IASParmsQueryUserProperty"
0x180029ef3  mov     [rbx+8], rax
0x180029ef7  call    cs:__imp_GetProcAddress
0x180029efd  mov     rcx, [rbx]; hModule
0x180029f00  lea     rdx, pszIasFreeUserParmsFunc; "IASParmsFreeUserParms"
0x180029f07  mov     [rbx+10h], rax
0x180029f0b  call    cs:__imp_GetProcAddress
0x180029f11  cmp     qword ptr [rbx+8], 0
0x180029f16  mov     [rbx+18h], rax
0x180029f1a  jz      short loc_180029F2C
0x180029f1c  cmp     qword ptr [rbx+10h], 0
0x180029f21  jz      short loc_180029F2C
0x180029f23  test    rax, rax
0x180029f26  jz      short loc_180029F2C
0x180029f28  xor     eax, eax
0x180029f2a  jmp     short loc_180029F3A
0x180029f2c  mov     rcx, [rbx]; hLibModule
0x180029f2f  call    cs:__imp_FreeLibrary
0x180029f35  mov     eax, 3EBh
0x180029f3a  add     rsp, 20h
0x180029f3e  pop     rbx
0x180029f3f  retn
```
