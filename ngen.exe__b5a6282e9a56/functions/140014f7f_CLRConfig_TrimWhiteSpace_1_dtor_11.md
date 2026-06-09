# _CLRConfig::TrimWhiteSpace_::_1_::dtor$11

- ea: `0x140014f7f`
- end: `0x140014f8b`
- name: `_CLRConfig::TrimWhiteSpace_::_1_::dtor$11`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007360`

## pseudocode

```c
void __fastcall CLRConfig::TrimWhiteSpace_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(a2 + 32);
}

```

## disassembly

```asm
0x140014f7f  lea     rcx, [rdx+20h]
0x140014f86  jmp     ??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ; BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
```
