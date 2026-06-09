# DllMain

- ea: `0x18001cf04`
- end: `0x18001cf24`
- name: `DllMain`
- size: `32`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bcb4`

## callees

- `0x18001cf04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001cf14`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001cf14`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    g_hInst = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18001cf04  sub     rsp, 28h
0x18001cf08  cmp     edx, 1
0x18001cf0b  jnz     short loc_18001CF1A
0x18001cf0d  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x18001cf14  call    cs:__imp_DisableThreadLibraryCalls
0x18001cf1a  mov     eax, 1
0x18001cf1f  add     rsp, 28h
0x18001cf23  retn
```
