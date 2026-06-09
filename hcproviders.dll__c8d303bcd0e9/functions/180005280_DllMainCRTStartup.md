# _DllMainCRTStartup

- ea: `0x180005280`
- end: `0x1800052bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005280`
- `0x1800052c4`
- `0x1800055f4`

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
0x180005280  mov     [rsp+arg_0], rbx
0x180005285  mov     [rsp+arg_8], rsi
0x18000528a  push    rdi
0x18000528b  sub     rsp, 20h
0x18000528f  mov     rdi, r8
0x180005292  mov     ebx, edx
0x180005294  mov     rsi, rcx
0x180005297  cmp     edx, 1
0x18000529a  jnz     short loc_1800052A1
0x18000529c  call    __security_init_cookie
0x1800052a1  mov     r8, rdi
0x1800052a4  mov     edx, ebx; fdwReason
0x1800052a6  mov     rcx, rsi; hinstDLL
0x1800052a9  mov     rbx, [rsp+28h+arg_0]
0x1800052ae  mov     rsi, [rsp+28h+arg_8]
0x1800052b3  add     rsp, 20h
0x1800052b7  pop     rdi
0x1800052b8  jmp     __DllMainCRTStartup
```
