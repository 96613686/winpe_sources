# _DllMainCRTStartup(x,x,x)

- ea: `0x1002e361`
- end: `0x1002e384`
- name: `__DllMainCRTStartup@12`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1002e361`
- `0x1002e384`
- `0x10034b0e`

## pseudocode

```c
BOOL __stdcall _DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    __security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1002e361  push    ebp
0x1002e362  mov     ebp, esp
0x1002e364  cmp     [ebp+fdwReason], 1
0x1002e368  jnz     short loc_1002E36F
0x1002e36a  call    ___security_init_cookie
0x1002e36f  push    [ebp+lpReserved]; lpvReserved
0x1002e372  push    [ebp+fdwReason]; fdwReason
0x1002e375  push    [ebp+hinstDLL]; hinstDLL
0x1002e378  call    __DllMainCRTStartup
0x1002e37d  add     esp, 0Ch
0x1002e380  pop     ebp
0x1002e381  retn    0Ch
```
