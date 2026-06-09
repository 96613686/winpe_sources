# DelayLoadCC

- ea: `0x180029c34`
- end: `0x180029c7e`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029890`
- `0x180029e64`

## callees

- `0x18002999c`
- `0x180029c34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029c62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029c62`

## string_xrefs

- `0x180029c55`: `comctl32.dll`

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
0x180029c34  sub     rsp, 28h
0x180029c38  cmp     cs:g_hinstCC, 0
0x180029c40  jnz     short loc_180029C74
0x180029c42  call    SHFusionLoadLibrary
0x180029c47  mov     cs:g_hinstCC, rax
0x180029c4e  test    rax, rax
0x180029c51  jnz     short loc_180029C74
0x180029c53  xor     edx, edx; hFile
0x180029c55  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180029c5c  mov     r8d, 4000h; dwFlags
0x180029c62  call    cs:__imp_LoadLibraryExW
0x180029c68  mov     cs:g_hinstCC, rax
0x180029c6f  test    rax, rax
0x180029c72  jz      short loc_180029C79
0x180029c74  mov     eax, 1
0x180029c79  add     rsp, 28h
0x180029c7d  retn
```
