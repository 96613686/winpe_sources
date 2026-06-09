# operator new(unsigned __int64)

- ea: `0x1800018e8`
- end: `0x180001921`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800027f8`

## callees

- `0x1800015dd`
- `0x1800018e8`
- `0x180001933`

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
0x1800018e8  mov     [rsp+arg_0], rbx
0x1800018ed  push    rdi
0x1800018ee  sub     rsp, 20h
0x1800018f2  mov     rdi, rcx
0x1800018f5  jmp     short loc_180001906
0x1800018f7  mov     rcx, rdi; Size
0x1800018fa  call    _callnewh_0
0x1800018ff  test    eax, eax
0x180001901  jz      short loc_180001913
0x180001903  mov     rcx, rdi; Size
0x180001906  call    malloc_0
0x18000190b  mov     rbx, rax
0x18000190e  test    rax, rax
0x180001911  jz      short loc_1800018F7
0x180001913  mov     rax, rbx
0x180001916  mov     rbx, [rsp+28h+arg_0]
0x18000191b  add     rsp, 20h
0x18000191f  pop     rdi
0x180001920  retn
```
