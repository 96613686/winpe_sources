# InitialiseDCI

- ea: `0x18000b7dc`
- end: `0x18000b920`
- name: `InitialiseDCI`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b3d8`

## callees

- `0x18000b7dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b904`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b83b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b856`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b88c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b8a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b83b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b856`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b88c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b8a7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18000b800`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18000b800`

## string_xrefs

- `0x18000b7f9`: `DCIMAN32.DLL`
- `0x18000b816`: `DCIOpenProvider`
- `0x18000b87e`: `DCIBeginAccess`
- `0x18000b848`: `DCICreatePrimary`
- `0x18000b863`: `DCIEndAccess`

## pseudocode

```c
__int64 InitialiseDCI()
{
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax

  ++dword_180023DA8;
  if ( dword_180023D94 )
    return 1;
  LibraryA = LoadLibraryA("DCIMAN32.DLL");
  hLibModule = LibraryA;
  if ( LibraryA )
  {
    pfnDCIOpenProvider = (__int64)GetProcAddress(LibraryA, szDCIOpenProvider);
    pfnDCICloseProvider = (__int64)GetProcAddress(hLibModule, szDCICloseProvider);
    pfnDCICreatePrimary = (__int64)GetProcAddress(hLibModule, szDCICreatePrimary);
    pfnDCIEndAccess = (__int64)GetProcAddress(hLibModule, szDCIEndAccess);
    pfnDCIBeginAccess = (__int64)GetProcAddress(hLibModule, szDCIBeginAccess);
    ProcAddress = GetProcAddress(hLibModule, szDCIDestroy);
    pfnDCIDestroy = (__int64)ProcAddress;
    if ( pfnDCIOpenProvider
      && pfnDCICloseProvider
      && pfnDCICreatePrimary
      && pfnDCIEndAccess
      && pfnDCIBeginAccess
      && ProcAddress )
    {
      dword_180023D94 = 1;
    }
    else
    {
      --dword_180023DA8;
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
  }
  return (unsigned int)dword_180023D94;
}

```

## disassembly

```asm
0x18000b7dc  sub     rsp, 28h
0x18000b7e0  inc     cs:dword_180023DA8
0x18000b7e6  cmp     cs:dword_180023D94, 0
0x18000b7ed  jz      short loc_18000B7F9
0x18000b7ef  mov     eax, 1
0x18000b7f4  jmp     loc_18000B91B
0x18000b7f9  lea     rcx, LibFileName; "DCIMAN32.DLL"
0x18000b800  call    cs:__imp_LoadLibraryA
0x18000b806  mov     cs:hLibModule, rax
0x18000b80d  test    rax, rax
0x18000b810  jz      loc_18000B915
0x18000b816  lea     rdx, szDCIOpenProvider; "DCIOpenProvider"
0x18000b81d  mov     rcx, rax; hModule
0x18000b820  call    cs:__imp_GetProcAddress
0x18000b826  mov     rcx, cs:hLibModule; hModule
0x18000b82d  lea     rdx, szDCICloseProvider; "DCICloseProvider"
0x18000b834  mov     cs:pfnDCIOpenProvider, rax
0x18000b83b  call    cs:__imp_GetProcAddress
0x18000b841  mov     rcx, cs:hLibModule; hModule
0x18000b848  lea     rdx, szDCICreatePrimary; "DCICreatePrimary"
0x18000b84f  mov     cs:pfnDCICloseProvider, rax
0x18000b856  call    cs:__imp_GetProcAddress
0x18000b85c  mov     rcx, cs:hLibModule; hModule
0x18000b863  lea     rdx, szDCIEndAccess; "DCIEndAccess"
0x18000b86a  mov     cs:pfnDCICreatePrimary, rax
0x18000b871  call    cs:__imp_GetProcAddress
0x18000b877  mov     rcx, cs:hLibModule; hModule
0x18000b87e  lea     rdx, szDCIBeginAccess; "DCIBeginAccess"
0x18000b885  mov     cs:pfnDCIEndAccess, rax
0x18000b88c  call    cs:__imp_GetProcAddress
0x18000b892  mov     rcx, cs:hLibModule; hModule
0x18000b899  lea     rdx, szDCIDestroy; "DCIDestroy"
0x18000b8a0  mov     cs:pfnDCIBeginAccess, rax
0x18000b8a7  call    cs:__imp_GetProcAddress
0x18000b8ad  cmp     cs:pfnDCIOpenProvider, 0
0x18000b8b5  mov     cs:pfnDCIDestroy, rax
0x18000b8bc  jz      short loc_18000B8F7
0x18000b8be  cmp     cs:pfnDCICloseProvider, 0
0x18000b8c6  jz      short loc_18000B8F7
0x18000b8c8  cmp     cs:pfnDCICreatePrimary, 0
0x18000b8d0  jz      short loc_18000B8F7
0x18000b8d2  cmp     cs:pfnDCIEndAccess, 0
0x18000b8da  jz      short loc_18000B8F7
0x18000b8dc  cmp     cs:pfnDCIBeginAccess, 0
0x18000b8e4  jz      short loc_18000B8F7
0x18000b8e6  test    rax, rax
0x18000b8e9  jz      short loc_18000B8F7
0x18000b8eb  mov     cs:dword_180023D94, 1
0x18000b8f5  jmp     short loc_18000B915
0x18000b8f7  dec     cs:dword_180023DA8
0x18000b8fd  mov     rcx, cs:hLibModule; hLibModule
0x18000b904  call    cs:__imp_FreeLibrary
0x18000b90a  mov     cs:hLibModule, 0
0x18000b915  mov     eax, cs:dword_180023D94
0x18000b91b  add     rsp, 28h
0x18000b91f  retn
```
