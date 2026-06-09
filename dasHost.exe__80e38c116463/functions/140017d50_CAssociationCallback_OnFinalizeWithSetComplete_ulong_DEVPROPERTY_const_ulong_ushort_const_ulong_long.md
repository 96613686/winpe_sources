# CAssociationCallback::OnFinalizeWithSetComplete(ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long)

- ea: `0x140017d50`
- end: `0x140017d88`
- name: `?OnFinalizeWithSetComplete@CAssociationCallback@@UEAAJKQEAU_DEVPROPERTY@@KPEAPEBGKJ@Z`
- size: `56`
- prototype: `__int64 __fastcall(CAssociationCallback *this, unsigned int, struct _DEVPROPERTY *const, unsigned int, unsigned __int16 **, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140017bf0`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::OnFinalizeWithSetComplete(
        CAssociationCallback *this,
        unsigned int a2,
        struct _DEVPROPERTY *const a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned int a6,
        unsigned int a7)
{
  return CAssociationCallback::OnFinalizePerUserCompleteCommon(this, 0, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x140017d50  sub     rsp, 48h
0x140017d54  mov     eax, [rsp+48h+arg_30]
0x140017d5b  mov     [rsp+48h+var_10], eax; int
0x140017d5f  mov     eax, [rsp+48h+arg_28]
0x140017d63  mov     [rsp+48h+var_18], eax; unsigned int
0x140017d67  mov     rax, [rsp+48h+arg_20]
0x140017d6c  mov     [rsp+48h+var_20], rax; unsigned __int16 **
0x140017d71  mov     [rsp+48h+var_28], r9d; unsigned int
0x140017d76  mov     r9, r8; struct _DEVPROPERTY *
0x140017d79  mov     r8d, edx; unsigned int
0x140017d7c  xor     edx, edx; int
0x140017d7e  call    ?OnFinalizePerUserCompleteCommon@CAssociationCallback@@IEAAJHKQEAU_DEVPROPERTY@@KPEAPEBGKJ@Z; CAssociationCallback::OnFinalizePerUserCompleteCommon(int,ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long)
0x140017d83  add     rsp, 48h
0x140017d87  retn
```
