# DelayLoadCC

- ea: `0x180012894`
- end: `0x1800128de`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800125d4`
- `0x1800128e4`

## callees

- `0x1800126e0`
- `0x180012894`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800128c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800128c2`

## string_xrefs

- `0x1800128b5`: `comctl32.dll`

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
0x180012894  sub     rsp, 28h
0x180012898  cmp     cs:g_hinstCC, 0
0x1800128a0  jnz     short loc_1800128D4
0x1800128a2  call    SHFusionLoadLibrary
0x1800128a7  mov     cs:g_hinstCC, rax
0x1800128ae  test    rax, rax
0x1800128b1  jnz     short loc_1800128D4
0x1800128b3  xor     edx, edx; hFile
0x1800128b5  lea     rcx, aComctl32Dll; "comctl32.dll"
0x1800128bc  mov     r8d, 4000h; dwFlags
0x1800128c2  call    cs:__imp_LoadLibraryExW
0x1800128c8  mov     cs:g_hinstCC, rax
0x1800128cf  test    rax, rax
0x1800128d2  jz      short loc_1800128D9
0x1800128d4  mov     eax, 1
0x1800128d9  add     rsp, 28h
0x1800128dd  retn
```
