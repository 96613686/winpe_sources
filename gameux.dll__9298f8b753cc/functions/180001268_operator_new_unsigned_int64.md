# operator new(unsigned __int64)

- ea: `0x180001268`
- end: `0x1800012a1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f44`
- `0x18000203c`
- `0x180002110`
- `0x180002788`
- `0x180002864`
- `0x180002914`

## callees

- `0x180001268`
- `0x180001861`
- `0x18000186d`

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
0x180001268  mov     [rsp+arg_0], rbx
0x18000126d  push    rdi
0x18000126e  sub     rsp, 20h
0x180001272  mov     rdi, rcx
0x180001275  jmp     short loc_180001286
0x180001277  mov     rcx, rdi; Size
0x18000127a  call    _callnewh_0
0x18000127f  test    eax, eax
0x180001281  jz      short loc_180001293
0x180001283  mov     rcx, rdi; Size
0x180001286  call    malloc_0
0x18000128b  mov     rbx, rax
0x18000128e  test    rax, rax
0x180001291  jz      short loc_180001277
0x180001293  mov     rax, rbx
0x180001296  mov     rbx, [rsp+28h+arg_0]
0x18000129b  add     rsp, 20h
0x18000129f  pop     rdi
0x1800012a0  retn
```
