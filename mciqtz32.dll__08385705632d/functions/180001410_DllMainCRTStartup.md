# _DllMainCRTStartup

- ea: `0x180001410`
- end: `0x18000144d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800012d4`
- `0x180001410`
- `0x180001484`

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
0x180001410  mov     [rsp+arg_0], rbx
0x180001415  mov     [rsp+arg_8], rsi
0x18000141a  push    rdi
0x18000141b  sub     rsp, 20h
0x18000141f  mov     rdi, r8
0x180001422  mov     ebx, edx
0x180001424  mov     rsi, rcx
0x180001427  cmp     edx, 1
0x18000142a  jnz     short loc_180001431
0x18000142c  call    __security_init_cookie
0x180001431  mov     r8, rdi; lpvReserved
0x180001434  mov     edx, ebx; fdwReason
0x180001436  mov     rcx, rsi; hinstDLL
0x180001439  mov     rbx, [rsp+28h+arg_0]
0x18000143e  mov     rsi, [rsp+28h+arg_8]
0x180001443  add     rsp, 20h
0x180001447  pop     rdi
0x180001448  jmp     dllmain_dispatch
```
