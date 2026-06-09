# _DllMainCRTStartup

- ea: `0x180002e40`
- end: `0x180002e7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002e40`
- `0x180002e84`
- `0x1800037b4`

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
0x180002e40  mov     [rsp+arg_0], rbx
0x180002e45  mov     [rsp+arg_8], rsi
0x180002e4a  push    rdi
0x180002e4b  sub     rsp, 20h
0x180002e4f  mov     rdi, r8
0x180002e52  mov     ebx, edx
0x180002e54  mov     rsi, rcx
0x180002e57  cmp     edx, 1
0x180002e5a  jnz     short loc_180002E61
0x180002e5c  call    __security_init_cookie
0x180002e61  mov     r8, rdi
0x180002e64  mov     edx, ebx; fdwReason
0x180002e66  mov     rcx, rsi; hinstDLL
0x180002e69  mov     rbx, [rsp+28h+arg_0]
0x180002e6e  mov     rsi, [rsp+28h+arg_8]
0x180002e73  add     rsp, 20h
0x180002e77  pop     rdi
0x180002e78  jmp     __DllMainCRTStartup
```
