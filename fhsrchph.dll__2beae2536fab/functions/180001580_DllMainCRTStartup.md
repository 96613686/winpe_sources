# _DllMainCRTStartup

- ea: `0x180001580`
- end: `0x1800015bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001580`
- `0x1800015c4`
- `0x180001e14`

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
0x180001580  mov     [rsp+arg_0], rbx
0x180001585  mov     [rsp+arg_8], rsi
0x18000158a  push    rdi
0x18000158b  sub     rsp, 20h
0x18000158f  mov     rdi, r8
0x180001592  mov     ebx, edx
0x180001594  mov     rsi, rcx
0x180001597  cmp     edx, 1
0x18000159a  jnz     short loc_1800015A1
0x18000159c  call    __security_init_cookie
0x1800015a1  mov     r8, rdi
0x1800015a4  mov     edx, ebx; fdwReason
0x1800015a6  mov     rcx, rsi; hinstDLL
0x1800015a9  mov     rbx, [rsp+28h+arg_0]
0x1800015ae  mov     rsi, [rsp+28h+arg_8]
0x1800015b3  add     rsp, 20h
0x1800015b7  pop     rdi
0x1800015b8  jmp     __DllMainCRTStartup
```
