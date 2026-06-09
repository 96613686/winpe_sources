# SwapBuffers

- ea: `0x180052650`
- end: `0x1800526cf`
- name: `SwapBuffers`
- size: `127`
- prototype: `BOOL __stdcall(HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180052650`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800526ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800526ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005268c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005268c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18005266e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18005266e`

## string_xrefs

- `0x180052665`: `OPENGL32`

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
0x180052650  mov     [rsp+arg_0], rbx
0x180052655  mov     [rsp+arg_8], rsi
0x18005265a  push    rdi
0x18005265b  sub     rsp, 20h
0x18005265f  mov     rsi, rcx
0x180052662  xor     r8d, r8d; dwFlags
0x180052665  lea     rcx, LibFileName; "OPENGL32"
0x18005266c  xor     edx, edx; hFile
0x18005266e  call    cs:__imp_LoadLibraryExA
0x180052675  nop     dword ptr [rax+rax+00h]
0x18005267a  mov     rdi, rax
0x18005267d  test    rax, rax
0x180052680  jz      short loc_1800526CB
0x180052682  lea     rdx, aWglswapbuffers; "wglSwapBuffers"
0x180052689  mov     rcx, rax; hModule
0x18005268c  call    cs:__imp_GetProcAddress
0x180052693  nop     dword ptr [rax+rax+00h]
0x180052698  xor     ebx, ebx
0x18005269a  test    rax, rax
0x18005269d  jz      short loc_1800526A9
0x18005269f  mov     rcx, rsi
0x1800526a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526a7  mov     ebx, eax
0x1800526a9  mov     rcx, rdi; hLibModule
0x1800526ac  call    cs:__imp_FreeLibrary
0x1800526b3  nop     dword ptr [rax+rax+00h]
0x1800526b8  mov     rsi, [rsp+28h+arg_8]
0x1800526bd  mov     eax, ebx
0x1800526bf  mov     rbx, [rsp+28h+arg_0]
0x1800526c4  add     rsp, 20h
0x1800526c8  pop     rdi
0x1800526c9  retn
0x1800526cb  xor     ebx, ebx
0x1800526cd  jmp     short loc_1800526B8
```
