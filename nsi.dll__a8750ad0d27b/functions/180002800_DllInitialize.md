# DllInitialize

- ea: `0x180002800`
- end: `0x18000282d`
- name: `DllInitialize`
- size: `45`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002800`
- `0x180002840`
- `0x1800028b8`

## pseudocode

```c
BOOL __stdcall DllInitialize(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    DllMainCRTStartupForGS2((__int64)hinstDLL, 1);
  return DllInitialize(hinstDLL, fdwReason);
}

```

## disassembly

```asm
0x180002800  mov     [rsp+arg_0], rbx
0x180002805  push    rdi
0x180002806  sub     rsp, 20h
0x18000280a  mov     edi, edx
0x18000280c  mov     rbx, rcx
0x18000280f  cmp     edx, 1
0x180002812  jnz     short loc_180002819
0x180002814  call    _DllMainCRTStartupForGS2
0x180002819  mov     edx, edi
0x18000281b  mov     rcx, rbx
0x18000281e  mov     rbx, [rsp+28h+arg_0]
0x180002823  add     rsp, 20h
0x180002827  pop     rdi
0x180002828  jmp     _DllInitialize
```
