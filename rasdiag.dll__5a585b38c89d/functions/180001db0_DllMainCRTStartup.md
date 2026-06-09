# _DllMainCRTStartup

- ea: `0x180001db0`
- end: `0x180001ded`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001db0`
- `0x180001df4`
- `0x180002784`

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
0x180001db0  mov     [rsp+arg_0], rbx
0x180001db5  mov     [rsp+arg_8], rsi
0x180001dba  push    rdi
0x180001dbb  sub     rsp, 20h
0x180001dbf  mov     rdi, r8
0x180001dc2  mov     ebx, edx
0x180001dc4  mov     rsi, rcx
0x180001dc7  cmp     edx, 1
0x180001dca  jnz     short loc_180001DD1
0x180001dcc  call    __security_init_cookie
0x180001dd1  mov     r8, rdi
0x180001dd4  mov     edx, ebx; fdwReason
0x180001dd6  mov     rcx, rsi; hinstDLL
0x180001dd9  mov     rbx, [rsp+28h+arg_0]
0x180001dde  mov     rsi, [rsp+28h+arg_8]
0x180001de3  add     rsp, 20h
0x180001de7  pop     rdi
0x180001de8  jmp     __DllMainCRTStartup
```
