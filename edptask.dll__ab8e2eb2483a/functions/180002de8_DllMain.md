# DllMain

- ea: `0x180002de8`
- end: `0x180002e01`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001944`

## callees

- `0x180002de8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002df1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002df1`

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
0x180002de8  sub     rsp, 28h
0x180002dec  cmp     edx, 1
0x180002def  jnz     short loc_180002DF7
0x180002df1  call    cs:__imp_DisableThreadLibraryCalls
0x180002df7  mov     eax, 1
0x180002dfc  add     rsp, 28h
0x180002e00  retn
```
