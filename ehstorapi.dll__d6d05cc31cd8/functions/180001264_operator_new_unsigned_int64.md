# operator new(unsigned __int64)

- ea: `0x180001264`
- end: `0x18000129d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180001258`
- `0x180002504`
- `0x180004220`
- `0x180006988`
- `0x180009b78`
- `0x180009c6c`
- `0x180009d90`
- `0x180009e88`
- `0x180009f90`

## callees

- `0x180001264`
- `0x1800017f6`
- `0x180001c4c`

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
0x180001264  mov     [rsp+arg_0], rbx
0x180001269  push    rdi
0x18000126a  sub     rsp, 20h
0x18000126e  mov     rdi, rcx
0x180001271  jmp     short loc_180001282
0x180001273  mov     rcx, rdi; Size
0x180001276  call    _callnewh_0
0x18000127b  test    eax, eax
0x18000127d  jz      short loc_18000128F
0x18000127f  mov     rcx, rdi; Size
0x180001282  call    malloc_0
0x180001287  mov     rbx, rax
0x18000128a  test    rax, rax
0x18000128d  jz      short loc_180001273
0x18000128f  mov     rax, rbx
0x180001292  mov     rbx, [rsp+28h+arg_0]
0x180001297  add     rsp, 20h
0x18000129b  pop     rdi
0x18000129c  retn
```
