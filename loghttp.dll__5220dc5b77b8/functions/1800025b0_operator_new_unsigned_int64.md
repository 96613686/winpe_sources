# operator new(unsigned __int64)

- ea: `0x1800025b0`
- end: `0x1800025e9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001080`
- `0x180001cd0`
- `0x180003510`
- `0x180004640`

## callees

- `0x1800025b0`
- `0x180002b99`
- `0x180002ba5`

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
0x1800025b0  mov     [rsp+arg_0], rbx
0x1800025b5  push    rdi
0x1800025b6  sub     rsp, 20h
0x1800025ba  mov     rdi, rcx
0x1800025bd  jmp     short loc_1800025CE
0x1800025bf  mov     rcx, rdi; Size
0x1800025c2  call    _callnewh_0
0x1800025c7  test    eax, eax
0x1800025c9  jz      short loc_1800025DB
0x1800025cb  mov     rcx, rdi; Size
0x1800025ce  call    malloc_0
0x1800025d3  mov     rbx, rax
0x1800025d6  test    rax, rax
0x1800025d9  jz      short loc_1800025BF
0x1800025db  mov     rax, rbx
0x1800025de  mov     rbx, [rsp+28h+arg_0]
0x1800025e3  add     rsp, 20h
0x1800025e7  pop     rdi
0x1800025e8  retn
```
