# DescribePixelFormat

- ea: `0x180056640`
- end: `0x1800566cc`
- name: `DescribePixelFormat`
- size: `140`
- prototype: `int __stdcall(HDC hdc, int iPixelFormat, UINT nBytes, LPPIXELFORMATDESCRIPTOR ppfd)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180033728`

## callees

- `0x180056640`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800566ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800566ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056683`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056683`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180056665`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180056665`

## string_xrefs

- `0x18005665b`: `OPENGL32`

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
0x180056640  push    rbx
0x180056642  push    rbp
0x180056643  push    rsi
0x180056644  push    rdi
0x180056645  push    r14
0x180056647  push    r15
0x180056649  sub     rsp, 38h
0x18005664d  mov     ebp, r8d
0x180056650  mov     r14d, edx
0x180056653  mov     r15, rcx
0x180056656  xor     r8d, r8d; dwFlags
0x180056659  xor     edx, edx; hFile
0x18005665b  lea     rcx, LibFileName; "OPENGL32"
0x180056662  mov     rsi, r9
0x180056665  call    cs:__imp_LoadLibraryExA
0x18005666c  nop     dword ptr [rax+rax+00h]
0x180056671  mov     rdi, rax
0x180056674  test    rax, rax
0x180056677  jz      short loc_1800566C8
0x180056679  lea     rdx, aWgldescribepix; "wglDescribePixelFormat"
0x180056680  mov     rcx, rax; hModule
0x180056683  call    cs:__imp_GetProcAddress
0x18005668a  nop     dword ptr [rax+rax+00h]
0x18005668f  xor     ebx, ebx
0x180056691  test    rax, rax
0x180056694  jz      short loc_1800566A9
0x180056696  mov     r9, rsi
0x180056699  mov     r8d, ebp
0x18005669c  mov     edx, r14d
0x18005669f  mov     rcx, r15
0x1800566a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566a7  mov     ebx, eax
0x1800566a9  mov     rcx, rdi; hLibModule
0x1800566ac  call    cs:__imp_FreeLibrary
0x1800566b3  nop     dword ptr [rax+rax+00h]
0x1800566b8  mov     eax, ebx
0x1800566ba  add     rsp, 38h
0x1800566be  pop     r15
0x1800566c0  pop     r14
0x1800566c2  pop     rdi
0x1800566c3  pop     rsi
0x1800566c4  pop     rbp
0x1800566c5  pop     rbx
0x1800566c6  retn
0x1800566c8  xor     ebx, ebx
0x1800566ca  jmp     short loc_1800566B8
```
