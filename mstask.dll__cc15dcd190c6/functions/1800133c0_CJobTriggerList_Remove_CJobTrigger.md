# CJobTriggerList::Remove(CJobTrigger *)

- ea: `0x1800133c0`
- end: `0x1800133c5`
- name: `?Remove@CJobTriggerList@@UEAAXPEAVCJobTrigger@@@Z`
- size: `5`
- prototype: `void __fastcall(CJobTriggerList *__hidden this, struct CJobTrigger *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180013390`

## pseudocode

```c
// attributes: thunk
void __fastcall CJobTriggerList::Remove(CDLinkList *this, struct CDLink *a2)
{
  CDLinkList::Remove(this, a2);
}

```

## disassembly

```asm
0x1800133c0  jmp     ?Remove@CDLinkList@@UEAAXPEAVCDLink@@@Z; CDLinkList::Remove(CDLink *)
```
