# _DllMainCRTStartup

- ea: `0x18000d794`
- end: `0x18000d7d1`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a530`

## callees

- `0x18000d664`
- `0x18000d794`
- `0x18000db48`

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
0x18000d794  mov     [rsp+arg_0], rbx
0x18000d799  mov     [rsp+arg_8], rsi
0x18000d79e  push    rdi
0x18000d79f  sub     rsp, 20h
0x18000d7a3  mov     rdi, r8
0x18000d7a6  mov     ebx, edx
0x18000d7a8  mov     rsi, rcx
0x18000d7ab  cmp     edx, 1
0x18000d7ae  jnz     short loc_18000D7B5
0x18000d7b0  call    __security_init_cookie
0x18000d7b5  mov     r8, rdi; lpvReserved
0x18000d7b8  mov     edx, ebx; fdwReason
0x18000d7ba  mov     rcx, rsi; hinstDLL
0x18000d7bd  mov     rbx, [rsp+28h+arg_0]
0x18000d7c2  mov     rsi, [rsp+28h+arg_8]
0x18000d7c7  add     rsp, 20h
0x18000d7cb  pop     rdi
0x18000d7cc  jmp     dllmain_dispatch
```
