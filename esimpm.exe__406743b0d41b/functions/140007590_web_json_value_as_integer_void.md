# web::json::value::as_integer(void)

- ea: `0x140007590`
- end: `0x1400075a2`
- name: `?as_integer@value@json@web@@QEBAHXZ`
- size: `18`
- prototype: `__int64 __fastcall(web::json::value *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140038f3c`
- `0x1400393ec`
- `0x14003a9d8`
- `0x14003aba0`
- `0x14003b25c`
- `0x14003b424`
- `0x14003b8bc`
- `0x14003ba84`

## callees

- `0x14003e010`

## pseudocode

```c
__int64 __fastcall web::json::value::as_integer(web::json::value *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 128LL))(*(_QWORD *)this);
}

```

## disassembly

```asm
0x140007590  mov     rcx, [rcx]
0x140007593  mov     rax, [rcx]
0x140007596  mov     rax, [rax+80h]
0x14000759d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
