# _DllMainCRTStartup

- ea: `0x180009df0`
- end: `0x180009e2d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009df0`
- `0x180009e34`
- `0x18000a624`

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
0x180009df0  mov     [rsp+arg_0], rbx
0x180009df5  mov     [rsp+arg_8], rsi
0x180009dfa  push    rdi
0x180009dfb  sub     rsp, 20h
0x180009dff  mov     rdi, r8
0x180009e02  mov     ebx, edx
0x180009e04  mov     rsi, rcx
0x180009e07  cmp     edx, 1
0x180009e0a  jnz     short loc_180009E11
0x180009e0c  call    __security_init_cookie
0x180009e11  mov     r8, rdi
0x180009e14  mov     edx, ebx; fdwReason
0x180009e16  mov     rcx, rsi; hinstDLL
0x180009e19  mov     rbx, [rsp+28h+arg_0]
0x180009e1e  mov     rsi, [rsp+28h+arg_8]
0x180009e23  add     rsp, 20h
0x180009e27  pop     rdi
0x180009e28  jmp     __DllMainCRTStartup
```
