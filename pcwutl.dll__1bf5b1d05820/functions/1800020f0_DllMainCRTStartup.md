# _DllMainCRTStartup

- ea: `0x1800020f0`
- end: `0x18000212d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020f0`
- `0x180002134`
- `0x180002914`

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
0x1800020f0  mov     [rsp+arg_0], rbx
0x1800020f5  mov     [rsp+arg_8], rsi
0x1800020fa  push    rdi
0x1800020fb  sub     rsp, 20h
0x1800020ff  mov     rdi, r8
0x180002102  mov     ebx, edx
0x180002104  mov     rsi, rcx
0x180002107  cmp     edx, 1
0x18000210a  jnz     short loc_180002111
0x18000210c  call    __security_init_cookie
0x180002111  mov     r8, rdi
0x180002114  mov     edx, ebx; fdwReason
0x180002116  mov     rcx, rsi; hinstDLL
0x180002119  mov     rbx, [rsp+28h+arg_0]
0x18000211e  mov     rsi, [rsp+28h+arg_8]
0x180002123  add     rsp, 20h
0x180002127  pop     rdi
0x180002128  jmp     __DllMainCRTStartup
```
