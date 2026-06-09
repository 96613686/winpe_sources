# DelayLoadCC

- ea: `0x18000ca08`
- end: `0x18000ca52`
- name: `DelayLoadCC`
- size: `74`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000642c`
- `0x18000c89c`
- `0x18000cad4`

## callees

- `0x18000c9a8`
- `0x18000ca08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ca36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ca36`

## string_xrefs

- `0x18000ca29`: `comctl32.dll`

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
0x18000ca08  sub     rsp, 28h
0x18000ca0c  cmp     cs:g_hinstCC, 0
0x18000ca14  jnz     short loc_18000CA48
0x18000ca16  call    SHFusionLoadLibrary
0x18000ca1b  mov     cs:g_hinstCC, rax
0x18000ca22  test    rax, rax
0x18000ca25  jnz     short loc_18000CA48
0x18000ca27  xor     edx, edx; hFile
0x18000ca29  lea     rcx, LibFileName; "comctl32.dll"
0x18000ca30  mov     r8d, 4000h; dwFlags
0x18000ca36  call    cs:__imp_LoadLibraryExW
0x18000ca3c  mov     cs:g_hinstCC, rax
0x18000ca43  test    rax, rax
0x18000ca46  jz      short loc_18000CA4D
0x18000ca48  mov     eax, 1
0x18000ca4d  add     rsp, 28h
0x18000ca51  retn
```
