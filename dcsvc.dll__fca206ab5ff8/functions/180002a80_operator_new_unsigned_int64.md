# operator new(unsigned __int64)

- ea: `0x180002a80`
- end: `0x180002abc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180001880`
- `0x180002a5c`
- `0x18000f238`
- `0x18000f428`
- `0x18000f6c8`
- `0x18000f798`
- `0x18000fcfc`

## callees

- `0x180002612`
- `0x1800026b0`
- `0x180002a80`
- `0x180002aec`
- `0x1800118bc`

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
0x180002a80  push    rbx
0x180002a82  sub     rsp, 20h
0x180002a86  mov     rbx, rcx
0x180002a89  jmp     short loc_180002A9A
0x180002a8b  mov     rcx, rbx
0x180002a8e  call    _o__callnewh_0
0x180002a93  test    eax, eax
0x180002a95  jz      short loc_180002AAA
0x180002a97  mov     rcx, rbx; Size
0x180002a9a  call    _o_malloc_0
0x180002a9f  test    rax, rax
0x180002aa2  jz      short loc_180002A8B
0x180002aa4  add     rsp, 20h
0x180002aa8  pop     rbx
0x180002aa9  retn
0x180002aaa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002aae  jz      short loc_180002AB6
0x180002ab0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002ab6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
