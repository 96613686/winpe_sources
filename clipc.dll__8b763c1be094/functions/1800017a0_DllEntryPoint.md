# DllEntryPoint

- ea: `0x1800017a0`
- end: `0x1800017dd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001664`
- `0x1800017a0`
- `0x180001c1c`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180001C1C();
  return sub_180001664(hinstDLL);
}

```

## disassembly

```asm
0x1800017a0  mov     [rsp+arg_0], rbx
0x1800017a5  mov     [rsp+arg_8], rsi
0x1800017aa  push    rdi
0x1800017ab  sub     rsp, 20h
0x1800017af  mov     rdi, r8
0x1800017b2  mov     ebx, edx
0x1800017b4  mov     rsi, rcx
0x1800017b7  cmp     edx, 1
0x1800017ba  jnz     short loc_1800017C1
0x1800017bc  call    sub_180001C1C
0x1800017c1  mov     r8, rdi
0x1800017c4  mov     edx, ebx
0x1800017c6  mov     rcx, rsi; hLibModule
0x1800017c9  mov     rbx, [rsp+28h+arg_0]
0x1800017ce  mov     rsi, [rsp+28h+arg_8]
0x1800017d3  add     rsp, 20h
0x1800017d7  pop     rdi
0x1800017d8  jmp     sub_180001664
```
