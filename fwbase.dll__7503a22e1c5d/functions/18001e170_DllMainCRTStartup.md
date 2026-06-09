# _DllMainCRTStartup

- ea: `0x18001e170`
- end: `0x18001e1ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001e034`
- `0x18001e170`
- `0x18001e5dc`

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
0x18001e170  mov     [rsp+arg_0], rbx
0x18001e175  mov     [rsp+arg_8], rsi
0x18001e17a  push    rdi
0x18001e17b  sub     rsp, 20h
0x18001e17f  mov     rdi, r8
0x18001e182  mov     ebx, edx
0x18001e184  mov     rsi, rcx
0x18001e187  cmp     edx, 1
0x18001e18a  jnz     short loc_18001E191
0x18001e18c  call    __security_init_cookie
0x18001e191  mov     r8, rdi; lpvReserved
0x18001e194  mov     edx, ebx; fdwReason
0x18001e196  mov     rcx, rsi; hinstDLL
0x18001e199  mov     rbx, [rsp+28h+arg_0]
0x18001e19e  mov     rsi, [rsp+28h+arg_8]
0x18001e1a3  add     rsp, 20h
0x18001e1a7  pop     rdi
0x18001e1a8  jmp     dllmain_dispatch
```
