# operator new(unsigned __int64)

- ea: `0x180001a9c`
- end: `0x180001ad5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001548`

## callees

- `0x180001731`
- `0x180001a9c`
- `0x180001adb`

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
0x180001a9c  mov     [rsp+arg_0], rbx
0x180001aa1  push    rdi
0x180001aa2  sub     rsp, 20h
0x180001aa6  mov     rdi, rcx
0x180001aa9  jmp     short loc_180001ABA
0x180001aab  mov     rcx, rdi; Size
0x180001aae  call    _callnewh_0
0x180001ab3  test    eax, eax
0x180001ab5  jz      short loc_180001AC7
0x180001ab7  mov     rcx, rdi; Size
0x180001aba  call    malloc_0
0x180001abf  mov     rbx, rax
0x180001ac2  test    rax, rax
0x180001ac5  jz      short loc_180001AAB
0x180001ac7  mov     rax, rbx
0x180001aca  mov     rbx, [rsp+28h+arg_0]
0x180001acf  add     rsp, 20h
0x180001ad3  pop     rdi
0x180001ad4  retn
```
