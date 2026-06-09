# DelayLoadCC

- ea: `0x180030c38`
- end: `0x180030c82`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800309a8`
- `0x180030e90`

## callees

- `0x180030ac0`
- `0x180030c38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030c66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030c66`

## string_xrefs

- `0x180030c59`: `comctl32.dll`

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
0x180030c38  sub     rsp, 28h
0x180030c3c  cmp     cs:g_hinstCC, 0
0x180030c44  jnz     short loc_180030C78
0x180030c46  call    SHFusionLoadLibrary
0x180030c4b  mov     cs:g_hinstCC, rax
0x180030c52  test    rax, rax
0x180030c55  jnz     short loc_180030C78
0x180030c57  xor     edx, edx; hFile
0x180030c59  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x180030c60  mov     r8d, 4000h; dwFlags
0x180030c66  call    cs:__imp_LoadLibraryExW
0x180030c6c  mov     cs:g_hinstCC, rax
0x180030c73  test    rax, rax
0x180030c76  jz      short loc_180030C7D
0x180030c78  mov     eax, 1
0x180030c7d  add     rsp, 28h
0x180030c81  retn
```
