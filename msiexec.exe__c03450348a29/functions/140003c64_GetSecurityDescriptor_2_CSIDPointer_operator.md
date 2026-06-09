# _GetSecurityDescriptor_::_2_::CSIDPointer::operator&

- ea: `0x140003c64`
- end: `0x140003c84`
- name: `_GetSecurityDescriptor_::_2_::CSIDPointer::operator&`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000580c`

## callees

- `0x140003c64`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x140003c75`
- `ADVAPI32!FreeSid` at `0x140003c75`

## pseudocode

```c
void **__fastcall GetSecurityDescriptor_::_2_::CSIDPointer::operator&(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    FreeSid(v2);
  return a1;
}

```

## disassembly

```asm
0x140003c64  push    rbx
0x140003c66  sub     rsp, 20h
0x140003c6a  mov     rbx, rcx
0x140003c6d  mov     rcx, [rcx]; pSid
0x140003c70  test    rcx, rcx
0x140003c73  jz      short loc_140003C7B
0x140003c75  call    cs:__imp_FreeSid
0x140003c7b  mov     rax, rbx
0x140003c7e  add     rsp, 20h
0x140003c82  pop     rbx
0x140003c83  retn
```
