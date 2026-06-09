# _DllMainCRTStartup

- ea: `0x180006740`
- end: `0x18000677d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006740`
- `0x180006784`
- `0x180006c74`

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
0x180006740  mov     [rsp+arg_0], rbx
0x180006745  mov     [rsp+arg_8], rsi
0x18000674a  push    rdi
0x18000674b  sub     rsp, 20h
0x18000674f  mov     rdi, r8
0x180006752  mov     ebx, edx
0x180006754  mov     rsi, rcx
0x180006757  cmp     edx, 1
0x18000675a  jnz     short loc_180006761
0x18000675c  call    __security_init_cookie
0x180006761  mov     r8, rdi
0x180006764  mov     edx, ebx; fdwReason
0x180006766  mov     rcx, rsi; hinstDLL
0x180006769  mov     rbx, [rsp+28h+arg_0]
0x18000676e  mov     rsi, [rsp+28h+arg_8]
0x180006773  add     rsp, 20h
0x180006777  pop     rdi
0x180006778  jmp     __DllMainCRTStartup
```
