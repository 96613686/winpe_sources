# _DllMainCRTStartup

- ea: `0x180001830`
- end: `0x18000186d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001830`
- `0x180001874`
- `0x1800021c4`

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
0x180001830  mov     [rsp+arg_0], rbx
0x180001835  mov     [rsp+arg_8], rsi
0x18000183a  push    rdi
0x18000183b  sub     rsp, 20h
0x18000183f  mov     rdi, r8
0x180001842  mov     ebx, edx
0x180001844  mov     rsi, rcx
0x180001847  cmp     edx, 1
0x18000184a  jnz     short loc_180001851
0x18000184c  call    __security_init_cookie
0x180001851  mov     r8, rdi
0x180001854  mov     edx, ebx; fdwReason
0x180001856  mov     rcx, rsi; hinstDLL
0x180001859  mov     rbx, [rsp+28h+arg_0]
0x18000185e  mov     rsi, [rsp+28h+arg_8]
0x180001863  add     rsp, 20h
0x180001867  pop     rdi
0x180001868  jmp     __DllMainCRTStartup
```
