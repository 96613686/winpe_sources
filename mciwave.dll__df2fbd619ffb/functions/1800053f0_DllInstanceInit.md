# DllInstanceInit

- ea: `0x1800053f0`
- end: `0x180005421`
- name: `DllInstanceInit`
- size: `49`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000118c`
- `0x1800053f0`
- `0x180005630`

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
0x1800053f0  mov     [rsp+arg_0], rbx
0x1800053f5  push    rdi
0x1800053f6  sub     rsp, 20h
0x1800053fa  mov     edi, edx
0x1800053fc  mov     rbx, rcx
0x1800053ff  mov     edx, 1
0x180005404  cmp     edi, edx
0x180005406  jnz     short loc_18000540D
0x180005408  call    _DllMainCRTStartupForGS2
0x18000540d  mov     edx, edi
0x18000540f  mov     rcx, rbx
0x180005412  mov     rbx, [rsp+28h+arg_0]
0x180005417  add     rsp, 20h
0x18000541b  pop     rdi
0x18000541c  jmp     _DllInstanceInit
```
