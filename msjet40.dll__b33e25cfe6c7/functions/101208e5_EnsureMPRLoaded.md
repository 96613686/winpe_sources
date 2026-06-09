# EnsureMPRLoaded()

- ea: `0x101208e5`
- end: `0x10120937`
- name: `_EnsureMPRLoaded@0`
- size: `82`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1012093d`

## callees

- `0x101208e5`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1012092c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1012092c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x101208ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x101208ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10120911`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10120911`

## string_xrefs

- `0x101208fa`: `mpr.dll`

## pseudocode

```c
int __stdcall EnsureMPRLoaded()
{
  int v0; // edi
  HMODULE Library; // eax
  HMODULE v2; // esi

  v0 = 0;
  if ( g_hMPRLibrary )
    return 1;
  Library = LoadLibraryExA("mpr.dll", 0, 8u);
  v2 = Library;
  if ( Library )
  {
    g_fnMPRWNetGetConnection = (int)GetProcAddress(Library, "WNetGetConnectionA");
    if ( g_fnMPRWNetGetConnection )
    {
      g_hMPRLibrary = v2;
      return 1;
    }
    else
    {
      FreeLibrary(v2);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x101208e5  mov     edi, edi
0x101208e7  push    edi
0x101208e8  xor     edi, edi
0x101208ea  cmp     _g_hMPRLibrary, edi
0x101208f0  jz      short loc_101208F5
0x101208f2  inc     edi
0x101208f3  jmp     short loc_10120933
0x101208f5  push    esi
0x101208f6  push    8; dwFlags
0x101208f8  push    0; hFile
0x101208fa  push    offset _SZMPRDll; "mpr.dll"
0x101208ff  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10120905  mov     esi, eax
0x10120907  test    esi, esi
0x10120909  jz      short loc_10120932
0x1012090b  push    offset _SZWNetGetConnection; "WNetGetConnectionA"
0x10120910  push    esi; hModule
0x10120911  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10120917  mov     _g_fnMPRWNetGetConnection, eax
0x1012091c  test    eax, eax
0x1012091e  jz      short loc_1012092B
0x10120920  xor     edi, edi
0x10120922  mov     _g_hMPRLibrary, esi
0x10120928  inc     edi
0x10120929  jmp     short loc_10120932
0x1012092b  push    esi; hLibModule
0x1012092c  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10120932  pop     esi
0x10120933  mov     eax, edi
0x10120935  pop     edi
0x10120936  retn
```
