# _CCompRC::GetLibrary_::_1_::dtor$2

- ea: `0x140015cd0`
- end: `0x140015cdc`
- name: `_CCompRC::GetLibrary_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001278c`

## pseudocode

```c
void __fastcall CCompRC::GetLibrary_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Holder<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),0,&int CompareDefault<void *>(void *,void *),2,1>::~Holder<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),0,&int CompareDefault<void *>(void *,void *),2,1>(a2 + 40);
}

```

## disassembly

```asm
0x140015cd0  lea     rcx, [rdx+28h]
0x140015cd7  jmp     ??1?$Holder@PEAX$1?ClrEnterCriticalSection@@YAXPEAX@Z$1?ClrLeaveCriticalSection@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01$00@@QEAA@XZ; Holder<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),0,&CompareDefault<void *>(void *,void *),2,1>::~Holder<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),0,&CompareDefault<void *>(void *,void *),2,1>(void)
```
