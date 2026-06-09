# registry_access_error::registry_access_error(registry_access_error const &)

- ea: `0x14000ede4`
- end: `0x14000ee17`
- name: `??0registry_access_error@@QEAA@AEBV0@@Z`
- size: `51`
- prototype: `registry_access_error *__fastcall(registry_access_error *__hidden this, const struct registry_access_error *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003a64`

## pseudocode

```c
registry_access_error *__fastcall registry_access_error::registry_access_error(
        registry_access_error *this,
        const struct registry_access_error *a2)
{
  std::bad_alloc::bad_alloc(this, a2);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  return this;
}

```

## disassembly

```asm
0x14000ede4  mov     [rsp+arg_0], rbx
0x14000ede9  push    rdi
0x14000edea  sub     rsp, 20h
0x14000edee  mov     rbx, rdx
0x14000edf1  mov     rdi, rcx
0x14000edf4  call    ??0bad_alloc@std@@QEAA@AEBV01@@Z; std::bad_alloc::bad_alloc(std::bad_alloc const &)
0x14000edf9  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000ee00  mov     [rdi], rax
0x14000ee03  mov     eax, [rbx+18h]
0x14000ee06  mov     rbx, [rsp+28h+arg_0]
0x14000ee0b  mov     [rdi+18h], eax
0x14000ee0e  mov     rax, rdi
0x14000ee11  add     rsp, 20h
0x14000ee15  pop     rdi
0x14000ee16  retn
```
