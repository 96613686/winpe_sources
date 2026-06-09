# _DllMainCRTStartup

- ea: `0x18000e2a0`
- end: `0x18000e2dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000e164`
- `0x18000e2a0`
- `0x18000e314`

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
0x18000e2a0  mov     [rsp+arg_0], rbx
0x18000e2a5  mov     [rsp+arg_8], rsi
0x18000e2aa  push    rdi
0x18000e2ab  sub     rsp, 20h
0x18000e2af  mov     rdi, r8
0x18000e2b2  mov     ebx, edx
0x18000e2b4  mov     rsi, rcx
0x18000e2b7  cmp     edx, 1
0x18000e2ba  jnz     short loc_18000E2C1
0x18000e2bc  call    __security_init_cookie
0x18000e2c1  mov     r8, rdi; lpvReserved
0x18000e2c4  mov     edx, ebx; fdwReason
0x18000e2c6  mov     rcx, rsi; hinstDLL
0x18000e2c9  mov     rbx, [rsp+28h+arg_0]
0x18000e2ce  mov     rsi, [rsp+28h+arg_8]
0x18000e2d3  add     rsp, 20h
0x18000e2d7  pop     rdi
0x18000e2d8  jmp     dllmain_dispatch
```
