# CAssociationCallback::OnFinalizePerUserComplete(ulong,_DEVPROPERTY * const,long)

- ea: `0x140017bb0`
- end: `0x140017bea`
- name: `?OnFinalizePerUserComplete@CAssociationCallback@@UEAAJKQEAU_DEVPROPERTY@@J@Z`
- size: `58`
- prototype: `int __fastcall(CAssociationCallback *this, unsigned int, struct _DEVPROPERTY *const, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140017bb0`
- `0x140017bf0`

## pseudocode

```c
int __fastcall CAssociationCallback::OnFinalizePerUserComplete(
        CAssociationCallback *this,
        unsigned int a2,
        struct _DEVPROPERTY *const a3,
        int a4)
{
  if ( *((_QWORD *)this + 6) )
    return CAssociationCallback::OnFinalizePerUserCompleteCommon(this, 1, a2, a3, 0, 0, 0, a4);
  else
    return -2140930011;
}

```

## disassembly

```asm
0x140017bb0  sub     rsp, 48h
0x140017bb4  xor     eax, eax
0x140017bb6  cmp     [rcx+30h], rax
0x140017bba  jnz     short loc_140017BC3
0x140017bbc  mov     eax, 80640025h
0x140017bc1  jmp     short loc_140017BE5
0x140017bc3  mov     [rsp+48h+var_10], r9d; int
0x140017bc8  mov     r9, r8; struct _DEVPROPERTY *
0x140017bcb  mov     [rsp+48h+var_18], eax; unsigned int
0x140017bcf  mov     r8d, edx; unsigned int
0x140017bd2  mov     [rsp+48h+var_20], rax; unsigned __int16 **
0x140017bd7  mov     edx, 1; int
0x140017bdc  mov     [rsp+48h+var_28], eax; unsigned int
0x140017be0  call    ?OnFinalizePerUserCompleteCommon@CAssociationCallback@@IEAAJHKQEAU_DEVPROPERTY@@KPEAPEBGKJ@Z; CAssociationCallback::OnFinalizePerUserCompleteCommon(int,ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long)
0x140017be5  add     rsp, 48h
0x140017be9  retn
```
