# _CCompRC::LoadLibraryHelper_::_1_::dtor$8

- ea: `0x140015d30`
- end: `0x140015d3c`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009eb4`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x140015d30  lea     rcx, [rdx+68h]
0x140015d37  jmp     ??1?$Wrapper@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVException@@@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>(void)
```
