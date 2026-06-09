# GetPixelFormat

- ea: `0x18002a540`
- end: `0x18002a5b0`
- name: `GetPixelFormat`
- size: `112`
- prototype: `int __stdcall(HDC hdc)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180029ee4`
- `0x180090830`

## callees

- `0x18002a540`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a598`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a598`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a580`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002a568`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002a568`

## string_xrefs

- `0x18002a55f`: `OPENGL32`

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
0x18002a540  mov     [rsp+arg_0], rbx
0x18002a545  mov     [rsp+arg_8], rsi
0x18002a54a  push    rdi
0x18002a54b  sub     rsp, 20h
0x18002a54f  xor     edi, edi
0x18002a551  mov     rsi, rcx
0x18002a554  cmp     cs:gbSetPixelFormatCalled, edi
0x18002a55a  jz      short loc_18002A59E
0x18002a55c  xor     r8d, r8d; dwFlags
0x18002a55f  lea     rcx, LibFileName; "OPENGL32"
0x18002a566  xor     edx, edx; hFile
0x18002a568  call    cs:__imp_LoadLibraryExA
0x18002a56e  mov     rbx, rax
0x18002a571  test    rax, rax
0x18002a574  jz      short loc_18002A59E
0x18002a576  lea     rdx, ProcName; "wglGetPixelFormat"
0x18002a57d  mov     rcx, rax; hModule
0x18002a580  call    cs:__imp_GetProcAddress
0x18002a586  test    rax, rax
0x18002a589  jz      short loc_18002A595
0x18002a58b  mov     rcx, rsi
0x18002a58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a593  mov     edi, eax
0x18002a595  mov     rcx, rbx; hLibModule
0x18002a598  call    cs:__imp_FreeLibrary
0x18002a59e  mov     rbx, [rsp+28h+arg_0]
0x18002a5a3  mov     eax, edi
0x18002a5a5  mov     rsi, [rsp+28h+arg_8]
0x18002a5aa  add     rsp, 20h
0x18002a5ae  pop     rdi
0x18002a5af  retn
```
