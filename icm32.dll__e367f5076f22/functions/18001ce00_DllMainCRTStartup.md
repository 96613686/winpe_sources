# _DllMainCRTStartup

- ea: `0x18001ce00`
- end: `0x18001ce3d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ce00`
- `0x18001ce44`
- `0x18001d16c`

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
0x18001ce00  mov     [rsp+arg_0], rbx
0x18001ce05  mov     [rsp+arg_8], rsi
0x18001ce0a  push    rdi
0x18001ce0b  sub     rsp, 20h
0x18001ce0f  mov     rdi, r8
0x18001ce12  mov     ebx, edx
0x18001ce14  mov     rsi, rcx
0x18001ce17  cmp     edx, 1
0x18001ce1a  jnz     short loc_18001CE21
0x18001ce1c  call    __security_init_cookie
0x18001ce21  mov     r8, rdi
0x18001ce24  mov     edx, ebx; fdwReason
0x18001ce26  mov     rcx, rsi; hinstDLL
0x18001ce29  mov     rbx, [rsp+28h+arg_0]
0x18001ce2e  mov     rsi, [rsp+28h+arg_8]
0x18001ce33  add     rsp, 20h
0x18001ce37  pop     rdi
0x18001ce38  jmp     __DllMainCRTStartup
```
