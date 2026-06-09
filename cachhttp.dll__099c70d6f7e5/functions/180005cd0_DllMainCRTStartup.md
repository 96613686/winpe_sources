# _DllMainCRTStartup

- ea: `0x180005cd0`
- end: `0x180005d0d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cd0`
- `0x180005d14`
- `0x180006044`

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
0x180005cd0  mov     [rsp+arg_0], rbx
0x180005cd5  mov     [rsp+arg_8], rsi
0x180005cda  push    rdi
0x180005cdb  sub     rsp, 20h
0x180005cdf  mov     rdi, r8
0x180005ce2  mov     ebx, edx
0x180005ce4  mov     rsi, rcx
0x180005ce7  cmp     edx, 1
0x180005cea  jnz     short loc_180005CF1
0x180005cec  call    __security_init_cookie
0x180005cf1  mov     r8, rdi
0x180005cf4  mov     edx, ebx; fdwReason
0x180005cf6  mov     rcx, rsi; hinstDLL
0x180005cf9  mov     rbx, [rsp+28h+arg_0]
0x180005cfe  mov     rsi, [rsp+28h+arg_8]
0x180005d03  add     rsp, 20h
0x180005d07  pop     rdi
0x180005d08  jmp     __DllMainCRTStartup
```
