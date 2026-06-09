# _BaseWrapper_HKEY_____FunctionBase_HKEY_____&DoNothing_HKEY______&RegKeyRelease_2__0_&CompareDefault_HKEY______2_::TypedAddressInitHolder::_TypedAddressInitHolder_::_1_::dtor$0

- ea: `0x140014855`
- end: `0x140014861`
- name: `_BaseWrapper_HKEY_____FunctionBase_HKEY_____&DoNothing_HKEY______&RegKeyRelease_2__0_&CompareDefault_HKEY______2_::TypedAddressInitHolder::_TypedAddressInitHolder_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009cdc`

## pseudocode

```c
_QWORD *__fastcall BaseWrapper_HKEY_____FunctionBase_HKEY______DoNothing_HKEY_______RegKeyRelease_2__0__CompareDefault_HKEY______2_::TypedAddressInitHolder::_TypedAddressInitHolder_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&void DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&void DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&int CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder(*(_QWORD **)(a2 + 8));
}

```

## disassembly

```asm
0x140014855  mov     rcx, [rdx+8]
0x14001485c  jmp     ??1AddressInitHolder@?$BaseWrapper@PEAUICLRMetaHostPolicy@@V?$FunctionBase@PEAUICLRMetaHostPolicy@@$1??$DoNothing@PEAUICLRMetaHostPolicy@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICLRMetaHostPolicy@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICLRMetaHostPolicy@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder(void)
```
