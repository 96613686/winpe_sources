# _DllMainCRTStartup

- ea: `0x180001350`
- end: `0x18000138d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001350`
- `0x180001394`
- `0x180001774`

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
0x180001350  mov     [rsp+arg_0], rbx
0x180001355  mov     [rsp+arg_8], rsi
0x18000135a  push    rdi
0x18000135b  sub     rsp, 20h
0x18000135f  mov     rdi, r8
0x180001362  mov     ebx, edx
0x180001364  mov     rsi, rcx
0x180001367  cmp     edx, 1
0x18000136a  jnz     short loc_180001371
0x18000136c  call    __security_init_cookie
0x180001371  mov     r8, rdi
0x180001374  mov     edx, ebx; fdwReason
0x180001376  mov     rcx, rsi; hinstDLL
0x180001379  mov     rbx, [rsp+28h+arg_0]
0x18000137e  mov     rsi, [rsp+28h+arg_8]
0x180001383  add     rsp, 20h
0x180001387  pop     rdi
0x180001388  jmp     __DllMainCRTStartup
```
