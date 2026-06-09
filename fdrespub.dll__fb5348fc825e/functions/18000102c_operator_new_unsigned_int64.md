# operator new(unsigned __int64)

- ea: `0x18000102c`
- end: `0x180001065`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001014`
- `0x180001cc0`
- `0x1800020f8`
- `0x1800047f8`

## callees

- `0x18000102c`
- `0x180001542`
- `0x18000154e`

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
0x18000102c  mov     [rsp+arg_0], rbx
0x180001031  push    rdi
0x180001032  sub     rsp, 20h
0x180001036  mov     rdi, rcx
0x180001039  jmp     short loc_18000104A
0x18000103b  mov     rcx, rdi; Size
0x18000103e  call    _callnewh_0
0x180001043  test    eax, eax
0x180001045  jz      short loc_180001057
0x180001047  mov     rcx, rdi; Size
0x18000104a  call    malloc_0
0x18000104f  mov     rbx, rax
0x180001052  test    rax, rax
0x180001055  jz      short loc_18000103B
0x180001057  mov     rax, rbx
0x18000105a  mov     rbx, [rsp+28h+arg_0]
0x18000105f  add     rsp, 20h
0x180001063  pop     rdi
0x180001064  retn
```
