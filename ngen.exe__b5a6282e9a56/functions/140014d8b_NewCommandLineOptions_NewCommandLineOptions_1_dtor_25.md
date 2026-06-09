# _NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor$25

- ea: `0x140014d8b`
- end: `0x140014d97`
- name: `_NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor$25`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009da0`

## pseudocode

```c
void __fastcall NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor_25(__int64 a1, __int64 a2)
{
  BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(*(_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x140014d8b  mov     rcx, [rdx+38h]
0x140014d92  jmp     ??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ; BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
```
