# Concurrency::agent::~agent(void)

- ea: `0x180001b80`
- end: `0x180001b93`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800cd774`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_1800CD774((char *)this + 8);
}

```

## disassembly

```asm
0x180001b80  lea     rax, ??_7exception@std@@6B@
0x180001b87  mov     [rcx], rax
0x180001b8a  add     rcx, 8
0x180001b8e  jmp     sub_1800CD774
```
