# _DllMainCRTStartup

- ea: `0x180001750`
- end: `0x18000178d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001750`
- `0x180001794`
- `0x180001ac4`

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
0x180001750  mov     [rsp+arg_0], rbx
0x180001755  mov     [rsp+arg_8], rsi
0x18000175a  push    rdi
0x18000175b  sub     rsp, 20h
0x18000175f  mov     rdi, r8
0x180001762  mov     ebx, edx
0x180001764  mov     rsi, rcx
0x180001767  cmp     edx, 1
0x18000176a  jnz     short loc_180001771
0x18000176c  call    __security_init_cookie
0x180001771  mov     r8, rdi
0x180001774  mov     edx, ebx; fdwReason
0x180001776  mov     rcx, rsi; hinstDLL
0x180001779  mov     rbx, [rsp+28h+arg_0]
0x18000177e  mov     rsi, [rsp+28h+arg_8]
0x180001783  add     rsp, 20h
0x180001787  pop     rdi
0x180001788  jmp     __DllMainCRTStartup
```
