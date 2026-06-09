# _DllMainCRTStartup

- ea: `0x180001340`
- end: `0x18000137d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001340`
- `0x180001384`
- `0x180001954`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup((__int64)hinstDLL, fdwReason, (__int64)lpReserved);
}

```

## disassembly

```asm
0x180001340  mov     [rsp+arg_0], rbx
0x180001345  mov     [rsp+arg_8], rsi
0x18000134a  push    rdi
0x18000134b  sub     rsp, 20h
0x18000134f  mov     rdi, r8
0x180001352  mov     ebx, edx
0x180001354  mov     rsi, rcx
0x180001357  cmp     edx, 1
0x18000135a  jnz     short loc_180001361
0x18000135c  call    __security_init_cookie
0x180001361  mov     r8, rdi
0x180001364  mov     edx, ebx
0x180001366  mov     rcx, rsi
0x180001369  mov     rbx, [rsp+28h+arg_0]
0x18000136e  mov     rsi, [rsp+28h+arg_8]
0x180001373  add     rsp, 20h
0x180001377  pop     rdi
0x180001378  jmp     __DllMainCRTStartup
```
