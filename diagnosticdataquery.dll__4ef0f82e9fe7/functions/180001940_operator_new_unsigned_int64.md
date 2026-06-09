# operator new(unsigned __int64)

- ea: `0x180001940`
- end: `0x18000197c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180009680`
- `0x1800097b0`
- `0x180009a20`
- `0x180009b50`
- `0x180009f60`

## callees

- `0x180001940`
- `0x180001f54`
- `0x180001f7c`
- `0x18000512e`
- `0x18000513a`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
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
0x180001940  push    rbx
0x180001942  sub     rsp, 20h
0x180001946  mov     rbx, rcx
0x180001949  jmp     short loc_18000195A
0x18000194b  mov     rcx, rbx; Size
0x18000194e  call    _callnewh_0
0x180001953  test    eax, eax
0x180001955  jz      short loc_18000196A
0x180001957  mov     rcx, rbx; Size
0x18000195a  call    malloc_0
0x18000195f  test    rax, rax
0x180001962  jz      short loc_18000194B
0x180001964  add     rsp, 20h
0x180001968  pop     rbx
0x180001969  retn
0x18000196a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000196e  jz      short loc_180001976
0x180001970  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001976  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
