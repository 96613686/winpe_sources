# _CCompRC::GetLibrary_::_1_::dtor$10

- ea: `0x140015cdc`
- end: `0x140015ce8`
- name: `_CCompRC::GetLibrary_::_1_::dtor$10`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012df4`

## pseudocode

```c
void __fastcall CCompRC::GetLibrary_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  BaseHolder<void *,FunctionBase<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>(a2 + 40);
}

```

## disassembly

```asm
0x140015cdc  lea     rcx, [rdx+28h]
0x140015ce3  jmp     ??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1?ClrEnterCriticalSection@@YAXPEAX@Z$1?ClrLeaveCriticalSection@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ; BaseHolder<void *,FunctionBase<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),2>,0,&CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),2>,0,&CompareDefault<void *>(void *,void *),2>(void)
```
