# _DllMainCRTStartup

- ea: `0x180004610`
- end: `0x18000464d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004610`
- `0x180004654`
- `0x180004d54`

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
0x180004610  mov     [rsp+arg_0], rbx
0x180004615  mov     [rsp+arg_8], rsi
0x18000461a  push    rdi
0x18000461b  sub     rsp, 20h
0x18000461f  mov     rdi, r8
0x180004622  mov     ebx, edx
0x180004624  mov     rsi, rcx
0x180004627  cmp     edx, 1
0x18000462a  jnz     short loc_180004631
0x18000462c  call    __security_init_cookie
0x180004631  mov     r8, rdi
0x180004634  mov     edx, ebx; fdwReason
0x180004636  mov     rcx, rsi; hinstDLL
0x180004639  mov     rbx, [rsp+28h+arg_0]
0x18000463e  mov     rsi, [rsp+28h+arg_8]
0x180004643  add     rsp, 20h
0x180004647  pop     rdi
0x180004648  jmp     __DllMainCRTStartup
```
