# operator new(unsigned __int64)

- ea: `0x1400021c0`
- end: `0x1400021fc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000316c`
- `0x14000422c`
- `0x140004390`
- `0x14000e3b8`
- `0x14000f8d0`

## callees

- `0x1400021c0`
- `0x1400027b8`
- `0x140002b16`
- `0x140002bf0`
- `0x14000ce78`

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
0x1400021c0  push    rbx
0x1400021c2  sub     rsp, 20h
0x1400021c6  mov     rbx, rcx
0x1400021c9  jmp     short loc_1400021DA
0x1400021cb  mov     rcx, rbx
0x1400021ce  call    _o__callnewh_0
0x1400021d3  test    eax, eax
0x1400021d5  jz      short loc_1400021EA
0x1400021d7  mov     rcx, rbx; Size
0x1400021da  call    _o_malloc_0
0x1400021df  test    rax, rax
0x1400021e2  jz      short loc_1400021CB
0x1400021e4  add     rsp, 20h
0x1400021e8  pop     rbx
0x1400021e9  retn
0x1400021ea  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400021ee  jz      short loc_1400021F6
0x1400021f0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400021f6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
