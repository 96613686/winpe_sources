# operator new(unsigned __int64)

- ea: `0x18000192c`
- end: `0x180001968`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180001970`
- `0x180005ad8`
- `0x180005d20`
- `0x180005e18`
- `0x180005f34`
- `0x180006f44`
- `0x180008a90`

## callees

- `0x18000192c`
- `0x180001e50`
- `0x180001f02`
- `0x180001f86`
- `0x180006ca8`

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
0x18000192c  push    rbx
0x18000192e  sub     rsp, 20h
0x180001932  mov     rbx, rcx
0x180001935  jmp     short loc_180001946
0x180001937  mov     rcx, rbx
0x18000193a  call    _o__callnewh_0
0x18000193f  test    eax, eax
0x180001941  jz      short loc_180001956
0x180001943  mov     rcx, rbx; Size
0x180001946  call    _o_malloc_0
0x18000194b  test    rax, rax
0x18000194e  jz      short loc_180001937
0x180001950  add     rsp, 20h
0x180001954  pop     rbx
0x180001955  retn
0x180001956  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000195a  jz      short loc_180001962
0x18000195c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001962  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
