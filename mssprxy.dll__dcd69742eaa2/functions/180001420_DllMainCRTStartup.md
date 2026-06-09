# _DllMainCRTStartup

- ea: `0x180001420`
- end: `0x18000145d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800012e4`
- `0x180001420`
- `0x180001494`

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
0x180001420  mov     [rsp+arg_0], rbx
0x180001425  mov     [rsp+arg_8], rsi
0x18000142a  push    rdi
0x18000142b  sub     rsp, 20h
0x18000142f  mov     rdi, r8
0x180001432  mov     ebx, edx
0x180001434  mov     rsi, rcx
0x180001437  cmp     edx, 1
0x18000143a  jnz     short loc_180001441
0x18000143c  call    __security_init_cookie
0x180001441  mov     r8, rdi; lpvReserved
0x180001444  mov     edx, ebx; fdwReason
0x180001446  mov     rcx, rsi; hinstDLL
0x180001449  mov     rbx, [rsp+28h+arg_0]
0x18000144e  mov     rsi, [rsp+28h+arg_8]
0x180001453  add     rsp, 20h
0x180001457  pop     rdi
0x180001458  jmp     dllmain_dispatch
```
