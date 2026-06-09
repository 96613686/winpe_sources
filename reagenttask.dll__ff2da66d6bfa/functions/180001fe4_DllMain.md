# DllMain

- ea: `0x180001fe4`
- end: `0x180002004`
- name: `DllMain`
- size: `32`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001324`

## callees

- `0x180001fe4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001fed`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001fed`

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
0x180001fe4  sub     rsp, 28h
0x180001fe8  cmp     edx, 1
0x180001feb  jnz     short loc_180001FF9
0x180001fed  call    cs:__imp_DisableThreadLibraryCalls
0x180001ff4  nop     dword ptr [rax+rax+00h]
0x180001ff9  mov     eax, 1
0x180001ffe  add     rsp, 28h
0x180002002  retn
```
