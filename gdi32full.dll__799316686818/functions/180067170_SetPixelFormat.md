# SetPixelFormat

- ea: `0x180067170`
- end: `0x18006723e`
- name: `SetPixelFormat`
- size: `206`
- prototype: `BOOL __stdcall(HDC hdc, int format, const PIXELFORMATDESCRIPTOR *ppfd)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180051bac`
- `0x180090830`

## callees

- `0x180067170`
- `0x18008da28`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800671eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800671eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800671a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800671a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180067190`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180067190`
- `GDI32!pldcGet` at `0x18006720b`
- `GDI32!pldcGet` at `0x18006720b`
- `GDI32!GdiSetLastError` at `0x180067234`
- `GDI32!GdiSetLastError` at `0x180067234`

## string_xrefs

- `0x180067189`: `OPENGL32`

## pseudocode

```c
BOOL __stdcall SetPixelFormat(HDC hdc, int format, const PIXELFORMATDESCRIPTOR *ppfd)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  int v8; // ebx
  __int64 v10; // rax
  __int64 v11; // rdx

  Library = LoadLibraryExA(LibFileName, 0, 0);
  v7 = Library;
  if ( Library )
    Library = (HMODULE)GetProcAddress(Library, "wglSetPixelFormat");
  v8 = 0;
  gbSetPixelFormatCalled = 1;
  if ( Library )
  {
    v8 = ((__int64 (__fastcall *)(HDC, _QWORD, const PIXELFORMATDESCRIPTOR *))Library)(hdc, (unsigned int)format, ppfd);
    if ( v8 )
    {
      if ( ((unsigned int)hdc & 0x7F0000) != 0x10000 && ((unsigned int)hdc & 0x7F0000) != 0x660000 )
      {
        v10 = pldcGet(hdc);
        if ( !v10 )
        {
          GdiSetLastError(6);
          return 0;
        }
        if ( *(_DWORD *)(v10 + 12) == 2 && !(unsigned int)MF_SetPixelFormat(hdc, v11, ppfd) )
          v8 = 0;
      }
    }
  }
  if ( v7 )
    FreeLibrary(v7);
  return v8;
}

```

## disassembly

```asm
0x180067170  push    rbx
0x180067172  push    rbp
0x180067173  push    rsi
0x180067174  push    rdi
0x180067175  push    r14
0x180067177  sub     rsp, 20h
0x18006717b  mov     rbp, r8
0x18006717e  mov     r14d, edx
0x180067181  mov     rsi, rcx
0x180067184  xor     r8d, r8d; dwFlags
0x180067187  xor     edx, edx; hFile
0x180067189  lea     rcx, LibFileName; "OPENGL32"
0x180067190  call    cs:__imp_LoadLibraryExA
0x180067196  mov     rdi, rax
0x180067199  test    rax, rax
0x18006719c  jz      short loc_1800671FE
0x18006719e  lea     rdx, aWglsetpixelfor; "wglSetPixelFormat"
0x1800671a5  mov     rcx, rax; hModule
0x1800671a8  call    cs:__imp_GetProcAddress
0x1800671ae  xor     ebx, ebx
0x1800671b0  mov     cs:gbSetPixelFormatCalled, 1
0x1800671ba  test    rax, rax
0x1800671bd  jz      short loc_1800671E3
0x1800671bf  mov     r8, rbp
0x1800671c2  mov     edx, r14d
0x1800671c5  mov     rcx, rsi
0x1800671c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671cd  mov     ebx, eax
0x1800671cf  test    eax, eax
0x1800671d1  jz      short loc_1800671E3
0x1800671d3  mov     ecx, esi
0x1800671d5  and     ecx, 7F0000h
0x1800671db  cmp     ecx, 10000h
0x1800671e1  jnz     short loc_180067200
0x1800671e3  test    rdi, rdi
0x1800671e6  jz      short loc_1800671F1
0x1800671e8  mov     rcx, rdi; hLibModule
0x1800671eb  call    cs:__imp_FreeLibrary
0x1800671f1  mov     eax, ebx
0x1800671f3  add     rsp, 20h
0x1800671f7  pop     r14
0x1800671f9  pop     rdi
0x1800671fa  pop     rsi
0x1800671fb  pop     rbp
0x1800671fc  pop     rbx
0x1800671fd  retn
0x1800671fe  jmp     short loc_1800671AE
0x180067200  cmp     ecx, 660000h
0x180067206  jz      short loc_1800671E3
0x180067208  mov     rcx, rsi
0x18006720b  call    cs:__imp_pldcGet
0x180067211  test    rax, rax
0x180067214  jz      short loc_18006722F
0x180067216  cmp     dword ptr [rax+0Ch], 2
0x18006721a  jnz     short loc_1800671E3
0x18006721c  mov     r8, rbp
0x18006721f  mov     rcx, rsi
0x180067222  call    MF_SetPixelFormat
0x180067227  test    eax, eax
0x180067229  jnz     short loc_1800671E3
0x18006722b  xor     ebx, ebx
0x18006722d  jmp     short loc_1800671E3
0x18006722f  mov     ecx, 6
0x180067234  call    cs:__imp_GdiSetLastError
0x18006723a  xor     eax, eax
0x18006723c  jmp     short loc_1800671F3
```
