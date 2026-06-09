# GetCryptProcs(void)

- ea: `0x1800d910c`
- end: `0x1800d9186`
- name: `?GetCryptProcs@@YA_NXZ`
- size: `122`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800d8f78`

## callees

- `0x1800d910c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9141`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9162`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9141`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9162`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d911f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d911f`

## string_xrefs

- `0x1800d9112`: `Crypt32.dll`

## pseudocode

```c
bool GetCryptProcs(void)
{
  HMODULE Library; // rax

  Library = LoadLibraryExW(L"Crypt32.dll", 0, 0x800u);
  g_hCrypt = Library;
  if ( Library )
  {
    g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(Library, "CryptProtectMemory");
    g_pfnCryptUnprotectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(
                                                                               g_hCrypt,
                                                                               "CryptUnprotectMemory");
    LOBYTE(Library) = g_pfnCryptProtectMemory != 0;
  }
  return (char)Library;
}

```

## disassembly

```asm
0x1800d910c  sub     rsp, 28h
0x1800d9110  xor     edx, edx; hFile
0x1800d9112  lea     rcx, aCrypt32Dll; "Crypt32.dll"
0x1800d9119  mov     r8d, 800h; dwFlags
0x1800d911f  call    cs:__imp_LoadLibraryExW
0x1800d9126  nop     dword ptr [rax+rax+00h]
0x1800d912b  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x1800d9132  test    rax, rax
0x1800d9135  jz      short loc_1800D9180
0x1800d9137  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x1800d913e  mov     rcx, rax; hModule
0x1800d9141  call    cs:__imp_GetProcAddress
0x1800d9148  nop     dword ptr [rax+rax+00h]
0x1800d914d  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x1800d9154  lea     rdx, aCryptunprotect; "CryptUnprotectMemory"
0x1800d915b  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x1800d9162  call    cs:__imp_GetProcAddress
0x1800d9169  nop     dword ptr [rax+rax+00h]
0x1800d916e  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, 0; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x1800d9176  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x1800d917d  setnz   al
0x1800d9180  add     rsp, 28h
0x1800d9184  retn
```
