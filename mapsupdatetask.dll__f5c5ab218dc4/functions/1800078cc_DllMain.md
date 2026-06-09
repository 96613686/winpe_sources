# DllMain

- ea: `0x1800078cc`
- end: `0x1800078e5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a54`

## callees

- `0x1800078cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800078d5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800078d5`

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
0x1800078cc  sub     rsp, 28h
0x1800078d0  cmp     edx, 1
0x1800078d3  jnz     short loc_1800078DB
0x1800078d5  call    cs:__imp_DisableThreadLibraryCalls
0x1800078db  mov     eax, 1
0x1800078e0  add     rsp, 28h
0x1800078e4  retn
```
