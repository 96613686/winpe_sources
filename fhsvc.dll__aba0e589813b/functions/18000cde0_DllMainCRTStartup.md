# _DllMainCRTStartup

- ea: `0x18000cde0`
- end: `0x18000ce1d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cde0`
- `0x18000ce24`
- `0x18000d364`

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
0x18000cde0  mov     [rsp+arg_0], rbx
0x18000cde5  mov     [rsp+arg_8], rsi
0x18000cdea  push    rdi
0x18000cdeb  sub     rsp, 20h
0x18000cdef  mov     rdi, r8
0x18000cdf2  mov     ebx, edx
0x18000cdf4  mov     rsi, rcx
0x18000cdf7  cmp     edx, 1
0x18000cdfa  jnz     short loc_18000CE01
0x18000cdfc  call    __security_init_cookie
0x18000ce01  mov     r8, rdi
0x18000ce04  mov     edx, ebx; fdwReason
0x18000ce06  mov     rcx, rsi; hinstDLL
0x18000ce09  mov     rbx, [rsp+28h+arg_0]
0x18000ce0e  mov     rsi, [rsp+28h+arg_8]
0x18000ce13  add     rsp, 20h
0x18000ce17  pop     rdi
0x18000ce18  jmp     __DllMainCRTStartup
```
