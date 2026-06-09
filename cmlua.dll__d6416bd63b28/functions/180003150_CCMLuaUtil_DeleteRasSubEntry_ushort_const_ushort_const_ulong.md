# CCMLuaUtil::DeleteRasSubEntry(ushort const *,ushort const *,ulong)

- ea: `0x180003150`
- end: `0x1800031fa`
- name: `?DeleteRasSubEntry@CCMLuaUtil@@UEAAJPEBG0K@Z`
- size: `170`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003150`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800031dc`
- `KERNEL32!FreeLibrary` at `0x1800031dc`
- `KERNEL32!LoadLibraryExW` at `0x18000316e`
- `KERNEL32!LoadLibraryExW` at `0x18000316e`
- `KERNEL32!GetProcAddress` at `0x1800031a2`
- `KERNEL32!GetProcAddress` at `0x1800031a2`
- `KERNEL32!GetLastError` at `0x18000317c`
- `KERNEL32!GetLastError` at `0x1800031ad`
- `KERNEL32!GetLastError` at `0x18000317c`
- `KERNEL32!GetLastError` at `0x1800031ad`

## string_xrefs

- `0x18000315c`: `RASAPI32.DLL`
- `0x180003182`: `LoadLibrary failed in DeleteRasSubEntry. GLE = %#x`
- `0x180003198`: `RasDeleteSubEntryW`
- `0x1800031b3`: `GetProcAddress failed in DeleteRasSubEntry. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::DeleteRasSubEntry(
        CCMLuaUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  DWORD LastError; // ebx
  __int64 v10; // r9
  FARPROC ProcAddress; // rax
  __int64 v12; // r9

  Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasDeleteSubEntryW");
    if ( ProcAddress )
    {
      LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _QWORD))ProcAddress)(
                    a2,
                    a3,
                    a4);
    }
    else
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in DeleteRasSubEntry. GLE = %#x", LastError, v12);
    }
    FreeLibrary(v8);
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in DeleteRasSubEntry. GLE = %#x", LastError, v10);
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180003150  push    rbx
0x180003152  push    rbp
0x180003153  push    rsi
0x180003154  push    rdi
0x180003155  sub     rsp, 28h
0x180003159  mov     rsi, r8
0x18000315c  lea     rcx, LibFileName; "RASAPI32.DLL"
0x180003163  mov     rbp, rdx
0x180003166  xor     r8d, r8d; dwFlags
0x180003169  xor     edx, edx; hFile
0x18000316b  mov     ebx, r9d
0x18000316e  call    cs:__imp_LoadLibraryExW
0x180003174  mov     rdi, rax
0x180003177  test    rax, rax
0x18000317a  jnz     short loc_180003198
0x18000317c  call    cs:__imp_GetLastError
0x180003182  lea     rdx, aLoadlibraryFai_4; "LoadLibrary failed in DeleteRasSubEntry"...
0x180003189  or      ecx, 0FFFFFFFFh
0x18000318c  mov     r8d, eax
0x18000318f  mov     ebx, eax
0x180003191  call    MyDbgPrintfW
0x180003196  jmp     short loc_1800031E2
0x180003198  lea     rdx, aRasdeletesuben; "RasDeleteSubEntryW"
0x18000319f  mov     rcx, rdi; hModule
0x1800031a2  call    cs:__imp_GetProcAddress
0x1800031a8  test    rax, rax
0x1800031ab  jnz     short loc_1800031C9
0x1800031ad  call    cs:__imp_GetLastError
0x1800031b3  lea     rdx, aGetprocaddress_1; "GetProcAddress failed in DeleteRasSubEn"...
0x1800031ba  or      ecx, 0FFFFFFFFh
0x1800031bd  mov     r8d, eax
0x1800031c0  mov     ebx, eax
0x1800031c2  call    MyDbgPrintfW
0x1800031c7  jmp     short loc_1800031D9
0x1800031c9  mov     r8d, ebx
0x1800031cc  mov     rdx, rsi
0x1800031cf  mov     rcx, rbp
0x1800031d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d7  mov     ebx, eax
0x1800031d9  mov     rcx, rdi; hLibModule
0x1800031dc  call    cs:__imp_FreeLibrary
0x1800031e2  test    ebx, ebx
0x1800031e4  jle     short loc_1800031EF
0x1800031e6  movzx   ebx, bx
0x1800031e9  or      ebx, 80070000h
0x1800031ef  mov     eax, ebx
0x1800031f1  add     rsp, 28h
0x1800031f5  pop     rdi
0x1800031f6  pop     rsi
0x1800031f7  pop     rbp
0x1800031f8  pop     rbx
0x1800031f9  retn
```
