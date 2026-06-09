# _DllMainCRTStartup

- ea: `0x180005720`
- end: `0x18000575d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005720`
- `0x180005764`
- `0x180005a94`

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
0x180005720  mov     [rsp+arg_0], rbx
0x180005725  mov     [rsp+arg_8], rsi
0x18000572a  push    rdi
0x18000572b  sub     rsp, 20h
0x18000572f  mov     rdi, r8
0x180005732  mov     ebx, edx
0x180005734  mov     rsi, rcx
0x180005737  cmp     edx, 1
0x18000573a  jnz     short loc_180005741
0x18000573c  call    __security_init_cookie
0x180005741  mov     r8, rdi
0x180005744  mov     edx, ebx; fdwReason
0x180005746  mov     rcx, rsi; hinstDLL
0x180005749  mov     rbx, [rsp+28h+arg_0]
0x18000574e  mov     rsi, [rsp+28h+arg_8]
0x180005753  add     rsp, 20h
0x180005757  pop     rdi
0x180005758  jmp     __DllMainCRTStartup
```
