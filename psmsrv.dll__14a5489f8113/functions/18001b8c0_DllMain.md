# DllMain

- ea: `0x18001b8c0`
- end: `0x18001b8e3`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b654`

## callees

- `0x18001b8c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001b8d3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001b8d3`

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
0x18001b8c0  sub     rsp, 28h
0x18001b8c4  cmp     edx, 1
0x18001b8c7  jnz     short loc_18001B8D9
0x18001b8c9  cmp     cs:_pRawDllMain, 0
0x18001b8d1  jnz     short loc_18001B8D9
0x18001b8d3  call    cs:__imp_DisableThreadLibraryCalls
0x18001b8d9  mov     eax, 1
0x18001b8de  add     rsp, 28h
0x18001b8e2  retn
```
