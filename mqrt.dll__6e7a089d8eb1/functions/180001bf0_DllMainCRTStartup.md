# _DllMainCRTStartup

- ea: `0x180001bf0`
- end: `0x180001c2d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001bf0`
- `0x180001c34`
- `0x1800024d4`

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
0x180001bf0  mov     [rsp+arg_0], rbx
0x180001bf5  mov     [rsp+arg_8], rsi
0x180001bfa  push    rdi
0x180001bfb  sub     rsp, 20h
0x180001bff  mov     rdi, r8
0x180001c02  mov     ebx, edx
0x180001c04  mov     rsi, rcx
0x180001c07  cmp     edx, 1
0x180001c0a  jnz     short loc_180001C11
0x180001c0c  call    __security_init_cookie
0x180001c11  mov     r8, rdi
0x180001c14  mov     edx, ebx; fdwReason
0x180001c16  mov     rcx, rsi; hinstDLL
0x180001c19  mov     rbx, [rsp+28h+arg_0]
0x180001c1e  mov     rsi, [rsp+28h+arg_8]
0x180001c23  add     rsp, 20h
0x180001c27  pop     rdi
0x180001c28  jmp     __DllMainCRTStartup
```
