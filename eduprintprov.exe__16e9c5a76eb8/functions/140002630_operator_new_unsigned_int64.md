# operator new(unsigned __int64)

- ea: `0x140002630`
- end: `0x14000266c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x1400028e4`
- `0x14000452c`
- `0x14000466c`
- `0x14000c318`
- `0x14000cc6c`
- `0x14000d2a4`
- `0x14000e150`
- `0x14000e440`
- `0x14000e624`
- `0x14000ebec`
- `0x14000f330`
- `0x14000f5c0`
- `0x14000fa88`
- `0x140010098`
- `0x140011344`

## callees

- `0x140002630`
- `0x140002f88`
- `0x14000303e`
- `0x140003120`
- `0x14000b940`

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
0x140002630  push    rbx
0x140002632  sub     rsp, 20h
0x140002636  mov     rbx, rcx
0x140002639  jmp     short loc_14000264A
0x14000263b  mov     rcx, rbx
0x14000263e  call    _o__callnewh_0
0x140002643  test    eax, eax
0x140002645  jz      short loc_14000265A
0x140002647  mov     rcx, rbx; Size
0x14000264a  call    _o_malloc_0
0x14000264f  test    rax, rax
0x140002652  jz      short loc_14000263B
0x140002654  add     rsp, 20h
0x140002658  pop     rbx
0x140002659  retn
0x14000265a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000265e  jz      short loc_140002666
0x140002660  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140002666  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
