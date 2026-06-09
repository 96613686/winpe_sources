# DllMain(x,x,x)

- ea: `0x10009841`
- end: `0x10009863`
- name: `_DllMain@12`
- size: `34`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100129d8`

## callees

- `0x10009841`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x10009856`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x10009856`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    ghModule = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x10009841  mov     edi, edi
0x10009843  push    ebp
0x10009844  mov     ebp, esp
0x10009846  cmp     [ebp+fdwReason], 1
0x1000984a  jnz     short loc_1000985C
0x1000984c  mov     ecx, [ebp+hinstDLL]
0x1000984f  push    ecx; hLibModule
0x10009850  mov     _ghModule, ecx
0x10009856  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x1000985c  xor     eax, eax
0x1000985e  inc     eax
0x1000985f  pop     ebp
0x10009860  retn    0Ch
```
