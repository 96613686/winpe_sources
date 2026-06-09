# operator new(unsigned __int64)

- ea: `0x14000190c`
- end: `0x140001948`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x1400021f0`
- `0x140002214`
- `0x14000e454`
- `0x14000e854`
- `0x14000f48c`
- `0x14000fea4`
- `0x140011224`
- `0x140011650`
- `0x14001176c`
- `0x140012748`
- `0x140012c08`
- `0x140016900`
- `0x140016d70`
- `0x140017880`
- `0x140018290`
- `0x140018438`
- `0x140018634`
- `0x140018b78`
- `0x140018f8c`
- `0x1400191ec`

## callees

- `0x14000190c`
- `0x140001ef4`
- `0x140001fc2`
- `0x1400020a0`
- `0x140014548`

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
0x14000190c  push    rbx
0x14000190e  sub     rsp, 20h
0x140001912  mov     rbx, rcx
0x140001915  jmp     short loc_140001926
0x140001917  mov     rcx, rbx
0x14000191a  call    _o__callnewh_0
0x14000191f  test    eax, eax
0x140001921  jz      short loc_140001936
0x140001923  mov     rcx, rbx; Size
0x140001926  call    _o_malloc_0
0x14000192b  test    rax, rax
0x14000192e  jz      short loc_140001917
0x140001930  add     rsp, 20h
0x140001934  pop     rbx
0x140001935  retn
0x140001936  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000193a  jz      short loc_140001942
0x14000193c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001942  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
