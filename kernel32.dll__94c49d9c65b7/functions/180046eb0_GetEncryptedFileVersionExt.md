# GetEncryptedFileVersionExt

- ea: `0x180046eb0`
- end: `0x180046f84`
- name: `GetEncryptedFileVersionExt`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000db20`

## callees

- `0x180046eb0`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046f18`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046f69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046f69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180046ede`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180046ede`

## string_xrefs

- `0x180046eca`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall GetEncryptedFileVersionExt(__int64 a1, _DWORD *a2)
{
  void (*v4)(void); // rsi
  HMODULE Library; // rax
  HMODULE v6; // rdi
  ULONG LastErrorValue; // ebx
  FARPROC ProcAddress; // rbx
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  v10 = 0;
  Library = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
  v6 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "EncryptedFileKeyInfo")) != 0
    && (v4 = (void (*)(void))GetProcAddress(v6, "FreeEncryptedFileKeyInfo")) != 0 )
  {
    LastErrorValue = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))ProcAddress)(a1, 2, &v10);
    if ( !LastErrorValue )
      *a2 = **(_DWORD **)(v10 + 8);
  }
  else
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
  }
  if ( v10 )
    v4();
  if ( v6 )
    FreeLibrary(v6);
  return LastErrorValue;
}

```

## disassembly

```asm
0x180046eb0  mov     [rsp+arg_0], rbx
0x180046eb5  mov     [rsp+arg_8], rbp
0x180046eba  push    rsi
0x180046ebb  push    rdi
0x180046ebc  push    r14
0x180046ebe  sub     rsp, 20h
0x180046ec2  mov     r14, rdx
0x180046ec5  mov     rbp, rcx
0x180046ec8  xor     esi, esi
0x180046eca  lea     rcx, AdvapiDllString; "advapi32.dll"
0x180046ed1  xor     edx, edx; hFile
0x180046ed3  mov     [rsp+38h+arg_10], rsi
0x180046ed8  mov     r8d, 800h; dwFlags
0x180046ede  call    cs:__imp_LoadLibraryExW
0x180046ee4  mov     rdi, rax
0x180046ee7  test    rax, rax
0x180046eea  jnz     short loc_180046EF6
0x180046eec  mov     ebx, gs:68h
0x180046ef4  jmp     short loc_180046F4F
0x180046ef6  lea     rdx, ENCRYPTEDFILEKEYINFO_NAME; "EncryptedFileKeyInfo"
0x180046efd  mov     rcx, rdi; hModule
0x180046f00  call    cs:__imp_GetProcAddress
0x180046f06  mov     rbx, rax
0x180046f09  test    rax, rax
0x180046f0c  jz      short loc_180046EEC
0x180046f0e  lea     rdx, FREEFILEKEYINFO_NAME; "FreeEncryptedFileKeyInfo"
0x180046f15  mov     rcx, rdi; hModule
0x180046f18  call    cs:__imp_GetProcAddress
0x180046f1e  mov     rsi, rax
0x180046f21  test    rax, rax
0x180046f24  jz      short loc_180046EEC
0x180046f26  lea     r8, [rsp+38h+arg_10]
0x180046f2b  mov     edx, 2
0x180046f30  mov     rcx, rbp
0x180046f33  mov     rax, rbx
0x180046f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f3b  mov     ebx, eax
0x180046f3d  test    eax, eax
0x180046f3f  jnz     short loc_180046F4F
0x180046f41  mov     rcx, [rsp+38h+arg_10]
0x180046f46  mov     rdx, [rcx+8]
0x180046f4a  mov     ecx, [rdx]
0x180046f4c  mov     [r14], ecx
0x180046f4f  mov     rcx, [rsp+38h+arg_10]
0x180046f54  test    rcx, rcx
0x180046f57  jz      short loc_180046F61
0x180046f59  mov     rax, rsi
0x180046f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f61  test    rdi, rdi
0x180046f64  jz      short loc_180046F6F
0x180046f66  mov     rcx, rdi; hLibModule
0x180046f69  call    cs:__imp_FreeLibrary
0x180046f6f  mov     rbp, [rsp+38h+arg_8]
0x180046f74  mov     eax, ebx
0x180046f76  mov     rbx, [rsp+38h+arg_0]
0x180046f7b  add     rsp, 20h
0x180046f7f  pop     r14
0x180046f81  pop     rdi
0x180046f82  pop     rsi
0x180046f83  retn
```
