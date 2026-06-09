# _DllMainCRTStartup

- ea: `0x1800012e0`
- end: `0x18000131d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800012e0`
- `0x180001324`
- `0x180001674`

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
0x1800012e0  mov     [rsp+arg_0], rbx
0x1800012e5  mov     [rsp+arg_8], rsi
0x1800012ea  push    rdi
0x1800012eb  sub     rsp, 20h
0x1800012ef  mov     rdi, r8
0x1800012f2  mov     ebx, edx
0x1800012f4  mov     rsi, rcx
0x1800012f7  cmp     edx, 1
0x1800012fa  jnz     short loc_180001301
0x1800012fc  call    __security_init_cookie
0x180001301  mov     r8, rdi
0x180001304  mov     edx, ebx; fdwReason
0x180001306  mov     rcx, rsi; hinstDLL
0x180001309  mov     rbx, [rsp+28h+arg_0]
0x18000130e  mov     rsi, [rsp+28h+arg_8]
0x180001313  add     rsp, 20h
0x180001317  pop     rdi
0x180001318  jmp     __DllMainCRTStartup
```
