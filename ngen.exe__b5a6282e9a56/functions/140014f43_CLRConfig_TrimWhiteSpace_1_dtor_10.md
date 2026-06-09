# _CLRConfig::TrimWhiteSpace_::_1_::dtor$10

- ea: `0x140014f43`
- end: `0x140014f4f`
- name: `_CLRConfig::TrimWhiteSpace_::_1_::dtor$10`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007338`

## pseudocode

```c
void __fastcall CLRConfig::TrimWhiteSpace_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&public: static void CLRConfig::FreeConfigString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&public: static void CLRConfig::FreeConfigString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(a2 + 32);
}

```

## disassembly

```asm
0x140014f43  lea     rcx, [rdx+20h]
0x140014f4a  jmp     ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?FreeConfigString@CLRConfig@@SAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&CLRConfig::FreeConfigString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&CLRConfig::FreeConfigString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)
```
