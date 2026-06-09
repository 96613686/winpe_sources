# operator new(unsigned __int64)

- ea: `0x1800088bc`
- end: `0x1800088f5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d20`
- `0x180002fc0`
- `0x180006f50`
- `0x180009fa0`
- `0x18000a9d8`
- `0x18000ae64`
- `0x18000b230`

## callees

- `0x1800088bc`
- `0x180008de2`
- `0x180008dee`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x1800088bc  mov     [rsp+arg_0], rbx
0x1800088c1  push    rdi
0x1800088c2  sub     rsp, 20h
0x1800088c6  mov     rdi, rcx
0x1800088c9  jmp     short loc_1800088DA
0x1800088cb  mov     rcx, rdi; Size
0x1800088ce  call    _callnewh_0
0x1800088d3  test    eax, eax
0x1800088d5  jz      short loc_1800088E7
0x1800088d7  mov     rcx, rdi; Size
0x1800088da  call    malloc_0
0x1800088df  mov     rbx, rax
0x1800088e2  test    rax, rax
0x1800088e5  jz      short loc_1800088CB
0x1800088e7  mov     rax, rbx
0x1800088ea  mov     rbx, [rsp+28h+arg_0]
0x1800088ef  add     rsp, 20h
0x1800088f3  pop     rdi
0x1800088f4  retn
```
