# _DllMainCRTStartup

- ea: `0x1800076f0`
- end: `0x18000772d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800075b4`
- `0x1800076f0`
- `0x180007764`

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
0x1800076f0  mov     [rsp+arg_0], rbx
0x1800076f5  mov     [rsp+arg_8], rsi
0x1800076fa  push    rdi
0x1800076fb  sub     rsp, 20h
0x1800076ff  mov     rdi, r8
0x180007702  mov     ebx, edx
0x180007704  mov     rsi, rcx
0x180007707  cmp     edx, 1
0x18000770a  jnz     short loc_180007711
0x18000770c  call    __security_init_cookie
0x180007711  mov     r8, rdi; lpvReserved
0x180007714  mov     edx, ebx; fdwReason
0x180007716  mov     rcx, rsi; hinstDLL
0x180007719  mov     rbx, [rsp+28h+arg_0]
0x18000771e  mov     rsi, [rsp+28h+arg_8]
0x180007723  add     rsp, 20h
0x180007727  pop     rdi
0x180007728  jmp     dllmain_dispatch
```
