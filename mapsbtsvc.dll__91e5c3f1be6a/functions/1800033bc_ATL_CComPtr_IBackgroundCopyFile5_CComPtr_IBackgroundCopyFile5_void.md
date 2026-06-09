# ATL::CComPtr<IBackgroundCopyFile5>::~CComPtr<IBackgroundCopyFile5>(void)

- ea: `0x1800033bc`
- end: `0x1800033c1`
- name: `??1?$CComPtr@UIBackgroundCopyFile5@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013bd8`
- `0x180013c4c`
- `0x180013c5e`
- `0x180013ca6`
- `0x180013cb8`
- `0x1800142c7`
- `0x18001437c`
- `0x180014479`
- `0x1800144af`
- `0x1800144d3`
- `0x180014575`
- `0x180014608`
- `0x18001477f`
- `0x1800147b5`
- `0x1800147d9`
- `0x1800147fd`

## callees

- `0x1800033d4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IBackgroundCopyFile5>::~CComPtr<IBackgroundCopyFile5>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x1800033bc  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
