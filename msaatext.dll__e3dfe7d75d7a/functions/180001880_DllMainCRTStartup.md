# _DllMainCRTStartup

- ea: `0x180001880`
- end: `0x1800018bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001880`
- `0x1800018c4`
- `0x180002094`

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
0x180001880  mov     [rsp+arg_0], rbx
0x180001885  mov     [rsp+arg_8], rsi
0x18000188a  push    rdi
0x18000188b  sub     rsp, 20h
0x18000188f  mov     rdi, r8
0x180001892  mov     ebx, edx
0x180001894  mov     rsi, rcx
0x180001897  cmp     edx, 1
0x18000189a  jnz     short loc_1800018A1
0x18000189c  call    __security_init_cookie
0x1800018a1  mov     r8, rdi
0x1800018a4  mov     edx, ebx; fdwReason
0x1800018a6  mov     rcx, rsi; hinstDLL
0x1800018a9  mov     rbx, [rsp+28h+arg_0]
0x1800018ae  mov     rsi, [rsp+28h+arg_8]
0x1800018b3  add     rsp, 20h
0x1800018b7  pop     rdi
0x1800018b8  jmp     __DllMainCRTStartup
```
