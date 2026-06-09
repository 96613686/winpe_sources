# _DllMainCRTStartup

- ea: `0x180014f00`
- end: `0x180014f3d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014f00`
- `0x180014f44`
- `0x180015254`

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
0x180014f00  mov     [rsp+arg_0], rbx
0x180014f05  mov     [rsp+arg_8], rsi
0x180014f0a  push    rdi
0x180014f0b  sub     rsp, 20h
0x180014f0f  mov     rdi, r8
0x180014f12  mov     ebx, edx
0x180014f14  mov     rsi, rcx
0x180014f17  cmp     edx, 1
0x180014f1a  jnz     short loc_180014F21
0x180014f1c  call    __security_init_cookie
0x180014f21  mov     r8, rdi
0x180014f24  mov     edx, ebx; fdwReason
0x180014f26  mov     rcx, rsi; hinstDLL
0x180014f29  mov     rbx, [rsp+28h+arg_0]
0x180014f2e  mov     rsi, [rsp+28h+arg_8]
0x180014f33  add     rsp, 20h
0x180014f37  pop     rdi
0x180014f38  jmp     __DllMainCRTStartup
```
