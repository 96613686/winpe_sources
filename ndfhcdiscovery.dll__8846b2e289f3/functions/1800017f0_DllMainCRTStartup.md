# _DllMainCRTStartup

- ea: `0x1800017f0`
- end: `0x18000182d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180001834`
- `0x1800020c4`

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
0x1800017f0  mov     [rsp+arg_0], rbx
0x1800017f5  mov     [rsp+arg_8], rsi
0x1800017fa  push    rdi
0x1800017fb  sub     rsp, 20h
0x1800017ff  mov     rdi, r8
0x180001802  mov     ebx, edx
0x180001804  mov     rsi, rcx
0x180001807  cmp     edx, 1
0x18000180a  jnz     short loc_180001811
0x18000180c  call    __security_init_cookie
0x180001811  mov     r8, rdi
0x180001814  mov     edx, ebx; fdwReason
0x180001816  mov     rcx, rsi; hinstDLL
0x180001819  mov     rbx, [rsp+28h+arg_0]
0x18000181e  mov     rsi, [rsp+28h+arg_8]
0x180001823  add     rsp, 20h
0x180001827  pop     rdi
0x180001828  jmp     __DllMainCRTStartup
```
