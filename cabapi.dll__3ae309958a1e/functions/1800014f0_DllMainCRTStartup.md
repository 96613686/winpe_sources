# _DllMainCRTStartup

- ea: `0x1800014f0`
- end: `0x18000152d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800013b4`
- `0x1800014f0`
- `0x18000199c`

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
0x1800014f0  mov     [rsp+arg_0], rbx
0x1800014f5  mov     [rsp+arg_8], rsi
0x1800014fa  push    rdi
0x1800014fb  sub     rsp, 20h
0x1800014ff  mov     rdi, r8
0x180001502  mov     ebx, edx
0x180001504  mov     rsi, rcx
0x180001507  cmp     edx, 1
0x18000150a  jnz     short loc_180001511
0x18000150c  call    __security_init_cookie
0x180001511  mov     r8, rdi; lpvReserved
0x180001514  mov     edx, ebx; fdwReason
0x180001516  mov     rcx, rsi; hinstDLL
0x180001519  mov     rbx, [rsp+28h+arg_0]
0x18000151e  mov     rsi, [rsp+28h+arg_8]
0x180001523  add     rsp, 20h
0x180001527  pop     rdi
0x180001528  jmp     dllmain_dispatch
```
