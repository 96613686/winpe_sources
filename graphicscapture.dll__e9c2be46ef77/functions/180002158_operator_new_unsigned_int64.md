# operator new(unsigned __int64)

- ea: `0x180002158`
- end: `0x180002194`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `39`
- callee_count: `5`
- tags: ``

## callers

- `0x18000219c`
- `0x180003df0`
- `0x180004120`
- `0x180004210`
- `0x180004340`
- `0x180006658`
- `0x18000d6a4`
- `0x18000d8c0`
- `0x18000df88`
- `0x18000e2f8`
- `0x18000f030`
- `0x180013310`
- `0x180013408`
- `0x180013ee8`
- `0x180015194`
- `0x180015c30`
- `0x180015fb8`
- `0x180016054`
- `0x180016de4`
- `0x180016e90`
- `0x180016ef0`
- `0x180016f58`
- `0x180016fb8`
- `0x180017224`
- `0x180018d8c`
- `0x18001a24c`
- `0x18001b378`
- `0x18001b724`
- `0x18001bedc`
- `0x18001c558`
- `0x18001c5c8`
- `0x18001cb6c`
- `0x18001cc30`
- `0x18001e850`
- `0x18001e8ec`
- `0x18001e97c`
- `0x18001ea04`
- `0x18001fa9c`
- `0x1800226bc`

## callees

- `0x180001ece`
- `0x180001f60`
- `0x180002158`
- `0x18000225c`
- `0x180002284`

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
0x180002158  push    rbx
0x18000215a  sub     rsp, 20h
0x18000215e  mov     rbx, rcx
0x180002161  jmp     short loc_180002172
0x180002163  mov     rcx, rbx
0x180002166  call    _o__callnewh_0
0x18000216b  test    eax, eax
0x18000216d  jz      short loc_180002182
0x18000216f  mov     rcx, rbx; Size
0x180002172  call    _o_malloc_0
0x180002177  test    rax, rax
0x18000217a  jz      short loc_180002163
0x18000217c  add     rsp, 20h
0x180002180  pop     rbx
0x180002181  retn
0x180002182  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002186  jz      short loc_18000218E
0x180002188  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000218e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
