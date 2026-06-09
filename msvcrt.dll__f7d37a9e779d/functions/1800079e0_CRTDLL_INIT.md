# _CRTDLL_INIT

- ea: `0x1800079e0`
- end: `0x180007a1d`
- name: `_CRTDLL_INIT`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800079e0`
- `0x180007a24`
- `0x180033ba0`

## pseudocode

```c
BOOL __stdcall CRTDLL_INIT(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _CRTDLL_INIT((__int64)hinstDLL, fdwReason, (__int64)lpReserved);
}

```

## disassembly

```asm
0x1800079e0  mov     [rsp+arg_0], rbx
0x1800079e5  mov     [rsp+arg_8], rsi
0x1800079ea  push    rdi
0x1800079eb  sub     rsp, 20h
0x1800079ef  mov     rdi, r8
0x1800079f2  mov     ebx, edx
0x1800079f4  mov     rsi, rcx
0x1800079f7  cmp     edx, 1
0x1800079fa  jnz     short loc_180007A01
0x1800079fc  call    __security_init_cookie
0x180007a01  mov     r8, rdi
0x180007a04  mov     edx, ebx
0x180007a06  mov     rcx, rsi
0x180007a09  mov     rbx, [rsp+28h+arg_0]
0x180007a0e  mov     rsi, [rsp+28h+arg_8]
0x180007a13  add     rsp, 20h
0x180007a17  pop     rdi
0x180007a18  jmp     __CRTDLL_INIT
```
