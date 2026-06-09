# DllMain

- ea: `0x1800014fc`
- end: `0x18000151f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x1800014fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000150f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000150f`

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
0x1800014fc  sub     rsp, 28h
0x180001500  cmp     edx, 1
0x180001503  jnz     short loc_180001515
0x180001505  cmp     cs:qword_1800149B0, 0
0x18000150d  jnz     short loc_180001515
0x18000150f  call    cs:DisableThreadLibraryCalls
0x180001515  mov     eax, 1
0x18000151a  add     rsp, 28h
0x18000151e  retn
```
