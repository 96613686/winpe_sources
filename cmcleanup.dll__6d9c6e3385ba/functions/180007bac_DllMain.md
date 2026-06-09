# DllMain

- ea: `0x180007bac`
- end: `0x180007bc5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001384`

## callees

- `0x180007bac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007bb5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007bb5`

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
0x180007bac  sub     rsp, 28h
0x180007bb0  cmp     edx, 1
0x180007bb3  jnz     short loc_180007BBB
0x180007bb5  call    cs:__imp_DisableThreadLibraryCalls
0x180007bbb  mov     eax, 1
0x180007bc0  add     rsp, 28h
0x180007bc4  retn
```
