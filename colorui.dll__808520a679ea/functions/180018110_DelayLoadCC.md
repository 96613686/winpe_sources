# DelayLoadCC

- ea: `0x180018110`
- end: `0x180018161`
- name: `DelayLoadCC`
- size: `81`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca3c`
- `0x18000d338`
- `0x180017cd8`
- `0x1800183e4`

## callees

- `0x180017df0`
- `0x180018110`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180018145`
- `KERNEL32!LoadLibraryExW` at `0x180018145`

## string_xrefs

- `0x18001811e`: `comctl32.dll`
- `0x180018138`: `comctl32.dll`

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
0x180018110  sub     rsp, 28h
0x180018114  cmp     cs:g_hinstCC, 0
0x18001811c  jnz     short loc_180018157
0x18001811e  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180018125  call    SHFusionLoadLibrary
0x18001812a  mov     cs:g_hinstCC, rax
0x180018131  test    rax, rax
0x180018134  jnz     short loc_180018157
0x180018136  xor     edx, edx; hFile
0x180018138  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18001813f  mov     r8d, 4000h; dwFlags
0x180018145  call    cs:__imp_LoadLibraryExW
0x18001814b  mov     cs:g_hinstCC, rax
0x180018152  test    rax, rax
0x180018155  jz      short loc_18001815C
0x180018157  mov     eax, 1
0x18001815c  add     rsp, 28h
0x180018160  retn
```
