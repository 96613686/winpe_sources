# std::length_error::length_error(char const *)

- ea: `0x180001168`
- end: `0x180001197`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001260`
- `0x18000128c`

## callees

- `0x180001dc0`

## pseudocode

```c
std::length_error *__fastcall std::length_error::length_error(std::length_error *this, char *a2)
{
  char *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a2;
  exception::exception(this, (const char *const *)&v4);
  *(_QWORD *)this = &std::length_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001168  mov     [rsp+arg_0], rcx
0x18000116d  push    rbx
0x18000116e  sub     rsp, 20h
0x180001172  mov     [rsp+28h+arg_0], rdx
0x180001177  mov     rbx, rcx
0x18000117a  lea     rdx, [rsp+28h+arg_0]; char **
0x18000117f  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001184  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x18000118b  mov     [rbx], rax
0x18000118e  mov     rax, rbx
0x180001191  add     rsp, 20h
0x180001195  pop     rbx
0x180001196  retn
```
