# _DllMainCRTStartup

- ea: `0x180001640`
- end: `0x18000167d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001640`
- `0x180001684`
- `0x180001e54`

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
0x180001640  mov     [rsp+arg_0], rbx
0x180001645  mov     [rsp+arg_8], rsi
0x18000164a  push    rdi
0x18000164b  sub     rsp, 20h
0x18000164f  mov     rdi, r8
0x180001652  mov     ebx, edx
0x180001654  mov     rsi, rcx
0x180001657  cmp     edx, 1
0x18000165a  jnz     short loc_180001661
0x18000165c  call    __security_init_cookie
0x180001661  mov     r8, rdi
0x180001664  mov     edx, ebx; fdwReason
0x180001666  mov     rcx, rsi; hinstDLL
0x180001669  mov     rbx, [rsp+28h+arg_0]
0x18000166e  mov     rsi, [rsp+28h+arg_8]
0x180001673  add     rsp, 20h
0x180001677  pop     rdi
0x180001678  jmp     __DllMainCRTStartup
```
