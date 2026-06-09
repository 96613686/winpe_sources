# operator new(unsigned __int64)

- ea: `0x180001ff0`
- end: `0x180002029`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x1800012c0`
- `0x180001d3c`
- `0x180004670`
- `0x1800065f0`
- `0x180007524`

## callees

- `0x180001ff0`
- `0x180002512`
- `0x18000251e`

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
0x180001ff0  mov     [rsp+arg_0], rbx
0x180001ff5  push    rdi
0x180001ff6  sub     rsp, 20h
0x180001ffa  mov     rdi, rcx
0x180001ffd  jmp     short loc_18000200E
0x180001fff  mov     rcx, rdi; Size
0x180002002  call    _callnewh_0
0x180002007  test    eax, eax
0x180002009  jz      short loc_18000201B
0x18000200b  mov     rcx, rdi; Size
0x18000200e  call    malloc_0
0x180002013  mov     rbx, rax
0x180002016  test    rax, rax
0x180002019  jz      short loc_180001FFF
0x18000201b  mov     rax, rbx
0x18000201e  mov     rbx, [rsp+28h+arg_0]
0x180002023  add     rsp, 20h
0x180002027  pop     rdi
0x180002028  retn
```
