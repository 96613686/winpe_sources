# DllMain

- ea: `0x180002bf8`
- end: `0x180002c11`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012d4`

## callees

- `0x180002bf8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002c01`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002c01`

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
0x180002bf8  sub     rsp, 28h
0x180002bfc  cmp     edx, 1
0x180002bff  jnz     short loc_180002C07
0x180002c01  call    cs:__imp_DisableThreadLibraryCalls
0x180002c07  mov     eax, 1
0x180002c0c  add     rsp, 28h
0x180002c10  retn
```
