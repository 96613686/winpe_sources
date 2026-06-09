# _DllMainCRTStartup

- ea: `0x180002a00`
- end: `0x180002a3d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a00`
- `0x180002a44`
- `0x180002d44`

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
0x180002a00  mov     [rsp+arg_0], rbx
0x180002a05  mov     [rsp+arg_8], rsi
0x180002a0a  push    rdi
0x180002a0b  sub     rsp, 20h
0x180002a0f  mov     rdi, r8
0x180002a12  mov     ebx, edx
0x180002a14  mov     rsi, rcx
0x180002a17  cmp     edx, 1
0x180002a1a  jnz     short loc_180002A21
0x180002a1c  call    __security_init_cookie
0x180002a21  mov     r8, rdi
0x180002a24  mov     edx, ebx; fdwReason
0x180002a26  mov     rcx, rsi; hinstDLL
0x180002a29  mov     rbx, [rsp+28h+arg_0]
0x180002a2e  mov     rsi, [rsp+28h+arg_8]
0x180002a33  add     rsp, 20h
0x180002a37  pop     rdi
0x180002a38  jmp     __DllMainCRTStartup
```
