# NtWin32LiveSystemProvider::GetTrueNTVersion(_OSVERSIONINFOW *)

- ea: `0x1800251f4`
- end: `0x180025284`
- name: `?GetTrueNTVersion@NtWin32LiveSystemProvider@@SAJPEAU_OSVERSIONINFOW@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(struct _OSVERSIONINFOW *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800062f4`
- `0x1800167a0`

## callees

- `0x1800251f4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002524a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002524a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18002520d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18002520d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180025258`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002526d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180025258`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002526d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002521b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002521b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025225`

## string_xrefs

- `0x180025204`: `ntdll.dll`

## pseudocode

```c
signed int __fastcall NtWin32LiveSystemProvider::GetTrueNTVersion(struct _OSVERSIONINFOW *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  signed int result; // eax
  FARPROC ProcAddress; // rax
  int v6; // ebx

  Library = LoadLibraryExA("ntdll.dll", 0, 0);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetVersion");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(struct _OSVERSIONINFOW *))ProcAddress)(a1);
      FreeLibrary(v3);
      return v6 | 0x10000000;
    }
    FreeLibrary(v3);
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800251f4  mov     [rsp+arg_0], rbx
0x1800251f9  push    rdi
0x1800251fa  sub     rsp, 20h
0x1800251fe  mov     rbx, rcx
0x180025201  xor     r8d, r8d; dwFlags
0x180025204  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18002520b  xor     edx, edx; hFile
0x18002520d  call    cs:__imp_LoadLibraryExA
0x180025213  mov     rdi, rax
0x180025216  test    rax, rax
0x180025219  jnz     short loc_180025240
0x18002521b  call    cs:__imp_GetLastError
0x180025221  test    eax, eax
0x180025223  jz      short loc_180025239
0x180025225  call    cs:__imp_GetLastError
0x18002522b  test    eax, eax
0x18002522d  jle     short loc_180025279
0x18002522f  movzx   eax, ax
0x180025232  or      eax, 80070000h
0x180025237  jmp     short loc_180025279
0x180025239  mov     eax, 80004005h
0x18002523e  jmp     short loc_180025279
0x180025240  lea     rdx, aRtlgetversion; "RtlGetVersion"
0x180025247  mov     rcx, rdi; hModule
0x18002524a  call    cs:__imp_GetProcAddress
0x180025250  test    rax, rax
0x180025253  jnz     short loc_180025260
0x180025255  mov     rcx, rdi; hLibModule
0x180025258  call    cs:__imp_FreeLibrary
0x18002525e  jmp     short loc_18002521B
0x180025260  mov     rcx, rbx
0x180025263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025268  mov     rcx, rdi; hLibModule
0x18002526b  mov     ebx, eax
0x18002526d  call    cs:__imp_FreeLibrary
0x180025273  bts     ebx, 1Ch
0x180025277  mov     eax, ebx
0x180025279  mov     rbx, [rsp+28h+arg_0]
0x18002527e  add     rsp, 20h
0x180025282  pop     rdi
0x180025283  retn
```
