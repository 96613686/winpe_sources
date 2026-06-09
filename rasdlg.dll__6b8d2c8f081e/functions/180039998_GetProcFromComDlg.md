# _GetProcFromComDlg

- ea: `0x180039998`
- end: `0x180039a0a`
- name: `_GetProcFromComDlg`
- size: `114`
- prototype: `HMODULE __fastcall(HMODULE *, const CHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039514`
- `0x180039580`

## callees

- `0x1800392c4`
- `0x180039998`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800399db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800399db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800399f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800399f6`

## string_xrefs

- `0x1800399b4`: `comdlg32.dll`
- `0x1800399ce`: `comdlg32.dll`

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
0x180039998  mov     [rsp+arg_0], rbx
0x18003999d  push    rdi
0x18003999e  sub     rsp, 20h
0x1800399a2  mov     rax, cs:g_hinstCD
0x1800399a9  mov     rdi, rdx
0x1800399ac  mov     rbx, rcx
0x1800399af  test    rax, rax
0x1800399b2  jnz     short loc_1800399F0
0x1800399b4  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x1800399bb  call    SHFusionLoadLibrary
0x1800399c0  mov     cs:g_hinstCD, rax
0x1800399c7  test    rax, rax
0x1800399ca  jnz     short loc_1800399E8
0x1800399cc  xor     edx, edx; hFile
0x1800399ce  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x1800399d5  mov     r8d, 4000h; dwFlags
0x1800399db  call    cs:__imp_LoadLibraryExW
0x1800399e1  mov     cs:g_hinstCD, rax
0x1800399e8  mov     rcx, rax
0x1800399eb  test    rax, rax
0x1800399ee  jz      short loc_1800399FC
0x1800399f0  mov     rdx, rdi; lpProcName
0x1800399f3  mov     rcx, rax; hModule
0x1800399f6  call    cs:__imp_GetProcAddress
0x1800399fc  mov     [rbx], rax
0x1800399ff  mov     rbx, [rsp+28h+arg_0]
0x180039a04  add     rsp, 20h
0x180039a08  pop     rdi
0x180039a09  retn
```
