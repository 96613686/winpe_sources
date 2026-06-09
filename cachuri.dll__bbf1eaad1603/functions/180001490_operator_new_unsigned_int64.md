# operator new(unsigned __int64)

- ea: `0x180001490`
- end: `0x1800014c9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001de0`

## callees

- `0x180001490`
- `0x1800019b2`
- `0x1800019be`

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
0x180001490  mov     [rsp+arg_0], rbx
0x180001495  push    rdi
0x180001496  sub     rsp, 20h
0x18000149a  mov     rdi, rcx
0x18000149d  jmp     short loc_1800014AE
0x18000149f  mov     rcx, rdi; Size
0x1800014a2  call    _callnewh_0
0x1800014a7  test    eax, eax
0x1800014a9  jz      short loc_1800014BB
0x1800014ab  mov     rcx, rdi; Size
0x1800014ae  call    malloc_0
0x1800014b3  mov     rbx, rax
0x1800014b6  test    rax, rax
0x1800014b9  jz      short loc_18000149F
0x1800014bb  mov     rax, rbx
0x1800014be  mov     rbx, [rsp+28h+arg_0]
0x1800014c3  add     rsp, 20h
0x1800014c7  pop     rdi
0x1800014c8  retn
```
