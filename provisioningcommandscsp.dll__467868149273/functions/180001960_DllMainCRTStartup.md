# _DllMainCRTStartup

- ea: `0x180001960`
- end: `0x18000199d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001960`
- `0x1800019a4`
- `0x180001ed4`

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
0x180001960  mov     [rsp+arg_0], rbx
0x180001965  mov     [rsp+arg_8], rsi
0x18000196a  push    rdi
0x18000196b  sub     rsp, 20h
0x18000196f  mov     rdi, r8
0x180001972  mov     ebx, edx
0x180001974  mov     rsi, rcx
0x180001977  cmp     edx, 1
0x18000197a  jnz     short loc_180001981
0x18000197c  call    __security_init_cookie
0x180001981  mov     r8, rdi
0x180001984  mov     edx, ebx; fdwReason
0x180001986  mov     rcx, rsi; hinstDLL
0x180001989  mov     rbx, [rsp+28h+arg_0]
0x18000198e  mov     rsi, [rsp+28h+arg_8]
0x180001993  add     rsp, 20h
0x180001997  pop     rdi
0x180001998  jmp     __DllMainCRTStartup
```
