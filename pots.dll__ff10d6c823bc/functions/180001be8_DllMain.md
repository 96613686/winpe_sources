# DllMain

- ea: `0x180001be8`
- end: `0x180001c01`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800014a4`

## callees

- `0x180001be8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001bf1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001bf1`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    DisableThreadLibraryCalls(hinstDLL);
  return 1;
}

```

## disassembly

```asm
0x180001be8  sub     rsp, 28h
0x180001bec  cmp     edx, 1
0x180001bef  jnz     short loc_180001BF7
0x180001bf1  call    cs:__imp_DisableThreadLibraryCalls
0x180001bf7  mov     eax, 1
0x180001bfc  add     rsp, 28h
0x180001c00  retn
```
