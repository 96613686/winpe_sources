# _DllMainCRTStartup

- ea: `0x1800025d0`
- end: `0x18000260d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002494`
- `0x1800025d0`
- `0x180002a20`

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
0x1800025d0  mov     [rsp+arg_0], rbx
0x1800025d5  mov     [rsp+arg_8], rsi
0x1800025da  push    rdi
0x1800025db  sub     rsp, 20h
0x1800025df  mov     rdi, r8
0x1800025e2  mov     ebx, edx
0x1800025e4  mov     rsi, rcx
0x1800025e7  cmp     edx, 1
0x1800025ea  jnz     short loc_1800025F1
0x1800025ec  call    __security_init_cookie
0x1800025f1  mov     r8, rdi; lpvReserved
0x1800025f4  mov     edx, ebx; fdwReason
0x1800025f6  mov     rcx, rsi; hinstDLL
0x1800025f9  mov     rbx, [rsp+28h+arg_0]
0x1800025fe  mov     rsi, [rsp+28h+arg_8]
0x180002603  add     rsp, 20h
0x180002607  pop     rdi
0x180002608  jmp     dllmain_dispatch
```
