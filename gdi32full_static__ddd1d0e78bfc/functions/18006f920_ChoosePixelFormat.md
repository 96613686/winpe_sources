# ChoosePixelFormat

- ea: `0x18006f920`
- end: `0x18006f998`
- name: `ChoosePixelFormat`
- size: `120`
- prototype: `int __stdcall(HDC hdc, const PIXELFORMATDESCRIPTOR *ppfd)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180057710`
- `0x180096330`

## callees

- `0x18006f920`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006f980`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006f980`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f95d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f95d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006f93b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006f93b`

## string_xrefs

- `0x18006f931`: `OPENGL32`

## pseudocode

```c
int __stdcall ChoosePixelFormat(HDC hdc, const PIXELFORMATDESCRIPTOR *ppfd)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  int v6; // ebx
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExA(LibFileName, 0, 0);
  v5 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "wglChoosePixelFormat");
  v6 = 0;
  if ( ProcAddress )
    v6 = ((__int64 (__fastcall *)(HDC, const PIXELFORMATDESCRIPTOR *))ProcAddress)(hdc, ppfd);
  FreeLibrary(v5);
  return v6;
}

```

## disassembly

```asm
0x18006f920  push    rbx
0x18006f922  push    rbp
0x18006f923  push    rsi
0x18006f924  push    rdi
0x18006f925  sub     rsp, 28h
0x18006f929  mov     rsi, rdx
0x18006f92c  mov     rbp, rcx
0x18006f92f  xor     edx, edx; hFile
0x18006f931  lea     rcx, LibFileName; "OPENGL32"
0x18006f938  xor     r8d, r8d; dwFlags
0x18006f93b  call    cs:__imp_LoadLibraryExA
0x18006f942  nop     dword ptr [rax+rax+00h]
0x18006f947  mov     rdi, rax
0x18006f94a  test    rax, rax
0x18006f94d  jnz     short loc_18006F953
0x18006f94f  xor     ebx, ebx
0x18006f951  jmp     short loc_18006F98C
0x18006f953  lea     rdx, aWglchoosepixel; "wglChoosePixelFormat"
0x18006f95a  mov     rcx, rdi; hModule
0x18006f95d  call    cs:__imp_GetProcAddress
0x18006f964  nop     dword ptr [rax+rax+00h]
0x18006f969  xor     ebx, ebx
0x18006f96b  test    rax, rax
0x18006f96e  jz      short loc_18006F97D
0x18006f970  mov     rdx, rsi
0x18006f973  mov     rcx, rbp
0x18006f976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f97b  mov     ebx, eax
0x18006f97d  mov     rcx, rdi; hLibModule
0x18006f980  call    cs:__imp_FreeLibrary
0x18006f987  nop     dword ptr [rax+rax+00h]
0x18006f98c  mov     eax, ebx
0x18006f98e  add     rsp, 28h
0x18006f992  pop     rdi
0x18006f993  pop     rsi
0x18006f994  pop     rbp
0x18006f995  pop     rbx
0x18006f996  retn
```
