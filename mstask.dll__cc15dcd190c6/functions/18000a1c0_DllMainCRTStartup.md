# _DllMainCRTStartup

- ea: `0x18000a1c0`
- end: `0x18000a1fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a1c0`
- `0x18000a204`
- `0x18000a844`

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
0x18000a1c0  mov     [rsp+arg_0], rbx
0x18000a1c5  mov     [rsp+arg_8], rsi
0x18000a1ca  push    rdi
0x18000a1cb  sub     rsp, 20h
0x18000a1cf  mov     rdi, r8
0x18000a1d2  mov     ebx, edx
0x18000a1d4  mov     rsi, rcx
0x18000a1d7  cmp     edx, 1
0x18000a1da  jnz     short loc_18000A1E1
0x18000a1dc  call    __security_init_cookie
0x18000a1e1  mov     r8, rdi
0x18000a1e4  mov     edx, ebx; fdwReason
0x18000a1e6  mov     rcx, rsi; hinstDLL
0x18000a1e9  mov     rbx, [rsp+28h+arg_0]
0x18000a1ee  mov     rsi, [rsp+28h+arg_8]
0x18000a1f3  add     rsp, 20h
0x18000a1f7  pop     rdi
0x18000a1f8  jmp     __DllMainCRTStartup
```
