# operator new(unsigned __int64)

- ea: `0x180001c04`
- end: `0x180001c40`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003dd0`
- `0x180007820`

## callees

- `0x180001c04`
- `0x180002218`
- `0x180002240`
- `0x180002576`
- `0x1800025fa`

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
0x180001c04  push    rbx
0x180001c06  sub     rsp, 20h
0x180001c0a  mov     rbx, rcx
0x180001c0d  jmp     short loc_180001C1E
0x180001c0f  mov     rcx, rbx
0x180001c12  call    _o__callnewh_0
0x180001c17  test    eax, eax
0x180001c19  jz      short loc_180001C2E
0x180001c1b  mov     rcx, rbx; Size
0x180001c1e  call    _o_malloc_0
0x180001c23  test    rax, rax
0x180001c26  jz      short loc_180001C0F
0x180001c28  add     rsp, 20h
0x180001c2c  pop     rbx
0x180001c2d  retn
0x180001c2e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001c32  jz      short loc_180001C3A
0x180001c34  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001c3a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
