# _GetCorService_::_1_::dtor$15

- ea: `0x140014a47`
- end: `0x140014a53`
- name: `_GetCorService_::_1_::dtor$15`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140009cdc`

## pseudocode

```c
_QWORD *__fastcall GetCorService_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  return BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&void DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&void DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&int CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x140014a47  lea     rcx, [rdx+60h]
0x140014a4e  jmp     ??1AddressInitHolder@?$BaseWrapper@PEAUICLRMetaHostPolicy@@V?$FunctionBase@PEAUICLRMetaHostPolicy@@$1??$DoNothing@PEAUICLRMetaHostPolicy@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICLRMetaHostPolicy@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICLRMetaHostPolicy@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder(void)
```
