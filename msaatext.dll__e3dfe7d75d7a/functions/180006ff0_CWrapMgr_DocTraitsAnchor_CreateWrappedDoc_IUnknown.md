# CWrapMgr<DocTraitsAnchor>::CreateWrappedDoc(IUnknown * *)

- ea: `0x180006ff0`
- end: `0x180006ff5`
- name: `?CreateWrappedDoc@?$CWrapMgr@VDocTraitsAnchor@@@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c4a0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CWrapMgr<DocTraitsAnchor>::CreateWrappedDoc(_QWORD *a1, __int64 **a2)
{
  return CWrapMgr<DocTraitsAnchor>::_CreateWrappedDoc(a1, a2);
}

```

## disassembly

```asm
0x180006ff0  jmp     ?_CreateWrappedDoc@?$CWrapMgr@VDocTraitsAnchor@@@@AEAAJPEAPEAUITextStoreAnchor@@@Z; CWrapMgr<DocTraitsAnchor>::_CreateWrappedDoc(ITextStoreAnchor * *)
```
