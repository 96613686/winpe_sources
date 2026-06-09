# std::exception::exception(std::exception const &)

- ea: `0x180003728`
- end: `0x18000375a`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003620`
- `0x180006f7c`
- `0x180006fa4`

## callees

- `0x1800029f6`

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
0x180003728  push    rbx
0x18000372a  sub     rsp, 20h
0x18000372e  mov     rbx, rcx
0x180003731  mov     rax, rdx
0x180003734  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000373b  xorps   xmm0, xmm0
0x18000373e  mov     [rbx], rcx
0x180003741  lea     rdx, [rbx+8]
0x180003745  lea     rcx, [rax+8]
0x180003749  movups  xmmword ptr [rdx], xmm0
0x18000374c  call    _o___std_exception_copy_0
0x180003751  mov     rax, rbx
0x180003754  add     rsp, 20h
0x180003758  pop     rbx
0x180003759  retn
```
