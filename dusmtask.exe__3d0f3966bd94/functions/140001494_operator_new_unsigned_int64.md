# operator new(unsigned __int64)

- ea: `0x140001494`
- end: `0x1400014d0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000311c`
- `0x1400032b8`
- `0x140003438`
- `0x14000356c`

## callees

- `0x140001494`
- `0x140001aa8`
- `0x140001e06`
- `0x140001ed2`
- `0x140006d54`

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
0x140001494  push    rbx
0x140001496  sub     rsp, 20h
0x14000149a  mov     rbx, rcx
0x14000149d  jmp     short loc_1400014AE
0x14000149f  mov     rcx, rbx
0x1400014a2  call    _o__callnewh_0
0x1400014a7  test    eax, eax
0x1400014a9  jz      short loc_1400014BE
0x1400014ab  mov     rcx, rbx; Size
0x1400014ae  call    _o_malloc_0
0x1400014b3  test    rax, rax
0x1400014b6  jz      short loc_14000149F
0x1400014b8  add     rsp, 20h
0x1400014bc  pop     rbx
0x1400014bd  retn
0x1400014be  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400014c2  jz      short loc_1400014CA
0x1400014c4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400014ca  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
