# _DllMainCRTStartup

- ea: `0x1800018a0`
- end: `0x1800018dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800018a0`
- `0x1800018e4`
- `0x1800022d4`

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
0x1800018a0  mov     [rsp+arg_0], rbx
0x1800018a5  mov     [rsp+arg_8], rsi
0x1800018aa  push    rdi
0x1800018ab  sub     rsp, 20h
0x1800018af  mov     rdi, r8
0x1800018b2  mov     ebx, edx
0x1800018b4  mov     rsi, rcx
0x1800018b7  cmp     edx, 1
0x1800018ba  jnz     short loc_1800018C1
0x1800018bc  call    __security_init_cookie
0x1800018c1  mov     r8, rdi
0x1800018c4  mov     edx, ebx; fdwReason
0x1800018c6  mov     rcx, rsi; hinstDLL
0x1800018c9  mov     rbx, [rsp+28h+arg_0]
0x1800018ce  mov     rsi, [rsp+28h+arg_8]
0x1800018d3  add     rsp, 20h
0x1800018d7  pop     rdi
0x1800018d8  jmp     __DllMainCRTStartup
```
