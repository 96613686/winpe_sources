# _DllMainCRTStartup

- ea: `0x180002ba0`
- end: `0x180002bdd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ba0`
- `0x180002be4`
- `0x180002f14`

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
0x180002ba0  mov     [rsp+arg_0], rbx
0x180002ba5  mov     [rsp+arg_8], rsi
0x180002baa  push    rdi
0x180002bab  sub     rsp, 20h
0x180002baf  mov     rdi, r8
0x180002bb2  mov     ebx, edx
0x180002bb4  mov     rsi, rcx
0x180002bb7  cmp     edx, 1
0x180002bba  jnz     short loc_180002BC1
0x180002bbc  call    __security_init_cookie
0x180002bc1  mov     r8, rdi
0x180002bc4  mov     edx, ebx; fdwReason
0x180002bc6  mov     rcx, rsi; hinstDLL
0x180002bc9  mov     rbx, [rsp+28h+arg_0]
0x180002bce  mov     rsi, [rsp+28h+arg_8]
0x180002bd3  add     rsp, 20h
0x180002bd7  pop     rdi
0x180002bd8  jmp     __DllMainCRTStartup
```
