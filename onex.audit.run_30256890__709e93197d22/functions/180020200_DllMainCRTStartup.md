# _DllMainCRTStartup

- ea: `0x180020200`
- end: `0x18002023d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800200c4`
- `0x180020200`
- `0x18002029c`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180020200  mov     [rsp+arg_0], rbx
0x180020205  mov     [rsp+arg_8], rsi
0x18002020a  push    rdi
0x18002020b  sub     rsp, 20h
0x18002020f  mov     rdi, r8
0x180020212  mov     ebx, edx
0x180020214  mov     rsi, rcx
0x180020217  cmp     edx, 1
0x18002021a  jnz     short loc_180020221
0x18002021c  call    __security_init_cookie
0x180020221  mov     r8, rdi; lpvReserved
0x180020224  mov     edx, ebx; fdwReason
0x180020226  mov     rcx, rsi; hinstDLL
0x180020229  mov     rbx, [rsp+28h+arg_0]
0x18002022e  mov     rsi, [rsp+28h+arg_8]
0x180020233  add     rsp, 20h
0x180020237  pop     rdi
0x180020238  jmp     dllmain_dispatch
```
