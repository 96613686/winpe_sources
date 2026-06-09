# operator new(unsigned __int64)

- ea: `0x140001290`
- end: `0x1400012c9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140002010`
- `0x140004cfc`
- `0x140005460`
- `0x140005a4c`

## callees

- `0x140001290`
- `0x1400016b2`
- `0x1400016be`

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
0x140001290  mov     [rsp+arg_0], rbx
0x140001295  push    rdi
0x140001296  sub     rsp, 20h
0x14000129a  mov     rdi, rcx
0x14000129d  jmp     short loc_1400012AE
0x14000129f  mov     rcx, rdi; Size
0x1400012a2  call    _callnewh_0
0x1400012a7  test    eax, eax
0x1400012a9  jz      short loc_1400012BB
0x1400012ab  mov     rcx, rdi; Size
0x1400012ae  call    malloc_0
0x1400012b3  mov     rbx, rax
0x1400012b6  test    rax, rax
0x1400012b9  jz      short loc_14000129F
0x1400012bb  mov     rax, rbx
0x1400012be  mov     rbx, [rsp+28h+arg_0]
0x1400012c3  add     rsp, 20h
0x1400012c7  pop     rdi
0x1400012c8  retn
```
