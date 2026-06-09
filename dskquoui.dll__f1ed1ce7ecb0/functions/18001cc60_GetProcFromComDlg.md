# _GetProcFromComDlg

- ea: `0x18001cc60`
- end: `0x18001ccd2`
- name: `_GetProcFromComDlg`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c930`
- `0x18001c9a4`

## callees

- `0x18001c3a4`
- `0x18001cc60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccbe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cca3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cca3`

## string_xrefs

- `0x18001cc7c`: `comdlg32.dll`
- `0x18001cc96`: `comdlg32.dll`

## pseudocode

```c
HMODULE __fastcall GetProcFromComDlg(HMODULE *a1, const CHAR *a2)
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
    result = (HMODULE)GetProcAddress(result, a2);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x18001cc60  mov     [rsp+arg_0], rbx
0x18001cc65  push    rdi
0x18001cc66  sub     rsp, 20h
0x18001cc6a  mov     rax, cs:g_hinstCD
0x18001cc71  mov     rdi, rdx
0x18001cc74  mov     rbx, rcx
0x18001cc77  test    rax, rax
0x18001cc7a  jnz     short loc_18001CCB8
0x18001cc7c  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18001cc83  call    SHFusionLoadLibrary
0x18001cc88  mov     cs:g_hinstCD, rax
0x18001cc8f  test    rax, rax
0x18001cc92  jnz     short loc_18001CCB0
0x18001cc94  xor     edx, edx; hFile
0x18001cc96  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18001cc9d  mov     r8d, 4000h; dwFlags
0x18001cca3  call    cs:__imp_LoadLibraryExW
0x18001cca9  mov     cs:g_hinstCD, rax
0x18001ccb0  mov     rcx, rax
0x18001ccb3  test    rax, rax
0x18001ccb6  jz      short loc_18001CCC4
0x18001ccb8  mov     rdx, rdi; lpProcName
0x18001ccbb  mov     rcx, rax; hModule
0x18001ccbe  call    cs:__imp_GetProcAddress
0x18001ccc4  mov     [rbx], rax
0x18001ccc7  mov     rbx, [rsp+28h+arg_0]
0x18001cccc  add     rsp, 20h
0x18001ccd0  pop     rdi
0x18001ccd1  retn
```
