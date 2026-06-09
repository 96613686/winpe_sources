# DllMain

- ea: `0x180012fdc`
- end: `0x180012ffc`
- name: `DllMain`
- size: `32`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014c34`

## callees

- `0x180012fdc`
- `0x180013004`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012fef`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012fef`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    ReadCompressionSettingsFromRegistry();
  }
  return 1;
}

```

## disassembly

```asm
0x180012fdc  sub     rsp, 28h
0x180012fe0  cmp     edx, 1
0x180012fe3  jz      short loc_180012FEF
0x180012fe5  mov     eax, 1
0x180012fea  add     rsp, 28h
0x180012fee  retn
0x180012fef  call    cs:__imp_DisableThreadLibraryCalls
0x180012ff5  call    ReadCompressionSettingsFromRegistry
0x180012ffa  jmp     short loc_180012FE5
```
