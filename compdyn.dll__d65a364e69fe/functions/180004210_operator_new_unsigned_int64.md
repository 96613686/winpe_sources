# operator new(unsigned __int64)

- ea: `0x180004210`
- end: `0x180004249`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x180001220`
- `0x1800012b0`
- `0x180001a60`
- `0x180003850`
- `0x180004130`

## callees

- `0x180004210`
- `0x180004732`
- `0x18000473e`

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
0x180004210  mov     [rsp+arg_0], rbx
0x180004215  push    rdi
0x180004216  sub     rsp, 20h
0x18000421a  mov     rdi, rcx
0x18000421d  jmp     short loc_18000422E
0x18000421f  mov     rcx, rdi; Size
0x180004222  call    _callnewh_0
0x180004227  test    eax, eax
0x180004229  jz      short loc_18000423B
0x18000422b  mov     rcx, rdi; Size
0x18000422e  call    malloc_0
0x180004233  mov     rbx, rax
0x180004236  test    rax, rax
0x180004239  jz      short loc_18000421F
0x18000423b  mov     rax, rbx
0x18000423e  mov     rbx, [rsp+28h+arg_0]
0x180004243  add     rsp, 20h
0x180004247  pop     rdi
0x180004248  retn
```
