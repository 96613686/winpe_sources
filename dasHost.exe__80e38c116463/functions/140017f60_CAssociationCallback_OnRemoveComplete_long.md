# CAssociationCallback::OnRemoveComplete(long)

- ea: `0x140017f60`
- end: `0x140017f6a`
- name: `?OnRemoveComplete@CAssociationCallback@@UEAAJJ@Z`
- size: `10`
- prototype: `int __fastcall(CAssociationCallback *this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140017f70`

## pseudocode

```c
int __fastcall CAssociationCallback::OnRemoveComplete(CAssociationCallback *this, int a2)
{
  return CAssociationCallback::OnRemoveCompleteCommon(this, 0, a2);
}

```

## disassembly

```asm
0x140017f60  mov     r8d, edx; int
0x140017f63  xor     edx, edx; int
0x140017f65  jmp     ?OnRemoveCompleteCommon@CAssociationCallback@@IEAAJHJ@Z; CAssociationCallback::OnRemoveCompleteCommon(int,long)
```
