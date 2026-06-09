# operator new(unsigned __int64)

- ea: `0x18000b828`
- end: `0x18000b864`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180005fd0`
- `0x180006228`
- `0x180008c40`
- `0x180008f38`
- `0x18000b81c`
- `0x18000eb4c`
- `0x18000f68c`
- `0x18000f8b0`
- `0x180011934`

## callees

- `0x18000b828`
- `0x18000bd04`
- `0x18000bd2c`
- `0x18000bdce`
- `0x18000be60`

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
0x18000b828  push    rbx
0x18000b82a  sub     rsp, 20h
0x18000b82e  mov     rbx, rcx
0x18000b831  jmp     short loc_18000B842
0x18000b833  mov     rcx, rbx
0x18000b836  call    _o__callnewh_0
0x18000b83b  test    eax, eax
0x18000b83d  jz      short loc_18000B852
0x18000b83f  mov     rcx, rbx; Size
0x18000b842  call    _o_malloc_0
0x18000b847  test    rax, rax
0x18000b84a  jz      short loc_18000B833
0x18000b84c  add     rsp, 20h
0x18000b850  pop     rbx
0x18000b851  retn
0x18000b852  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b856  jz      short loc_18000B85E
0x18000b858  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000b85e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
