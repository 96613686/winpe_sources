# _DllMainCRTStartup

- ea: `0x18000aae0`
- end: `0x18000ab1d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a9a4`
- `0x18000aae0`
- `0x18000af00`

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
0x18000aae0  mov     [rsp+arg_0], rbx
0x18000aae5  mov     [rsp+arg_8], rsi
0x18000aaea  push    rdi
0x18000aaeb  sub     rsp, 20h
0x18000aaef  mov     rdi, r8
0x18000aaf2  mov     ebx, edx
0x18000aaf4  mov     rsi, rcx
0x18000aaf7  cmp     edx, 1
0x18000aafa  jnz     short loc_18000AB01
0x18000aafc  call    __security_init_cookie
0x18000ab01  mov     r8, rdi; lpvReserved
0x18000ab04  mov     edx, ebx; fdwReason
0x18000ab06  mov     rcx, rsi; hinstDLL
0x18000ab09  mov     rbx, [rsp+28h+arg_0]
0x18000ab0e  mov     rsi, [rsp+28h+arg_8]
0x18000ab13  add     rsp, 20h
0x18000ab17  pop     rdi
0x18000ab18  jmp     dllmain_dispatch
```
