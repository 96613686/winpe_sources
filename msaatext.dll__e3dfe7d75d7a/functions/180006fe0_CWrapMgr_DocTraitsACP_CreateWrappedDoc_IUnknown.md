# CWrapMgr<DocTraitsACP>::CreateWrappedDoc(IUnknown * *)

- ea: `0x180006fe0`
- end: `0x180006fe5`
- name: `?CreateWrappedDoc@?$CWrapMgr@VDocTraitsACP@@@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c250`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CWrapMgr<DocTraitsACP>::CreateWrappedDoc(_QWORD *a1, __int64 **a2)
{
  return CWrapMgr<DocTraitsACP>::_CreateWrappedDoc(a1, a2);
}

```

## disassembly

```asm
0x180006fe0  jmp     ?_CreateWrappedDoc@?$CWrapMgr@VDocTraitsACP@@@@AEAAJPEAPEAUITextStoreACP@@@Z; CWrapMgr<DocTraitsACP>::_CreateWrappedDoc(ITextStoreACP * *)
```
