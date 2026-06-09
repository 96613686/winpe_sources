# _DllMainCRTStartup

- ea: `0x180001f20`
- end: `0x180001f5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f20`
- `0x180001f64`
- `0x180002594`

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
0x180001f20  mov     [rsp+arg_0], rbx
0x180001f25  mov     [rsp+arg_8], rsi
0x180001f2a  push    rdi
0x180001f2b  sub     rsp, 20h
0x180001f2f  mov     rdi, r8
0x180001f32  mov     ebx, edx
0x180001f34  mov     rsi, rcx
0x180001f37  cmp     edx, 1
0x180001f3a  jnz     short loc_180001F41
0x180001f3c  call    __security_init_cookie
0x180001f41  mov     r8, rdi
0x180001f44  mov     edx, ebx; fdwReason
0x180001f46  mov     rcx, rsi; hinstDLL
0x180001f49  mov     rbx, [rsp+28h+arg_0]
0x180001f4e  mov     rsi, [rsp+28h+arg_8]
0x180001f53  add     rsp, 20h
0x180001f57  pop     rdi
0x180001f58  jmp     __DllMainCRTStartup
```
