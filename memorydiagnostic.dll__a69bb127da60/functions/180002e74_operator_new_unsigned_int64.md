# operator new(unsigned __int64)

- ea: `0x180002e74`
- end: `0x180002eb0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x180002eb8`
- `0x1800032cc`
- `0x180005e78`
- `0x180006210`
- `0x180006eec`
- `0x18000b238`
- `0x18001a890`
- `0x18001a930`
- `0x18001a9e4`
- `0x18001de90`
- `0x18001fa10`

## callees

- `0x180002e74`
- `0x1800037c0`
- `0x180003872`
- `0x180003910`
- `0x1800156a0`

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
0x180002e74  push    rbx
0x180002e76  sub     rsp, 20h
0x180002e7a  mov     rbx, rcx
0x180002e7d  jmp     short loc_180002E8E
0x180002e7f  mov     rcx, rbx
0x180002e82  call    _o__callnewh_0
0x180002e87  test    eax, eax
0x180002e89  jz      short loc_180002E9E
0x180002e8b  mov     rcx, rbx; Size
0x180002e8e  call    _o_malloc_0
0x180002e93  test    rax, rax
0x180002e96  jz      short loc_180002E7F
0x180002e98  add     rsp, 20h
0x180002e9c  pop     rbx
0x180002e9d  retn
0x180002e9e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002ea2  jz      short loc_180002EAA
0x180002ea4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002eaa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
