# DelayLoadCC

- ea: `0x18001b72c`
- end: `0x18001b776`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b5c8`
- `0x18001b7e4`

## callees

- `0x18001b6d4`
- `0x18001b72c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b75a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b75a`

## string_xrefs

- `0x18001b74d`: `comctl32.dll`

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
0x18001b72c  sub     rsp, 28h
0x18001b730  cmp     cs:g_hinstCC, 0
0x18001b738  jnz     short loc_18001B76C
0x18001b73a  call    SHFusionLoadLibrary
0x18001b73f  mov     cs:g_hinstCC, rax
0x18001b746  test    rax, rax
0x18001b749  jnz     short loc_18001B76C
0x18001b74b  xor     edx, edx; hFile
0x18001b74d  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18001b754  mov     r8d, 4000h; dwFlags
0x18001b75a  call    cs:__imp_LoadLibraryExW
0x18001b760  mov     cs:g_hinstCC, rax
0x18001b767  test    rax, rax
0x18001b76a  jz      short loc_18001B771
0x18001b76c  mov     eax, 1
0x18001b771  add     rsp, 28h
0x18001b775  retn
```
