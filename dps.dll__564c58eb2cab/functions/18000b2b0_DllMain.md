# DllMain

- ea: `0x18000b2b0`
- end: `0x18000b2c9`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009e24`

## callees

- `0x18000b2b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b2b9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b2b9`

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
0x18000b2b0  sub     rsp, 28h
0x18000b2b4  cmp     edx, 1
0x18000b2b7  jnz     short loc_18000B2BF
0x18000b2b9  call    cs:__imp_DisableThreadLibraryCalls
0x18000b2bf  mov     eax, 1
0x18000b2c4  add     rsp, 28h
0x18000b2c8  retn
```
