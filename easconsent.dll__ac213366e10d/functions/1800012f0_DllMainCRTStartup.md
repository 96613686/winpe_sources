# _DllMainCRTStartup

- ea: `0x1800012f0`
- end: `0x18000132d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800012f0`
- `0x180001334`
- `0x180001740`

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
0x1800012f0  mov     [rsp+arg_0], rbx
0x1800012f5  mov     [rsp+arg_8], rsi
0x1800012fa  push    rdi
0x1800012fb  sub     rsp, 20h
0x1800012ff  mov     rdi, r8
0x180001302  mov     ebx, edx
0x180001304  mov     rsi, rcx
0x180001307  cmp     edx, 1
0x18000130a  jnz     short loc_180001311
0x18000130c  call    __security_init_cookie
0x180001311  mov     r8, rdi
0x180001314  mov     edx, ebx; fdwReason
0x180001316  mov     rcx, rsi; hinstDLL
0x180001319  mov     rbx, [rsp+28h+arg_0]
0x18000131e  mov     rsi, [rsp+28h+arg_8]
0x180001323  add     rsp, 20h
0x180001327  pop     rdi
0x180001328  jmp     __DllMainCRTStartup
```
