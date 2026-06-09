# std::exception::exception(std::exception const &)

- ea: `0x180006598`
- end: `0x1800065ca`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180006490`
- `0x1800096a8`
- `0x1800096e4`
- `0x18000970c`
- `0x1800097ac`
- `0x180009904`
- `0x180009960`

## callees

- `0x180005a56`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0((char *)a2 + 8);
  return this;
}

```

## disassembly

```asm
0x180006598  push    rbx
0x18000659a  sub     rsp, 20h
0x18000659e  mov     rbx, rcx
0x1800065a1  mov     rax, rdx
0x1800065a4  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800065ab  xorps   xmm0, xmm0
0x1800065ae  mov     [rbx], rcx
0x1800065b1  lea     rdx, [rbx+8]
0x1800065b5  lea     rcx, [rax+8]
0x1800065b9  movups  xmmword ptr [rdx], xmm0
0x1800065bc  call    _o___std_exception_copy_0
0x1800065c1  mov     rax, rbx
0x1800065c4  add     rsp, 20h
0x1800065c8  pop     rbx
0x1800065c9  retn
```
