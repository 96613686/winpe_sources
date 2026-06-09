# operator new(unsigned __int64)

- ea: `0x1400022c4`
- end: `0x140002300`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400048b8`
- `0x1400049f8`
- `0x140004b84`
- `0x140004d34`
- `0x1400050cc`
- `0x1400051f8`
- `0x140010660`

## callees

- `0x1400022c4`
- `0x1400028c8`
- `0x140002c36`
- `0x140002d10`
- `0x1400103f0`

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
0x1400022c4  push    rbx
0x1400022c6  sub     rsp, 20h
0x1400022ca  mov     rbx, rcx
0x1400022cd  jmp     short loc_1400022DE
0x1400022cf  mov     rcx, rbx
0x1400022d2  call    _o__callnewh_0
0x1400022d7  test    eax, eax
0x1400022d9  jz      short loc_1400022EE
0x1400022db  mov     rcx, rbx; Size
0x1400022de  call    _o_malloc_0
0x1400022e3  test    rax, rax
0x1400022e6  jz      short loc_1400022CF
0x1400022e8  add     rsp, 20h
0x1400022ec  pop     rbx
0x1400022ed  retn
0x1400022ee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400022f2  jz      short loc_1400022FA
0x1400022f4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400022fa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
