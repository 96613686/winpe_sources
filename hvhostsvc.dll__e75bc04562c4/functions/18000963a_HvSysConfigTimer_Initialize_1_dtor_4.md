# _HvSysConfigTimer::Initialize_::_1_::dtor$4

- ea: `0x18000963a`
- end: `0x180009657`
- name: `_HvSysConfigTimer::Initialize_::_1_::dtor$4`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x1800024d0`

## pseudocode

```c
void __fastcall HvSysConfigTimer::Initialize_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48), (const struct std::nothrow_t *)8);
}

```

## disassembly

```asm
0x18000963a  push    rbp
0x18000963c  sub     rsp, 20h
0x180009640  mov     rbp, rdx
0x180009643  mov     edx, 8; struct std::nothrow_t *
0x180009648  mov     rcx, [rbp+30h]; void *
0x18000964c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009651  add     rsp, 20h
0x180009655  pop     rbp
0x180009656  retn
```
