# _DllMainCRTStartup

- ea: `0x180001950`
- end: `0x18000198d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001950`
- `0x180001994`
- `0x180001ec4`

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
0x180001950  mov     [rsp+arg_0], rbx
0x180001955  mov     [rsp+arg_8], rsi
0x18000195a  push    rdi
0x18000195b  sub     rsp, 20h
0x18000195f  mov     rdi, r8
0x180001962  mov     ebx, edx
0x180001964  mov     rsi, rcx
0x180001967  cmp     edx, 1
0x18000196a  jnz     short loc_180001971
0x18000196c  call    __security_init_cookie
0x180001971  mov     r8, rdi
0x180001974  mov     edx, ebx; fdwReason
0x180001976  mov     rcx, rsi; hinstDLL
0x180001979  mov     rbx, [rsp+28h+arg_0]
0x18000197e  mov     rsi, [rsp+28h+arg_8]
0x180001983  add     rsp, 20h
0x180001987  pop     rdi
0x180001988  jmp     __DllMainCRTStartup
```
