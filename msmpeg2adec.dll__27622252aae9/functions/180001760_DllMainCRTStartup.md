# _DllMainCRTStartup

- ea: `0x180001760`
- end: `0x18000179d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001624`
- `0x180001760`
- `0x180001bbc`

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
0x180001760  mov     [rsp+arg_0], rbx
0x180001765  mov     [rsp+arg_8], rsi
0x18000176a  push    rdi
0x18000176b  sub     rsp, 20h
0x18000176f  mov     rdi, r8
0x180001772  mov     ebx, edx
0x180001774  mov     rsi, rcx
0x180001777  cmp     edx, 1
0x18000177a  jnz     short loc_180001781
0x18000177c  call    __security_init_cookie
0x180001781  mov     r8, rdi; lpvReserved
0x180001784  mov     edx, ebx; fdwReason
0x180001786  mov     rcx, rsi; hinstDLL
0x180001789  mov     rbx, [rsp+28h+arg_0]
0x18000178e  mov     rsi, [rsp+28h+arg_8]
0x180001793  add     rsp, 20h
0x180001797  pop     rdi
0x180001798  jmp     dllmain_dispatch
```
