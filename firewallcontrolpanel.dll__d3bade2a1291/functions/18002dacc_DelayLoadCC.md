# DelayLoadCC

- ea: `0x18002dacc`
- end: `0x18002db1d`
- name: `DelayLoadCC`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d858`
- `0x18002d90c`
- `0x18002ddbc`

## callees

- `0x18002da18`
- `0x18002dacc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002db01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002db01`

## string_xrefs

- `0x18002dada`: `comctl32.dll`
- `0x18002daf4`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (HMODULE)SHFusionLoadLibrary(L"comctl32.dll");
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
0x18002dacc  sub     rsp, 28h
0x18002dad0  cmp     cs:g_hinstCC, 0
0x18002dad8  jnz     short loc_18002DB13
0x18002dada  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002dae1  call    SHFusionLoadLibrary
0x18002dae6  mov     cs:g_hinstCC, rax
0x18002daed  test    rax, rax
0x18002daf0  jnz     short loc_18002DB13
0x18002daf2  xor     edx, edx; hFile
0x18002daf4  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002dafb  mov     r8d, 4000h; dwFlags
0x18002db01  call    cs:__imp_LoadLibraryExW
0x18002db07  mov     cs:g_hinstCC, rax
0x18002db0e  test    rax, rax
0x18002db11  jz      short loc_18002DB18
0x18002db13  mov     eax, 1
0x18002db18  add     rsp, 28h
0x18002db1c  retn
```
