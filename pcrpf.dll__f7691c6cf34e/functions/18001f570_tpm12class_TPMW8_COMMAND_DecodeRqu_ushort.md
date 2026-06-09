# tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)

- ea: `0x18001f570`
- end: `0x18001f63b`
- name: `?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z`
- size: `203`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020f20`
- `0x1800216e0`
- `0x180021df0`

## callees

- `0x18001f570`
- `0x1800242bc`
- `0x1800242f0`
- `0x1800246cc`
- `0x1800249fc`

## string_xrefs

- `0x18001f594`: `TPMW8_COMMAND`
- `0x18001f5d6`: `commandSize`
- `0x18001f60f`: `commandCode`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::DecodeRqu(tpm12class::TPMW8_COMMAND *this, unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned __int8 v6; // [rsp+28h] [rbp-10h]

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = TraceIdentifier(a2, L"TPMW8_COMMAND");
    if ( v4 >= 0 )
    {
      v4 = TraceUINT16Value(a2, L"tag", *((_WORD *)this + 28), 0, (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ST, v6);
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"commandSize", *((_DWORD *)this + 15), 1u, 0, 0);
        if ( v4 >= 0 )
          return (unsigned int)TraceUINT32Value(
                                 a2,
                                 L"commandCode",
                                 *((_DWORD *)this + 40),
                                 0,
                                 (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                                 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f570  mov     [rsp+arg_0], rbx
0x18001f575  mov     [rsp+arg_8], rsi
0x18001f57a  push    rdi
0x18001f57b  sub     rsp, 30h
0x18001f57f  mov     rdi, rdx
0x18001f582  mov     rsi, rcx
0x18001f585  xor     ebx, ebx
0x18001f587  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18001f58c  test    al, al
0x18001f58e  jz      loc_18001F628
0x18001f594  lea     rdx, aTpmw8Command; "TPMW8_COMMAND"
0x18001f59b  mov     rcx, rdi; unsigned __int16 *
0x18001f59e  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x18001f5a3  mov     ebx, eax
0x18001f5a5  test    eax, eax
0x18001f5a7  js      short loc_18001F628
0x18001f5a9  movzx   r8d, word ptr [rsi+38h]; unsigned __int16
0x18001f5ae  lea     rax, ?st_TPMW8_ST@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ST
0x18001f5b5  xor     r9d, r9d; unsigned __int8
0x18001f5b8  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18001f5bd  lea     rdx, aTag; "tag"
0x18001f5c4  mov     rcx, rdi; unsigned __int16 *
0x18001f5c7  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18001f5cc  mov     ebx, eax
0x18001f5ce  test    eax, eax
0x18001f5d0  js      short loc_18001F628
0x18001f5d2  mov     r8d, [rsi+3Ch]; unsigned int
0x18001f5d6  lea     rdx, aCommandsize; "commandSize"
0x18001f5dd  mov     [rsp+38h+var_10], 0; unsigned __int8
0x18001f5e2  mov     r9b, 1; unsigned __int8
0x18001f5e5  mov     rcx, rdi; unsigned __int16 *
0x18001f5e8  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x18001f5f1  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18001f5f6  mov     ebx, eax
0x18001f5f8  test    eax, eax
0x18001f5fa  js      short loc_18001F628
0x18001f5fc  mov     r8d, [rsi+0A0h]; unsigned int
0x18001f603  lea     rax, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x18001f60a  mov     [rsp+38h+var_10], 0; unsigned __int8
0x18001f60f  lea     rdx, aCommandcode; "commandCode"
0x18001f616  xor     r9d, r9d; unsigned __int8
0x18001f619  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18001f61e  mov     rcx, rdi; unsigned __int16 *
0x18001f621  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18001f626  mov     ebx, eax
0x18001f628  mov     rsi, [rsp+38h+arg_8]
0x18001f62d  mov     eax, ebx
0x18001f62f  mov     rbx, [rsp+38h+arg_0]
0x18001f634  add     rsp, 30h
0x18001f638  pop     rdi
0x18001f639  retn
```
