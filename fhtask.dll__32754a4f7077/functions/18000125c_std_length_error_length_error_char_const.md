# std::length_error::length_error(char const *)

- ea: `0x18000125c`
- end: `0x18000128b`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012d8`
- `0x180001304`

## callees

- `0x180001ce8`

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
0x18000125c  mov     [rsp+arg_0], rcx
0x180001261  push    rbx
0x180001262  sub     rsp, 20h
0x180001266  mov     [rsp+28h+arg_0], rdx
0x18000126b  mov     rbx, rcx
0x18000126e  lea     rdx, [rsp+28h+arg_0]; char **
0x180001273  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001278  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x18000127f  mov     [rbx], rax
0x180001282  mov     rax, rbx
0x180001285  add     rsp, 20h
0x180001289  pop     rbx
0x18000128a  retn
```
