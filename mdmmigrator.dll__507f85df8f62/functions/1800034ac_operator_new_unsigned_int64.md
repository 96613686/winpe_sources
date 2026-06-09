# operator new(unsigned __int64)

- ea: `0x1800034ac`
- end: `0x1800034e8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x1800034f0`
- `0x18000360c`
- `0x180007890`
- `0x180007ac0`
- `0x180007dd4`
- `0x180008010`
- `0x1800082ac`
- `0x180008940`
- `0x18000a2a4`
- `0x18000aa2c`
- `0x18000c460`
- `0x18000c554`
- `0x18000c740`
- `0x18000cf04`
- `0x18000d6b8`
- `0x18000de8c`
- `0x180010864`
- `0x1800110d0`
- `0x180012ed4`
- `0x180019e58`

## callees

- `0x180002be2`
- `0x180002c80`
- `0x1800034ac`
- `0x1800035b4`
- `0x18000970c`

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
0x1800034ac  push    rbx
0x1800034ae  sub     rsp, 20h
0x1800034b2  mov     rbx, rcx
0x1800034b5  jmp     short loc_1800034C6
0x1800034b7  mov     rcx, rbx
0x1800034ba  call    _o__callnewh_0
0x1800034bf  test    eax, eax
0x1800034c1  jz      short loc_1800034D6
0x1800034c3  mov     rcx, rbx; Size
0x1800034c6  call    _o_malloc_0
0x1800034cb  test    rax, rax
0x1800034ce  jz      short loc_1800034B7
0x1800034d0  add     rsp, 20h
0x1800034d4  pop     rbx
0x1800034d5  retn
0x1800034d6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800034da  jz      short loc_1800034E2
0x1800034dc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800034e2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
