# CAssociationCallback::OnRemovePerUserComplete(long)

- ea: `0x140017fd0`
- end: `0x140017fdd`
- name: `?OnRemovePerUserComplete@CAssociationCallback@@UEAAJJ@Z`
- size: `13`
- prototype: `__int64 __fastcall(void **this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140017f70`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::OnRemovePerUserComplete(void **this, int a2)
{
  return CAssociationCallback::OnRemoveCompleteCommon(this, 1, a2);
}

```

## disassembly

```asm
0x140017fd0  mov     r8d, edx; int
0x140017fd3  mov     edx, 1; int
0x140017fd8  jmp     ?OnRemoveCompleteCommon@CAssociationCallback@@IEAAJHJ@Z; CAssociationCallback::OnRemoveCompleteCommon(int,long)
```
