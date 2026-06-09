# CCommand::GetPCTransactionState(void)

- ea: `0x10013ba0`
- end: `0x10013ba4`
- name: `?GetPCTransactionState@CCommand@@MAEPAVCTransactionState@@XZ`
- size: `4`
- prototype: `struct CTransactionState *__thiscall(CCommand *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct CTransactionState *__thiscall CCommand::GetPCTransactionState(CCommand *this)
{
  return (struct CTransactionState *)*((_DWORD *)this + 14);
}

```

## disassembly

```asm
0x10013ba0  mov     eax, [ecx+38h]
0x10013ba3  retn
```
