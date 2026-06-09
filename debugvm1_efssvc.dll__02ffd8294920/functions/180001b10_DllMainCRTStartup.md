# _DllMainCRTStartup

- ea: `0x180001b10`
- end: `0x180001b4d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b10`
- `0x180001b54`
- `0x180001e84`

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
0x180001b10  mov     [rsp+arg_0], rbx
0x180001b15  mov     [rsp+arg_8], rsi
0x180001b1a  push    rdi
0x180001b1b  sub     rsp, 20h
0x180001b1f  mov     rdi, r8
0x180001b22  mov     ebx, edx
0x180001b24  mov     rsi, rcx
0x180001b27  cmp     edx, 1
0x180001b2a  jnz     short loc_180001B31
0x180001b2c  call    __security_init_cookie
0x180001b31  mov     r8, rdi
0x180001b34  mov     edx, ebx; fdwReason
0x180001b36  mov     rcx, rsi; hinstDLL
0x180001b39  mov     rbx, [rsp+28h+arg_0]
0x180001b3e  mov     rsi, [rsp+28h+arg_8]
0x180001b43  add     rsp, 20h
0x180001b47  pop     rdi
0x180001b48  jmp     __DllMainCRTStartup
```
