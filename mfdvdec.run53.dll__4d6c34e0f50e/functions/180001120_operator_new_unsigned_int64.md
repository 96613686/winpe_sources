# operator new(unsigned __int64)

- ea: `0x180001120`
- end: `0x180001159`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000116c`
- `0x180002370`
- `0x180004818`
- `0x180007bc0`
- `0x180007ef0`
- `0x18000872c`
- `0x180009404`
- `0x1800094b8`

## callees

- `0x180001120`
- `0x180001dfa`
- `0x180001e80`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001120  mov     [rsp+arg_0], rbx
0x180001125  push    rdi
0x180001126  sub     rsp, 20h
0x18000112a  mov     rdi, rcx
0x18000112d  jmp     short loc_18000113E
0x18000112f  mov     rcx, rdi
0x180001132  call    _o__callnewh_0
0x180001137  test    eax, eax
0x180001139  jz      short loc_18000114B
0x18000113b  mov     rcx, rdi; Size
0x18000113e  call    _o_malloc_0
0x180001143  mov     rbx, rax
0x180001146  test    rax, rax
0x180001149  jz      short loc_18000112F
0x18000114b  mov     rax, rbx
0x18000114e  mov     rbx, [rsp+28h+arg_0]
0x180001153  add     rsp, 20h
0x180001157  pop     rdi
0x180001158  retn
```
