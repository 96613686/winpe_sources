# operator new(unsigned __int64)

- ea: `0x180002970`
- end: `0x1800029a9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001080`
- `0x180001600`
- `0x180003c20`

## callees

- `0x180002970`
- `0x180002ea9`
- `0x180002eb5`

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
0x180002970  mov     [rsp+arg_0], rbx
0x180002975  push    rdi
0x180002976  sub     rsp, 20h
0x18000297a  mov     rdi, rcx
0x18000297d  jmp     short loc_18000298E
0x18000297f  mov     rcx, rdi; Size
0x180002982  call    _callnewh_0
0x180002987  test    eax, eax
0x180002989  jz      short loc_18000299B
0x18000298b  mov     rcx, rdi; Size
0x18000298e  call    malloc_0
0x180002993  mov     rbx, rax
0x180002996  test    rax, rax
0x180002999  jz      short loc_18000297F
0x18000299b  mov     rax, rbx
0x18000299e  mov     rbx, [rsp+28h+arg_0]
0x1800029a3  add     rsp, 20h
0x1800029a7  pop     rdi
0x1800029a8  retn
```
