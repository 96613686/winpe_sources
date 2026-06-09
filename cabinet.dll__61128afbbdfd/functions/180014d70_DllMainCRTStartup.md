# _DllMainCRTStartup

- ea: `0x180014d70`
- end: `0x180014dad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180014c34`
- `0x180014d70`
- `0x180014e10`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180014d70  mov     [rsp+arg_0], rbx
0x180014d75  mov     [rsp+arg_8], rsi
0x180014d7a  push    rdi
0x180014d7b  sub     rsp, 20h
0x180014d7f  mov     rdi, r8
0x180014d82  mov     ebx, edx
0x180014d84  mov     rsi, rcx
0x180014d87  cmp     edx, 1
0x180014d8a  jnz     short loc_180014D91
0x180014d8c  call    __security_init_cookie
0x180014d91  mov     r8, rdi; lpvReserved
0x180014d94  mov     edx, ebx; fdwReason
0x180014d96  mov     rcx, rsi; hinstDLL
0x180014d99  mov     rbx, [rsp+28h+arg_0]
0x180014d9e  mov     rsi, [rsp+28h+arg_8]
0x180014da3  add     rsp, 20h
0x180014da7  pop     rdi
0x180014da8  jmp     dllmain_dispatch
```
