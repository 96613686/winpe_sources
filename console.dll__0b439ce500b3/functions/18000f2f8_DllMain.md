# DllMain

- ea: `0x18000f2f8`
- end: `0x18000f31f`
- name: `DllMain`
- size: `39`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001424`

## callees

- `0x18000f2f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f308`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f308`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    ghInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18000f2f8  sub     rsp, 28h
0x18000f2fc  cmp     edx, 1
0x18000f2ff  jnz     short loc_18000F314
0x18000f301  mov     cs:?ghInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * ghInstance
0x18000f308  call    cs:__imp_DisableThreadLibraryCalls
0x18000f30f  nop     dword ptr [rax+rax+00h]
0x18000f314  mov     eax, 1
0x18000f319  add     rsp, 28h
0x18000f31d  retn
```
