# operator new(unsigned __int64)

- ea: `0x180002110`
- end: `0x18000214c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `13`
- callee_count: `5`
- tags: ``

## callers

- `0x180002084`
- `0x180002160`
- `0x180006140`
- `0x180006648`
- `0x180009740`
- `0x180010154`
- `0x180010294`
- `0x180012444`
- `0x180012b94`
- `0x180015530`
- `0x1800157d0`
- `0x180017898`
- `0x1800180ac`

## callees

- `0x180001dca`
- `0x180001e4e`
- `0x180002110`
- `0x180002194`
- `0x180009624`

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
0x180002110  push    rbx
0x180002112  sub     rsp, 20h
0x180002116  mov     rbx, rcx
0x180002119  jmp     short loc_18000212A
0x18000211b  mov     rcx, rbx
0x18000211e  call    _o__callnewh_0
0x180002123  test    eax, eax
0x180002125  jz      short loc_18000213A
0x180002127  mov     rcx, rbx; Size
0x18000212a  call    _o_malloc_0
0x18000212f  test    rax, rax
0x180002132  jz      short loc_18000211B
0x180002134  add     rsp, 20h
0x180002138  pop     rbx
0x180002139  retn
0x18000213a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000213e  jz      short loc_180002146
0x180002140  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002146  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
