# DllMain

- ea: `0x180001ed4`
- end: `0x180001ef7`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001584`

## callees

- `0x180001ed4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!DisableThreadLibraryCalls` at `0x180001ee7`
- `api-ms-win-core-libraryloader-l1-1-0!DisableThreadLibraryCalls` at `0x180001ee7`

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
0x180001ed4  sub     rsp, 28h
0x180001ed8  cmp     edx, 1
0x180001edb  jnz     short loc_180001EED
0x180001edd  cmp     cs:_pRawDllMain, 0
0x180001ee5  jnz     short loc_180001EED
0x180001ee7  call    cs:__imp_DisableThreadLibraryCalls
0x180001eed  mov     eax, 1
0x180001ef2  add     rsp, 28h
0x180001ef6  retn
```
