# DescribePixelFormat

- ea: `0x180050ba0`
- end: `0x180050c19`
- name: `DescribePixelFormat`
- size: `121`
- prototype: `int __stdcall(HDC hdc, int iPixelFormat, UINT nBytes, LPPIXELFORMATDESCRIPTOR ppfd)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180029ee4`

## callees

- `0x180050ba0`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050c00`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050c00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050bdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050bdd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180050bc5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180050bc5`

## string_xrefs

- `0x180050bbb`: `OPENGL32`

## pseudocode

```c
int __stdcall DescribePixelFormat(HDC hdc, int iPixelFormat, UINT nBytes, LPPIXELFORMATDESCRIPTOR ppfd)
{
  HMODULE Library; // rax
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rax
  int v11; // ebx

  Library = LoadLibraryExA(LibFileName, 0, 0);
  v9 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "wglDescribePixelFormat");
  v11 = 0;
  if ( ProcAddress )
    v11 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, LPPIXELFORMATDESCRIPTOR))ProcAddress)(
            hdc,
            (unsigned int)iPixelFormat,
            nBytes,
            ppfd);
  FreeLibrary(v9);
  return v11;
}

```

## disassembly

```asm
0x180050ba0  push    rbx
0x180050ba2  push    rbp
0x180050ba3  push    rsi
0x180050ba4  push    rdi
0x180050ba5  push    r14
0x180050ba7  push    r15
0x180050ba9  sub     rsp, 38h
0x180050bad  mov     ebp, r8d
0x180050bb0  mov     r14d, edx
0x180050bb3  mov     r15, rcx
0x180050bb6  xor     r8d, r8d; dwFlags
0x180050bb9  xor     edx, edx; hFile
0x180050bbb  lea     rcx, LibFileName; "OPENGL32"
0x180050bc2  mov     rsi, r9
0x180050bc5  call    cs:__imp_LoadLibraryExA
0x180050bcb  mov     rdi, rax
0x180050bce  test    rax, rax
0x180050bd1  jz      short loc_180050C15
0x180050bd3  lea     rdx, aWgldescribepix; "wglDescribePixelFormat"
0x180050bda  mov     rcx, rax; hModule
0x180050bdd  call    cs:__imp_GetProcAddress
0x180050be3  xor     ebx, ebx
0x180050be5  test    rax, rax
0x180050be8  jz      short loc_180050BFD
0x180050bea  mov     r9, rsi
0x180050bed  mov     r8d, ebp
0x180050bf0  mov     edx, r14d
0x180050bf3  mov     rcx, r15
0x180050bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bfb  mov     ebx, eax
0x180050bfd  mov     rcx, rdi; hLibModule
0x180050c00  call    cs:__imp_FreeLibrary
0x180050c06  mov     eax, ebx
0x180050c08  add     rsp, 38h
0x180050c0c  pop     r15
0x180050c0e  pop     r14
0x180050c10  pop     rdi
0x180050c11  pop     rsi
0x180050c12  pop     rbp
0x180050c13  pop     rbx
0x180050c14  retn
0x180050c15  xor     ebx, ebx
0x180050c17  jmp     short loc_180050C06
```
