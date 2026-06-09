# _DllMainCRTStartup

- ea: `0x180002660`
- end: `0x18000269d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002528`
- `0x180002660`
- `0x180002b58`

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
0x180002660  mov     [rsp+arg_0], rbx
0x180002665  mov     [rsp+arg_8], rsi
0x18000266a  push    rdi
0x18000266b  sub     rsp, 20h
0x18000266f  mov     rdi, r8
0x180002672  mov     ebx, edx
0x180002674  mov     rsi, rcx
0x180002677  cmp     edx, 1
0x18000267a  jnz     short loc_180002681
0x18000267c  call    __security_init_cookie
0x180002681  mov     r8, rdi; lpvReserved
0x180002684  mov     edx, ebx; fdwReason
0x180002686  mov     rcx, rsi; hinstDLL
0x180002689  mov     rbx, [rsp+28h+arg_0]
0x18000268e  mov     rsi, [rsp+28h+arg_8]
0x180002693  add     rsp, 20h
0x180002697  pop     rdi
0x180002698  jmp     dllmain_dispatch
```
