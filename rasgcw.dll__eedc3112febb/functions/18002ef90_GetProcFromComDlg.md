# _GetProcFromComDlg

- ea: `0x18002ef90`
- end: `0x18002eff8`
- name: `_GetProcFromComDlg`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002edb8`

## callees

- `0x18002eb58`
- `0x18002ef90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002efe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002efe6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002efc7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002efc7`

## string_xrefs

- `0x18002efa0`: `comdlg32.dll`
- `0x18002efba`: `comdlg32.dll`

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
    result = (HMODULE)GetProcAddress(result, "PrintDlgW");
  qword_18004DC58 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x18002ef90  sub     rsp, 28h
0x18002ef94  mov     rax, cs:g_hinstCD
0x18002ef9b  test    rax, rax
0x18002ef9e  jnz     short loc_18002EFDC
0x18002efa0  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18002efa7  call    SHFusionLoadLibrary
0x18002efac  mov     cs:g_hinstCD, rax
0x18002efb3  test    rax, rax
0x18002efb6  jnz     short loc_18002EFD4
0x18002efb8  xor     edx, edx; hFile
0x18002efba  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18002efc1  mov     r8d, 4000h; dwFlags
0x18002efc7  call    cs:__imp_LoadLibraryExW
0x18002efcd  mov     cs:g_hinstCD, rax
0x18002efd4  mov     rcx, rax
0x18002efd7  test    rax, rax
0x18002efda  jz      short loc_18002EFEC
0x18002efdc  lea     rdx, aPrintdlgw; "PrintDlgW"
0x18002efe3  mov     rcx, rax; hModule
0x18002efe6  call    cs:__imp_GetProcAddress
0x18002efec  mov     cs:qword_18004DC58, rax
0x18002eff3  add     rsp, 28h
0x18002eff7  retn
```
