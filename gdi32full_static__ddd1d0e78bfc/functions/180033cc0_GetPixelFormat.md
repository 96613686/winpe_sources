# GetPixelFormat

- ea: `0x180033cc0`
- end: `0x180033d43`
- name: `GetPixelFormat`
- size: `131`
- prototype: `int __stdcall(HDC hdc)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180033728`
- `0x180096330`

## callees

- `0x180033cc0`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033d24`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033d24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033d06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033d06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180033ce8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180033ce8`

## string_xrefs

- `0x180033cdf`: `OPENGL32`

## pseudocode

```c
int __stdcall GetPixelFormat(HDC hdc)
{
  int v1; // edi
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rax

  v1 = 0;
  if ( gbSetPixelFormatCalled )
  {
    Library = LoadLibraryExA(LibFileName, 0, 0);
    v4 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "wglGetPixelFormat");
      if ( ProcAddress )
        v1 = ((__int64 (__fastcall *)(HDC))ProcAddress)(hdc);
      FreeLibrary(v4);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180033cc0  mov     [rsp+arg_0], rbx
0x180033cc5  mov     [rsp+arg_8], rsi
0x180033cca  push    rdi
0x180033ccb  sub     rsp, 20h
0x180033ccf  xor     edi, edi
0x180033cd1  mov     rsi, rcx
0x180033cd4  cmp     cs:gbSetPixelFormatCalled, edi
0x180033cda  jz      short loc_180033D30
0x180033cdc  xor     r8d, r8d; dwFlags
0x180033cdf  lea     rcx, LibFileName; "OPENGL32"
0x180033ce6  xor     edx, edx; hFile
0x180033ce8  call    cs:__imp_LoadLibraryExA
0x180033cef  nop     dword ptr [rax+rax+00h]
0x180033cf4  mov     rbx, rax
0x180033cf7  test    rax, rax
0x180033cfa  jz      short loc_180033D30
0x180033cfc  lea     rdx, ProcName; "wglGetPixelFormat"
0x180033d03  mov     rcx, rax; hModule
0x180033d06  call    cs:__imp_GetProcAddress
0x180033d0d  nop     dword ptr [rax+rax+00h]
0x180033d12  test    rax, rax
0x180033d15  jz      short loc_180033D21
0x180033d17  mov     rcx, rsi
0x180033d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d1f  mov     edi, eax
0x180033d21  mov     rcx, rbx; hLibModule
0x180033d24  call    cs:__imp_FreeLibrary
0x180033d2b  nop     dword ptr [rax+rax+00h]
0x180033d30  mov     rbx, [rsp+28h+arg_0]
0x180033d35  mov     eax, edi
0x180033d37  mov     rsi, [rsp+28h+arg_8]
0x180033d3c  add     rsp, 20h
0x180033d40  pop     rdi
0x180033d41  retn
```
