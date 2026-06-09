# DllMain

- ea: `0x180001fcc`
- end: `0x180001fe5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001324`

## callees

- `0x180001fcc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001fd5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001fd5`

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
0x180001fcc  sub     rsp, 28h
0x180001fd0  cmp     edx, 1
0x180001fd3  jnz     short loc_180001FDB
0x180001fd5  call    cs:__imp_DisableThreadLibraryCalls
0x180001fdb  mov     eax, 1
0x180001fe0  add     rsp, 28h
0x180001fe4  retn
```
