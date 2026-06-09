# _DllMainCRTStartup

- ea: `0x180001b90`
- end: `0x180001bcd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001a54`
- `0x180001b90`
- `0x18000202c`

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
0x180001b90  mov     [rsp+arg_0], rbx
0x180001b95  mov     [rsp+arg_8], rsi
0x180001b9a  push    rdi
0x180001b9b  sub     rsp, 20h
0x180001b9f  mov     rdi, r8
0x180001ba2  mov     ebx, edx
0x180001ba4  mov     rsi, rcx
0x180001ba7  cmp     edx, 1
0x180001baa  jnz     short loc_180001BB1
0x180001bac  call    __security_init_cookie
0x180001bb1  mov     r8, rdi; lpvReserved
0x180001bb4  mov     edx, ebx; fdwReason
0x180001bb6  mov     rcx, rsi; hinstDLL
0x180001bb9  mov     rbx, [rsp+28h+arg_0]
0x180001bbe  mov     rsi, [rsp+28h+arg_8]
0x180001bc3  add     rsp, 20h
0x180001bc7  pop     rdi
0x180001bc8  jmp     dllmain_dispatch
```
