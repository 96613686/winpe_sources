# _IsNewCommandLine_::_1_::dtor$28

- ea: `0x140013fb6`
- end: `0x140013fc2`
- name: `_IsNewCommandLine_::_1_::dtor$28`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400016a8`

## pseudocode

```c
void __fastcall IsNewCommandLine_::_1_::dtor_28(__int64 a1, __int64 a2)
{
  BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x140013fb6  mov     rcx, [rdx+30h]
0x140013fbd  jmp     ??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ; BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
```
