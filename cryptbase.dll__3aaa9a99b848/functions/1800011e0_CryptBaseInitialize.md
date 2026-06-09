# CryptBaseInitialize

- ea: `0x1800011e0`
- end: `0x180001219`
- name: `CryptBaseInitialize`
- size: `57`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800011e0`
- `0x180001220`
- `0x1800025a8`

## pseudocode

```c
BOOL __stdcall CryptBaseInitialize(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    DllMainCRTStartupForGS2((__int64)hinstDLL, 1);
  return (unsigned __int8)CryptBaseInitialize(hinstDLL, fdwReason);
}

```

## disassembly

```asm
0x1800011e0  mov     [rsp+arg_0], rbx
0x1800011e5  push    rdi
0x1800011e6  sub     rsp, 20h
0x1800011ea  mov     ebx, edx
0x1800011ec  mov     rdi, rcx
0x1800011ef  cmp     edx, 1
0x1800011f2  jz      short loc_18000120D
0x1800011f4  mov     edx, ebx
0x1800011f6  mov     rcx, rdi
0x1800011f9  call    _CryptBaseInitialize
0x1800011fe  mov     rbx, [rsp+28h+arg_0]
0x180001203  movzx   eax, al
0x180001206  add     rsp, 20h
0x18000120a  pop     rdi
0x18000120b  retn
0x18000120d  mov     edx, 1
0x180001212  call    _DllMainCRTStartupForGS2
0x180001217  jmp     short loc_1800011F4
```
