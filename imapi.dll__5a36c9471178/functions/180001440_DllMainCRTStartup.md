# _DllMainCRTStartup

- ea: `0x180001440`
- end: `0x18000147d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001440`
- `0x180001484`
- `0x180001d44`

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
0x180001440  mov     [rsp+arg_0], rbx
0x180001445  mov     [rsp+arg_8], rsi
0x18000144a  push    rdi
0x18000144b  sub     rsp, 20h
0x18000144f  mov     rdi, r8
0x180001452  mov     ebx, edx
0x180001454  mov     rsi, rcx
0x180001457  cmp     edx, 1
0x18000145a  jnz     short loc_180001461
0x18000145c  call    __security_init_cookie
0x180001461  mov     r8, rdi
0x180001464  mov     edx, ebx; fdwReason
0x180001466  mov     rcx, rsi; hinstDLL
0x180001469  mov     rbx, [rsp+28h+arg_0]
0x18000146e  mov     rsi, [rsp+28h+arg_8]
0x180001473  add     rsp, 20h
0x180001477  pop     rdi
0x180001478  jmp     __DllMainCRTStartup
```
