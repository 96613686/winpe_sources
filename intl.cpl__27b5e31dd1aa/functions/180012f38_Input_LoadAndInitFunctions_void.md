# Input_LoadAndInitFunctions(void)

- ea: `0x180012f38`
- end: `0x180013035`
- name: `?Input_LoadAndInitFunctions@@YAHXZ`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009870`
- `0x180009f88`
- `0x18001325c`
- `0x180014c90`
- `0x180022100`
- `0x180022180`
- `0x180022230`
- `0x1800222e0`

## callees

- `0x180012f38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ff6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ff6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012f5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012f5b`

## string_xrefs

- `0x180012f4e`: `input.dll`

## pseudocode

```c
__int64 Input_LoadAndInitFunctions(void)
{
  HMODULE Library; // rax
  unsigned int v1; // ebx

  Library = g_hInputDLL;
  v1 = 0;
  if ( g_hInputDLL || (Library = LoadLibraryExW(L"input.dll", 0, 0x800u), (g_hInputDLL = Library) != 0) )
  {
    g_pfnInstallLayoutOrTip = (int (*)(const unsigned __int16 *, unsigned int))GetProcAddress(Library, (LPCSTR)0x68);
    g_pfnSetDefaultLayoutOrTip = (int (*)(const unsigned __int16 *, unsigned int))GetProcAddress(
                                                                                    g_hInputDLL,
                                                                                    (LPCSTR)0x6B);
    g_pfnSaveDefaultUserInputSettings = (int (*)(HWND, HKEY))GetProcAddress(g_hInputDLL, (LPCSTR)0x69);
    g_pfnSaveSystemAcctInputSettings = (int (*)(HWND, HKEY))GetProcAddress(g_hInputDLL, (LPCSTR)0x6A);
    g_pfnGetDefaultLayout = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(
                                                                                                     g_hInputDLL,
                                                                                                     (LPCSTR)0x71);
    g_pfnGetLayoutDescription = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(g_hInputDLL, (LPCSTR)0x72);
    if ( g_pfnInstallLayoutOrTip
      && g_pfnSetDefaultLayoutOrTip
      && g_pfnSaveDefaultUserInputSettings
      && g_pfnSaveSystemAcctInputSettings )
    {
      return 1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180012f38  push    rbx
0x180012f3a  sub     rsp, 20h
0x180012f3e  mov     rax, cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInputDLL
0x180012f45  xor     ebx, ebx
0x180012f47  test    rax, rax
0x180012f4a  jnz     short loc_180012F71
0x180012f4c  xor     edx, edx; hFile
0x180012f4e  lea     rcx, LibFileName; "input.dll"
0x180012f55  mov     r8d, 800h; dwFlags
0x180012f5b  call    cs:__imp_LoadLibraryExW
0x180012f61  mov     cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInputDLL
0x180012f68  test    rax, rax
0x180012f6b  jz      loc_18001302D
0x180012f71  mov     edx, 68h ; 'h'; lpProcName
0x180012f76  mov     rcx, rax; hModule
0x180012f79  call    cs:__imp_GetProcAddress
0x180012f7f  mov     rcx, cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180012f86  mov     edx, 6Bh ; 'k'; lpProcName
0x180012f8b  mov     cs:?g_pfnInstallLayoutOrTip@@3P6AHPEBGK@ZEA, rax; int (*g_pfnInstallLayoutOrTip)(ushort const *,ulong)
0x180012f92  call    cs:__imp_GetProcAddress
0x180012f98  mov     rcx, cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180012f9f  mov     edx, 69h ; 'i'; lpProcName
0x180012fa4  mov     cs:?g_pfnSetDefaultLayoutOrTip@@3P6AHPEBGK@ZEA, rax; int (*g_pfnSetDefaultLayoutOrTip)(ushort const *,ulong)
0x180012fab  call    cs:__imp_GetProcAddress
0x180012fb1  mov     rcx, cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180012fb8  mov     edx, 6Ah ; 'j'; lpProcName
0x180012fbd  mov     cs:?g_pfnSaveDefaultUserInputSettings@@3P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, rax; int (*g_pfnSaveDefaultUserInputSettings)(HWND__ *,HKEY__ *)
0x180012fc4  call    cs:__imp_GetProcAddress
0x180012fca  mov     rcx, cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180012fd1  mov     edx, 71h ; 'q'; lpProcName
0x180012fd6  mov     cs:?g_pfnSaveSystemAcctInputSettings@@3P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, rax; int (*g_pfnSaveSystemAcctInputSettings)(HWND__ *,HKEY__ *)
0x180012fdd  call    cs:__imp_GetProcAddress
0x180012fe3  mov     rcx, cs:?g_hInputDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180012fea  mov     edx, 72h ; 'r'; lpProcName
0x180012fef  mov     cs:?g_pfnGetDefaultLayout@@3P6AJPEBGPEAGPEAK@ZEA, rax; long (*g_pfnGetDefaultLayout)(ushort const *,ushort *,ulong *)
0x180012ff6  call    cs:__imp_GetProcAddress
0x180012ffc  cmp     cs:?g_pfnInstallLayoutOrTip@@3P6AHPEBGK@ZEA, rbx; int (*g_pfnInstallLayoutOrTip)(ushort const *,ulong)
0x180013003  mov     cs:?g_pfnGetLayoutDescription@@3P6AJPEBGPEAGPEAK@ZEA, rax; long (*g_pfnGetLayoutDescription)(ushort const *,ushort *,ulong *)
0x18001300a  jz      short loc_18001302D
0x18001300c  cmp     cs:?g_pfnSetDefaultLayoutOrTip@@3P6AHPEBGK@ZEA, rbx; int (*g_pfnSetDefaultLayoutOrTip)(ushort const *,ulong)
0x180013013  jz      short loc_18001302D
0x180013015  cmp     cs:?g_pfnSaveDefaultUserInputSettings@@3P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, rbx; int (*g_pfnSaveDefaultUserInputSettings)(HWND__ *,HKEY__ *)
0x18001301c  jz      short loc_18001302D
0x18001301e  cmp     cs:?g_pfnSaveSystemAcctInputSettings@@3P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, rbx; int (*g_pfnSaveSystemAcctInputSettings)(HWND__ *,HKEY__ *)
0x180013025  mov     eax, 1
0x18001302a  cmovnz  ebx, eax
0x18001302d  mov     eax, ebx
0x18001302f  add     rsp, 20h
0x180013033  pop     rbx
0x180013034  retn
```
