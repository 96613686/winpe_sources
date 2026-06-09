# _DllMainCRTStartup

- ea: `0x180008b80`
- end: `0x180008bbd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008b80`
- `0x180008bc4`
- `0x180008ef4`

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
0x180008b80  mov     [rsp+arg_0], rbx
0x180008b85  mov     [rsp+arg_8], rsi
0x180008b8a  push    rdi
0x180008b8b  sub     rsp, 20h
0x180008b8f  mov     rdi, r8
0x180008b92  mov     ebx, edx
0x180008b94  mov     rsi, rcx
0x180008b97  cmp     edx, 1
0x180008b9a  jnz     short loc_180008BA1
0x180008b9c  call    __security_init_cookie
0x180008ba1  mov     r8, rdi
0x180008ba4  mov     edx, ebx; fdwReason
0x180008ba6  mov     rcx, rsi; hinstDLL
0x180008ba9  mov     rbx, [rsp+28h+arg_0]
0x180008bae  mov     rsi, [rsp+28h+arg_8]
0x180008bb3  add     rsp, 20h
0x180008bb7  pop     rdi
0x180008bb8  jmp     __DllMainCRTStartup
```
