# _DllMainCRTStartup

- ea: `0x180001520`
- end: `0x18000155d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180001564`
- `0x180001974`

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
0x180001520  mov     [rsp+arg_0], rbx
0x180001525  mov     [rsp+arg_8], rsi
0x18000152a  push    rdi
0x18000152b  sub     rsp, 20h
0x18000152f  mov     rdi, r8
0x180001532  mov     ebx, edx
0x180001534  mov     rsi, rcx
0x180001537  cmp     edx, 1
0x18000153a  jnz     short loc_180001541
0x18000153c  call    __security_init_cookie
0x180001541  mov     r8, rdi
0x180001544  mov     edx, ebx; fdwReason
0x180001546  mov     rcx, rsi; hinstDLL
0x180001549  mov     rbx, [rsp+28h+arg_0]
0x18000154e  mov     rsi, [rsp+28h+arg_8]
0x180001553  add     rsp, 20h
0x180001557  pop     rdi
0x180001558  jmp     __DllMainCRTStartup
```
