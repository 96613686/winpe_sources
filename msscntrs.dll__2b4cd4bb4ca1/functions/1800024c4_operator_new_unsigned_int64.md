# operator new(unsigned __int64)

- ea: `0x1800024c4`
- end: `0x180002500`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ce0`
- `0x180002c8c`
- `0x1800040bc`
- `0x18000b0cc`
- `0x18000b258`
- `0x180010a34`

## callees

- `0x1800024c4`
- `0x180002f18`
- `0x18000325e`
- `0x1800032f0`
- `0x18000a410`

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
0x1800024c4  push    rbx
0x1800024c6  sub     rsp, 20h
0x1800024ca  mov     rbx, rcx
0x1800024cd  jmp     short loc_1800024DE
0x1800024cf  mov     rcx, rbx
0x1800024d2  call    _o__callnewh_0
0x1800024d7  test    eax, eax
0x1800024d9  jz      short loc_1800024EE
0x1800024db  mov     rcx, rbx; Size
0x1800024de  call    _o_malloc_0
0x1800024e3  test    rax, rax
0x1800024e6  jz      short loc_1800024CF
0x1800024e8  add     rsp, 20h
0x1800024ec  pop     rbx
0x1800024ed  retn
0x1800024ee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800024f2  jz      short loc_1800024FA
0x1800024f4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800024fa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
