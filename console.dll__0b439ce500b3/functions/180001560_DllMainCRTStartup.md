# _DllMainCRTStartup

- ea: `0x180001560`
- end: `0x18000159d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001424`
- `0x180001560`
- `0x180001a54`

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
0x180001560  mov     [rsp+arg_0], rbx
0x180001565  mov     [rsp+arg_8], rsi
0x18000156a  push    rdi
0x18000156b  sub     rsp, 20h
0x18000156f  mov     rdi, r8
0x180001572  mov     ebx, edx
0x180001574  mov     rsi, rcx
0x180001577  cmp     edx, 1
0x18000157a  jnz     short loc_180001581
0x18000157c  call    __security_init_cookie
0x180001581  mov     r8, rdi; lpvReserved
0x180001584  mov     edx, ebx; fdwReason
0x180001586  mov     rcx, rsi; hinstDLL
0x180001589  mov     rbx, [rsp+28h+arg_0]
0x18000158e  mov     rsi, [rsp+28h+arg_8]
0x180001593  add     rsp, 20h
0x180001597  pop     rdi
0x180001598  jmp     dllmain_dispatch
```
