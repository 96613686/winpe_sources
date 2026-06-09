# _DeploymentServiceComClassFactory::CreateInstance_::_1_::dtor$0

- ea: `0x18001f000`
- end: `0x18001f01f`
- name: `_DeploymentServiceComClassFactory::CreateInstance_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180012b30`

## pseudocode

```c
void __fastcall DeploymentServiceComClassFactory::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72), (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x18001f000  push    rbp
0x18001f002  sub     rsp, 20h
0x18001f006  mov     rbp, rdx
0x18001f009  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f010  mov     rcx, [rbp+48h]; void *
0x18001f014  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18001f019  add     rsp, 20h
0x18001f01d  pop     rbp
0x18001f01e  retn
```
