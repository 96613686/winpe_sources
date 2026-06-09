# DpiAwarenessApiWrapper::SetThreadDpiAwarenessContext(DPI_AWARENESS_CONTEXT__ *)

- ea: `0x1800dfb1c`
- end: `0x1800dfb75`
- name: `?SetThreadDpiAwarenessContext@DpiAwarenessApiWrapper@@SAPEAUDPI_AWARENESS_CONTEXT__@@PEAU2@@Z`
- size: `89`
- prototype: `struct DPI_AWARENESS_CONTEXT__ *__fastcall(struct DPI_AWARENESS_CONTEXT__ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005d190`

## callees

- `0x1800dfb1c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dfb47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dfb47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dfb61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dfb61`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800dfb2f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800dfb2f`

## string_xrefs

- `0x1800dfb26`: `ext-ms-win-rtcore-ntuser-dpi-l1-2-0.dll`
- `0x1800dfb3d`: `SetThreadDpiAwarenessContext`

## pseudocode

```c
struct DPI_AWARENESS_CONTEXT__ *__fastcall DpiAwarenessApiWrapper::SetThreadDpiAwarenessContext(
        struct DPI_AWARENESS_CONTEXT__ *a1)
{
  __int64 v1; // rdi
  HMODULE LibraryW; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax

  v1 = 0;
  LibraryW = LoadLibraryW(L"ext-ms-win-rtcore-ntuser-dpi-l1-2-0.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SetThreadDpiAwarenessContext");
    if ( ProcAddress )
      v1 = ((__int64 (__fastcall *)(__int64))ProcAddress)(-3);
    FreeLibrary(v3);
  }
  return (struct DPI_AWARENESS_CONTEXT__ *)v1;
}

```

## disassembly

```asm
0x1800dfb1c  mov     [rsp+arg_0], rbx
0x1800dfb21  push    rdi
0x1800dfb22  sub     rsp, 20h
0x1800dfb26  lea     rcx, aExtMsWinRtcore_4; "ext-ms-win-rtcore-ntuser-dpi-l1-2-0.dll"
0x1800dfb2d  xor     edi, edi
0x1800dfb2f  call    cs:__imp_LoadLibraryW
0x1800dfb35  mov     rbx, rax
0x1800dfb38  test    rax, rax
0x1800dfb3b  jz      short loc_1800DFB67
0x1800dfb3d  lea     rdx, aSetthreaddpiaw; "SetThreadDpiAwarenessContext"
0x1800dfb44  mov     rcx, rax; hModule
0x1800dfb47  call    cs:__imp_GetProcAddress
0x1800dfb4d  test    rax, rax
0x1800dfb50  jz      short loc_1800DFB5E
0x1800dfb52  lea     rcx, [rdi-3]
0x1800dfb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfb5b  mov     rdi, rax
0x1800dfb5e  mov     rcx, rbx; hLibModule
0x1800dfb61  call    cs:__imp_FreeLibrary
0x1800dfb67  mov     rbx, [rsp+28h+arg_0]
0x1800dfb6c  mov     rax, rdi
0x1800dfb6f  add     rsp, 20h
0x1800dfb73  pop     rdi
0x1800dfb74  retn
```
