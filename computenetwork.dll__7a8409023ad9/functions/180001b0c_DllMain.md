# DllMain

- ea: `0x180001b0c`
- end: `0x180001b2f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001474`

## callees

- `0x180001b0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001b1f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001b1f`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 && !pRawDllMain )
    DisableThreadLibraryCalls(hinstDLL);
  return 1;
}

```

## disassembly

```asm
0x180001b0c  sub     rsp, 28h
0x180001b10  cmp     edx, 1
0x180001b13  jnz     short loc_180001B25
0x180001b15  cmp     cs:_pRawDllMain, 0
0x180001b1d  jnz     short loc_180001B25
0x180001b1f  call    cs:__imp_DisableThreadLibraryCalls
0x180001b25  mov     eax, 1
0x180001b2a  add     rsp, 28h
0x180001b2e  retn
```
