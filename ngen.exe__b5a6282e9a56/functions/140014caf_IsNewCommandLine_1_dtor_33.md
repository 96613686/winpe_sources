# _IsNewCommandLine_::_1_::dtor$33

- ea: `0x140014caf`
- end: `0x140014cbb`
- name: `_IsNewCommandLine_::_1_::dtor$33`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009e80`

## pseudocode

```c
__int64 __fastcall IsNewCommandLine_::_1_::dtor_33(__int64 a1, __int64 a2)
{
  return Wrapper<ICorSvcManager *,&void DoNothing<ICorSvcManager *>(ICorSvcManager *),&void DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&int CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>::~Wrapper<ICorSvcManager *,&void DoNothing<ICorSvcManager *>(ICorSvcManager *),&void DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&int CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140014caf  lea     rcx, [rdx+30h]
0x140014cb6  jmp     ??1?$Wrapper@PEAUICorSvcManager@@$1??$DoNothing@PEAUICorSvcManager@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcManager@@@@YAX0@Z$0A@$1??$CompareDefault@PEAUICorSvcManager@@@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<ICorSvcManager *,&DoNothing<ICorSvcManager *>(ICorSvcManager *),&DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>::~Wrapper<ICorSvcManager *,&DoNothing<ICorSvcManager *>(ICorSvcManager *),&DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>(void)
```
