# Concurrency::agent::~agent(void)

- ea: `0x1800021a8`
- end: `0x1800021bb`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800022f6`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  o___std_exception_destroy((char *)this + 8);
}

```

## disassembly

```asm
0x1800021a8  lea     rax, ??_7exception@std@@6B@
0x1800021af  mov     [rcx], rax
0x1800021b2  add     rcx, 8
0x1800021b6  jmp     _o___std_exception_destroy
```
