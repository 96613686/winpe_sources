# _DllMainCRTStartup

- ea: `0x180001280`
- end: `0x1800012bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001280`
- `0x1800012c4`
- `0x18000191c`

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
0x180001280  mov     [rsp+arg_0], rbx
0x180001285  mov     [rsp+arg_8], rsi
0x18000128a  push    rdi
0x18000128b  sub     rsp, 20h
0x18000128f  mov     rdi, r8
0x180001292  mov     ebx, edx
0x180001294  mov     rsi, rcx
0x180001297  cmp     edx, 1
0x18000129a  jnz     short loc_1800012A1
0x18000129c  call    __security_init_cookie
0x1800012a1  mov     r8, rdi
0x1800012a4  mov     edx, ebx; fdwReason
0x1800012a6  mov     rcx, rsi; hinstDLL
0x1800012a9  mov     rbx, [rsp+28h+arg_0]
0x1800012ae  mov     rsi, [rsp+28h+arg_8]
0x1800012b3  add     rsp, 20h
0x1800012b7  pop     rdi
0x1800012b8  jmp     __DllMainCRTStartup
```
