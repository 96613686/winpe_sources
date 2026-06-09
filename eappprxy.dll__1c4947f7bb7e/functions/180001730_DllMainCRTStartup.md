# _DllMainCRTStartup

- ea: `0x180001730`
- end: `0x18000176d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800015f4`
- `0x180001730`
- `0x180001bb0`

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
0x180001730  mov     [rsp+arg_0], rbx
0x180001735  mov     [rsp+arg_8], rsi
0x18000173a  push    rdi
0x18000173b  sub     rsp, 20h
0x18000173f  mov     rdi, r8
0x180001742  mov     ebx, edx
0x180001744  mov     rsi, rcx
0x180001747  cmp     edx, 1
0x18000174a  jnz     short loc_180001751
0x18000174c  call    __security_init_cookie
0x180001751  mov     r8, rdi; lpvReserved
0x180001754  mov     edx, ebx; fdwReason
0x180001756  mov     rcx, rsi; hinstDLL
0x180001759  mov     rbx, [rsp+28h+arg_0]
0x18000175e  mov     rsi, [rsp+28h+arg_8]
0x180001763  add     rsp, 20h
0x180001767  pop     rdi
0x180001768  jmp     dllmain_dispatch
```
