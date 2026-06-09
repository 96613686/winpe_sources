# ATL::CComPtr<ITaskService>::~CComPtr<ITaskService>(void)

- ea: `0x180003128`
- end: `0x18000312d`
- name: `??1?$CComPtr@UITaskService@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037b4b`
- `0x180037b6f`
- `0x180037b93`
- `0x180037ba5`
- `0x180037bb7`
- `0x180037bc9`
- `0x180037bed`
- `0x180037c49`
- `0x180037c5b`
- `0x180037c7f`
- `0x18003873b`
- `0x1800389a4`

## callees

- `0x180003134`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<ITaskService>::~CComPtr<ITaskService>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x180003128  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
