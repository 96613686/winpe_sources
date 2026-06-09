# operator new(unsigned __int64)

- ea: `0x180005860`
- end: `0x180005899`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010c0`
- `0x180002ab0`
- `0x180002ec0`
- `0x180003080`
- `0x180006da0`

## callees

- `0x180005860`
- `0x180005d82`
- `0x180005d8e`

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
0x180005860  mov     [rsp+arg_0], rbx
0x180005865  push    rdi
0x180005866  sub     rsp, 20h
0x18000586a  mov     rdi, rcx
0x18000586d  jmp     short loc_18000587E
0x18000586f  mov     rcx, rdi; Size
0x180005872  call    _callnewh_0
0x180005877  test    eax, eax
0x180005879  jz      short loc_18000588B
0x18000587b  mov     rcx, rdi; Size
0x18000587e  call    malloc_0
0x180005883  mov     rbx, rax
0x180005886  test    rax, rax
0x180005889  jz      short loc_18000586F
0x18000588b  mov     rax, rbx
0x18000588e  mov     rbx, [rsp+28h+arg_0]
0x180005893  add     rsp, 20h
0x180005897  pop     rdi
0x180005898  retn
```
