# _DllMainCRTStartup

- ea: `0x180002ad0`
- end: `0x180002b0d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180002b14`
- `0x180003644`

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
0x180002ad0  mov     [rsp+arg_0], rbx
0x180002ad5  mov     [rsp+arg_8], rsi
0x180002ada  push    rdi
0x180002adb  sub     rsp, 20h
0x180002adf  mov     rdi, r8
0x180002ae2  mov     ebx, edx
0x180002ae4  mov     rsi, rcx
0x180002ae7  cmp     edx, 1
0x180002aea  jnz     short loc_180002AF1
0x180002aec  call    __security_init_cookie
0x180002af1  mov     r8, rdi
0x180002af4  mov     edx, ebx; fdwReason
0x180002af6  mov     rcx, rsi; hinstDLL
0x180002af9  mov     rbx, [rsp+28h+arg_0]
0x180002afe  mov     rsi, [rsp+28h+arg_8]
0x180002b03  add     rsp, 20h
0x180002b07  pop     rdi
0x180002b08  jmp     __DllMainCRTStartup
```
