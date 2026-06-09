# DllInstanceInit

- ea: `0x180002280`
- end: `0x1800022b1`
- name: `DllInstanceInit`
- size: `49`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x180002280`
- `0x180002590`

## pseudocode

```c
BOOL __stdcall DllInstanceInit(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    DllMainCRTStartupForGS2((__int64)hinstDLL, 1);
  return DllInstanceInit(hinstDLL, fdwReason);
}

```

## disassembly

```asm
0x180002280  mov     [rsp+arg_0], rbx
0x180002285  push    rdi
0x180002286  sub     rsp, 20h
0x18000228a  mov     edi, edx
0x18000228c  mov     rbx, rcx
0x18000228f  mov     edx, 1
0x180002294  cmp     edi, edx
0x180002296  jnz     short loc_18000229D
0x180002298  call    _DllMainCRTStartupForGS2
0x18000229d  mov     edx, edi
0x18000229f  mov     rcx, rbx; hLibModule
0x1800022a2  mov     rbx, [rsp+28h+arg_0]
0x1800022a7  add     rsp, 20h
0x1800022ab  pop     rdi
0x1800022ac  jmp     _DllInstanceInit
```
