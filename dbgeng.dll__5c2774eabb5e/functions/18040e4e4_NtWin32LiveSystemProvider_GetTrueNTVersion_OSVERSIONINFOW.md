# NtWin32LiveSystemProvider::GetTrueNTVersion(_OSVERSIONINFOW *)

- ea: `0x18040e4e4`
- end: `0x18040e599`
- name: `?GetTrueNTVersion@NtWin32LiveSystemProvider@@SAJPEAU_OSVERSIONINFOW@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct _OSVERSIONINFOW *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180402d9c`

## callees

- `0x18040e4e4`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040e560`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040e57b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040e560`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040e57b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040e54c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040e54c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18040e4fd`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18040e4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040e511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040e521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040e511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040e521`

## string_xrefs

- `0x18040e4f4`: `ntdll.dll`

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
0x18040e4e4  mov     [rsp+arg_0], rbx
0x18040e4e9  push    rdi
0x18040e4ea  sub     rsp, 20h
0x18040e4ee  mov     rbx, rcx
0x18040e4f1  xor     r8d, r8d; dwFlags
0x18040e4f4  lea     rcx, ModuleName; "ntdll.dll"
0x18040e4fb  xor     edx, edx; hFile
0x18040e4fd  call    cs:__imp_LoadLibraryExA
0x18040e504  nop     dword ptr [rax+rax+00h]
0x18040e509  mov     rdi, rax
0x18040e50c  test    rax, rax
0x18040e50f  jnz     short loc_18040E542
0x18040e511  call    cs:__imp_GetLastError
0x18040e518  nop     dword ptr [rax+rax+00h]
0x18040e51d  test    eax, eax
0x18040e51f  jz      short loc_18040E53B
0x18040e521  call    cs:__imp_GetLastError
0x18040e528  nop     dword ptr [rax+rax+00h]
0x18040e52d  test    eax, eax
0x18040e52f  jle     short loc_18040E58D
0x18040e531  movzx   eax, ax
0x18040e534  or      eax, 80070000h
0x18040e539  jmp     short loc_18040E58D
0x18040e53b  mov     eax, 80004005h
0x18040e540  jmp     short loc_18040E58D
0x18040e542  lea     rdx, aRtlgetversion; "RtlGetVersion"
0x18040e549  mov     rcx, rdi; hModule
0x18040e54c  call    cs:__imp_GetProcAddress
0x18040e553  nop     dword ptr [rax+rax+00h]
0x18040e558  test    rax, rax
0x18040e55b  jnz     short loc_18040E56E
0x18040e55d  mov     rcx, rdi; hLibModule
0x18040e560  call    cs:__imp_FreeLibrary
0x18040e567  nop     dword ptr [rax+rax+00h]
0x18040e56c  jmp     short loc_18040E511
0x18040e56e  mov     rcx, rbx
0x18040e571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040e576  mov     rcx, rdi; hLibModule
0x18040e579  mov     ebx, eax
0x18040e57b  call    cs:__imp_FreeLibrary
0x18040e582  nop     dword ptr [rax+rax+00h]
0x18040e587  bts     ebx, 1Ch
0x18040e58b  mov     eax, ebx
0x18040e58d  mov     rbx, [rsp+28h+arg_0]
0x18040e592  add     rsp, 20h
0x18040e596  pop     rdi
0x18040e597  retn
```
