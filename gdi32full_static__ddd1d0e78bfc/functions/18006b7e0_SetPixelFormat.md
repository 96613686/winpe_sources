# SetPixelFormat

- ea: `0x18006b7e0`
- end: `0x18006b8cd`
- name: `SetPixelFormat`
- size: `237`
- prototype: `BOOL __stdcall(HDC hdc, int format, const PIXELFORMATDESCRIPTOR *ppfd)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180057710`
- `0x180096330`

## callees

- `0x18006b7e0`
- `0x1800932fc`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b867`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b867`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b81e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b81e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006b800`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006b800`
- `GDI32!pldcGet` at `0x18006b88e`
- `GDI32!pldcGet` at `0x18006b88e`
- `GDI32!GdiSetLastError` at `0x18006b8bd`
- `GDI32!GdiSetLastError` at `0x18006b8bd`

## string_xrefs

- `0x18006b7f9`: `OPENGL32`

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
0x18006b7e0  push    rbx
0x18006b7e2  push    rbp
0x18006b7e3  push    rsi
0x18006b7e4  push    rdi
0x18006b7e5  push    r14
0x18006b7e7  sub     rsp, 20h
0x18006b7eb  mov     rbp, r8
0x18006b7ee  mov     r14d, edx
0x18006b7f1  mov     rsi, rcx
0x18006b7f4  xor     r8d, r8d; dwFlags
0x18006b7f7  xor     edx, edx; hFile
0x18006b7f9  lea     rcx, LibFileName; "OPENGL32"
0x18006b800  call    cs:__imp_LoadLibraryExA
0x18006b807  nop     dword ptr [rax+rax+00h]
0x18006b80c  mov     rdi, rax
0x18006b80f  test    rax, rax
0x18006b812  jz      short loc_18006B881
0x18006b814  lea     rdx, aWglsetpixelfor; "wglSetPixelFormat"
0x18006b81b  mov     rcx, rax; hModule
0x18006b81e  call    cs:__imp_GetProcAddress
0x18006b825  nop     dword ptr [rax+rax+00h]
0x18006b82a  xor     ebx, ebx
0x18006b82c  mov     cs:gbSetPixelFormatCalled, 1
0x18006b836  test    rax, rax
0x18006b839  jz      short loc_18006B85F
0x18006b83b  mov     r8, rbp
0x18006b83e  mov     edx, r14d
0x18006b841  mov     rcx, rsi
0x18006b844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b849  mov     ebx, eax
0x18006b84b  test    eax, eax
0x18006b84d  jz      short loc_18006B85F
0x18006b84f  mov     ecx, esi
0x18006b851  and     ecx, 7F0000h
0x18006b857  cmp     ecx, 10000h
0x18006b85d  jnz     short loc_18006B883
0x18006b85f  test    rdi, rdi
0x18006b862  jz      short loc_18006B873
0x18006b864  mov     rcx, rdi; hLibModule
0x18006b867  call    cs:__imp_FreeLibrary
0x18006b86e  nop     dword ptr [rax+rax+00h]
0x18006b873  mov     eax, ebx
0x18006b875  add     rsp, 20h
0x18006b879  pop     r14
0x18006b87b  pop     rdi
0x18006b87c  pop     rsi
0x18006b87d  pop     rbp
0x18006b87e  pop     rbx
0x18006b87f  retn
0x18006b881  jmp     short loc_18006B82A
0x18006b883  cmp     ecx, 660000h
0x18006b889  jz      short loc_18006B85F
0x18006b88b  mov     rcx, rsi
0x18006b88e  call    cs:__imp_pldcGet
0x18006b895  nop     dword ptr [rax+rax+00h]
0x18006b89a  test    rax, rax
0x18006b89d  jz      short loc_18006B8B8
0x18006b89f  cmp     dword ptr [rax+0Ch], 2
0x18006b8a3  jnz     short loc_18006B85F
0x18006b8a5  mov     r8, rbp
0x18006b8a8  mov     rcx, rsi
0x18006b8ab  call    MF_SetPixelFormat
0x18006b8b0  test    eax, eax
0x18006b8b2  jnz     short loc_18006B85F
0x18006b8b4  xor     ebx, ebx
0x18006b8b6  jmp     short loc_18006B85F
0x18006b8b8  mov     ecx, 6
0x18006b8bd  call    cs:__imp_GdiSetLastError
0x18006b8c4  nop     dword ptr [rax+rax+00h]
0x18006b8c9  xor     eax, eax
0x18006b8cb  jmp     short loc_18006B875
```
