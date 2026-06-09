# operator new(unsigned __int64)

- ea: `0x1800028e0`
- end: `0x180002919`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013f0`
- `0x180003720`

## callees

- `0x1800028e0`
- `0x180002e02`
- `0x180002e0e`

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
0x1800028e0  mov     [rsp+arg_0], rbx
0x1800028e5  push    rdi
0x1800028e6  sub     rsp, 20h
0x1800028ea  mov     rdi, rcx
0x1800028ed  jmp     short loc_1800028FE
0x1800028ef  mov     rcx, rdi; Size
0x1800028f2  call    _callnewh_0
0x1800028f7  test    eax, eax
0x1800028f9  jz      short loc_18000290B
0x1800028fb  mov     rcx, rdi; Size
0x1800028fe  call    malloc_0
0x180002903  mov     rbx, rax
0x180002906  test    rax, rax
0x180002909  jz      short loc_1800028EF
0x18000290b  mov     rax, rbx
0x18000290e  mov     rbx, [rsp+28h+arg_0]
0x180002913  add     rsp, 20h
0x180002917  pop     rdi
0x180002918  retn
```
