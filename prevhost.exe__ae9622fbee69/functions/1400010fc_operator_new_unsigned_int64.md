# operator new(unsigned __int64)

- ea: `0x1400010fc`
- end: `0x140001135`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001494`
- `0x140003190`
- `0x140004000`
- `0x14000568c`

## callees

- `0x1400010fc`
- `0x140001d3e`
- `0x140001e0a`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x1400010fc  mov     [rsp+arg_0], rbx
0x140001101  push    rdi
0x140001102  sub     rsp, 20h
0x140001106  mov     rdi, rcx
0x140001109  jmp     short loc_14000111A
0x14000110b  mov     rcx, rdi
0x14000110e  call    _o__callnewh_0
0x140001113  test    eax, eax
0x140001115  jz      short loc_140001127
0x140001117  mov     rcx, rdi; Size
0x14000111a  call    _o_malloc_0
0x14000111f  mov     rbx, rax
0x140001122  test    rax, rax
0x140001125  jz      short loc_14000110B
0x140001127  mov     rax, rbx
0x14000112a  mov     rbx, [rsp+28h+arg_0]
0x14000112f  add     rsp, 20h
0x140001133  pop     rdi
0x140001134  retn
```
