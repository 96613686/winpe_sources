# _GetSecurityDescriptor_::_2_::Security::Security

- ea: `0x140003b44`
- end: `0x140003b56`
- name: `_GetSecurityDescriptor_::_2_::Security::Security`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000580c`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor_::_2_::Security::Security(__int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)a1 = 0;
  result = a1;
  *(_DWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x140003b44  mov     qword ptr [rcx], 0
0x140003b4b  mov     rax, rcx
0x140003b4e  mov     dword ptr [rcx+8], 0
0x140003b55  retn
```
