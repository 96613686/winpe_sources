# _ExceptionHolderTemplate_Exception_::_ExceptionHolderTemplate_Exception__::_1_::dtor$0

- ea: `0x1400155b9`
- end: `0x1400155c5`
- name: `_ExceptionHolderTemplate_Exception_::_ExceptionHolderTemplate_Exception__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009eb4`

## pseudocode

```c
void __fastcall ExceptionHolderTemplate_Exception_::_ExceptionHolderTemplate_Exception__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>(*(__int64 **)(a2 + 48));
}

```

## disassembly

```asm
0x1400155b9  mov     rcx, [rdx+30h]
0x1400155c0  jmp     ??1?$Wrapper@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVException@@@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>(void)
```
