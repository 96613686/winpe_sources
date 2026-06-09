# LoadInternationalDLL

- ea: `0x1002496b`
- end: `0x100249ac`
- name: `LoadInternationalDLL`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10024d8e`

## callees

- `0x1002496b`
- `0x10032d47`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100249a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100249a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002498b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002498b`

## string_xrefs

- `0x1002496f`: `MSJINT40.DLL`

## pseudocode

```c
int LoadInternationalDLL()
{
  HMODULE Library; // eax

  Library = JetLoadLibraryExW(L"MSJINT40.DLL", 0, 0);
  dword_1003AE54 = Library;
  if ( !Library )
    return 0;
  CchLszOfId2 = GetProcAddress(Library, "CchLszOfId2");
  if ( !CchLszOfId2 )
  {
    FreeLibrary(dword_1003AE54);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1002496b  push    0; int
0x1002496d  push    0; hFile
0x1002496f  push    offset LibFileName; "MSJINT40.DLL"
0x10024974  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x10024979  mov     dword_1003AE54, eax
0x1002497e  test    eax, eax
0x10024980  jnz     short loc_10024985
0x10024982  xor     eax, eax
0x10024984  retn
0x10024985  push    offset ProcName; "CchLszOfId2"
0x1002498a  push    eax; hModule
0x1002498b  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10024991  mov     CchLszOfId2, eax
0x10024996  test    eax, eax
0x10024998  jnz     short loc_100249A8
0x1002499a  push    dword_1003AE54; hLibModule
0x100249a0  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100249a6  jmp     short loc_10024982
0x100249a8  xor     eax, eax
0x100249aa  inc     eax
0x100249ab  retn
```
