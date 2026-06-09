# _DllMainCRTStartup

- ea: `0x180002644`
- end: `0x180002681`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b2d0`

## callees

- `0x180002514`
- `0x180002644`
- `0x180002688`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpvReserved);
}

```

## disassembly

```asm
0x180002644  mov     [rsp+arg_0], rbx
0x180002649  mov     [rsp+arg_8], rsi
0x18000264e  push    rdi
0x18000264f  sub     rsp, 20h
0x180002653  mov     rdi, r8
0x180002656  mov     ebx, edx
0x180002658  mov     rsi, rcx
0x18000265b  cmp     edx, 1
0x18000265e  jnz     short loc_180002665
0x180002660  call    __security_init_cookie
0x180002665  mov     r8, rdi; lpvReserved
0x180002668  mov     edx, ebx; fdwReason
0x18000266a  mov     rcx, rsi; hinstDLL
0x18000266d  mov     rbx, [rsp+28h+arg_0]
0x180002672  mov     rsi, [rsp+28h+arg_8]
0x180002677  add     rsp, 20h
0x18000267b  pop     rdi
0x18000267c  jmp     dllmain_dispatch
```
