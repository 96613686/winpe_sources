# _GetProcFromComDlg

- ea: `0x18002de0c`
- end: `0x18002de74`
- name: `_GetProcFromComDlg`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002db24`

## callees

- `0x18002da18`
- `0x18002de0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002de62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002de62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002de43`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002de43`

## string_xrefs

- `0x18002de1c`: `comdlg32.dll`
- `0x18002de36`: `comdlg32.dll`
- `0x18002de58`: `GetOpenFileNameW`

## pseudocode

```c
HMODULE GetProcFromComDlg()
{
  HMODULE result; // rax

  result = g_hinstCD;
  if ( g_hinstCD )
    goto LABEL_5;
  result = (HMODULE)SHFusionLoadLibrary(L"comdlg32.dll");
  g_hinstCD = result;
  if ( !result )
  {
    result = LoadLibraryExW(L"comdlg32.dll", 0, 0x4000u);
    g_hinstCD = result;
  }
  if ( result )
LABEL_5:
    result = (HMODULE)GetProcAddress(result, "GetOpenFileNameW");
  qword_180046418 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x18002de0c  sub     rsp, 28h
0x18002de10  mov     rax, cs:g_hinstCD
0x18002de17  test    rax, rax
0x18002de1a  jnz     short loc_18002DE58
0x18002de1c  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18002de23  call    SHFusionLoadLibrary
0x18002de28  mov     cs:g_hinstCD, rax
0x18002de2f  test    rax, rax
0x18002de32  jnz     short loc_18002DE50
0x18002de34  xor     edx, edx; hFile
0x18002de36  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18002de3d  mov     r8d, 4000h; dwFlags
0x18002de43  call    cs:__imp_LoadLibraryExW
0x18002de49  mov     cs:g_hinstCD, rax
0x18002de50  mov     rcx, rax
0x18002de53  test    rax, rax
0x18002de56  jz      short loc_18002DE68
0x18002de58  lea     rdx, aGetopenfilenam; "GetOpenFileNameW"
0x18002de5f  mov     rcx, rax; hModule
0x18002de62  call    cs:__imp_GetProcAddress
0x18002de68  mov     cs:qword_180046418, rax
0x18002de6f  add     rsp, 28h
0x18002de73  retn
```
