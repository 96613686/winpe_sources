# DllMain

- ea: `0x1800022fc`
- end: `0x180002315`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001384`

## callees

- `0x1800022fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002305`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002305`

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
0x1800022fc  sub     rsp, 28h
0x180002300  cmp     edx, 1
0x180002303  jnz     short loc_18000230B
0x180002305  call    cs:__imp_DisableThreadLibraryCalls
0x18000230b  mov     eax, 1
0x180002310  add     rsp, 28h
0x180002314  retn
```
