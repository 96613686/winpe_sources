# operator new(unsigned __int64)

- ea: `0x180005438`
- end: `0x180005474`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b68`
- `0x180003e50`
- `0x18000547c`

## callees

- `0x180005438`
- `0x1800059d4`
- `0x1800059fc`
- `0x180005a86`
- `0x180005b20`

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
0x180005438  push    rbx
0x18000543a  sub     rsp, 20h
0x18000543e  mov     rbx, rcx
0x180005441  jmp     short loc_180005452
0x180005443  mov     rcx, rbx
0x180005446  call    _o__callnewh_0
0x18000544b  test    eax, eax
0x18000544d  jz      short loc_180005462
0x18000544f  mov     rcx, rbx; Size
0x180005452  call    _o_malloc_0
0x180005457  test    rax, rax
0x18000545a  jz      short loc_180005443
0x18000545c  add     rsp, 20h
0x180005460  pop     rbx
0x180005461  retn
0x180005462  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005466  jz      short loc_18000546E
0x180005468  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000546e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
