# _DllMainCRTStartup

- ea: `0x18000c7b0`
- end: `0x18000c7ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c360`
- `0x18000c674`
- `0x18000c7b0`

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
0x18000c7b0  mov     [rsp+arg_0], rbx
0x18000c7b5  mov     [rsp+arg_8], rsi
0x18000c7ba  push    rdi
0x18000c7bb  sub     rsp, 20h
0x18000c7bf  mov     rdi, r8
0x18000c7c2  mov     ebx, edx
0x18000c7c4  mov     rsi, rcx
0x18000c7c7  cmp     edx, 1
0x18000c7ca  jnz     short loc_18000C7D1
0x18000c7cc  call    __security_init_cookie
0x18000c7d1  mov     r8, rdi; lpvReserved
0x18000c7d4  mov     edx, ebx; fdwReason
0x18000c7d6  mov     rcx, rsi; hinstDLL
0x18000c7d9  mov     rbx, [rsp+28h+arg_0]
0x18000c7de  mov     rsi, [rsp+28h+arg_8]
0x18000c7e3  add     rsp, 20h
0x18000c7e7  pop     rdi
0x18000c7e8  jmp     dllmain_dispatch
```
