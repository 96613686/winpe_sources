# _CCompRC::LoadLibraryHelper_::_1_::dtor$9

- ea: `0x140015d3c`
- end: `0x140015d48`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009f40`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  BaseWrapper<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseWrapper<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x140015d3c  lea     rcx, [rdx+68h]
0x140015d43  jmp     ??1?$BaseWrapper@PEAVException@@V?$FunctionBase@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVException@@@@YAHPEAV1@0@Z$01@@QEAA@XZ; BaseWrapper<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseWrapper<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>(void)
```
