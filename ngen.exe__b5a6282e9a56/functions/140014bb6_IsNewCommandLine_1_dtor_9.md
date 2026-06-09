# _IsNewCommandLine_::_1_::dtor$9

- ea: `0x140014bb6`
- end: `0x140014bc9`
- name: `_IsNewCommandLine_::_1_::dtor$9`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001680`

## pseudocode

```c
void __fastcall IsNewCommandLine_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(a2 + 240);
}

```

## disassembly

```asm
0x140014bb6  lea     rcx, [rdx+40h]
0x140014bbd  add     rcx, 0B0h
0x140014bc4  jmp     ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)
```
