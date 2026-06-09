# operator new(unsigned __int64)

- ea: `0x18000686c`
- end: `0x1800068a5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c10`
- `0x180008c30`

## callees

- `0x18000686c`
- `0x180006dc6`
- `0x180006dd2`

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
0x18000686c  mov     [rsp+arg_0], rbx
0x180006871  push    rdi
0x180006872  sub     rsp, 20h
0x180006876  mov     rdi, rcx
0x180006879  jmp     short loc_18000688A
0x18000687b  mov     rcx, rdi; Size
0x18000687e  call    _callnewh_0
0x180006883  test    eax, eax
0x180006885  jz      short loc_180006897
0x180006887  mov     rcx, rdi; Size
0x18000688a  call    malloc_0
0x18000688f  mov     rbx, rax
0x180006892  test    rax, rax
0x180006895  jz      short loc_18000687B
0x180006897  mov     rax, rbx
0x18000689a  mov     rbx, [rsp+28h+arg_0]
0x18000689f  add     rsp, 20h
0x1800068a3  pop     rdi
0x1800068a4  retn
```
