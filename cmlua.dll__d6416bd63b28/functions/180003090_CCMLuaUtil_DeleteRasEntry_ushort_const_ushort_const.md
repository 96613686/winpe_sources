# CCMLuaUtil::DeleteRasEntry(ushort const *,ushort const *)

- ea: `0x180003090`
- end: `0x180003141`
- name: `?DeleteRasEntry@CCMLuaUtil@@UEAAJPEBG0@Z`
- size: `177`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003090`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000311c`
- `KERNEL32!FreeLibrary` at `0x18000311c`
- `KERNEL32!LoadLibraryExW` at `0x1800030b1`
- `KERNEL32!LoadLibraryExW` at `0x1800030b1`
- `KERNEL32!GetProcAddress` at `0x1800030e5`
- `KERNEL32!GetProcAddress` at `0x1800030e5`
- `KERNEL32!GetLastError` at `0x1800030bf`
- `KERNEL32!GetLastError` at `0x1800030f0`
- `KERNEL32!GetLastError` at `0x1800030bf`
- `KERNEL32!GetLastError` at `0x1800030f0`

## string_xrefs

- `0x1800030a2`: `RASAPI32.DLL`
- `0x1800030c5`: `LoadLibrary failed in DeleteRasEntry. GLE = %#x`
- `0x1800030db`: `RasDeleteEntryW`
- `0x1800030f6`: `GetProcAddress failed in DeleteRasEntry. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::DeleteRasEntry(CCMLuaUtil *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HMODULE Library; // rax
  HMODULE v6; // rdi
  DWORD LastError; // ebx
  __int64 v8; // r9
  FARPROC ProcAddress; // rax
  __int64 v10; // r9

  Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasDeleteEntryW");
    if ( ProcAddress )
    {
      LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(a2, a3);
    }
    else
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in DeleteRasEntry. GLE = %#x", LastError, v10);
    }
    FreeLibrary(v6);
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in DeleteRasEntry. GLE = %#x", LastError, v8);
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180003090  mov     [rsp+arg_0], rbx
0x180003095  mov     [rsp+arg_8], rsi
0x18000309a  push    rdi
0x18000309b  sub     rsp, 20h
0x18000309f  mov     rbx, r8
0x1800030a2  lea     rcx, LibFileName; "RASAPI32.DLL"
0x1800030a9  mov     rsi, rdx
0x1800030ac  xor     r8d, r8d; dwFlags
0x1800030af  xor     edx, edx; hFile
0x1800030b1  call    cs:__imp_LoadLibraryExW
0x1800030b7  mov     rdi, rax
0x1800030ba  test    rax, rax
0x1800030bd  jnz     short loc_1800030DB
0x1800030bf  call    cs:__imp_GetLastError
0x1800030c5  lea     rdx, aLoadlibraryFai_3; "LoadLibrary failed in DeleteRasEntry. G"...
0x1800030cc  or      ecx, 0FFFFFFFFh
0x1800030cf  mov     r8d, eax
0x1800030d2  mov     ebx, eax
0x1800030d4  call    MyDbgPrintfW
0x1800030d9  jmp     short loc_180003122
0x1800030db  lea     rdx, ProcName; "RasDeleteEntryW"
0x1800030e2  mov     rcx, rdi; hModule
0x1800030e5  call    cs:__imp_GetProcAddress
0x1800030eb  test    rax, rax
0x1800030ee  jnz     short loc_18000310C
0x1800030f0  call    cs:__imp_GetLastError
0x1800030f6  lea     rdx, aGetprocaddress_4; "GetProcAddress failed in DeleteRasEntry"...
0x1800030fd  or      ecx, 0FFFFFFFFh
0x180003100  mov     r8d, eax
0x180003103  mov     ebx, eax
0x180003105  call    MyDbgPrintfW
0x18000310a  jmp     short loc_180003119
0x18000310c  mov     rdx, rbx
0x18000310f  mov     rcx, rsi
0x180003112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003117  mov     ebx, eax
0x180003119  mov     rcx, rdi; hLibModule
0x18000311c  call    cs:__imp_FreeLibrary
0x180003122  test    ebx, ebx
0x180003124  jle     short loc_18000312F
0x180003126  movzx   ebx, bx
0x180003129  or      ebx, 80070000h
0x18000312f  mov     rsi, [rsp+28h+arg_8]
0x180003134  mov     eax, ebx
0x180003136  mov     rbx, [rsp+28h+arg_0]
0x18000313b  add     rsp, 20h
0x18000313f  pop     rdi
0x180003140  retn
```
