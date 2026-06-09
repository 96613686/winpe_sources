# operator new(unsigned __int64)

- ea: `0x180001afc`
- end: `0x180001b38`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180001b40`
- `0x180002100`
- `0x1800029d4`
- `0x18000e410`
- `0x18000e4e0`
- `0x18000e5b0`
- `0x18000e674`
- `0x18000e750`
- `0x18000e860`

## callees

- `0x180001afc`
- `0x180002134`
- `0x18000215c`
- `0x180002496`
- `0x180002530`

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
0x180001afc  push    rbx
0x180001afe  sub     rsp, 20h
0x180001b02  mov     rbx, rcx
0x180001b05  jmp     short loc_180001B16
0x180001b07  mov     rcx, rbx
0x180001b0a  call    _o__callnewh_0
0x180001b0f  test    eax, eax
0x180001b11  jz      short loc_180001B26
0x180001b13  mov     rcx, rbx; Size
0x180001b16  call    _o_malloc_0
0x180001b1b  test    rax, rax
0x180001b1e  jz      short loc_180001B07
0x180001b20  add     rsp, 20h
0x180001b24  pop     rbx
0x180001b25  retn
0x180001b26  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001b2a  jz      short loc_180001B32
0x180001b2c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001b32  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
