# _DllMainCRTStartup

- ea: `0x180002040`
- end: `0x18000207d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002040`
- `0x180002084`
- `0x1800023b4`

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
0x180002040  mov     [rsp+arg_0], rbx
0x180002045  mov     [rsp+arg_8], rsi
0x18000204a  push    rdi
0x18000204b  sub     rsp, 20h
0x18000204f  mov     rdi, r8
0x180002052  mov     ebx, edx
0x180002054  mov     rsi, rcx
0x180002057  cmp     edx, 1
0x18000205a  jnz     short loc_180002061
0x18000205c  call    __security_init_cookie
0x180002061  mov     r8, rdi
0x180002064  mov     edx, ebx; fdwReason
0x180002066  mov     rcx, rsi; hinstDLL
0x180002069  mov     rbx, [rsp+28h+arg_0]
0x18000206e  mov     rsi, [rsp+28h+arg_8]
0x180002073  add     rsp, 20h
0x180002077  pop     rdi
0x180002078  jmp     __DllMainCRTStartup
```
