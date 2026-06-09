# _DllMainCRTStartup

- ea: `0x180016040`
- end: `0x18001607d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180015f04`
- `0x180016040`
- `0x18001614c`

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
0x180016040  mov     [rsp+arg_0], rbx
0x180016045  mov     [rsp+arg_8], rsi
0x18001604a  push    rdi
0x18001604b  sub     rsp, 20h
0x18001604f  mov     rdi, r8
0x180016052  mov     ebx, edx
0x180016054  mov     rsi, rcx
0x180016057  cmp     edx, 1
0x18001605a  jnz     short loc_180016061
0x18001605c  call    __security_init_cookie
0x180016061  mov     r8, rdi; lpvReserved
0x180016064  mov     edx, ebx; fdwReason
0x180016066  mov     rcx, rsi; hinstDLL
0x180016069  mov     rbx, [rsp+28h+arg_0]
0x18001606e  mov     rsi, [rsp+28h+arg_8]
0x180016073  add     rsp, 20h
0x180016077  pop     rdi
0x180016078  jmp     dllmain_dispatch
```
