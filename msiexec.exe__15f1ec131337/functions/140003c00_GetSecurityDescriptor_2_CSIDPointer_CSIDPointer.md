# _GetSecurityDescriptor_::_2_::CSIDPointer::_CSIDPointer

- ea: `0x140003c00`
- end: `0x140003c17`
- name: `_GetSecurityDescriptor_::_2_::CSIDPointer::_CSIDPointer`
- size: `23`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003c3c`

## callees

- `0x140003c00`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x140003c0c`
- `ADVAPI32!FreeSid` at `0x140003c0c`

## pseudocode

```c
PVOID __fastcall GetSecurityDescriptor_::_2_::CSIDPointer::_CSIDPointer(void **a1)
{
  void *v1; // rcx
  PVOID result; // rax

  v1 = *a1;
  if ( v1 )
    return FreeSid(v1);
  return result;
}

```

## disassembly

```asm
0x140003c00  sub     rsp, 28h
0x140003c04  mov     rcx, [rcx]; pSid
0x140003c07  test    rcx, rcx
0x140003c0a  jz      short loc_140003C12
0x140003c0c  call    cs:__imp_FreeSid
0x140003c12  add     rsp, 28h
0x140003c16  retn
```
