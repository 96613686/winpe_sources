# _DllMainCRTStartup

- ea: `0x18000f490`
- end: `0x18000f4cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f490`
- `0x18000f4d4`
- `0x18000fac4`

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
0x18000f490  mov     [rsp+arg_0], rbx
0x18000f495  mov     [rsp+arg_8], rsi
0x18000f49a  push    rdi
0x18000f49b  sub     rsp, 20h
0x18000f49f  mov     rdi, r8
0x18000f4a2  mov     ebx, edx
0x18000f4a4  mov     rsi, rcx
0x18000f4a7  cmp     edx, 1
0x18000f4aa  jnz     short loc_18000F4B1
0x18000f4ac  call    __security_init_cookie
0x18000f4b1  mov     r8, rdi
0x18000f4b4  mov     edx, ebx; fdwReason
0x18000f4b6  mov     rcx, rsi; hinstDLL
0x18000f4b9  mov     rbx, [rsp+28h+arg_0]
0x18000f4be  mov     rsi, [rsp+28h+arg_8]
0x18000f4c3  add     rsp, 20h
0x18000f4c7  pop     rdi
0x18000f4c8  jmp     __DllMainCRTStartup
```
