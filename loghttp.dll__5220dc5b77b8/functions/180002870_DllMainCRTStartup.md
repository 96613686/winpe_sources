# _DllMainCRTStartup

- ea: `0x180002870`
- end: `0x1800028ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002870`
- `0x1800028b4`
- `0x180002ca4`

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
0x180002870  mov     [rsp+arg_0], rbx
0x180002875  mov     [rsp+arg_8], rsi
0x18000287a  push    rdi
0x18000287b  sub     rsp, 20h
0x18000287f  mov     rdi, r8
0x180002882  mov     ebx, edx
0x180002884  mov     rsi, rcx
0x180002887  cmp     edx, 1
0x18000288a  jnz     short loc_180002891
0x18000288c  call    __security_init_cookie
0x180002891  mov     r8, rdi
0x180002894  mov     edx, ebx; fdwReason
0x180002896  mov     rcx, rsi; hinstDLL
0x180002899  mov     rbx, [rsp+28h+arg_0]
0x18000289e  mov     rsi, [rsp+28h+arg_8]
0x1800028a3  add     rsp, 20h
0x1800028a7  pop     rdi
0x1800028a8  jmp     __DllMainCRTStartup
```
