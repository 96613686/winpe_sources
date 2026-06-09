# SwapBuffers

- ea: `0x18004cb40`
- end: `0x18004cbac`
- name: `SwapBuffers`
- size: `108`
- prototype: `BOOL __stdcall(HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18004cb40`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004cb90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004cb90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004cb76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004cb76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18004cb5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18004cb5e`

## string_xrefs

- `0x18004cb55`: `OPENGL32`

## pseudocode

```c
BOOL __stdcall SwapBuffers(HDC a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  int v5; // ebx

  Library = LoadLibraryExA(LibFileName, 0, 0);
  v3 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "wglSwapBuffers");
  v5 = 0;
  if ( ProcAddress )
    v5 = ((__int64 (__fastcall *)(HDC))ProcAddress)(a1);
  FreeLibrary(v3);
  return v5;
}

```

## disassembly

```asm
0x18004cb40  mov     [rsp+arg_0], rbx
0x18004cb45  mov     [rsp+arg_8], rsi
0x18004cb4a  push    rdi
0x18004cb4b  sub     rsp, 20h
0x18004cb4f  mov     rsi, rcx
0x18004cb52  xor     r8d, r8d; dwFlags
0x18004cb55  lea     rcx, LibFileName; "OPENGL32"
0x18004cb5c  xor     edx, edx; hFile
0x18004cb5e  call    cs:__imp_LoadLibraryExA
0x18004cb64  mov     rdi, rax
0x18004cb67  test    rax, rax
0x18004cb6a  jz      short loc_18004CBA8
0x18004cb6c  lea     rdx, aWglswapbuffers; "wglSwapBuffers"
0x18004cb73  mov     rcx, rax; hModule
0x18004cb76  call    cs:__imp_GetProcAddress
0x18004cb7c  xor     ebx, ebx
0x18004cb7e  test    rax, rax
0x18004cb81  jz      short loc_18004CB8D
0x18004cb83  mov     rcx, rsi
0x18004cb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb8b  mov     ebx, eax
0x18004cb8d  mov     rcx, rdi; hLibModule
0x18004cb90  call    cs:__imp_FreeLibrary
0x18004cb96  mov     rsi, [rsp+28h+arg_8]
0x18004cb9b  mov     eax, ebx
0x18004cb9d  mov     rbx, [rsp+28h+arg_0]
0x18004cba2  add     rsp, 20h
0x18004cba6  pop     rdi
0x18004cba7  retn
0x18004cba8  xor     ebx, ebx
0x18004cbaa  jmp     short loc_18004CB96
```
