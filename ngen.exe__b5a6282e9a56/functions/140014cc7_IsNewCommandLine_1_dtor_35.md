# _IsNewCommandLine_::_1_::dtor$35

- ea: `0x140014cc7`
- end: `0x140014cd3`
- name: `_IsNewCommandLine_::_1_::dtor$35`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140009f98`

## pseudocode

```c
__int64 __fastcall IsNewCommandLine_::_1_::dtor_35(__int64 a1, __int64 a2)
{
  return BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&void DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&void DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&int CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>::~BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&void DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&void DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&int CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140014cc7  lea     rcx, [rdx+30h]
0x140014cce  jmp     ??1?$BaseHolder@PEAUICorSvcSetLegacyServiceBehavior@@V?$FunctionBase@PEAUICorSvcSetLegacyServiceBehavior@@$1??$DoNothing@PEAUICorSvcSetLegacyServiceBehavior@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcSetLegacyServiceBehavior@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcSetLegacyServiceBehavior@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>::~BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>(void)
```
