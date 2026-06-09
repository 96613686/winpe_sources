# _DllMainCRTStartup

- ea: `0x18001b6d0`
- end: `0x18001b70d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b6d0`
- `0x18001b714`
- `0x18001bd34`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18001b6d0  mov     [rsp+arg_0], rbx
0x18001b6d5  mov     [rsp+arg_8], rsi
0x18001b6da  push    rdi
0x18001b6db  sub     rsp, 20h
0x18001b6df  mov     rdi, r8
0x18001b6e2  mov     ebx, edx
0x18001b6e4  mov     rsi, rcx
0x18001b6e7  cmp     edx, 1
0x18001b6ea  jnz     short loc_18001B6F1
0x18001b6ec  call    __security_init_cookie
0x18001b6f1  mov     r8, rdi
0x18001b6f4  mov     edx, ebx; fdwReason
0x18001b6f6  mov     rcx, rsi; hinstDLL
0x18001b6f9  mov     rbx, [rsp+28h+arg_0]
0x18001b6fe  mov     rsi, [rsp+28h+arg_8]
0x18001b703  add     rsp, 20h
0x18001b707  pop     rdi
0x18001b708  jmp     __DllMainCRTStartup
```
