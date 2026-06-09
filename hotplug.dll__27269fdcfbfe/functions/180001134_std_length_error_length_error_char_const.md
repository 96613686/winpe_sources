# std::length_error::length_error(char const *)

- ea: `0x180001134`
- end: `0x180001163`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800013d8`
- `0x180001404`

## callees

- `0x180002195`

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
0x180001134  mov     [rsp+arg_0], rcx
0x180001139  push    rbx
0x18000113a  sub     rsp, 20h
0x18000113e  mov     [rsp+28h+arg_0], rdx
0x180001143  mov     rbx, rcx
0x180001146  lea     rdx, [rsp+28h+arg_0]; char **
0x18000114b  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001150  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x180001157  mov     [rbx], rax
0x18000115a  mov     rax, rbx
0x18000115d  add     rsp, 20h
0x180001161  pop     rbx
0x180001162  retn
```
