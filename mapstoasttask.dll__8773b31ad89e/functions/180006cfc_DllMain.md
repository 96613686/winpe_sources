# DllMain

- ea: `0x180006cfc`
- end: `0x180006d15`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001424`

## callees

- `0x180006cfc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006d05`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006d05`

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
0x180006cfc  sub     rsp, 28h
0x180006d00  cmp     edx, 1
0x180006d03  jnz     short loc_180006D0B
0x180006d05  call    cs:__imp_DisableThreadLibraryCalls
0x180006d0b  mov     eax, 1
0x180006d10  add     rsp, 28h
0x180006d14  retn
```
