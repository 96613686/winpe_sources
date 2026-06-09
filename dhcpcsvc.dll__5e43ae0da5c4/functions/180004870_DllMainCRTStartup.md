# _DllMainCRTStartup

- ea: `0x180004870`
- end: `0x1800048ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004734`
- `0x180004870`
- `0x1800048e4`

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
0x180004870  mov     [rsp+arg_0], rbx
0x180004875  mov     [rsp+arg_8], rsi
0x18000487a  push    rdi
0x18000487b  sub     rsp, 20h
0x18000487f  mov     rdi, r8
0x180004882  mov     ebx, edx
0x180004884  mov     rsi, rcx
0x180004887  cmp     edx, 1
0x18000488a  jnz     short loc_180004891
0x18000488c  call    __security_init_cookie
0x180004891  mov     r8, rdi; lpvReserved
0x180004894  mov     edx, ebx; fdwReason
0x180004896  mov     rcx, rsi; hinstDLL
0x180004899  mov     rbx, [rsp+28h+arg_0]
0x18000489e  mov     rsi, [rsp+28h+arg_8]
0x1800048a3  add     rsp, 20h
0x1800048a7  pop     rdi
0x1800048a8  jmp     dllmain_dispatch
```
