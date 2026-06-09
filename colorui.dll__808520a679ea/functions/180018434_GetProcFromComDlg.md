# _GetProcFromComDlg

- ea: `0x180018434`
- end: `0x1800184a6`
- name: `_GetProcFromComDlg`
- size: `114`
- prototype: `HMODULE __fastcall(HMODULE *, const CHAR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017e4c`
- `0x1800181b8`
- `0x18001822c`

## callees

- `0x180017df0`
- `0x180018434`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180018492`
- `KERNEL32!GetProcAddress` at `0x180018492`
- `KERNEL32!LoadLibraryExW` at `0x180018477`
- `KERNEL32!LoadLibraryExW` at `0x180018477`

## string_xrefs

- `0x180018450`: `comdlg32.dll`
- `0x18001846a`: `comdlg32.dll`

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
0x180018434  mov     [rsp+arg_0], rbx
0x180018439  push    rdi
0x18001843a  sub     rsp, 20h
0x18001843e  mov     rax, cs:g_hinstCD
0x180018445  mov     rdi, rdx
0x180018448  mov     rbx, rcx
0x18001844b  test    rax, rax
0x18001844e  jnz     short loc_18001848C
0x180018450  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x180018457  call    SHFusionLoadLibrary
0x18001845c  mov     cs:g_hinstCD, rax
0x180018463  test    rax, rax
0x180018466  jnz     short loc_180018484
0x180018468  xor     edx, edx; hFile
0x18001846a  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x180018471  mov     r8d, 4000h; dwFlags
0x180018477  call    cs:__imp_LoadLibraryExW
0x18001847d  mov     cs:g_hinstCD, rax
0x180018484  mov     rcx, rax
0x180018487  test    rax, rax
0x18001848a  jz      short loc_180018498
0x18001848c  mov     rdx, rdi; lpProcName
0x18001848f  mov     rcx, rax; hModule
0x180018492  call    cs:__imp_GetProcAddress
0x180018498  mov     [rbx], rax
0x18001849b  mov     rbx, [rsp+28h+arg_0]
0x1800184a0  add     rsp, 20h
0x1800184a4  pop     rdi
0x1800184a5  retn
```
