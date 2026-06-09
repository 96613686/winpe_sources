# _NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor$2

- ea: `0x140014cf3`
- end: `0x140014d03`
- name: `_NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001680`

## pseudocode

```c
void __fastcall NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(*(_QWORD *)(a2 + 48) + 56LL);
}

```

## disassembly

```asm
0x140014cf3  mov     rcx, [rdx+30h]
0x140014cfa  add     rcx, 38h ; '8'
0x140014cfe  jmp     ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ
```
