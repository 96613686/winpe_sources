# _GetSecurityDescriptor_::_2_::Security::_Security

- ea: `0x140003c3c`
- end: `0x140003c41`
- name: `_GetSecurityDescriptor_::_2_::Security::_Security`
- size: `5`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000580c`

## callees

- `0x140003c00`

## pseudocode

```c
// attributes: thunk
PVOID __fastcall GetSecurityDescriptor_::_2_::Security::_Security(void **a1)
{
  return GetSecurityDescriptor_::_2_::CSIDPointer::_CSIDPointer(a1);
}

```

## disassembly

```asm
0x140003c3c  jmp     _GetSecurityDescriptor____2___CSIDPointer___CSIDPointer
```
