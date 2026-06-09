# operator new(unsigned __int64)

- ea: `0x180005a0c`
- end: `0x180005a45`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180001280`
- `0x1800020d0`
- `0x180002670`
- `0x1800039d0`
- `0x180004220`
- `0x180004778`
- `0x180007918`

## callees

- `0x180005a0c`
- `0x180005f32`
- `0x180005f3e`

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
0x180005a0c  mov     [rsp+arg_0], rbx
0x180005a11  push    rdi
0x180005a12  sub     rsp, 20h
0x180005a16  mov     rdi, rcx
0x180005a19  jmp     short loc_180005A2A
0x180005a1b  mov     rcx, rdi; Size
0x180005a1e  call    _callnewh_0
0x180005a23  test    eax, eax
0x180005a25  jz      short loc_180005A37
0x180005a27  mov     rcx, rdi; Size
0x180005a2a  call    malloc_0
0x180005a2f  mov     rbx, rax
0x180005a32  test    rax, rax
0x180005a35  jz      short loc_180005A1B
0x180005a37  mov     rax, rbx
0x180005a3a  mov     rbx, [rsp+28h+arg_0]
0x180005a3f  add     rsp, 20h
0x180005a43  pop     rdi
0x180005a44  retn
```
