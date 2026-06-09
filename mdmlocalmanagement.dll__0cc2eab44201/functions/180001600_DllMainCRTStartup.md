# _DllMainCRTStartup

- ea: `0x180001600`
- end: `0x18000163d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800014c4`
- `0x180001600`
- `0x180001a80`

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
0x180001600  mov     [rsp+arg_0], rbx
0x180001605  mov     [rsp+arg_8], rsi
0x18000160a  push    rdi
0x18000160b  sub     rsp, 20h
0x18000160f  mov     rdi, r8
0x180001612  mov     ebx, edx
0x180001614  mov     rsi, rcx
0x180001617  cmp     edx, 1
0x18000161a  jnz     short loc_180001621
0x18000161c  call    __security_init_cookie
0x180001621  mov     r8, rdi; lpvReserved
0x180001624  mov     edx, ebx; fdwReason
0x180001626  mov     rcx, rsi; hinstDLL
0x180001629  mov     rbx, [rsp+28h+arg_0]
0x18000162e  mov     rsi, [rsp+28h+arg_8]
0x180001633  add     rsp, 20h
0x180001637  pop     rdi
0x180001638  jmp     dllmain_dispatch
```
