# ATL::CComPtr<IFhFileRecordEnum>::~CComPtr<IFhFileRecordEnum>(void)

- ea: `0x180007a90`
- end: `0x180007a95`
- name: `??1?$CComPtr@UIFhFileRecordEnum@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180031e8f`
- `0x180031f43`
- `0x18003254c`
- `0x1800326e3`
- `0x1800326f5`
- `0x180032707`
- `0x1800332c0`

## callees

- `0x1800031b0`

## pseudocode

```c
// attributes: thunk
void __fastcall ATL::CComPtr<IFhFileRecordEnum>::~CComPtr<IFhFileRecordEnum>(void *a1)
{
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(a1);
}

```

## disassembly

```asm
0x180007a90  jmp     ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
```
