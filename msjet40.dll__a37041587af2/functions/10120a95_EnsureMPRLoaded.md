# EnsureMPRLoaded()

- ea: `0x10120a95`
- end: `0x10120ae7`
- name: `_EnsureMPRLoaded@0`
- size: `82`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10120aed`

## callees

- `0x10120a95`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10120adc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10120adc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10120aaf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10120aaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10120ac1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10120ac1`

## string_xrefs

- `0x10120aaa`: `mpr.dll`

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
0x10120a95  mov     edi, edi
0x10120a97  push    edi
0x10120a98  xor     edi, edi
0x10120a9a  cmp     _g_hMPRLibrary, edi
0x10120aa0  jz      short loc_10120AA5
0x10120aa2  inc     edi
0x10120aa3  jmp     short loc_10120AE3
0x10120aa5  push    esi
0x10120aa6  push    8; dwFlags
0x10120aa8  push    0; hFile
0x10120aaa  push    offset _SZMPRDll; "mpr.dll"
0x10120aaf  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10120ab5  mov     esi, eax
0x10120ab7  test    esi, esi
0x10120ab9  jz      short loc_10120AE2
0x10120abb  push    offset _SZWNetGetConnection; "WNetGetConnectionA"
0x10120ac0  push    esi; hModule
0x10120ac1  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10120ac7  mov     _g_fnMPRWNetGetConnection, eax
0x10120acc  test    eax, eax
0x10120ace  jz      short loc_10120ADB
0x10120ad0  xor     edi, edi
0x10120ad2  mov     _g_hMPRLibrary, esi
0x10120ad8  inc     edi
0x10120ad9  jmp     short loc_10120AE2
0x10120adb  push    esi; hLibModule
0x10120adc  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10120ae2  pop     esi
0x10120ae3  mov     eax, edi
0x10120ae5  pop     edi
0x10120ae6  retn
```
