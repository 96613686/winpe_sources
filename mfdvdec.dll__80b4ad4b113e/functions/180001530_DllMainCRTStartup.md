# _DllMainCRTStartup

- ea: `0x180001530`
- end: `0x18000156d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800013f4`
- `0x180001530`
- `0x1800015a4`

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
0x180001530  mov     [rsp+arg_0], rbx
0x180001535  mov     [rsp+arg_8], rsi
0x18000153a  push    rdi
0x18000153b  sub     rsp, 20h
0x18000153f  mov     rdi, r8
0x180001542  mov     ebx, edx
0x180001544  mov     rsi, rcx
0x180001547  cmp     edx, 1
0x18000154a  jnz     short loc_180001551
0x18000154c  call    __security_init_cookie
0x180001551  mov     r8, rdi; lpvReserved
0x180001554  mov     edx, ebx; fdwReason
0x180001556  mov     rcx, rsi; hinstDLL
0x180001559  mov     rbx, [rsp+28h+arg_0]
0x18000155e  mov     rsi, [rsp+28h+arg_8]
0x180001563  add     rsp, 20h
0x180001567  pop     rdi
0x180001568  jmp     dllmain_dispatch
```
