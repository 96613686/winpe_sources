# _DllMainCRTStartup(x,x,x)

- ea: `0x1004d100`
- end: `0x1004d116`
- name: `__DllMainCRTStartup@12`
- size: `22`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1004d100`
- `0x1004d142`
- `0x1004dad9`

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
0x1004d100  mov     edi, edi
0x1004d102  push    ebp
0x1004d103  mov     ebp, esp
0x1004d105  cmp     [ebp+fdwReason], 1
0x1004d109  jnz     short loc_1004D110
0x1004d10b  call    ___security_init_cookie
0x1004d110  pop     ebp
0x1004d111  jmp     __DllMainCRTStartup
```
