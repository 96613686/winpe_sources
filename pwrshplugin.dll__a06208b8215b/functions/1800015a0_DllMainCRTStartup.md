# _DllMainCRTStartup

- ea: `0x1800015a0`
- end: `0x1800015dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800015a0`
- `0x1800015e4`
- `0x180001f24`

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
0x1800015a0  mov     [rsp+arg_0], rbx
0x1800015a5  mov     [rsp+arg_8], rsi
0x1800015aa  push    rdi
0x1800015ab  sub     rsp, 20h
0x1800015af  mov     rdi, r8
0x1800015b2  mov     ebx, edx
0x1800015b4  mov     rsi, rcx
0x1800015b7  cmp     edx, 1
0x1800015ba  jnz     short loc_1800015C1
0x1800015bc  call    __security_init_cookie
0x1800015c1  mov     r8, rdi
0x1800015c4  mov     edx, ebx; fdwReason
0x1800015c6  mov     rcx, rsi; hinstDLL
0x1800015c9  mov     rbx, [rsp+28h+arg_0]
0x1800015ce  mov     rsi, [rsp+28h+arg_8]
0x1800015d3  add     rsp, 20h
0x1800015d7  pop     rdi
0x1800015d8  jmp     __DllMainCRTStartup
```
