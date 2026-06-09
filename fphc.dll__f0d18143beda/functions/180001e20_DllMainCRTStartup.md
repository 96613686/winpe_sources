# _DllMainCRTStartup

- ea: `0x180001e20`
- end: `0x180001e5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e20`
- `0x180001e64`
- `0x1800027f4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001e20  mov     [rsp+arg_0], rbx
0x180001e25  mov     [rsp+arg_8], rsi
0x180001e2a  push    rdi
0x180001e2b  sub     rsp, 20h
0x180001e2f  mov     rdi, r8
0x180001e32  mov     ebx, edx
0x180001e34  mov     rsi, rcx
0x180001e37  cmp     edx, 1
0x180001e3a  jnz     short loc_180001E41
0x180001e3c  call    __security_init_cookie
0x180001e41  mov     r8, rdi
0x180001e44  mov     edx, ebx; fdwReason
0x180001e46  mov     rcx, rsi; hinstDLL
0x180001e49  mov     rbx, [rsp+28h+arg_0]
0x180001e4e  mov     rsi, [rsp+28h+arg_8]
0x180001e53  add     rsp, 20h
0x180001e57  pop     rdi
0x180001e58  jmp     __DllMainCRTStartup
```
