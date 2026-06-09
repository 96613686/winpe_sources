# ChoosePixelFormat

- ea: `0x18006b060`
- end: `0x18006b0c5`
- name: `ChoosePixelFormat`
- size: `101`
- prototype: `int __stdcall(HDC hdc, const PIXELFORMATDESCRIPTOR *ppfd)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180051bac`
- `0x180090830`

## callees

- `0x18006b060`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b0b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b0b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b097`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b097`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006b07b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006b07b`

## string_xrefs

- `0x18006b071`: `OPENGL32`

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
0x18006b060  push    rbx
0x18006b062  push    rbp
0x18006b063  push    rsi
0x18006b064  push    rdi
0x18006b065  sub     rsp, 28h
0x18006b069  mov     rsi, rdx
0x18006b06c  mov     rbp, rcx
0x18006b06f  xor     edx, edx; hFile
0x18006b071  lea     rcx, LibFileName; "OPENGL32"
0x18006b078  xor     r8d, r8d; dwFlags
0x18006b07b  call    cs:__imp_LoadLibraryExA
0x18006b081  mov     rdi, rax
0x18006b084  test    rax, rax
0x18006b087  jnz     short loc_18006B08D
0x18006b089  xor     ebx, ebx
0x18006b08b  jmp     short loc_18006B0BA
0x18006b08d  lea     rdx, aWglchoosepixel; "wglChoosePixelFormat"
0x18006b094  mov     rcx, rdi; hModule
0x18006b097  call    cs:__imp_GetProcAddress
0x18006b09d  xor     ebx, ebx
0x18006b09f  test    rax, rax
0x18006b0a2  jz      short loc_18006B0B1
0x18006b0a4  mov     rdx, rsi
0x18006b0a7  mov     rcx, rbp
0x18006b0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0af  mov     ebx, eax
0x18006b0b1  mov     rcx, rdi; hLibModule
0x18006b0b4  call    cs:__imp_FreeLibrary
0x18006b0ba  mov     eax, ebx
0x18006b0bc  add     rsp, 28h
0x18006b0c0  pop     rdi
0x18006b0c1  pop     rsi
0x18006b0c2  pop     rbp
0x18006b0c3  pop     rbx
0x18006b0c4  retn
```
