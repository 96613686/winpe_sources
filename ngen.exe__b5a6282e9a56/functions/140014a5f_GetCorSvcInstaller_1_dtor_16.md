# _GetCorSvcInstaller_::_1_::dtor$16

- ea: `0x140014a5f`
- end: `0x140014a6b`
- name: `_GetCorSvcInstaller_::_1_::dtor$16`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009f0c`

## pseudocode

```c
__int64 __fastcall GetCorSvcInstaller_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  return BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&void DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&void DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&int CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>::~BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&void DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&void DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&int CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x140014a5f  lea     rcx, [rdx+38h]
0x140014a66  jmp     ??1?$BaseWrapper@PEAUICorSvcOptimizer@@V?$FunctionBase@PEAUICorSvcOptimizer@@$1??$DoNothing@PEAUICorSvcOptimizer@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcOptimizer@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcOptimizer@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>::~BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>(void)
```
