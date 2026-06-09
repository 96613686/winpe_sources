# _CreateSecurityDescriptorForCom_::_1_::dtor$0

- ea: `0x180004786`
- end: `0x180004794`
- name: `_CreateSecurityDescriptorForCom_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000478d`

## pseudocode

```c
void __fastcall CreateSecurityDescriptorForCom_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  BUFFER::~BUFFER((BUFFER *)(a2 + 96));
}

```

## disassembly

```asm
0x180004786  lea     rcx, [rdx+60h]
0x18000478d  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
