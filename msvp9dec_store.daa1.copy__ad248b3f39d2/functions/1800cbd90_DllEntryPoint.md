# DllEntryPoint

- ea: `0x1800cbd90`
- end: `0x1800cbdcd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800cbc54`
- `0x1800cbd90`
- `0x1800cc520`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_1800CC520();
  return sub_1800CBC54(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1800cbd90  mov     [rsp+arg_0], rbx
0x1800cbd95  mov     [rsp+arg_8], rsi
0x1800cbd9a  push    rdi
0x1800cbd9b  sub     rsp, 20h
0x1800cbd9f  mov     rdi, r8
0x1800cbda2  mov     ebx, edx
0x1800cbda4  mov     rsi, rcx
0x1800cbda7  cmp     edx, 1
0x1800cbdaa  jnz     short loc_1800CBDB1
0x1800cbdac  call    sub_1800CC520
0x1800cbdb1  mov     r8, rdi
0x1800cbdb4  mov     edx, ebx
0x1800cbdb6  mov     rcx, rsi
0x1800cbdb9  mov     rbx, [rsp+28h+arg_0]
0x1800cbdbe  mov     rsi, [rsp+28h+arg_8]
0x1800cbdc3  add     rsp, 20h
0x1800cbdc7  pop     rdi
0x1800cbdc8  jmp     sub_1800CBC54
```
