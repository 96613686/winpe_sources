# DllMain

- ea: `0x180002df0`
- end: `0x180002e13`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002304`

## callees

- `0x180002df0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002e03`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002e03`

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
0x180002df0  sub     rsp, 28h
0x180002df4  cmp     edx, 1
0x180002df7  jnz     short loc_180002E09
0x180002df9  cmp     cs:_pRawDllMain, 0
0x180002e01  jnz     short loc_180002E09
0x180002e03  call    cs:__imp_DisableThreadLibraryCalls
0x180002e09  mov     eax, 1
0x180002e0e  add     rsp, 28h
0x180002e12  retn
```
