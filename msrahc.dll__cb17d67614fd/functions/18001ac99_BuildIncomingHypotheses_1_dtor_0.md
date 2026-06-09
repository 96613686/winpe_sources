# _BuildIncomingHypotheses_::_1_::dtor$0

- ea: `0x18001ac99`
- end: `0x18001acb8`
- name: `_BuildIncomingHypotheses_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800020c0`

## pseudocode

```c
void __fastcall BuildIncomingHypotheses_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete[](*(void **)(a2 + 48), (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x18001ac99  push    rbp
0x18001ac9b  sub     rsp, 20h
0x18001ac9f  mov     rbp, rdx
0x18001aca2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aca9  mov     rcx, [rbp+30h]; void *
0x18001acad  call    ??_V@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete[](void *,std::nothrow_t const &)
0x18001acb2  add     rsp, 20h
0x18001acb6  pop     rbp
0x18001acb7  retn
```
