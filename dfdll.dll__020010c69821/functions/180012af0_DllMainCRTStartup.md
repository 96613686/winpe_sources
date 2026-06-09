# _DllMainCRTStartup

- ea: `0x180012af0`
- end: `0x180012b2d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800129bc`
- `0x180012af0`
- `0x180013010`

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
0x180012af0  mov     [rsp+arg_0], rbx
0x180012af5  mov     [rsp+arg_8], rsi
0x180012afa  push    rdi
0x180012afb  sub     rsp, 20h
0x180012aff  mov     rdi, r8
0x180012b02  mov     ebx, edx
0x180012b04  mov     rsi, rcx
0x180012b07  cmp     edx, 1
0x180012b0a  jnz     short loc_180012B11
0x180012b0c  call    __security_init_cookie
0x180012b11  mov     r8, rdi; lpvReserved
0x180012b14  mov     edx, ebx; fdwReason
0x180012b16  mov     rcx, rsi; hinstDLL
0x180012b19  mov     rbx, [rsp+28h+arg_0]
0x180012b1e  mov     rsi, [rsp+28h+arg_8]
0x180012b23  add     rsp, 20h
0x180012b27  pop     rdi
0x180012b28  jmp     dllmain_dispatch
```
