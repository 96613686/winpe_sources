# _CManagerThread::GetConfigDescriptor_::_1_::dtor$1

- ea: `0x180011e7e`
- end: `0x180011e9d`
- name: `_CManagerThread::GetConfigDescriptor_::_1_::dtor$1`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18000d0d0`

## pseudocode

```c
void __fastcall CManagerThread::GetConfigDescriptor_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 96), (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x180011e7e  push    rbp
0x180011e80  sub     rsp, 20h
0x180011e84  mov     rbp, rdx
0x180011e87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011e8e  mov     rcx, [rbp+60h]; void *
0x180011e92  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011e97  add     rsp, 20h
0x180011e9b  pop     rbp
0x180011e9c  retn
```
