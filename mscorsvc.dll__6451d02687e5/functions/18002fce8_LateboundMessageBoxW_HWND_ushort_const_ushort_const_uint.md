# LateboundMessageBoxW(HWND__ *,ushort const *,ushort const *,uint)

- ea: `0x18002fce8`
- end: `0x18002fdd9`
- name: `?LateboundMessageBoxW@@YAHPEAUHWND__@@PEBG1I@Z`
- size: `241`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003aad8`

## callees

- `0x18002fc18`
- `0x18002fce8`
- `0x18003f280`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18002fdb3`
- `KERNEL32!DebugBreak` at `0x18002fdb3`
- `KERNEL32!LoadLibraryExW` at `0x18002fd16`
- `KERNEL32!LoadLibraryExW` at `0x18002fd16`
- `KERNEL32!FreeLibrary` at `0x18002fd54`
- `KERNEL32!FreeLibrary` at `0x18002fd54`
- `KERNEL32!IsDebuggerPresent` at `0x18002fda9`
- `KERNEL32!IsDebuggerPresent` at `0x18002fda9`
- `KERNEL32!GetProcAddress` at `0x18002fd33`
- `KERNEL32!GetProcAddress` at `0x18002fd33`

## pseudocode

```c
__int64 __fastcall LateboundMessageBoxW(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  FARPROC ProcAddress; // rax
  const wchar_t *v12; // rbx
  const wchar_t *v13; // rdx

  Library = LoadLibraryExW(L"user32", 0, 0);
  v8 = Library;
  if ( Library )
  {
    v9 = 2;
    ProcAddress = GetProcAddress(Library, "MessageBoxW");
    if ( ProcAddress )
      v9 = ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, _QWORD))ProcAddress)(
             0,
             a2,
             a3,
             a4);
    FreeLibrary(v8);
    return v9;
  }
  else
  {
    v12 = L"<null>";
    v13 = L"<null>";
    if ( a3 )
      v13 = a3;
    DbgWPrintf(L"**** MessageBox invoked, title '%s' ****\n", v13);
    if ( a2 )
      v12 = a2;
    DbgWPrintf(L"  %s\n", v12);
    DbgWPrintf(L"********\n");
    DbgWPrintf(L"\n");
    if ( IsDebuggerPresent() )
      DebugBreak();
    return 2;
  }
}

```

## disassembly

```asm
0x18002fce8  mov     rax, rsp
0x18002fceb  mov     [rax+8], rbx
0x18002fcef  mov     [rax+10h], rbp
0x18002fcf3  mov     [rax+18h], rsi
0x18002fcf7  mov     [rax+20h], rdi
0x18002fcfb  push    r14
0x18002fcfd  sub     rsp, 30h
0x18002fd01  mov     rsi, r8
0x18002fd04  lea     rcx, aUser32; "user32"
0x18002fd0b  mov     rbp, rdx
0x18002fd0e  xor     r8d, r8d; dwFlags
0x18002fd11  xor     edx, edx; hFile
0x18002fd13  mov     r14d, r9d
0x18002fd16  call    cs:__imp_LoadLibraryExW
0x18002fd1c  mov     rdi, rax
0x18002fd1f  test    rax, rax
0x18002fd22  jz      short loc_18002FD5E
0x18002fd24  lea     rdx, aMessageboxw; "MessageBoxW"
0x18002fd2b  mov     rcx, rax; hModule
0x18002fd2e  mov     ebx, 2
0x18002fd33  call    cs:__imp_GetProcAddress
0x18002fd39  test    rax, rax
0x18002fd3c  jz      short loc_18002FD51
0x18002fd3e  mov     r9d, r14d
0x18002fd41  mov     r8, rsi
0x18002fd44  mov     rdx, rbp
0x18002fd47  xor     ecx, ecx
0x18002fd49  call    cs:__guard_dispatch_icall_fptr
0x18002fd4f  mov     ebx, eax
0x18002fd51  mov     rcx, rdi; hLibModule
0x18002fd54  call    cs:__imp_FreeLibrary
0x18002fd5a  mov     eax, ebx
0x18002fd5c  jmp     short loc_18002FDBE
0x18002fd5e  lea     rbx, aNull_0; "<null>"
0x18002fd65  test    rsi, rsi
0x18002fd68  mov     rdx, rbx
0x18002fd6b  lea     rcx, aMessageboxInvo; "**** MessageBox invoked, title '%s' ***"...
0x18002fd72  cmovnz  rdx, rsi
0x18002fd76  call    ?DbgWPrintf@@YAXQEBGZZ; DbgWPrintf(ushort const * const,...)
0x18002fd7b  test    rbp, rbp
0x18002fd7e  lea     rcx, aS; "  %s\n"
0x18002fd85  cmovnz  rbx, rbp
0x18002fd89  mov     rdx, rbx
0x18002fd8c  call    ?DbgWPrintf@@YAXQEBGZZ; DbgWPrintf(ushort const * const,...)
0x18002fd91  lea     rcx, asc_18005C0A8; "********\n"
0x18002fd98  call    ?DbgWPrintf@@YAXQEBGZZ; DbgWPrintf(ushort const * const,...)
0x18002fd9d  lea     rcx, asc_180051EB0; "\n"
0x18002fda4  call    ?DbgWPrintf@@YAXQEBGZZ; DbgWPrintf(ushort const * const,...)
0x18002fda9  call    cs:__imp_IsDebuggerPresent
0x18002fdaf  test    eax, eax
0x18002fdb1  jz      short loc_18002FDB9
0x18002fdb3  call    cs:__imp_DebugBreak
0x18002fdb9  mov     eax, 2
0x18002fdbe  mov     rbx, [rsp+38h+arg_0]
0x18002fdc3  mov     rbp, [rsp+38h+arg_8]
0x18002fdc8  mov     rsi, [rsp+38h+arg_10]
0x18002fdcd  mov     rdi, [rsp+38h+arg_18]
0x18002fdd2  add     rsp, 30h
0x18002fdd6  pop     r14
0x18002fdd8  retn
```
