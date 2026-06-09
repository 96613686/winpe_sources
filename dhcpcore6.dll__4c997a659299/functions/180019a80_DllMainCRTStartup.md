# _DllMainCRTStartup

- ea: `0x180019a80`
- end: `0x180019abd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180019944`
- `0x180019a80`
- `0x180019b20`

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
0x180019a80  mov     [rsp+arg_0], rbx
0x180019a85  mov     [rsp+arg_8], rsi
0x180019a8a  push    rdi
0x180019a8b  sub     rsp, 20h
0x180019a8f  mov     rdi, r8
0x180019a92  mov     ebx, edx
0x180019a94  mov     rsi, rcx
0x180019a97  cmp     edx, 1
0x180019a9a  jnz     short loc_180019AA1
0x180019a9c  call    __security_init_cookie
0x180019aa1  mov     r8, rdi; lpvReserved
0x180019aa4  mov     edx, ebx; fdwReason
0x180019aa6  mov     rcx, rsi; hinstDLL
0x180019aa9  mov     rbx, [rsp+28h+arg_0]
0x180019aae  mov     rsi, [rsp+28h+arg_8]
0x180019ab3  add     rsp, 20h
0x180019ab7  pop     rdi
0x180019ab8  jmp     dllmain_dispatch
```
