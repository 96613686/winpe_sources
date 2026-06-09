# operator new(unsigned __int64)

- ea: `0x180002cdc`
- end: `0x180002d18`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180001bf0`
- `0x180001ca0`
- `0x180002c98`
- `0x18000d844`
- `0x18000d984`
- `0x18000f210`
- `0x18000f750`
- `0x180011950`
- `0x180011b50`
- `0x1800130f4`

## callees

- `0x180002b0e`
- `0x180002bac`
- `0x180002cdc`
- `0x180002e24`
- `0x18000eb80`

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
0x180002cdc  push    rbx
0x180002cde  sub     rsp, 20h
0x180002ce2  mov     rbx, rcx
0x180002ce5  jmp     short loc_180002CF6
0x180002ce7  mov     rcx, rbx
0x180002cea  call    _o__callnewh_0
0x180002cef  test    eax, eax
0x180002cf1  jz      short loc_180002D06
0x180002cf3  mov     rcx, rbx; Size
0x180002cf6  call    _o_malloc_0
0x180002cfb  test    rax, rax
0x180002cfe  jz      short loc_180002CE7
0x180002d00  add     rsp, 20h
0x180002d04  pop     rbx
0x180002d05  retn
0x180002d06  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002d0a  jz      short loc_180002D12
0x180002d0c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002d12  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
