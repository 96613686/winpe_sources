# _GetCorSvcInstaller_::_1_::dtor$29

- ea: `0x140014af6`
- end: `0x140014b02`
- name: `_GetCorSvcInstaller_::_1_::dtor$29`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140009cdc`

## pseudocode

```c
_QWORD *__fastcall GetCorSvcInstaller_::_1_::dtor_29(__int64 a1, __int64 a2)
{
  return BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&void DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&void DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&int CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder((_QWORD *)(a2 + 144));
}

```

## disassembly

```asm
0x140014af6  lea     rcx, [rdx+90h]
0x140014afd  jmp     ??1AddressInitHolder@?$BaseWrapper@PEAUICLRMetaHostPolicy@@V?$FunctionBase@PEAUICLRMetaHostPolicy@@$1??$DoNothing@PEAUICLRMetaHostPolicy@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICLRMetaHostPolicy@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICLRMetaHostPolicy@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder(void)
```
