# std::length_error::length_error(char const *)

- ea: `0x180001e78`
- end: `0x180001ea7`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `__int64 __fastcall(std::length_error *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002128`
- `0x180002154`

## callees

- `0x1800027bc`

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
0x180001e78  mov     [rsp+arg_0], rcx
0x180001e7d  push    rbx
0x180001e7e  sub     rsp, 20h
0x180001e82  mov     [rsp+28h+arg_0], rdx
0x180001e87  mov     rbx, rcx
0x180001e8a  lea     rdx, [rsp+28h+arg_0]; char **
0x180001e8f  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001e94  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x180001e9b  mov     [rbx], rax
0x180001e9e  mov     rax, rbx
0x180001ea1  add     rsp, 20h
0x180001ea5  pop     rbx
0x180001ea6  retn
```
