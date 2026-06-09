# HHSHGetFolderPath(HWND__ *,int,void *,ulong,char *)

- ea: `0x18004f184`
- end: `0x18004f3c5`
- name: `?HHSHGetFolderPath@@YAJPEAUHWND__@@HPEAXKPEAD@Z`
- size: `577`
- prototype: `__int64 __fastcall(HWND, int, void *, unsigned int, LPSTR)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18004eafc`
- `0x18004ed7c`
- `0x18004f3cc`

## callees

- `0x180002a64`
- `0x18000c02c`
- `0x18004f184`
- `0x18004f5e4`
- `0x18004f6e0`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetShortPathNameW` at `0x18004f2e9`
- `KERNEL32!GetShortPathNameW` at `0x18004f2e9`
- `KERNEL32!FreeLibrary` at `0x18004f200`
- `KERNEL32!FreeLibrary` at `0x18004f353`
- `KERNEL32!FreeLibrary` at `0x18004f39d`
- `KERNEL32!FreeLibrary` at `0x18004f200`
- `KERNEL32!FreeLibrary` at `0x18004f353`
- `KERNEL32!FreeLibrary` at `0x18004f39d`
- `KERNEL32!GetProcAddress` at `0x18004f1ef`
- `KERNEL32!GetProcAddress` at `0x18004f228`
- `KERNEL32!GetProcAddress` at `0x18004f345`
- `KERNEL32!GetProcAddress` at `0x18004f377`
- `KERNEL32!GetProcAddress` at `0x18004f1ef`
- `KERNEL32!GetProcAddress` at `0x18004f228`
- `KERNEL32!GetProcAddress` at `0x18004f345`
- `KERNEL32!GetProcAddress` at `0x18004f377`

## string_xrefs

- `0x18004f1cd`: `shell32.dll`
- `0x18004f1e5`: `SHGetFolderPathW`
- `0x18004f21e`: `SHGetFolderPathW`
- `0x18004f206`: `shfolder.dll`
- `0x18004f33b`: `SHGetFolderPathA`
- `0x18004f36d`: `SHGetFolderPathA`
- `0x18004f359`: `shfolder.dll`
- `0x18004f327`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall HHSHGetFolderPath(HWND a1, unsigned int a2, void *a3, __int64 a4, LPSTR a5)
{
  int v6; // r14d
  HMODULE LibraryW; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rdi
  HMODULE v10; // rax
  HMODULE LibraryA; // rax
  FARPROC v12; // rax
  HMODULE v13; // rax
  CHAR v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL v16[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR szLongPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szShortPath[264]; // [rsp+260h] [rbp+160h] BYREF

  v6 = -2147467259;
  *a5 = 0;
  if ( (unsigned int)IsNT() )
  {
    LibraryW = (HMODULE)IsolationAwareLoadLibraryW(L"shell32.dll");
    v8 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SHGetFolderPathW");
      if ( ProcAddress )
      {
LABEL_6:
        memset_0(szLongPath, 0, 0x208u);
        v15[0] = 63;
        v16[0] = 0;
        v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, WCHAR *))ProcAddress)(0, a2, 0, 0, szLongPath);
        if ( v6 >= 0 )
        {
          HHWideCharToMultiByte(0, 0, szLongPath, -1, a5, 260, v15, v16);
          if ( v16[0] )
          {
            memset_0(szShortPath, 0, 0x208u);
            *a5 = 0;
            if ( GetShortPathNameW(szLongPath, szShortPath, 0x104u) )
              HHWideCharToMultiByte(0, 0, szShortPath, -1, a5, 260, 0, 0);
          }
        }
        goto LABEL_15;
      }
      FreeLibrary(v8);
      v10 = (HMODULE)IsolationAwareLoadLibraryW(L"shfolder.dll");
      v8 = v10;
      if ( v10 )
      {
        ProcAddress = GetProcAddress(v10, "SHGetFolderPathW");
        if ( ProcAddress )
          goto LABEL_6;
LABEL_15:
        FreeLibrary(v8);
      }
    }
  }
  else
  {
    LibraryA = (HMODULE)IsolationAwareLoadLibraryA("shell32.dll");
    v8 = LibraryA;
    if ( LibraryA )
    {
      v12 = GetProcAddress(LibraryA, "SHGetFolderPathA");
      if ( !v12 )
      {
        FreeLibrary(v8);
        v13 = (HMODULE)IsolationAwareLoadLibraryA("shfolder.dll");
        v8 = v13;
        if ( !v13 )
          return (unsigned int)v6;
        v12 = GetProcAddress(v13, "SHGetFolderPathA");
        if ( !v12 )
          goto LABEL_15;
      }
      v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, LPSTR))v12)(0, a2, 0, 0, a5);
      goto LABEL_15;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004f184  push    rbp
0x18004f186  push    rbx
0x18004f187  push    rsi
0x18004f188  push    rdi
0x18004f189  push    r14
0x18004f18b  push    r15
0x18004f18d  lea     rbp, [rsp-388h]
0x18004f195  sub     rsp, 488h
0x18004f19c  mov     rax, cs:__security_cookie
0x18004f1a3  xor     rax, rsp
0x18004f1a6  mov     [rbp+3B0h+var_40], rax
0x18004f1ad  mov     rsi, [rbp+3B0h+arg_20]
0x18004f1b4  mov     r15d, edx
0x18004f1b7  mov     r14d, 80004005h
0x18004f1bd  mov     byte ptr [rsi], 0
0x18004f1c0  call    ?IsNT@@YAHXZ; IsNT(void)
0x18004f1c5  test    eax, eax
0x18004f1c7  jz      loc_18004F327
0x18004f1cd  lea     rcx, aShell32Dll_1; "shell32.dll"
0x18004f1d4  call    IsolationAwareLoadLibraryW
0x18004f1d9  mov     rbx, rax
0x18004f1dc  test    rax, rax
0x18004f1df  jz      loc_18004F3A3
0x18004f1e5  lea     rdx, aShgetfolderpat_0; "SHGetFolderPathW"
0x18004f1ec  mov     rcx, rax; hModule
0x18004f1ef  call    cs:__imp_GetProcAddress
0x18004f1f5  mov     rdi, rax
0x18004f1f8  test    rax, rax
0x18004f1fb  jnz     short loc_18004F23A
0x18004f1fd  mov     rcx, rbx; hLibModule
0x18004f200  call    cs:__imp_FreeLibrary
0x18004f206  lea     rcx, aShfolderDll; "shfolder.dll"
0x18004f20d  call    IsolationAwareLoadLibraryW
0x18004f212  mov     rbx, rax
0x18004f215  test    rax, rax
0x18004f218  jz      loc_18004F3A3
0x18004f21e  lea     rdx, aShgetfolderpat_0; "SHGetFolderPathW"
0x18004f225  mov     rcx, rax; hModule
0x18004f228  call    cs:__imp_GetProcAddress
0x18004f22e  mov     rdi, rax
0x18004f231  test    rax, rax
0x18004f234  jz      loc_18004F39A
0x18004f23a  xor     edx, edx; Val
0x18004f23c  lea     rcx, [rsp+4B0h+szLongPath]; void *
0x18004f241  mov     r8d, 208h; Size
0x18004f247  call    memset_0
0x18004f24c  lea     rax, [rsp+4B0h+szLongPath]
0x18004f251  mov     [rsp+4B0h+var_470], 3Fh ; '?'
0x18004f256  mov     [rsp+4B0h+var_490], rax
0x18004f25b  xor     r9d, r9d
0x18004f25e  mov     rax, rdi
0x18004f261  mov     [rsp+4B0h+var_46C], 0
0x18004f269  xor     r8d, r8d
0x18004f26c  mov     edx, r15d
0x18004f26f  xor     ecx, ecx
0x18004f271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f276  mov     r14d, eax
0x18004f279  test    eax, eax
0x18004f27b  js      loc_18004F39A
0x18004f281  lea     rax, [rsp+4B0h+var_46C]
0x18004f286  mov     edi, 104h
0x18004f28b  mov     [rsp+4B0h+var_478], rax; LPBOOL
0x18004f290  lea     r8, [rsp+4B0h+szLongPath]; unsigned __int16 *
0x18004f295  lea     rax, [rsp+4B0h+var_470]
0x18004f29a  or      r15d, 0FFFFFFFFh
0x18004f29e  mov     [rsp+4B0h+var_480], rax; LPCCH
0x18004f2a3  mov     r9d, r15d; int
0x18004f2a6  mov     [rsp+4B0h+var_488], edi; int
0x18004f2aa  xor     edx, edx; unsigned int
0x18004f2ac  xor     ecx, ecx; unsigned int
0x18004f2ae  mov     [rsp+4B0h+var_490], rsi; LPSTR
0x18004f2b3  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18004f2b8  cmp     [rsp+4B0h+var_46C], 0
0x18004f2bd  jz      loc_18004F39A
0x18004f2c3  xor     edx, edx; Val
0x18004f2c5  lea     rcx, [rbp+3B0h+szShortPath]; void *
0x18004f2cc  mov     r8d, 208h; Size
0x18004f2d2  call    memset_0
0x18004f2d7  mov     r8d, edi; cchBuffer
0x18004f2da  mov     byte ptr [rsi], 0
0x18004f2dd  lea     rdx, [rbp+3B0h+szShortPath]; lpszShortPath
0x18004f2e4  lea     rcx, [rsp+4B0h+szLongPath]; lpszLongPath
0x18004f2e9  call    cs:__imp_GetShortPathNameW
0x18004f2ef  test    eax, eax
0x18004f2f1  jz      loc_18004F39A
0x18004f2f7  mov     [rsp+4B0h+var_478], 0; LPBOOL
0x18004f300  lea     r8, [rbp+3B0h+szShortPath]; unsigned __int16 *
0x18004f307  mov     [rsp+4B0h+var_480], 0; LPCCH
0x18004f310  mov     r9d, r15d; int
0x18004f313  mov     [rsp+4B0h+var_488], edi; int
0x18004f317  xor     edx, edx; unsigned int
0x18004f319  xor     ecx, ecx; unsigned int
0x18004f31b  mov     [rsp+4B0h+var_490], rsi; LPSTR
0x18004f320  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18004f325  jmp     short loc_18004F39A
0x18004f327  lea     rcx, aShell32Dll_0; "shell32.dll"
0x18004f32e  call    IsolationAwareLoadLibraryA
0x18004f333  mov     rbx, rax
0x18004f336  test    rax, rax
0x18004f339  jz      short loc_18004F3A3
0x18004f33b  lea     rdx, aShgetfolderpat; "SHGetFolderPathA"
0x18004f342  mov     rcx, rax; hModule
0x18004f345  call    cs:__imp_GetProcAddress
0x18004f34b  test    rax, rax
0x18004f34e  jnz     short loc_18004F382
0x18004f350  mov     rcx, rbx; hLibModule
0x18004f353  call    cs:__imp_FreeLibrary
0x18004f359  lea     rcx, aShfolderDll_0; "shfolder.dll"
0x18004f360  call    IsolationAwareLoadLibraryA
0x18004f365  mov     rbx, rax
0x18004f368  test    rax, rax
0x18004f36b  jz      short loc_18004F3A3
0x18004f36d  lea     rdx, aShgetfolderpat; "SHGetFolderPathA"
0x18004f374  mov     rcx, rax; hModule
0x18004f377  call    cs:__imp_GetProcAddress
0x18004f37d  test    rax, rax
0x18004f380  jz      short loc_18004F39A
0x18004f382  xor     r9d, r9d
0x18004f385  mov     [rsp+4B0h+var_490], rsi
0x18004f38a  xor     r8d, r8d
0x18004f38d  mov     edx, r15d
0x18004f390  xor     ecx, ecx
0x18004f392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f397  mov     r14d, eax
0x18004f39a  mov     rcx, rbx; hLibModule
0x18004f39d  call    cs:__imp_FreeLibrary
0x18004f3a3  mov     eax, r14d
0x18004f3a6  mov     rcx, [rbp+3B0h+var_40]
0x18004f3ad  xor     rcx, rsp; StackCookie
0x18004f3b0  call    __security_check_cookie
0x18004f3b5  add     rsp, 488h
0x18004f3bc  pop     r15
0x18004f3be  pop     r14
0x18004f3c0  pop     rdi
0x18004f3c1  pop     rsi
0x18004f3c2  pop     rbx
0x18004f3c3  pop     rbp
0x18004f3c4  retn
```
