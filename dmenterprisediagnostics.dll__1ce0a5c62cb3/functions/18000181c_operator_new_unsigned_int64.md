# operator new(unsigned __int64)

- ea: `0x18000181c`
- end: `0x180001858`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `40`
- callee_count: `5`
- tags: ``

## callers

- `0x180002230`
- `0x180003430`
- `0x180003450`
- `0x180007e58`
- `0x180009bd8`
- `0x180009cc8`
- `0x180009d98`
- `0x180009e80`
- `0x18000efe8`
- `0x18000fa7c`
- `0x1800104f0`
- `0x180010610`
- `0x180014198`
- `0x180015d78`
- `0x180017bc0`
- `0x180017bf4`
- `0x180017c28`
- `0x180017c5c`
- `0x180018014`
- `0x180018130`
- `0x180018328`
- `0x180019318`
- `0x18001a25c`
- `0x18001af5c`
- `0x18001b188`
- `0x18001bb78`
- `0x18001c358`
- `0x18001c43c`
- `0x18001cd8c`
- `0x18001e034`
- `0x18001e068`
- `0x18001e818`
- `0x18001eeac`
- `0x18002012c`
- `0x18002097c`
- `0x180020dbc`
- `0x180020f04`
- `0x180021238`
- `0x180021320`
- `0x180021960`

## callees

- `0x18000181c`
- `0x180001f34`
- `0x180001f5c`
- `0x1800022c2`
- `0x18000236c`

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
0x18000181c  push    rbx
0x18000181e  sub     rsp, 20h
0x180001822  mov     rbx, rcx
0x180001825  jmp     short loc_180001836
0x180001827  mov     rcx, rbx
0x18000182a  call    _o__callnewh_0
0x18000182f  test    eax, eax
0x180001831  jz      short loc_180001846
0x180001833  mov     rcx, rbx; Size
0x180001836  call    _o_malloc_0
0x18000183b  test    rax, rax
0x18000183e  jz      short loc_180001827
0x180001840  add     rsp, 20h
0x180001844  pop     rbx
0x180001845  retn
0x180001846  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000184a  jz      short loc_180001852
0x18000184c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001852  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
