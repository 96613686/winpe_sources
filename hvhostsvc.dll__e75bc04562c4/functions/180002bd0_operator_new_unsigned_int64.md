# operator new(unsigned __int64)

- ea: `0x180002bd0`
- end: `0x180002c0c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000195c`
- `0x180001a80`
- `0x180002d58`
- `0x1800069f4`
- `0x180006b68`
- `0x180007b7c`
- `0x1800084f4`

## callees

- `0x180002a32`
- `0x180002ad0`
- `0x180002bd0`
- `0x180002da4`
- `0x180002dcc`

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
0x180002bd0  push    rbx
0x180002bd2  sub     rsp, 20h
0x180002bd6  mov     rbx, rcx
0x180002bd9  jmp     short loc_180002BEA
0x180002bdb  mov     rcx, rbx
0x180002bde  call    _o__callnewh_0
0x180002be3  test    eax, eax
0x180002be5  jz      short loc_180002BFA
0x180002be7  mov     rcx, rbx; Size
0x180002bea  call    _o_malloc_0
0x180002bef  test    rax, rax
0x180002bf2  jz      short loc_180002BDB
0x180002bf4  add     rsp, 20h
0x180002bf8  pop     rbx
0x180002bf9  retn
0x180002bfa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002bfe  jz      short loc_180002C06
0x180002c00  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002c06  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
