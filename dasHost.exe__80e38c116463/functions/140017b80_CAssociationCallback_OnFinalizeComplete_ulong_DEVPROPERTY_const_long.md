# CAssociationCallback::OnFinalizeComplete(ulong,_DEVPROPERTY * const,long)

- ea: `0x140017b80`
- end: `0x140017baa`
- name: `?OnFinalizeComplete@CAssociationCallback@@UEAAJKQEAU_DEVPROPERTY@@J@Z`
- size: `42`
- prototype: `int __fastcall(CAssociationCallback *this, unsigned int, struct _DEVPROPERTY *const, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140017bf0`

## pseudocode

```c
int __fastcall CAssociationCallback::OnFinalizeComplete(
        CAssociationCallback *this,
        unsigned int a2,
        struct _DEVPROPERTY *const a3,
        int a4)
{
  return CAssociationCallback::OnFinalizePerUserCompleteCommon(this, 0, a2, a3, 0, 0, 0, a4);
}

```

## disassembly

```asm
0x140017b80  sub     rsp, 48h
0x140017b84  mov     [rsp+48h+var_10], r9d; int
0x140017b89  xor     eax, eax
0x140017b8b  mov     [rsp+48h+var_18], eax; unsigned int
0x140017b8f  mov     r9, r8; struct _DEVPROPERTY *
0x140017b92  mov     r8d, edx; unsigned int
0x140017b95  mov     [rsp+48h+var_20], rax; unsigned __int16 **
0x140017b9a  xor     edx, edx; int
0x140017b9c  mov     [rsp+48h+var_28], eax; unsigned int
0x140017ba0  call    ?OnFinalizePerUserCompleteCommon@CAssociationCallback@@IEAAJHKQEAU_DEVPROPERTY@@KPEAPEBGKJ@Z; CAssociationCallback::OnFinalizePerUserCompleteCommon(int,ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long)
0x140017ba5  add     rsp, 48h
0x140017ba9  retn
```
