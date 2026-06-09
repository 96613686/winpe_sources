# operator new(unsigned __int64)

- ea: `0x1800015b0`
- end: `0x1800015e9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002320`

## callees

- `0x1800015b0`
- `0x180001ad2`
- `0x180001ade`

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
0x1800015b0  mov     [rsp+arg_0], rbx
0x1800015b5  push    rdi
0x1800015b6  sub     rsp, 20h
0x1800015ba  mov     rdi, rcx
0x1800015bd  jmp     short loc_1800015CE
0x1800015bf  mov     rcx, rdi; Size
0x1800015c2  call    _callnewh_0
0x1800015c7  test    eax, eax
0x1800015c9  jz      short loc_1800015DB
0x1800015cb  mov     rcx, rdi; Size
0x1800015ce  call    malloc_0
0x1800015d3  mov     rbx, rax
0x1800015d6  test    rax, rax
0x1800015d9  jz      short loc_1800015BF
0x1800015db  mov     rax, rbx
0x1800015de  mov     rbx, [rsp+28h+arg_0]
0x1800015e3  add     rsp, 20h
0x1800015e7  pop     rdi
0x1800015e8  retn
```
