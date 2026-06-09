# operator new(unsigned __int64)

- ea: `0x180003280`
- end: `0x1800032bc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002cd4`
- `0x180004338`
- `0x180004b3c`

## callees

- `0x180003280`
- `0x1800036e4`
- `0x18000370c`
- `0x1800037d8`
- `0x180003860`

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
0x180003280  push    rbx
0x180003282  sub     rsp, 20h
0x180003286  mov     rbx, rcx
0x180003289  jmp     short loc_18000329A
0x18000328b  mov     rcx, rbx
0x18000328e  call    _o__callnewh_0
0x180003293  test    eax, eax
0x180003295  jz      short loc_1800032AA
0x180003297  mov     rcx, rbx; Size
0x18000329a  call    _o_malloc_0
0x18000329f  test    rax, rax
0x1800032a2  jz      short loc_18000328B
0x1800032a4  add     rsp, 20h
0x1800032a8  pop     rbx
0x1800032a9  retn
0x1800032aa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800032ae  jz      short loc_1800032B6
0x1800032b0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800032b6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
