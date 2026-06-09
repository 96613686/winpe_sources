# _GetCorSvcInstaller_::_1_::dtor$33

- ea: `0x140014aa9`
- end: `0x140014ab5`
- name: `_GetCorSvcInstaller_::_1_::dtor$33`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009e80`

## pseudocode

```c
__int64 __fastcall GetCorSvcInstaller_::_1_::dtor_33(__int64 a1, __int64 a2)
{
  return Wrapper<ICorSvcManager *,&void DoNothing<ICorSvcManager *>(ICorSvcManager *),&void DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&int CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>::~Wrapper<ICorSvcManager *,&void DoNothing<ICorSvcManager *>(ICorSvcManager *),&void DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&int CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x140014aa9  lea     rcx, [rdx+48h]
0x140014ab0  jmp     ??1?$Wrapper@PEAUICorSvcManager@@$1??$DoNothing@PEAUICorSvcManager@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcManager@@@@YAX0@Z$0A@$1??$CompareDefault@PEAUICorSvcManager@@@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<ICorSvcManager *,&DoNothing<ICorSvcManager *>(ICorSvcManager *),&DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>::~Wrapper<ICorSvcManager *,&DoNothing<ICorSvcManager *>(ICorSvcManager *),&DoTheRelease<ICorSvcManager>(ICorSvcManager *),0,&CompareDefault<ICorSvcManager *>(ICorSvcManager *,ICorSvcManager *),2,1>(void)
```
