# operator new(unsigned __int64)

- ea: `0x180001a0c`
- end: `0x180001a48`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a010`
- `0x18000a608`
- `0x18000b6c8`
- `0x18000b8c4`

## callees

- `0x180001a0c`
- `0x180001f20`
- `0x180001fd2`
- `0x180002056`
- `0x18000b520`

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
0x180001a0c  push    rbx
0x180001a0e  sub     rsp, 20h
0x180001a12  mov     rbx, rcx
0x180001a15  jmp     short loc_180001A26
0x180001a17  mov     rcx, rbx
0x180001a1a  call    _o__callnewh_0
0x180001a1f  test    eax, eax
0x180001a21  jz      short loc_180001A36
0x180001a23  mov     rcx, rbx; Size
0x180001a26  call    _o_malloc_0
0x180001a2b  test    rax, rax
0x180001a2e  jz      short loc_180001A17
0x180001a30  add     rsp, 20h
0x180001a34  pop     rbx
0x180001a35  retn
0x180001a36  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001a3a  jz      short loc_180001A42
0x180001a3c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001a42  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
