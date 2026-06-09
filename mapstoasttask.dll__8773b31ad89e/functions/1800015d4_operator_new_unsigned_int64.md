# operator new(unsigned __int64)

- ea: `0x1800015d4`
- end: `0x180001610`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002074`
- `0x1800020a4`
- `0x1800021e4`
- `0x180002e00`
- `0x1800044a8`
- `0x1800064c0`
- `0x180006c50`

## callees

- `0x1800015d4`
- `0x180001bf8`
- `0x180001f46`
- `0x180001fca`
- `0x1800063b4`

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
0x1800015d4  push    rbx
0x1800015d6  sub     rsp, 20h
0x1800015da  mov     rbx, rcx
0x1800015dd  jmp     short loc_1800015EE
0x1800015df  mov     rcx, rbx
0x1800015e2  call    _o__callnewh_0
0x1800015e7  test    eax, eax
0x1800015e9  jz      short loc_1800015FE
0x1800015eb  mov     rcx, rbx; Size
0x1800015ee  call    _o_malloc_0
0x1800015f3  test    rax, rax
0x1800015f6  jz      short loc_1800015DF
0x1800015f8  add     rsp, 20h
0x1800015fc  pop     rbx
0x1800015fd  retn
0x1800015fe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001602  jz      short loc_18000160A
0x180001604  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000160a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
