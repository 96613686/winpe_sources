# _CDimsJobTaskHandler::Start_::_1_::dtor$2

- ea: `0x18000af70`
- end: `0x18000af7c`
- name: `_CDimsJobTaskHandler::Start_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003260`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Start_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>::~CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x18000af70  lea     rcx, [rdx+30h]
0x18000af77  jmp     ??1?$CAutoResource@PEAUITaskHandlerStatus@@U?$_CComObjectReleaser@UITaskHandlerStatus@@@@$0A@@@QEAA@XZ; CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>::~CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>(void)
```
