# _DllMainCRTStartup

- ea: `0x180013ad0`
- end: `0x180013b0d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180013994`
- `0x180013ad0`
- `0x180013fcc`

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
0x180013ad0  mov     [rsp+arg_0], rbx
0x180013ad5  mov     [rsp+arg_8], rsi
0x180013ada  push    rdi
0x180013adb  sub     rsp, 20h
0x180013adf  mov     rdi, r8
0x180013ae2  mov     ebx, edx
0x180013ae4  mov     rsi, rcx
0x180013ae7  cmp     edx, 1
0x180013aea  jnz     short loc_180013AF1
0x180013aec  call    __security_init_cookie
0x180013af1  mov     r8, rdi; lpvReserved
0x180013af4  mov     edx, ebx; fdwReason
0x180013af6  mov     rcx, rsi; hinstDLL
0x180013af9  mov     rbx, [rsp+28h+arg_0]
0x180013afe  mov     rsi, [rsp+28h+arg_8]
0x180013b03  add     rsp, 20h
0x180013b07  pop     rdi
0x180013b08  jmp     dllmain_dispatch
```
