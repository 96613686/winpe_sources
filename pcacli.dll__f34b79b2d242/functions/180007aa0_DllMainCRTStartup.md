# _DllMainCRTStartup

- ea: `0x180007aa0`
- end: `0x180007add`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007aa0`
- `0x180007ae4`
- `0x180008104`

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
0x180007aa0  mov     [rsp+arg_0], rbx
0x180007aa5  mov     [rsp+arg_8], rsi
0x180007aaa  push    rdi
0x180007aab  sub     rsp, 20h
0x180007aaf  mov     rdi, r8
0x180007ab2  mov     ebx, edx
0x180007ab4  mov     rsi, rcx
0x180007ab7  cmp     edx, 1
0x180007aba  jnz     short loc_180007AC1
0x180007abc  call    __security_init_cookie
0x180007ac1  mov     r8, rdi
0x180007ac4  mov     edx, ebx; fdwReason
0x180007ac6  mov     rcx, rsi; hinstDLL
0x180007ac9  mov     rbx, [rsp+28h+arg_0]
0x180007ace  mov     rsi, [rsp+28h+arg_8]
0x180007ad3  add     rsp, 20h
0x180007ad7  pop     rdi
0x180007ad8  jmp     __DllMainCRTStartup
```
