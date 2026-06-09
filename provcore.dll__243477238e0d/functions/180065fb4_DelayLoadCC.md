# DelayLoadCC

- ea: `0x180065fb4`
- end: `0x180065ffe`
- name: `DelayLoadCC`
- size: `74`
- prototype: `int(...)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065e44`
- `0x1800660c8`

## callees

- `0x180065f5c`
- `0x180065fb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065fe2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065fe2`

## string_xrefs

- `0x180065fd5`: `comctl32.dll`

## pseudocode

```c
__int64 __fastcall DelayLoadCC(const wchar_t *a1)
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = SHFusionLoadLibrary(a1);
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  g_hinstCC = (HMODULE)result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180065fb4  sub     rsp, 28h
0x180065fb8  cmp     cs:g_hinstCC, 0
0x180065fc0  jnz     short loc_180065FF4
0x180065fc2  call    SHFusionLoadLibrary
0x180065fc7  mov     cs:g_hinstCC, rax
0x180065fce  test    rax, rax
0x180065fd1  jnz     short loc_180065FF4
0x180065fd3  xor     edx, edx; hFile
0x180065fd5  lea     rcx, LibFileName; "comctl32.dll"
0x180065fdc  mov     r8d, 4000h; dwFlags
0x180065fe2  call    cs:__imp_LoadLibraryExW
0x180065fe8  mov     cs:g_hinstCC, rax
0x180065fef  test    rax, rax
0x180065ff2  jz      short loc_180065FF9
0x180065ff4  mov     eax, 1
0x180065ff9  add     rsp, 28h
0x180065ffd  retn
```
