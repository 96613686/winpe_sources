# operator new(unsigned __int64)

- ea: `0x180001fb8`
- end: `0x180001ff4`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800022cc`
- `0x18000739c`
- `0x180007414`
- `0x180007834`
- `0x180007ae8`
- `0x180007c50`
- `0x180007ec0`
- `0x1800081ec`
- `0x180008334`

## callees

- `0x180001fb8`
- `0x180002824`
- `0x1800028c2`
- `0x180002960`
- `0x18000a938`

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
0x180001fb8  push    rbx
0x180001fba  sub     rsp, 20h
0x180001fbe  mov     rbx, rcx
0x180001fc1  jmp     short loc_180001FD2
0x180001fc3  mov     rcx, rbx
0x180001fc6  call    _o__callnewh_0
0x180001fcb  test    eax, eax
0x180001fcd  jz      short loc_180001FE2
0x180001fcf  mov     rcx, rbx; Size
0x180001fd2  call    _o_malloc_0
0x180001fd7  test    rax, rax
0x180001fda  jz      short loc_180001FC3
0x180001fdc  add     rsp, 20h
0x180001fe0  pop     rbx
0x180001fe1  retn
0x180001fe2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001fe6  jz      short loc_180001FEE
0x180001fe8  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001fee  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
