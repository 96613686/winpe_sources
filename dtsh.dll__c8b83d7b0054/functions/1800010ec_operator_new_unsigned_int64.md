# operator new(unsigned __int64)

- ea: `0x1800010ec`
- end: `0x180001125`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e48`
- `0x180001f90`

## callees

- `0x1800010ec`
- `0x1800016e1`
- `0x1800016ed`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x1800010ec  mov     [rsp+arg_0], rbx
0x1800010f1  push    rdi
0x1800010f2  sub     rsp, 20h
0x1800010f6  mov     rdi, rcx
0x1800010f9  jmp     short loc_18000110A
0x1800010fb  mov     rcx, rdi; Size
0x1800010fe  call    _callnewh_0
0x180001103  test    eax, eax
0x180001105  jz      short loc_180001117
0x180001107  mov     rcx, rdi; Size
0x18000110a  call    malloc_0
0x18000110f  mov     rbx, rax
0x180001112  test    rax, rax
0x180001115  jz      short loc_1800010FB
0x180001117  mov     rax, rbx
0x18000111a  mov     rbx, [rsp+28h+arg_0]
0x18000111f  add     rsp, 20h
0x180001123  pop     rdi
0x180001124  retn
```
