# operator new(unsigned __int64)

- ea: `0x18000183c`
- end: `0x180001878`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `40`
- callee_count: `5`
- tags: ``

## callers

- `0x180002250`
- `0x180003480`
- `0x1800034a4`
- `0x1800081e4`
- `0x18000a13c`
- `0x18000a22c`
- `0x18000a2fc`
- `0x18000a3e8`
- `0x18000f670`
- `0x18001016c`
- `0x1800102a8`
- `0x180010c84`
- `0x180010d9c`
- `0x180014a00`
- `0x180016758`
- `0x1800185dc`
- `0x180018610`
- `0x180018644`
- `0x180018678`
- `0x180018aec`
- `0x180018cd8`
- `0x180019d4c`
- `0x18001acf4`
- `0x18001ba0c`
- `0x18001bc48`
- `0x18001c664`
- `0x18001ce3c`
- `0x18001cf1c`
- `0x18001d8a0`
- `0x18001eb84`
- `0x18001ebb8`
- `0x18001f3bc`
- `0x18001fa9c`
- `0x180020e0c`
- `0x18002168c`
- `0x180021acc`
- `0x180021c10`
- `0x180021f3c`
- `0x18002201c`
- `0x1800226b0`

## callees

- `0x18000183c`
- `0x180001f54`
- `0x180001f7c`
- `0x1800022e2`
- `0x18000238c`

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
0x18000183c  push    rbx
0x18000183e  sub     rsp, 20h
0x180001842  mov     rbx, rcx
0x180001845  jmp     short loc_180001856
0x180001847  mov     rcx, rbx
0x18000184a  call    _o__callnewh_0
0x18000184f  test    eax, eax
0x180001851  jz      short loc_180001866
0x180001853  mov     rcx, rbx; Size
0x180001856  call    _o_malloc_0
0x18000185b  test    rax, rax
0x18000185e  jz      short loc_180001847
0x180001860  add     rsp, 20h
0x180001864  pop     rbx
0x180001865  retn
0x180001866  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000186a  jz      short loc_180001872
0x18000186c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001872  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
