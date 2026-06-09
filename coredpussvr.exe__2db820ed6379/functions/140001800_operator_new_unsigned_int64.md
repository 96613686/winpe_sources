# operator new(unsigned __int64)

- ea: `0x140001800`
- end: `0x14000183c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400017cc`
- `0x140001844`
- `0x140006b40`

## callees

- `0x140001800`
- `0x140001f64`
- `0x140001f8c`
- `0x14000203a`
- `0x140002120`

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
0x140001800  push    rbx
0x140001802  sub     rsp, 20h
0x140001806  mov     rbx, rcx
0x140001809  jmp     short loc_14000181A
0x14000180b  mov     rcx, rbx
0x14000180e  call    _o__callnewh_0
0x140001813  test    eax, eax
0x140001815  jz      short loc_14000182A
0x140001817  mov     rcx, rbx; Size
0x14000181a  call    _o_malloc_0
0x14000181f  test    rax, rax
0x140001822  jz      short loc_14000180B
0x140001824  add     rsp, 20h
0x140001828  pop     rbx
0x140001829  retn
0x14000182a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000182e  jz      short loc_140001836
0x140001830  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001836  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
