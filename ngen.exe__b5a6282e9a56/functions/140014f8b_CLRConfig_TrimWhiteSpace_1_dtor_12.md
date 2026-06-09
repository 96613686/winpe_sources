# _CLRConfig::TrimWhiteSpace_::_1_::dtor$12

- ea: `0x140014f8b`
- end: `0x140014f97`
- name: `_CLRConfig::TrimWhiteSpace_::_1_::dtor$12`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009d24`

## pseudocode

```c
void __fastcall CLRConfig::TrimWhiteSpace_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(a2 + 32);
}

```

## disassembly

```asm
0x140014f8b  lea     rcx, [rdx+20h]
0x140014f92  jmp     ??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ; BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
```
