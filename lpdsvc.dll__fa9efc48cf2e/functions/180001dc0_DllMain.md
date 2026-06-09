# DllMain

- ea: `0x180001dc0`
- end: `0x180001de3`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b54`

## callees

- `0x180001dc0`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180001dd3`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180001dd3`

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
0x180001dc0  sub     rsp, 28h
0x180001dc4  cmp     edx, 1
0x180001dc7  jnz     short loc_180001DD9
0x180001dc9  cmp     cs:_pRawDllMain, 0
0x180001dd1  jnz     short loc_180001DD9
0x180001dd3  call    cs:__imp_DisableThreadLibraryCalls
0x180001dd9  mov     eax, 1
0x180001dde  add     rsp, 28h
0x180001de2  retn
```
