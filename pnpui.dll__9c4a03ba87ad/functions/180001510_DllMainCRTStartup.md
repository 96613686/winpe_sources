# _DllMainCRTStartup

- ea: `0x180001510`
- end: `0x18000154d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001510`
- `0x180001554`
- `0x180001964`

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
0x180001510  mov     [rsp+arg_0], rbx
0x180001515  mov     [rsp+arg_8], rsi
0x18000151a  push    rdi
0x18000151b  sub     rsp, 20h
0x18000151f  mov     rdi, r8
0x180001522  mov     ebx, edx
0x180001524  mov     rsi, rcx
0x180001527  cmp     edx, 1
0x18000152a  jnz     short loc_180001531
0x18000152c  call    __security_init_cookie
0x180001531  mov     r8, rdi
0x180001534  mov     edx, ebx; fdwReason
0x180001536  mov     rcx, rsi; hinstDLL
0x180001539  mov     rbx, [rsp+28h+arg_0]
0x18000153e  mov     rsi, [rsp+28h+arg_8]
0x180001543  add     rsp, 20h
0x180001547  pop     rdi
0x180001548  jmp     __DllMainCRTStartup
```
