# operator new(unsigned __int64)

- ea: `0x18000116c`
- end: `0x1800011a5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002db0`
- `0x180002e60`
- `0x180003930`

## callees

- `0x18000116c`
- `0x18000193c`
- `0x180001948`

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
0x18000116c  mov     [rsp+arg_0], rbx
0x180001171  push    rdi
0x180001172  sub     rsp, 20h
0x180001176  mov     rdi, rcx
0x180001179  jmp     short loc_18000118A
0x18000117b  mov     rcx, rdi; Size
0x18000117e  call    _callnewh_0
0x180001183  test    eax, eax
0x180001185  jz      short loc_180001197
0x180001187  mov     rcx, rdi; Size
0x18000118a  call    malloc_0
0x18000118f  mov     rbx, rax
0x180001192  test    rax, rax
0x180001195  jz      short loc_18000117B
0x180001197  mov     rax, rbx
0x18000119a  mov     rbx, [rsp+28h+arg_0]
0x18000119f  add     rsp, 20h
0x1800011a3  pop     rdi
0x1800011a4  retn
```
