# _DllMainCRTStartup(x,x,x)

- ea: `0x10012b20`
- end: `0x10012b45`
- name: `__DllMainCRTStartup@12`
- size: `37`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x100129d8`
- `0x10012b20`
- `0x10012bb9`

## pseudocode

```c
BOOL __stdcall _DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    __security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x10012b20  mov     edi, edi
0x10012b22  push    ebp
0x10012b23  mov     ebp, esp
0x10012b25  cmp     [ebp+fdwReason], 1
0x10012b29  jnz     short loc_10012B30
0x10012b2b  call    ___security_init_cookie
0x10012b30  push    [ebp+lpReserved]; lpvReserved
0x10012b33  push    [ebp+fdwReason]; fdwReason
0x10012b36  push    [ebp+hinstDLL]; hinstDLL
0x10012b39  call    dllmain_dispatch
0x10012b3e  add     esp, 0Ch
0x10012b41  pop     ebp
0x10012b42  retn    0Ch
```
