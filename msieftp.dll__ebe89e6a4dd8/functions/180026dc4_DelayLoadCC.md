# DelayLoadCC

- ea: `0x180026dc4`
- end: `0x180026e0e`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025830`
- `0x18002663c`
- `0x1800266cc`
- `0x180026fa0`

## callees

- `0x1800267d8`
- `0x180026dc4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026df2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026df2`

## string_xrefs

- `0x180026de5`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = SHFusionLoadLibrary();
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
0x180026dc4  sub     rsp, 28h
0x180026dc8  cmp     cs:g_hinstCC, 0
0x180026dd0  jnz     short loc_180026E04
0x180026dd2  call    SHFusionLoadLibrary
0x180026dd7  mov     cs:g_hinstCC, rax
0x180026dde  test    rax, rax
0x180026de1  jnz     short loc_180026E04
0x180026de3  xor     edx, edx; hFile
0x180026de5  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180026dec  mov     r8d, 4000h; dwFlags
0x180026df2  call    cs:__imp_LoadLibraryExW
0x180026df8  mov     cs:g_hinstCC, rax
0x180026dff  test    rax, rax
0x180026e02  jz      short loc_180026E09
0x180026e04  mov     eax, 1
0x180026e09  add     rsp, 28h
0x180026e0d  retn
```
