# operator new(unsigned __int64)

- ea: `0x18000210c`
- end: `0x180002148`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180001850`
- `0x1800028dc`
- `0x1800070e0`
- `0x180007680`
- `0x180009790`
- `0x18000bd98`

## callees

- `0x18000210c`
- `0x1800025f4`
- `0x180002692`
- `0x180002716`
- `0x180007270`

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
0x18000210c  push    rbx
0x18000210e  sub     rsp, 20h
0x180002112  mov     rbx, rcx
0x180002115  jmp     short loc_180002126
0x180002117  mov     rcx, rbx
0x18000211a  call    _o__callnewh_0
0x18000211f  test    eax, eax
0x180002121  jz      short loc_180002136
0x180002123  mov     rcx, rbx; Size
0x180002126  call    _o_malloc_0
0x18000212b  test    rax, rax
0x18000212e  jz      short loc_180002117
0x180002130  add     rsp, 20h
0x180002134  pop     rbx
0x180002135  retn
0x180002136  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000213a  jz      short loc_180002142
0x18000213c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002142  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
