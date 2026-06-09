# _DllMainCRTStartup

- ea: `0x1800015d0`
- end: `0x18000160d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800015d0`
- `0x180001614`
- `0x180001a04`

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
0x1800015d0  mov     [rsp+arg_0], rbx
0x1800015d5  mov     [rsp+arg_8], rsi
0x1800015da  push    rdi
0x1800015db  sub     rsp, 20h
0x1800015df  mov     rdi, r8
0x1800015e2  mov     ebx, edx
0x1800015e4  mov     rsi, rcx
0x1800015e7  cmp     edx, 1
0x1800015ea  jnz     short loc_1800015F1
0x1800015ec  call    __security_init_cookie
0x1800015f1  mov     r8, rdi
0x1800015f4  mov     edx, ebx; fdwReason
0x1800015f6  mov     rcx, rsi; hinstDLL
0x1800015f9  mov     rbx, [rsp+28h+arg_0]
0x1800015fe  mov     rsi, [rsp+28h+arg_8]
0x180001603  add     rsp, 20h
0x180001607  pop     rdi
0x180001608  jmp     __DllMainCRTStartup
```
