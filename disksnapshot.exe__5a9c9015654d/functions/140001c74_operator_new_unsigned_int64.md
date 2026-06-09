# operator new(unsigned __int64)

- ea: `0x140001c74`
- end: `0x140001cb0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `18`
- callee_count: `5`
- tags: ``

## callers

- `0x140001d20`
- `0x140002c84`
- `0x140002d90`
- `0x140004dc8`
- `0x140004fec`
- `0x1400052b0`
- `0x14000549c`
- `0x14000588c`
- `0x140005bd0`
- `0x140006424`
- `0x140006c30`
- `0x140007c84`
- `0x1400082d0`
- `0x140008a38`
- `0x140009ee0`
- `0x14000ae5c`
- `0x14000b144`
- `0x14000c310`

## callees

- `0x140001c74`
- `0x1400025d0`
- `0x1400026ca`
- `0x14000278a`
- `0x140003580`

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
0x140001c74  push    rbx
0x140001c76  sub     rsp, 20h
0x140001c7a  mov     rbx, rcx
0x140001c7d  jmp     short loc_140001C8E
0x140001c7f  mov     rcx, rbx
0x140001c82  call    _o__callnewh_0
0x140001c87  test    eax, eax
0x140001c89  jz      short loc_140001C9E
0x140001c8b  mov     rcx, rbx; Size
0x140001c8e  call    _o_malloc_0
0x140001c93  test    rax, rax
0x140001c96  jz      short loc_140001C7F
0x140001c98  add     rsp, 20h
0x140001c9c  pop     rbx
0x140001c9d  retn
0x140001c9e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140001ca2  jz      short loc_140001CAA
0x140001ca4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001caa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
