# _DllMainCRTStartup

- ea: `0x180002320`
- end: `0x18000235d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002320`
- `0x180002364`
- `0x18000267c`

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
0x180002320  mov     [rsp+arg_0], rbx
0x180002325  mov     [rsp+arg_8], rsi
0x18000232a  push    rdi
0x18000232b  sub     rsp, 20h
0x18000232f  mov     rdi, r8
0x180002332  mov     ebx, edx
0x180002334  mov     rsi, rcx
0x180002337  cmp     edx, 1
0x18000233a  jnz     short loc_180002341
0x18000233c  call    __security_init_cookie
0x180002341  mov     r8, rdi
0x180002344  mov     edx, ebx; fdwReason
0x180002346  mov     rcx, rsi; hinstDLL
0x180002349  mov     rbx, [rsp+28h+arg_0]
0x18000234e  mov     rsi, [rsp+28h+arg_8]
0x180002353  add     rsp, 20h
0x180002357  pop     rdi
0x180002358  jmp     __DllMainCRTStartup
```
