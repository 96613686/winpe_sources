# std::bad_alloc::bad_alloc(void)

- ea: `0x180001f30`
- end: `0x180001f71`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `65`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f90`

## callees

- `0x18000201f`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this)
{
  char *v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = "bad allocation";
  exception::exception(this, (const char *const *)&v3, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001f30  push    rbx
0x180001f32  sub     rsp, 30h
0x180001f36  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001f3f  mov     rbx, rcx
0x180001f42  lea     rax, aBadAllocation; "bad allocation"
0x180001f49  mov     [rsp+38h+arg_0], rax
0x180001f4e  mov     r8d, 1; int
0x180001f54  lea     rdx, [rsp+38h+arg_0]; char **
0x180001f59  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x180001f5e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001f65  mov     [rbx], rax
0x180001f68  mov     rax, rbx
0x180001f6b  add     rsp, 30h
0x180001f6f  pop     rbx
0x180001f70  retn
```
