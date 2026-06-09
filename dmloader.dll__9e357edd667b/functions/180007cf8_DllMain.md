# DllMain

- ea: `0x180007cf8`
- end: `0x180007d2b`
- name: `DllMain`
- size: `51`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001444`

## callees

- `0x180007cf8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007d1b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007d1b`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 && ++dword_1800154E0 == 1 )
  {
    g_hModule = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x180007cf8  sub     rsp, 28h
0x180007cfc  cmp     edx, 1
0x180007cff  jnz     short loc_180007D21
0x180007d01  mov     edx, cs:dword_1800154E0
0x180007d07  inc     edx
0x180007d09  mov     cs:dword_1800154E0, edx
0x180007d0f  cmp     edx, 1
0x180007d12  jnz     short loc_180007D21
0x180007d14  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hModule
0x180007d1b  call    cs:__imp_DisableThreadLibraryCalls
0x180007d21  mov     eax, 1
0x180007d26  add     rsp, 28h
0x180007d2a  retn
```
