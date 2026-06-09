# std::exception::exception(std::exception const &)

- ea: `0x180005de4`
- end: `0x180005e16`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005bf0`
- `0x180005d6c`
- `0x180005d94`

## callees

- `0x180004c66`

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
0x180005de4  push    rbx
0x180005de6  sub     rsp, 20h
0x180005dea  mov     rbx, rcx
0x180005ded  mov     rax, rdx
0x180005df0  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180005df7  xorps   xmm0, xmm0
0x180005dfa  mov     [rbx], rcx
0x180005dfd  lea     rdx, [rbx+8]
0x180005e01  lea     rcx, [rax+8]
0x180005e05  movups  xmmword ptr [rdx], xmm0
0x180005e08  call    _o___std_exception_copy_0
0x180005e0d  mov     rax, rbx
0x180005e10  add     rsp, 20h
0x180005e14  pop     rbx
0x180005e15  retn
```
