# _DllMainCRTStartup

- ea: `0x180003a40`
- end: `0x180003a7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003a40`
- `0x180003a84`
- `0x1800041b4`

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
0x180003a40  mov     [rsp+arg_0], rbx
0x180003a45  mov     [rsp+arg_8], rsi
0x180003a4a  push    rdi
0x180003a4b  sub     rsp, 20h
0x180003a4f  mov     rdi, r8
0x180003a52  mov     ebx, edx
0x180003a54  mov     rsi, rcx
0x180003a57  cmp     edx, 1
0x180003a5a  jnz     short loc_180003A61
0x180003a5c  call    __security_init_cookie
0x180003a61  mov     r8, rdi
0x180003a64  mov     edx, ebx; fdwReason
0x180003a66  mov     rcx, rsi; hinstDLL
0x180003a69  mov     rbx, [rsp+28h+arg_0]
0x180003a6e  mov     rsi, [rsp+28h+arg_8]
0x180003a73  add     rsp, 20h
0x180003a77  pop     rdi
0x180003a78  jmp     __DllMainCRTStartup
```
