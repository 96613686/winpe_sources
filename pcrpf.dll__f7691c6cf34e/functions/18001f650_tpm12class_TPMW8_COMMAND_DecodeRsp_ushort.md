# tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)

- ea: `0x18001f650`
- end: `0x18001f6fb`
- name: `?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z`
- size: `171`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fa88`
- `0x180021050`
- `0x180021a20`
- `0x180021e80`

## callees

- `0x18001f650`
- `0x1800242bc`
- `0x1800242f0`
- `0x1800246cc`
- `0x1800249fc`
- `0x180024f08`

## string_xrefs

- `0x18001f670`: `TPMW8_COMMAND`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::DecodeRsp(tpm12class::TPMW8_COMMAND *this, unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned __int8 v6; // [rsp+28h] [rbp-10h]

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = TraceIdentifier(a2, L"TPMW8_COMMAND");
    if ( v4 >= 0 )
    {
      v4 = TraceUINT16Value(a2, L"tag", *((_WORD *)this + 29), 0, (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ST, v6);
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"responseSize", *((_DWORD *)this + 16), 1u, 0, 0);
        if ( v4 >= 0 )
          return (unsigned int)TraceW8ReturnCode(a2, *((_DWORD *)this + 41));
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f650  mov     [rsp+arg_0], rbx
0x18001f655  mov     [rsp+arg_8], rsi
0x18001f65a  push    rdi
0x18001f65b  sub     rsp, 30h
0x18001f65f  mov     rdi, rdx
0x18001f662  mov     rsi, rcx
0x18001f665  xor     ebx, ebx
0x18001f667  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18001f66c  test    al, al
0x18001f66e  jz      short loc_18001F6E8
0x18001f670  lea     rdx, aTpmw8Command; "TPMW8_COMMAND"
0x18001f677  mov     rcx, rdi; unsigned __int16 *
0x18001f67a  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x18001f67f  mov     ebx, eax
0x18001f681  test    eax, eax
0x18001f683  js      short loc_18001F6E8
0x18001f685  movzx   r8d, word ptr [rsi+3Ah]; unsigned __int16
0x18001f68a  lea     rax, ?st_TPMW8_ST@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ST
0x18001f691  xor     r9d, r9d; unsigned __int8
0x18001f694  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18001f699  lea     rdx, aTag; "tag"
0x18001f6a0  mov     rcx, rdi; unsigned __int16 *
0x18001f6a3  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18001f6a8  mov     ebx, eax
0x18001f6aa  test    eax, eax
0x18001f6ac  js      short loc_18001F6E8
0x18001f6ae  mov     r8d, [rsi+40h]; unsigned int
0x18001f6b2  lea     rdx, aResponsesize; "responseSize"
0x18001f6b9  mov     [rsp+38h+var_10], 0; unsigned __int8
0x18001f6be  mov     r9b, 1; unsigned __int8
0x18001f6c1  mov     rcx, rdi; unsigned __int16 *
0x18001f6c4  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x18001f6cd  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18001f6d2  mov     ebx, eax
0x18001f6d4  test    eax, eax
0x18001f6d6  js      short loc_18001F6E8
0x18001f6d8  mov     edx, [rsi+0A4h]; unsigned int
0x18001f6de  mov     rcx, rdi; unsigned __int16 *
0x18001f6e1  call    ?TraceW8ReturnCode@@YAJPEAGI@Z; TraceW8ReturnCode(ushort *,uint)
0x18001f6e6  mov     ebx, eax
0x18001f6e8  mov     rsi, [rsp+38h+arg_8]
0x18001f6ed  mov     eax, ebx
0x18001f6ef  mov     rbx, [rsp+38h+arg_0]
0x18001f6f4  add     rsp, 30h
0x18001f6f8  pop     rdi
0x18001f6f9  retn
```
