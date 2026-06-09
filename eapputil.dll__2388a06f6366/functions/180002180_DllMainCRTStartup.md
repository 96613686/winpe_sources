# _DllMainCRTStartup

- ea: `0x180002180`
- end: `0x1800021bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002044`
- `0x180002180`
- `0x1800025dc`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180002180  mov     [rsp+arg_0], rbx
0x180002185  mov     [rsp+arg_8], rsi
0x18000218a  push    rdi
0x18000218b  sub     rsp, 20h
0x18000218f  mov     rdi, r8
0x180002192  mov     ebx, edx
0x180002194  mov     rsi, rcx
0x180002197  cmp     edx, 1
0x18000219a  jnz     short loc_1800021A1
0x18000219c  call    __security_init_cookie
0x1800021a1  mov     r8, rdi; lpvReserved
0x1800021a4  mov     edx, ebx; fdwReason
0x1800021a6  mov     rcx, rsi; hinstDLL
0x1800021a9  mov     rbx, [rsp+28h+arg_0]
0x1800021ae  mov     rsi, [rsp+28h+arg_8]
0x1800021b3  add     rsp, 20h
0x1800021b7  pop     rdi
0x1800021b8  jmp     dllmain_dispatch
```
