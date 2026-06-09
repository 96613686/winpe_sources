# _DllMainCRTStartup

- ea: `0x180002220`
- end: `0x18000225d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800020e4`
- `0x180002220`
- `0x180002640`

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
0x180002220  mov     [rsp+arg_0], rbx
0x180002225  mov     [rsp+arg_8], rsi
0x18000222a  push    rdi
0x18000222b  sub     rsp, 20h
0x18000222f  mov     rdi, r8
0x180002232  mov     ebx, edx
0x180002234  mov     rsi, rcx
0x180002237  cmp     edx, 1
0x18000223a  jnz     short loc_180002241
0x18000223c  call    __security_init_cookie
0x180002241  mov     r8, rdi; lpvReserved
0x180002244  mov     edx, ebx; fdwReason
0x180002246  mov     rcx, rsi; hinstDLL
0x180002249  mov     rbx, [rsp+28h+arg_0]
0x18000224e  mov     rsi, [rsp+28h+arg_8]
0x180002253  add     rsp, 20h
0x180002257  pop     rdi
0x180002258  jmp     dllmain_dispatch
```
