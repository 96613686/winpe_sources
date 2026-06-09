# operator new(unsigned __int64)

- ea: `0x180001d80`
- end: `0x180001db9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001290`
- `0x180001580`
- `0x180001c10`

## callees

- `0x180001d80`
- `0x1800022a2`
- `0x1800022ae`

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
0x180001d80  mov     [rsp+arg_0], rbx
0x180001d85  push    rdi
0x180001d86  sub     rsp, 20h
0x180001d8a  mov     rdi, rcx
0x180001d8d  jmp     short loc_180001D9E
0x180001d8f  mov     rcx, rdi; Size
0x180001d92  call    _callnewh_0
0x180001d97  test    eax, eax
0x180001d99  jz      short loc_180001DAB
0x180001d9b  mov     rcx, rdi; Size
0x180001d9e  call    malloc_0
0x180001da3  mov     rbx, rax
0x180001da6  test    rax, rax
0x180001da9  jz      short loc_180001D8F
0x180001dab  mov     rax, rbx
0x180001dae  mov     rbx, [rsp+28h+arg_0]
0x180001db3  add     rsp, 20h
0x180001db7  pop     rdi
0x180001db8  retn
```
