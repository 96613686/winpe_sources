# _IsNewCommandLine_::_1_::dtor$11

- ea: `0x140014bdc`
- end: `0x140014bef`
- name: `_IsNewCommandLine_::_1_::dtor$11`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001680`

## pseudocode

```c
void __fastcall IsNewCommandLine_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(a2 + 280);
}

```

## disassembly

```asm
0x140014bdc  lea     rcx, [rdx+40h]
0x140014be3  add     rcx, 0D8h
0x140014bea  jmp     ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)
```
