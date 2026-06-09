# operator new(unsigned __int64)

- ea: `0x180001534`
- end: `0x180001570`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001578`
- `0x180003ba0`
- `0x180007b00`

## callees

- `0x180001534`
- `0x180001c94`
- `0x180001cbc`
- `0x180002006`
- `0x1800020a0`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001534  push    rbx
0x180001536  sub     rsp, 20h
0x18000153a  mov     rbx, rcx
0x18000153d  jmp     short loc_18000154E
0x18000153f  mov     rcx, rbx
0x180001542  call    _o__callnewh_0
0x180001547  test    eax, eax
0x180001549  jz      short loc_18000155E
0x18000154b  mov     rcx, rbx; Size
0x18000154e  call    _o_malloc_0
0x180001553  test    rax, rax
0x180001556  jz      short loc_18000153F
0x180001558  add     rsp, 20h
0x18000155c  pop     rbx
0x18000155d  retn
0x18000155e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001562  jz      short loc_18000156A
0x180001564  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000156a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
