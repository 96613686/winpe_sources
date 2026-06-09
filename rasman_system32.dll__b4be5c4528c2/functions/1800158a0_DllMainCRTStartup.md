# _DllMainCRTStartup

- ea: `0x1800158a0`
- end: `0x1800158dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800158a0`
- `0x1800158e4`
- `0x180015bf4`

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
0x1800158a0  mov     [rsp+arg_0], rbx
0x1800158a5  mov     [rsp+arg_8], rsi
0x1800158aa  push    rdi
0x1800158ab  sub     rsp, 20h
0x1800158af  mov     rdi, r8
0x1800158b2  mov     ebx, edx
0x1800158b4  mov     rsi, rcx
0x1800158b7  cmp     edx, 1
0x1800158ba  jnz     short loc_1800158C1
0x1800158bc  call    __security_init_cookie
0x1800158c1  mov     r8, rdi
0x1800158c4  mov     edx, ebx; fdwReason
0x1800158c6  mov     rcx, rsi; hinstDLL
0x1800158c9  mov     rbx, [rsp+28h+arg_0]
0x1800158ce  mov     rsi, [rsp+28h+arg_8]
0x1800158d3  add     rsp, 20h
0x1800158d7  pop     rdi
0x1800158d8  jmp     __DllMainCRTStartup
```
