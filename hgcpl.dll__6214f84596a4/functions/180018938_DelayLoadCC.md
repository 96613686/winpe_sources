# DelayLoadCC

- ea: `0x180018938`
- end: `0x180018982`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800187c8`

## callees

- `0x1800188e0`
- `0x180018938`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018966`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018966`

## string_xrefs

- `0x180018959`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (__int64)SHFusionLoadLibrary();
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  g_hinstCC = result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180018938  sub     rsp, 28h
0x18001893c  cmp     cs:g_hinstCC, 0
0x180018944  jnz     short loc_180018978
0x180018946  call    SHFusionLoadLibrary
0x18001894b  mov     cs:g_hinstCC, rax
0x180018952  test    rax, rax
0x180018955  jnz     short loc_180018978
0x180018957  xor     edx, edx; hFile
0x180018959  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x180018960  mov     r8d, 4000h; dwFlags
0x180018966  call    cs:__imp_LoadLibraryExW
0x18001896c  mov     cs:g_hinstCC, rax
0x180018973  test    rax, rax
0x180018976  jz      short loc_18001897D
0x180018978  mov     eax, 1
0x18001897d  add     rsp, 28h
0x180018981  retn
```
