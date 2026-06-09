# _DllMainCRTStartup

- ea: `0x180005b20`
- end: `0x180005b5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005b20`
- `0x180005b64`
- `0x180005e94`

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
0x180005b20  mov     [rsp+arg_0], rbx
0x180005b25  mov     [rsp+arg_8], rsi
0x180005b2a  push    rdi
0x180005b2b  sub     rsp, 20h
0x180005b2f  mov     rdi, r8
0x180005b32  mov     ebx, edx
0x180005b34  mov     rsi, rcx
0x180005b37  cmp     edx, 1
0x180005b3a  jnz     short loc_180005B41
0x180005b3c  call    __security_init_cookie
0x180005b41  mov     r8, rdi
0x180005b44  mov     edx, ebx; fdwReason
0x180005b46  mov     rcx, rsi; hinstDLL
0x180005b49  mov     rbx, [rsp+28h+arg_0]
0x180005b4e  mov     rsi, [rsp+28h+arg_8]
0x180005b53  add     rsp, 20h
0x180005b57  pop     rdi
0x180005b58  jmp     __DllMainCRTStartup
```
