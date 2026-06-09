# _DllMainCRTStartup

- ea: `0x180001610`
- end: `0x18000164d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001610`
- `0x180001654`
- `0x180001df4`

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
0x180001610  mov     [rsp+arg_0], rbx
0x180001615  mov     [rsp+arg_8], rsi
0x18000161a  push    rdi
0x18000161b  sub     rsp, 20h
0x18000161f  mov     rdi, r8
0x180001622  mov     ebx, edx
0x180001624  mov     rsi, rcx
0x180001627  cmp     edx, 1
0x18000162a  jnz     short loc_180001631
0x18000162c  call    __security_init_cookie
0x180001631  mov     r8, rdi
0x180001634  mov     edx, ebx; fdwReason
0x180001636  mov     rcx, rsi; hinstDLL
0x180001639  mov     rbx, [rsp+28h+arg_0]
0x18000163e  mov     rsi, [rsp+28h+arg_8]
0x180001643  add     rsp, 20h
0x180001647  pop     rdi
0x180001648  jmp     __DllMainCRTStartup
```
