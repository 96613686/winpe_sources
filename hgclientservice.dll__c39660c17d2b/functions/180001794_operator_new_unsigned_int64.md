# operator new(unsigned __int64)

- ea: `0x180001794`
- end: `0x1800017d0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `28`
- callee_count: `5`
- tags: ``

## callers

- `0x1800017d8`
- `0x180002abc`
- `0x180003d0c`
- `0x180003e30`
- `0x180007920`
- `0x1800082f0`
- `0x1800091c0`
- `0x180009300`
- `0x18000b4c4`
- `0x18000b78c`
- `0x18000b8b0`
- `0x18000b990`
- `0x18000ba8c`
- `0x18000d4d8`
- `0x18000e670`
- `0x18000e7d8`
- `0x18000eaa4`
- `0x18000f1ac`
- `0x18000f814`
- `0x18000fe14`
- `0x180010e48`
- `0x180011274`
- `0x180011400`
- `0x180012234`
- `0x18001446c`
- `0x180014600`
- `0x18001486c`
- `0x180014c74`

## callees

- `0x180001794`
- `0x180001dd8`
- `0x180002126`
- `0x1800021cc`
- `0x1800073c4`

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
0x180001794  push    rbx
0x180001796  sub     rsp, 20h
0x18000179a  mov     rbx, rcx
0x18000179d  jmp     short loc_1800017AE
0x18000179f  mov     rcx, rbx
0x1800017a2  call    _o__callnewh_0
0x1800017a7  test    eax, eax
0x1800017a9  jz      short loc_1800017BE
0x1800017ab  mov     rcx, rbx; Size
0x1800017ae  call    _o_malloc_0
0x1800017b3  test    rax, rax
0x1800017b6  jz      short loc_18000179F
0x1800017b8  add     rsp, 20h
0x1800017bc  pop     rbx
0x1800017bd  retn
0x1800017be  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800017c2  jz      short loc_1800017CA
0x1800017c4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800017ca  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
