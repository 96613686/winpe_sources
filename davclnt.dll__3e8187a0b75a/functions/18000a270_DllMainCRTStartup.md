# _DllMainCRTStartup

- ea: `0x18000a270`
- end: `0x18000a2ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a270`
- `0x18000a2b4`
- `0x18000a7b4`

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
0x18000a270  mov     [rsp+arg_0], rbx
0x18000a275  mov     [rsp+arg_8], rsi
0x18000a27a  push    rdi
0x18000a27b  sub     rsp, 20h
0x18000a27f  mov     rdi, r8
0x18000a282  mov     ebx, edx
0x18000a284  mov     rsi, rcx
0x18000a287  cmp     edx, 1
0x18000a28a  jnz     short loc_18000A291
0x18000a28c  call    __security_init_cookie
0x18000a291  mov     r8, rdi
0x18000a294  mov     edx, ebx; fdwReason
0x18000a296  mov     rcx, rsi; hinstDLL
0x18000a299  mov     rbx, [rsp+28h+arg_0]
0x18000a29e  mov     rsi, [rsp+28h+arg_8]
0x18000a2a3  add     rsp, 20h
0x18000a2a7  pop     rdi
0x18000a2a8  jmp     __DllMainCRTStartup
```
